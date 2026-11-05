# LLM-as-a-Judge: Calibrating Virtual Judges

How to use a language model to grade AI-generated content against your content standards, and how to prove the grades can be trusted. This is where content design and AI evaluation meet: a judge is only as good as the rubric it applies, and writing rubrics is content design work.

## When you need a judge

| Situation | Method |
|---|---|
| Checking length, banned words, format, required fields | **Code**: deterministic checks are free, exact, and never miscount |
| Judging accuracy, tone, relevance, completeness | **An LLM judge**, calibrated against people |
| Deciding what "good" means, resolving disputes, high-stakes cases | **People** |

The three layers work together. Airbnb's engineering team describes the same structure, programmatic checks, then LLM judges, then human evaluation, in its post [Eval-driven development](https://airbnb.tech/ai-ml/eval-driven-development-lessons-from-evaluating-genai-at-scale/).

## Step 1: Turn content principles into rules

Judges can't apply taste. They can apply rules. Start from your [voice and tone framework](../../style-guides/voice-and-tone-framework.md) and turn each principle into something a person, a script, or a model could apply the same way twice.

| Principle | Too vague to judge | Judgeable rule | Layer |
|---|---|---|---|
| Be concise | "Is it concise?" | "Under 200 characters and at most 2 sentences" | Code |
| Don't oversell | "Does it sound salesy?" | "No phrase pushes emotion without adding information, like 'breathtaking' or 'you'll fall in love'" | Judge |
| Be accurate | "Is it accurate?" | "Every factual claim is supported by the source data" | Judge, claim by claim |
| Distance is a promise | "Is the location right?" | "'Steps from' means 2 minutes' walk or less; 'a short walk' means 10 or less" | Judge |

Each rule should live in exactly one place. If clichés are penalized under both "tone" and "constraints," one defect costs two points and you can't tell what moved.

## Step 2: One judge per dimension

A single judge scoring four dimensions on 1–5 scales is the most common first attempt, and the least reliable. Split it.

| Instead of | Use |
|---|---|
| One judge, many dimensions | One judge per dimension |
| 1–5 scales with adjective anchors ("good," "excellent") | Pass/fail with typed errors |
| A holistic accuracy score | Claim-by-claim verdicts, failed in code if any claim is unsupported |
| No examples | 3–5 worked examples, including failures, from outside your test set |
| Free-text output | Strict JSON with a reason field |

```
Score the voice of this listing highlight. Return pass (1) or fail (0).

Fail if it has ANY of these:
- salesy: phrases that push emotion without information ("breathtaking," "dream home")
- jargon: words a guest wouldn't use ("domicile," "aquatic amenity")
- fragment: no complete sentence
- hedging: "may possibly offer"

Honest negatives are GOOD writing. "It's a third-floor walk-up" passes.

Return only: {"errors": [["<type>", "<words>"]], "score": 0 or 1}
```

## Step 3: Build a labeled golden set

1. **Collect 50–100 examples,** including plenty of bad ones. You can't test whether a judge catches failures without failures to catch.
2. **Have people label them blind,** without seeing the judge's scores or the author's intent.
3. **Measure agreement between people first.** Use Cohen's kappa for two raters or Krippendorff's alpha for more. If people disagree on a dimension, fix the rule before automating it. Human agreement is the ceiling no judge can beat.
4. **Keep few-shot examples out of the golden set,** or agreement will look better than it is.

## Step 4: Calibrate the judge

Run the judge on the golden set and compare it with the human labels.

| Metric | What it tells you |
|---|---|
| **Agreement %** | How often the judge matches people. Easy to read, but inflated when most items pass. |
| **Cohen's kappa** | Agreement corrected for chance. Above about 0.6 is substantial; above 0.8 is strong. |
| **Fail recall** | Of the items people failed, how many the judge also failed. Usually the most important number, because missed failures reach users. |
| **Fail precision** | Of the items the judge failed, how many people also failed. Low precision means false alarms. |

Then **read every disagreement.** Each one is either a judge mistake (fix the prompt or examples), a human mistake (fix the label), or an unclear rule (fix the rule). Change one thing, rerun, and record the before and after.

## Step 5: Stress-test with planted defects

Take outputs people labeled as good, inject one known defect, and check whether the judge catches it. This gives you ground truth by construction.

| Defect | Example | Should fail |
|---|---|---|
| Distance compression | "an 8-minute walk" → "steps from" | Accuracy |
| Unlisted feature | Add "a hot tub" that isn't in the data | Accuracy |
| Shared made private | "a shared pool" → "a private pool" | Accuracy |
| Commodity lead | Replace the highlight with a Wi-Fi-and-kitchen checklist | Relevance |
| Novel puffery | Prefix "Prepare to fall in love with…" | Voice |

Also run **unchanged controls** to measure false alarms.

## Step 6: Check for judge bias

- **Length bias:** among items people failed, does the judge pass longer ones more often?
- **Position bias (pairwise judging):** run each comparison in both orders; count it only if the verdict survives the swap.
- **Self-preference:** use a different model family for the judge than for the generator.
- **Consistency:** run the same items several times and check that verdicts don't flip.

## Step 7: Monitor in production

- Sample live outputs regularly, run code checks and judges, and send flagged items to human review.
- Recalibrate whenever the generator's model or prompt changes.
- Turn every new failure pattern into a new rule, example, or planted defect.
- Gate releases on fail recall for accuracy, not on average scores.

## Worked example

[Airbnb LLM-as-a-Judge Listing Evals](https://github.com/jkelleman/airbnb-llm-as-a-judge-listing-evals) applies every step on this page to AI-written listing highlights: content principles mapped to enforcement layers, three single-purpose judges, a blind labeling tool, 207 planted defects, and agreement metrics. It's an independent portfolio project, not affiliated with Airbnb.

## How leading companies do it

| Company | What they teach |
|---|---|
| **Microsoft** | Publish evaluations alongside AI products: the Microsoft 365 Copilot transparency note describes both performance and quality tests and risk and safety tests. ([Copilot transparency note](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-transparency-note)) |
| **Google** | Some AI errors are "background errors" that neither users nor the system notice, so they need deliberate stress testing rather than user feedback. ([PAIR: Errors + Graceful Failure](https://pair.withgoogle.com/chapter/People%20+%20AI%20Guidebook%20-%20Errors%20+%20Graceful%20Failure.pdf)) |
| **Amazon** | Document expected performance and fairness testing, with sample results on a representative dataset. ([AI Service Cards](https://aws.amazon.com/blogs/machine-learning/introducing-aws-ai-service-cards-a-new-resource-to-enhance-transparency-and-advance-responsible-ai)) |
| **Salesforce** | Scan generated content for toxicity and bias before people see it, as a standing check rather than a one-time test. ([Trusted AI](https://salesforce.com/uk/artificial-intelligence/trusted-ai/)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related resources

- [AI Content Evaluation](ai-content-evaluation.md)
- [Content Testing](content-testing.md)
- [Content Metrics](content-metrics.md)
- [Prompt Design](../../templates/ai-content/prompt-design.md)
- [Voice and Tone Framework](../../style-guides/voice-and-tone-framework.md)
