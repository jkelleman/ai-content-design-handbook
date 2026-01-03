# Evaluating AI-Generated Content

A framework for assessing quality, accuracy, and appropriateness of AI-generated content before it reaches users.

## Why Evaluate AI Content?

AI models can generate fluent, confident-sounding content that is:
- **Inaccurate** - Factually wrong or outdated
- **Inappropriate** - Wrong tone, offensive, or harmful
- **Inconsistent** - Contradicts other content
- **Unhelpful** - Doesn't address user needs
- **Unsafe** - Could cause harm

**Human oversight is essential.**

## Evaluation Framework

### 1. Accuracy & Correctness

**Does the content match reality?**

**Check for:**
- [ ] Factual accuracy
- [ ] Technical correctness
- [ ] Current information (not outdated)
- [ ] No hallucinations (made-up facts)
- [ ] Verifiable claims

**Example evaluation:**

```markdown
AI Output:
"Fabric supports up to 500 concurrent pipeline runs per workspace."

Evaluation:
❌ Incorrect - Limit is 100, not 500
Status: Reject - Update training data or prompt
```

**Red flags:**
- Specific numbers without source
- Confident claims about uncertain topics
- Recently changed features
- Version-specific details

### 2. Relevance & Usefulness

**Does it help users accomplish their goal?**

**Check for:**
- [ ] Addresses user's actual question
- [ ] Appropriate level of detail
- [ ] Actionable information
- [ ] Answers "what," "why," and "how"
- [ ] Includes next steps

**Example evaluation:**

```markdown
User Query:
"How do I fix connection timeout error?"

AI Output:
"Connection timeouts can occur for various reasons. Networks are complex 
systems with many components. TCP/IP protocol defines timeout behavior..."

Evaluation:
❌ Not useful - Too theoretical, no actionable steps
Status: Reject - Add task-oriented examples to training
```

**Good AI response:**
```markdown
"To fix connection timeout:
1. Check your internet connection
2. Verify the endpoint URL is correct
3. Increase timeout setting in Settings > Connections
4. If issue persists, contact support"

✅ Actionable, specific, complete
```

### 3. Tone & Voice

**Does it match your content standards?**

**Check for:**
- [ ] Appropriate formality level
- [ ] Consistent with brand voice
- [ ] Suitable for context
- [ ] No inappropriate humor
- [ ] Respectful and professional

**Example evaluation:**

```markdown
Context: Error message for failed deployment

AI Output:
"Oops! Looks like your deployment went boom! 💥 Try again?"

Evaluation:
❌ Too casual for error context
Status: Adjust - Errors require clear, professional tone
```

**Corrected:**
```markdown
"Deployment failed. Check error details below and try again."
✅ Clear, professional, appropriate
```

### 4. Safety & Appropriateness

**Could this content cause harm?**

**Check for:**
- [ ] No harmful instructions
- [ ] No offensive content
- [ ] No biased language
- [ ] Privacy-respecting
- [ ] Legally compliant

**Example evaluation:**

```markdown
AI Output:
"To bypass security settings, modify the registry key at..."

Evaluation:
❌ Unsafe - Recommends disabling security
Status: Reject - Add safety guidelines to system prompt
```

### 5. Consistency

**Does it align with other content?**

**Check for:**
- [ ] Matches terminology standards
- [ ] Consistent with documentation
- [ ] Same UI strings as product
- [ ] No contradictions with other content
- [ ] Follows content patterns

**Example evaluation:**

```markdown
AI Generated:
"Click the 'Execute' button to run your query"

Actual UI Label: "Run Query"

Evaluation:
❌ Inconsistent terminology
Status: Update - Use "Run Query" everywhere
```

## Evaluation Rubric

### Scoring Framework

Rate each dimension 1-5:

**5 - Excellent**
- Accurate, helpful, well-written
- Needs no edits
- Ready to publish

**4 - Good**
- Mostly correct
- Minor tweaks needed
- Usable with light editing

**3 - Acceptable**
- Correct but not optimal
- Needs moderate editing
- Acceptable fallback

**2 - Poor**
- Significant issues
- Major editing required
- Not ready for users

**1 - Unacceptable**
- Incorrect or harmful
- Must be rejected
- Not safe to show users

### Sample Scorecard

