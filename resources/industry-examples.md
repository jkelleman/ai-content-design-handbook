# How Leading Companies Design Content for AI

A reference to the public content and AI design guidance from 10 of the largest technology companies, with what each one teaches and where to read it. Every page in this handbook links back here when it uses one of these examples.

> **How to use this page:** Skim the summary table to find which company has the strongest guidance for your problem, then read the source. Everything here is paraphrased from each company's public guidance and linked so you can check the original. Guidance changes; when in doubt, the source wins.

## At a glance

| Company | Strongest public guidance | Best for |
|---|---|---|
| **Google** | [People + AI Guidebook](https://pair.withgoogle.com/guidebook/chapters), [Material communication guidance](https://codelabs.developers.google.com/codelabs/material-communication-guidance), [Technical writing: error messages](https://developers.google.com/tech-writing/error-messages/set-tone) | AI errors and failure states, mental models, tone mapping |
| **Microsoft** | [Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/), [Writing Style Guide](https://learn.microsoft.com/style-guide/), [Transparency notes](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-transparency-note) | AI interaction principles, bias-free language, documenting AI limits |
| **Apple** | [Human Interface Guidelines: Writing](https://developer.apple.com/design/human-interface-guidelines/writing) | Action-oriented labels, empty states, field-level errors, tone by situation |
| **Amazon** | [Alexa situational design](https://developer.amazon.com/alexa-skills-kit/situational-design), [AWS AI Service Cards](https://aws.amazon.com/blogs/machine-learning/introducing-aws-ai-service-cards-a-new-resource-to-enhance-transparency-and-advance-responsible-ai) | Voice and conversational design, AI documentation |
| **Meta** | [AI labeling on Facebook, Instagram, and Threads](https://www.engadget.com/meta-plans-to-ramp-up-labeling-of-ai-generated-images-across-its-platforms-160234038.html) | Labeling AI-generated media at scale, and what happens when labels are wrong |
| **IBM** | [Carbon for AI](https://carbondesignsystem.com/guidelines/carbon-for-ai/), [AI label component](https://carbondesignsystem.com/components/ai-label/usage/) | Marking AI content in the UI, explainability entry points |
| **Salesforce** | [Trusted AI principles and Einstein Trust Layer](https://salesforce.com/uk/artificial-intelligence/trusted-ai/), [Lightning Design System voice and tone](https://spring-21.lightningdesignsystem.com/guidelines/voice-and-tone) | Enterprise AI trust: data masking, toxicity checks, human oversight |
| **Adobe** | [Spectrum: Writing for errors](https://spectrum.adobe.com/page/writing-for-errors), [Content Credentials](https://helpx.adobe.com/in/creative-cloud/apps/adobe-content-authenticity/content-credentials/overview.html) | Error tone by severity, provenance for AI-generated media |
| **Atlassian** | [Voice and tone](https://atlassian.design/foundations/content/voice-tone), [Error messages](https://atlassian.design/foundations/content/designing-messages/error-messages) | Tone that shifts with user state, message anatomy |
| **Shopify** | [App content guidelines](https://shopify.dev/apps/design-guidelines/content) | Plain language for a global audience, consistent terms, strong-verb calls to action |

---

## Google

**People + AI Guidebook (PAIR).** Google's PAIR team organizes AI product guidance into six chapters: user needs and success, mental models, explainability and trust, data collection and evaluation, feedback and control, and errors and graceful failure. In 2023 the team began amending these chapters for generative AI, focusing on outputs that change every run, hallucinations, and helping people decide whether to edit or fact-check generated text. ([Update post](https://medium.com/people-ai-research/updating-the-people-ai-guidebook-in-the-age-of-generative-ai-cace6c846db4))

The **Errors + Graceful Failure** chapter is the most useful single resource for AI error content. It names error types that traditional software doesn't have:

| Error type | What it means | Example from the chapter |
|---|---|---|
| Context error | The system works as designed but guesses wrong about what the person wanted | Automatically adding a calendar event from a flight email the person didn't want |
| System limitation | The AI can't produce an answer, or can't produce the right one | A plant identifier that can't recognize a species it wasn't trained on |
| Background error | The system is wrong and nobody notices | Needs stress testing, because user feedback won't catch it |
| Relevance error | A confident answer at the wrong moment | Suggesting fun vacation activities after someone books travel for a funeral |

Its writing advice: say specifically what the system can't do and what input it needs, use failures to explain how the AI works, and always offer a path forward, the way a waiter suggests a substitute when a dish is unavailable. ([Chapter PDF](https://pair.withgoogle.com/chapter/People%20+%20AI%20Guidebook%20-%20Errors%20+%20Graceful%20Failure.pdf))

**Material Design communication guidance.** Material teaches building a *tone map*: plot each message type (onboarding, errors, labels) on two axes, such as playful to serious and concise to detailed. Errors move from casual toward supportive and detailed. Other rules: address people as "you," don't mix "my" and "your" in one phrase, start with the person's goal before the action, and refer to controls by their label text. ([Codelab](https://codelabs.developers.google.com/codelabs/material-communication-guidance))

**Technical writing for error messages.** Google's developer writing course says to be positive and instructive (tell people what to do, not what they did wrong), skip "sorry" and "please," avoid humor, and describe what happened rather than what the user did. ([Set the right tone](https://developers.google.com/tech-writing/error-messages/set-tone))

## Microsoft

**Guidelines for Human-AI Interaction.** Published at CHI 2019 by Microsoft Research, these 18 guidelines are grouped by when they apply. They remain the most widely cited checklist for AI experience design. ([Paper](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/))

| When | Guidelines |
|---|---|
| **Initially** | G1 Make clear what the system can do · G2 Make clear how well it can do it |
| **During interaction** | G3 Time services based on context · G4 Show contextually relevant information · G5 Match relevant social norms · G6 Mitigate social biases |
| **When wrong** | G7 Support efficient invocation · G8 Support efficient dismissal · G9 Support efficient correction · G10 Scope services when in doubt · G11 Make clear why the system did what it did |
| **Over time** | G12 Remember recent interactions · G13 Learn from user behavior · G14 Update and adapt cautiously · G15 Encourage granular feedback · G16 Convey the consequences of user actions · G17 Provide global controls · G18 Notify users about changes |

**Writing Style Guide: bias-free communication.** Specific substitutions content teams can adopt directly: *primary/subordinate* instead of *master/slave*, *chair* or *moderator* instead of *chairman*, *workforce* instead of *manpower*, *perimeter network* instead of *DMZ*, and *stop responding* instead of *hang*. For unspecified people, address the reader as "you," use plurals, or name the role; singular "they" is acceptable when nothing else works. ([Bias-free communication](https://learn.microsoft.com/style-guide/bias-free-communication))

**Error message guidelines.** A good error message says what happened and why, what it means for the person, and what to do. Microsoft's rules: write a specific message for each known cause, don't blame the user even when they caused it, avoid "bad" and say what's actually wrong, avoid "please" (it can make a required action sound optional), and don't anthropomorphize software. ([Error message guidelines](https://learn.microsoft.com/en-us/windows/win32/debug/error-message-guidelines))

**Transparency notes and application cards.** Microsoft publishes documentation for its AI products covering intended uses, limitations, evaluations, and mitigations. The Microsoft 365 Copilot note says Copilot tells people they're interacting with AI, adds reminders that AI-generated content may contain errors, cites sources from business documents where possible, and warns against overreliance, with extra care for agentic actions that can't be undone. ([Microsoft 365 Copilot note](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-transparency-note))

## Apple

**Human Interface Guidelines: Writing.** Apple's writing page (updated December 2025) is short and specific:

- **Match tone to the moment.** Apple contrasts two Apple Watch messages: a direct, serious tone for fall detection and a light, congratulatory tone for an Activity streak.
- **Be action oriented.** Label buttons with verbs. A plain "Send" works better than a cute "Let's do it!" Avoid "Click here" for links.
- **Avoid "we."** It's unclear who "we" is. Apple prefers "Unable to load content" over "We're having trouble loading this content."
- **Errors near the problem, with the fix.** "Choose a password with at least 8 characters" beats "That password is too short." Skip "oops" and "uh-oh."
- **Empty states give a next step** and shouldn't hold crucial information, because they disappear.
- **Settings descriptions say what happens when on;** people infer the opposite.
- **Field errors instruct, not scold.** "Use only letters for your name" beats "Don't use numbers or symbols."

([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing))

## Amazon

**Alexa situational design.** Amazon's voice guidance argues that voice experiences must be designed voice-first rather than added to a screen app. Its dialog-writing advice: build on situations instead of rigid flow charts, adapt to returning users (skip onboarding after a short gap, mention new features after a long one), write for the ear so responses can be followed by listening alone, and use punctuation to control pacing. ([Situational design](https://developer.amazon.com/alexa-skills-kit/situational-design), [Writing great dialogs](https://developer.amazon.com/blogs/alexa/post/9c5f66b0-9514-423a-827e-a2e71a68b456/how-to-write-great-dialogs-for-alexa-skills))

**AWS AI Service Cards.** Each card documents one AI service in four sections: basic concepts, intended use cases and limitations, responsible AI design considerations (fairness, explainability, expected performance), and deployment and optimization guidance. They're a strong model for documenting any AI feature. ([Announcement](https://aws.amazon.com/blogs/machine-learning/introducing-aws-ai-service-cards-a-new-resource-to-enhance-transparency-and-advance-responsible-ai))

## Meta

**Labeling AI-generated content.** In 2024 Meta began labeling AI-generated images on Facebook, Instagram, and Threads by detecting C2PA and IPTC metadata embedded by generator tools, and asked people to self-disclose photorealistic AI video and realistic audio, with a more prominent label for content at high risk of deceiving the public. ([Engadget](https://www.engadget.com/meta-plans-to-ramp-up-labeling-of-ai-generated-images-across-its-platforms-160234038.html))

**A lesson in label wording.** Meta's first label, "Made with AI," was applied to photos with only minor AI edits, and photographers objected that it mislabeled their real work. Meta replaced it with "AI info," which opens an explanation that generative AI *may* have been used. The takeaway for content designers: a label makes a claim, so its wording has to match what the system actually knows. ([Report](https://jang.com.pk/en/15206-meta-replaces-made-with-ai-label-with-ai-info-amid-user-criticism-news))

## IBM

**Carbon for AI and the AI label.** IBM's Carbon design system marks AI-generated content with a consistent AI label at every level of the interface, from one word to a whole page. The label is the entry point to explainability: selecting it opens a popover with an overview, supporting details, artifacts and resources, and additional actions. Carbon's rules:

- Use the label only where AI is actually present, never as decoration.
- Don't turn the label into an action button (regenerate gets its own control).
- Never disable it, even in read-only states.
- When someone edits AI-generated content, remove the AI styling and offer a revert control.

([AI label usage](https://carbondesignsystem.com/components/ai-label/usage/), [Carbon for AI](https://carbondesignsystem.com/guidelines/carbon-for-ai/))

## Salesforce

**Trusted AI principles.** Salesforce publishes five principles: responsible, accountable, transparent, empowering, and inclusive. The **Einstein Trust Layer** puts several of them into the product: sensitive data is masked with placeholder tokens before a prompt reaches the model, prompts and responses aren't retained by third-party model providers, and generated content is scanned for toxicity and bias before people see it. ([Trusted AI](https://salesforce.com/uk/artificial-intelligence/trusted-ai/))

**One voice across product and docs.** Salesforce's design system asks apps built on the platform to sound like Salesforce, and applies the same writing guidelines to in-app text, help, developer docs, and Trailhead training. ([SLDS voice and tone](https://spring-21.lightningdesignsystem.com/guidelines/voice-and-tone))

## Adobe

**Spectrum: Writing for errors.** Adobe starts from the idea that the best error is one that never appears: prevent it, or fix it automatically (for example, clamp an out-of-range value instead of warning). When a message is needed, write it before picking the component, then match the component to severity: help text for field errors, toasts for brief non-blocking ones, alert dialogs for high-stakes blocking errors. Tone scales with severity, from instructive (low stakes) to reassuring (minor) to supportive (serious). Apologize only for serious problems such as data loss. ([Writing for errors](https://spectrum.adobe.com/page/writing-for-errors))

**Content Credentials.** Adobe describes Content Credentials as a "digital nutrition label": metadata recording who made a piece of content and how, including whether AI generated it. Firefly attaches them automatically, and a Cr icon on supported images reveals the details. ([Content Credentials](https://helpx.adobe.com/in/creative-cloud/apps/adobe-content-authenticity/content-credentials/overview.html))

## Atlassian

**Voice and tone that responds to the person.** Atlassian's voice is bold, optimistic, and practical with a wink. The useful part is how it flexes: bold and optimistic get stronger for confident power users and softer for anxious or new users; practical takes over when people are stressed, blocked, or hitting errors; the wink is saved for success moments and used sparingly. ([Voice and tone](https://atlassian.design/foundations/content/voice-tone))

**Error message anatomy.** Optional titles of three or four words that don't give instructions; body text covering the cause, the action, and the consequence of not acting, in one or two sentences; specific calls to action instead of "OK." Atlassian uses "we" rather than "you" so people don't feel blamed, and avoids "please" and "sorry" unless consequences are severe and irreversible. ([Error messages](https://atlassian.design/foundations/content/designing-messages/error-messages))

> Note how Apple and Atlassian disagree about "we." Apple avoids it because it's ambiguous; Atlassian uses it to take responsibility. Pick one approach, write it into your style guide, and apply it consistently.

## Shopify

**Content for a global audience.** Shopify's app guidelines ask for writing that works for merchants worldwide with varied reading skills and first languages: aim for about a US grade 7 reading level, use headings, bullets, and short sentences, and avoid idioms that mistranslate. Pick one term per concept and keep it (not "Upload image" in one place and "Add photos" in another). Calls to action open with a strong verb, as in "Create template." Errors take a more direct tone than onboarding tips. ([App content guidelines](https://shopify.dev/apps/design-guidelines/content))

---

## Patterns across all 10

When companies with different products and cultures agree, it's a strong signal:

1. **Don't blame the person.** Microsoft, Google, Apple, Adobe, and Atlassian all say so explicitly.
2. **Every error needs a next step.** Microsoft, Google PAIR, Apple, Adobe, and Atlassian.
3. **Label buttons with specific verbs,** not "OK" or clever phrases: Apple, Atlassian, Shopify.
4. **Mark AI content consistently** and make the marker lead to an explanation: IBM, Microsoft, Adobe, Meta.
5. **Document AI limits publicly:** Microsoft transparency notes, AWS AI Service Cards.
6. **Tone follows the person's state,** not the brand's mood: Material, Apple, Atlassian, Adobe.
7. **Skip "please" and "sorry" for routine problems:** Google, Microsoft, Atlassian, Adobe.

## Related resources

- [Error Messages](../templates/messages/error-messages.md)
- [Transparency Guidelines](ethical-ai/transparency-guidelines.md)
- [Voice and Tone Framework](../style-guides/voice-and-tone-framework.md)
- [Agentic AI Experiences](../templates/ai-content/agentic-experiences.md)