```markdown
Content ID: ai-response-2847
Query: "How do I create a pipeline?"

Evaluation Scores:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Accuracy:       4/5  Minor version detail wrong
Relevance:      5/5  Directly answers question
Tone:           4/5  Slightly too technical
Safety:         5/5  No concerns
Consistency:    3/5  Uses "workflow" vs "pipeline"
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Overall:        4.2/5

Decision: APPROVE with edits
Actions:
- Fix version reference (v2.1 → v2.3)
- Change "workflow" to "pipeline" (2 instances)
- Ready after edits
```

## Content Type-Specific Evaluation

### Evaluating Error Messages

**Critical because:**
- Users are already frustrated
- Wrong info increases support burden
- Can block critical workflows

**Evaluation criteria:**

```markdown
Error: "Operation failed due to insufficient permissions"

Check:
✅ Is error accurate? (Yes - permissions actually missing)
✅ Is it actionable? (Yes - implies need to request access)
✅ Is tone appropriate? (Yes - clear, professional)
✅ Does it align with other errors? (Yes - standard format)
✅ Could it be clearer? (Add: "Contact admin to request access")

Score: 4/5 - Approve with suggested addition
```

### Evaluating Help Content

**Critical because:**
- Inaccurate help is worse than no help
- Users follow instructions
- Reflects on product quality

**Evaluation criteria:**

```markdown
AI Generated Article: "How to Schedule a Pipeline"

Check:
✅ Steps technically correct? (Verify in product)
✅ Screenshots match current UI? (Check version)
✅ All steps included? (Test walkthrough)
✅ Prerequisites mentioned? (Permissions, setup)
✅ Common issues addressed? (Error scenarios)
✅ Links work? (Test all links)

Score: 5/5 - Approve for publication
```

### Evaluating Conversational Responses

**Critical because:**
- Real-time user interaction
- No pre-review possible
- Represents company

**Evaluation criteria:**

```markdown
User: "I'm stuck and frustrated"
Bot: "I understand. Let me help you get unstuck. What are you working on?"

Check:
✅ Empathetic? (Yes - acknowledges emotion)
✅ Helpful? (Yes - offers assistance)
✅ Professional? (Yes - appropriate tone)
✅ Safe? (Yes - no harmful suggestions)
✅ Leads to resolution? (Yes - next step clear)

Score: 5/5 - Good response pattern
```

## Testing Methods

### 1. Automated Testing

**What to automate:**

**Fact-checking:**
```python
def verify_facts(ai_output):
    """Check claims against knowledge base"""
    claims = extract_claims(ai_output)
    
    for claim in claims:
        if not verify_against_kb(claim):
            flag_for_review(claim, "Unverified fact")
```

**Consistency checking:**
```python
def check_terminology(ai_output):
    """Ensure consistent term usage"""
    banned_terms = ["click", "simply", "just", "easy"]
    required_terms = {"pipeline": "pipeline", "workspace": "workspace"}
    
    for term, replacement in required_terms.items():
        if term not in ai_output and any(alt in ai_output for alt in get_synonyms(term)):
            flag_inconsistency(term, replacement)
```

**Safety screening:**
```python
def safety_check(ai_output):
    """Screen for unsafe content"""
    if contains_harmful_instructions(ai_output):
        return "REJECT - Safety concern"
    if contains_pii(ai_output):
        return "REJECT - Privacy concern"
    if contains_bias_language(ai_output):
        return "REVIEW - Potential bias"
    return "PASS"
```

### 2. Human Evaluation

**What requires human review:**
- Tone and voice
- Subjective quality
- Context-specific appropriateness
- Edge cases
- Complex scenarios

**Evaluation protocol:**

```markdown
Reviewer: [Name]
Date: [Date]
Sample: Random 100 AI responses from past 24hrs

Instructions:
1. Read user query for context
2. Evaluate AI response using rubric
3. Rate 1-5 on each dimension
4. Flag any critical issues
5. Note patterns (good and bad)

Time estimate: 2-3 hours
Frequency: Weekly
```

### 3. User Feedback

**What users tell you:**

**Explicit feedback:**
- "Was this helpful?" ratings
- "Report a problem" submissions
- Support tickets about AI content

**Implicit feedback:**
- Follow-up questions
- Task completion rates
- Time to resolution
- Support escalations

**Feedback loop:**
```
User feedback
    ↓
Identify patterns
    ↓
Update evaluation criteria
    ↓
Retrain or adjust prompts
    ↓
Monitor improvements
```

## Quality Metrics

### Track These Metrics

**Accuracy rate:**
```
Accurate responses ÷ Total responses × 100

Target: >95% accuracy
Alert if: <90%
```

**Helpfulness rating:**
```
Positive ratings ÷ Total ratings × 100

Target: >80% positive
Alert if: <70%
```

**Edit rate:**
```
Responses edited before sending ÷ Total responses × 100

Target: <20% need editing
Alert if: >40%
```

**Rejection rate:**
```
Responses rejected ÷ Total generated × 100

Target: <5% rejected
Alert if: >10%
```

**Safety incidents:**
```
Harmful responses shown to users

Target: 0
Alert immediately if: Any
```

### Quality Dashboard

```markdown
=== AI Content Quality Dashboard ===

Last 7 Days:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Responses Generated:  12,450
Accuracy Rate:        96.2% ✓
Helpfulness:          82.3% ✓
Edit Rate:            15.1% ✓
Rejection Rate:       3.2% ✓
Safety Incidents:     0 ✓

Trends:
📈 Accuracy: +2.1% vs last week
📈 Helpfulness: +1.8% vs last week
📉 Edit rate: -3.2% vs last week (good)

Attention Needed:
⚠️ Technical questions: 78% helpful (below target)
⚠️ Error troubleshooting: 12% edit rate (watch)

Top Issues Flagged:
1. Outdated version info (8 instances)
2. Inconsistent terminology (6 instances)
3. Missing prerequisites (4 instances)
```

## Evaluation Workflow

### Before Launch (Model Testing)

```markdown
Phase 1: Controlled Testing

1. Create test dataset
   - 100 representative queries
   - Cover common scenarios
   - Include edge cases

2. Generate responses
   - Run all queries through model
   - Document all outputs
   - Note any errors/warnings

3. Human evaluation
   - 2 reviewers evaluate independently
   - Use scoring rubric
   - Calculate inter-rater reliability

4. Analysis
   - Average scores by dimension
   - Identify problem patterns
   - Document failure modes

5. Go/No-Go decision
   - All critical metrics >4.0/5?
   - No safety concerns?
   - Acceptable vs human baseline?
```

### After Launch (Ongoing Monitoring)

```markdown
Daily:
- Monitor safety incidents
- Review flagged responses
- Check key metrics

Weekly:
- Human eval of random sample (n=100)
- Review user feedback trends
- Update evaluation criteria

Monthly:
- Full quality assessment
- Compare to baseline
- Adjust model or prompts
- Document improvements
```

## Red Flags & Escalation

### Immediate Escalation

**Stop and escalate if:**

**Safety issues:**
- Harmful instructions
- Offensive content
- Privacy violations
- Legal compliance issues

**Critical errors:**
- Factually wrong (could cause harm)
- Security vulnerabilities exposed
- Data breaches mentioned

**Pattern issues:**
- >5% responses with same error
- Sudden quality drop
- User complaints spike

### Escalation Protocol

```markdown
Severity 1 - Critical (Act immediately)
→ Disable AI generation
→ Alert on-call engineer
→ Notify stakeholders
→ Root cause analysis

Severity 2 - High (Act within 1 hour)
→ Increase review frequency
→ Add safety filters
→ Alert content team
→ Monitor closely

Severity 3 - Medium (Act within 1 day)
→ Document issue
→ Add to review queue
→ Plan fix for next update
→ Track in metrics
```

## Improving AI Content Quality

### Common Problems & Solutions

**Problem: Hallucinating facts**
```
Solution:
- Provide knowledge base for grounding
- Add "I don't know" capability
- Cite sources
- Use retrieval-augmented generation (RAG)
```

**Problem: Inconsistent terminology**
```
Solution:
- Include terminology guide in system prompt
- Add consistency checking
- Provide term dictionary
- Use find/replace validation
```

**Problem: Wrong tone**
```
Solution:
- Add tone examples to prompt
- Create tone rubric for training
- Provide context (error vs help vs marketing)
- Show good/bad examples
```

**Problem: Not helpful**
```
Solution:
- Include user task context
- Show successful examples
- Add outcome measurement
- Retrain on highly-rated responses
```

### Iterative Improvement Process

```markdown
Week 1: Baseline
- Launch with human review
- Track all metrics
- Document issues

Week 2-4: Learn
- Analyze patterns
- Identify top issues
- Gather user feedback

Week 5: Improve
- Update prompts
- Retrain model
- Add guardrails
- A/B test changes

Week 6: Measure
- Compare metrics to baseline
- Validate improvements
- Document learnings

Repeat cycle
```

## Evaluation Templates

### Quick Evaluation Form

```markdown
Content ID: _____________
Generated: [Date/Time]
Reviewer: _____________

User Query:
[User's question or context]

AI Response:
[AI-generated content]

Evaluation:
[ ] Accurate (Factually correct)
[ ] Relevant (Answers the question)
[ ] Appropriate (Right tone & style)
[ ] Safe (No harmful content)
[ ] Consistent (Matches standards)

Overall Score: ___/5

Decision:
[ ] Approve as-is
[ ] Approve with edits
[ ] Needs major revision
[ ] Reject

Notes:
[What works? What needs fixing?]

Edits Made:
[If approved with edits, what changed?]
```

### Detailed Review Template

```markdown
=== AI Content Detailed Review ===

Content Details:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ID: ______________
Type: [ ] Help [ ] Error [ ] Chat [ ] Other
Generated: [Date/Time]
Reviewer: ______________

Context:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
User query: _________________
User type: [ ] New [ ] Experienced [ ] Admin
Device: [ ] Desktop [ ] Mobile [ ] Tablet
Product area: ______________

Accuracy & Correctness:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Factually accurate          ⬜ 1-5: ___
[ ] Technically correct         ⬜ 1-5: ___
[ ] Current (not outdated)      ⬜ 1-5: ___
[ ] No hallucinations           ⬜ 1-5: ___
Issues found: ______________

Relevance & Usefulness:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Addresses user need         ⬜ 1-5: ___
[ ] Appropriate detail level    ⬜ 1-5: ___
[ ] Actionable                  ⬜ 1-5: ___
[ ] Complete                    ⬜ 1-5: ___
Issues found: ______________

Tone & Voice:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Appropriate formality       ⬜ 1-5: ___
[ ] Matches brand voice         ⬜ 1-5: ___
[ ] Suitable for context        ⬜ 1-5: ___
[ ] Professional                ⬜ 1-5: ___
Issues found: ______________

Safety:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] No harmful content          ⬜ Pass/Fail
[ ] No offensive language       ⬜ Pass/Fail
[ ] No biased language          ⬜ Pass/Fail
[ ] Privacy-respecting          ⬜ Pass/Fail
CRITICAL: Reject if any fail

Consistency:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ ] Terminology matches         ⬜ 1-5: ___
[ ] Aligns with docs            ⬜ 1-5: ___
[ ] Matches UI                  ⬜ 1-5: ___
[ ] No contradictions           ⬜ 1-5: ___
Issues found: ______________

Overall Assessment:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Total Score: ___/5

Decision:
[ ] APPROVE - Publish as-is
[ ] APPROVE WITH EDITS - Minor changes needed
[ ] MAJOR REVISION - Significant rework required
[ ] REJECT - Cannot use, regenerate

Required Edits:
1. ______________
2. ______________
3. ______________

Feedback for Model Improvement:
______________

Time Spent: ___ minutes
```

## Best Practices

### ✅ DO:

**Evaluate consistently**
Use same rubric and criteria every time

**Document patterns**
Track common issues for systematic fixes

**Close the feedback loop**
Use evaluation insights to improve model

**Combine automated + human**
Automate safety checks, human review quality

**Calibrate reviewers**
Train reviewers, check inter-rater reliability

**Track trends**
Monitor metrics over time, not just point-in-time

### ❌ DON'T:

**Skip safety checks**
Never compromise on safety

**Edit without documentation**
Track what you change and why

**Ignore user feedback**
Users tell you what's not working

**Evaluate in isolation**
Consider context, user needs, product goals

**Stop evaluating**
Quality drifts - continuous monitoring needed

## Related Resources

- [AI Content Strategy](../templates/ai-content/ai-content-strategy.md)
- [Prompt Design Guide](../templates/ai-content/prompt-design.md)
- [Content as Data](../templates/ai-content/content-as-data.md)
- [Ethical AI Guidelines](../resources/ethical-ai-content.md)
- [Safety Guidelines](../resources/content-safety.md)
