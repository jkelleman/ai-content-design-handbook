# Voice and Tone Framework

A template for defining your product's voice and tone guidelines.

## Voice vs. Tone

**Voice** = Your product's personality (consistent across all content)
**Tone** = How voice adapts to context (changes based on situation)

Think of it like a person:
- **Voice** = Their core personality traits
- **Tone** = How they adjust their communication style based on the situation

## Defining Your Voice

### Voice Attributes

Choose 3-5 core attributes that define your product's personality:

| Attribute | What It Means | Example |
|-----------|---------------|---------|
| [Attribute 1] | [Definition] | [Example phrase] |
| [Attribute 2] | [Definition] | [Example phrase] |
| [Attribute 3] | [Definition] | [Example phrase] |

**Example:**

| Attribute | What It Means | Example |
|-----------|---------------|---------|
| Helpful | We anticipate needs and guide users toward success | "Here's what you can do next" |
| Clear | We use simple language without jargon | "Pipeline failed" not "Execution terminated with non-zero exit code" |
| Confident | We're knowledgeable but not arrogant | "This will create a backup" not "This might maybe create a backup" |

### Voice Principles

**We are:**
- [Principle 1]
- [Principle 2]
- [Principle 3]

**We are NOT:**
- [Anti-principle 1]
- [Anti-principle 2]
- [Anti-principle 3]

**Example:**

**We are:**
- Clear and direct
- Professional but approachable
- Empowering users with knowledge

**We are NOT:**
- Overly technical or jargon-heavy
- Cute or trying too hard to be funny
- Talking down to users

## Tone Guidelines

Tone adapts based on context. Define how your voice shifts across different situations.

### Tone Matrix

| Context | User's Feeling | Our Tone | Example |
|---------|----------------|----------|---------|
| Success | Accomplished | Affirming | "Great! Your pipeline is running." |
| Error | Frustrated | Helpful, calm | "Connection failed. Check your network and try again." |
| Onboarding | Uncertain | Encouraging, clear | "Let's create your first pipeline together." |
| Warning | Concerned | Clear, serious | "This action will permanently delete your data." |
| Empty state | Lost | Motivating, guiding | "Ready to get started? Create your first dataset." |
| Complex task | Overwhelmed | Supportive, step-by-step | "We'll walk through this together." |

### Tone Spectrum

For each context, define where your tone falls on key spectrums:

**Formal ←→ Casual**
```
Most contexts: Slightly casual
Errors: Professional but approachable
Legal/compliance: More formal
```

**Serious ←→ Playful**
```
Most contexts: Friendly but focused
Errors: Serious, never playful
Success states: Can be more upbeat
```

**Direct ←→ Indirect**
```
Errors and warnings: Very direct
Instructions: Direct and clear
Marketing: Can be more narrative
```

**Technical ←→ Plain language**
```
Documentation: Balance both
UI text: Plain language
API docs: More technical acceptable
```

## Language Guidelines

### Words We Use

**Preferred terms:**
- [Term 1] instead of [alternative]
- [Term 2] instead of [alternative]
- [Term 3] instead of [alternative]

**Example:**
- "Select" instead of "click"
- "Error" instead of "failure" or "problem"
- "Sign in" instead of "log in"

### Words We Avoid

❌ **Avoid:**
- Jargon without definition
- Cutesy language ("Oopsie!")
- Diminishing words ("just," "simply," "easy")
- Assumptive language ("obviously," "of course")
- Gendered language ("guys," "he/she")
- Ableist language ("crazy," "blind spot")

### Grammar & Mechanics

**Capitalization:**
- [Your rules]
- Example: Sentence case for buttons, title case for headers

**Punctuation:**
- [Your rules]
- Example: No periods in button labels, periods in complete sentences

**Contractions:**
- [Your policy]
- Example: Use contractions for conversational tone ("you're" not "you are")

**Active vs. Passive voice:**
- [Your preference]
- Example: Use active voice ("System processes your request" not "Your request is processed")

## Voice Examples

### ✅ Good Examples

Show your voice in action across different content types:

**Error message:**
```
✅ "Connection timeout. Check your network settings and try again."

Why it works: Clear, actionable, maintains helpful tone even in error state
```

**Success message:**
```
✅ "Pipeline created! You can monitor its progress in the dashboard."

Why it works: Affirming but not overly excited, points user to next step
```

**Empty state:**
```
✅ "No pipelines yet. Ready to create your first one?"

Why it works: Encouraging without being pushy, clear call to action
```

### ❌ Bad Examples

Show what NOT to do:

**Error message:**
```
❌ "Oops! Something went wrong. 😕"

Why it's bad: Not helpful, no actionable guidance, inappropriate tone for error
```

**Success message:**
```
❌ "OMG! You totally crushed it! 🎉🎉🎉"

Why it's bad: Overly enthusiastic, unprofessional, too casual
```

**Technical content:**
```
❌ "Utilize the pipeline orchestration service to facilitate data ingestion workflows"

Why it's bad: Unnecessarily complex language, jargon-heavy
```

## Context-Specific Guidelines

### Error Messages

**Tone:** Calm, helpful, clear
**Structure:** [What happened] + [Why/Context] + [What to do]
**Example:** "Pipeline failed. Network connection lost. Check your connection and try again."

### Success Messages

**Tone:** Affirming, forward-looking
**Structure:** [Confirm action] + [Next step optional]
**Example:** "Dataset created successfully. Add data to get started."

### Onboarding

**Tone:** Encouraging, clear, patient
**Structure:** [Welcome/Context] + [Simple explanation] + [Clear next step]
**Example:** "Welcome to Fabric! Let's create your first pipeline. It takes about 2 minutes."

### Documentation

**Tone:** Clear, authoritative, helpful
**Structure:** [Concept] + [Step-by-step] + [Example]
**Example:** "Pipelines automate data workflows. To create one: 1. Select Create Pipeline 2. Configure settings 3. Add activities"

### Marketing/Landing Pages

**Tone:** [Your preference]
**Structure:** [Your pattern]
**Example:** [Your example]

### Legal/Compliance

**Tone:** Clear, professional, accurate
**Structure:** [Requirement] + [User action needed]
**Example:** "Your data is encrypted at rest and in transit. By continuing, you agree to our Terms of Service."

## AI-Specific Voice Guidelines

If your product includes AI features, define how voice applies to AI interactions:

### AI Transparency

**Always disclose AI:**
```
✅ "I'm an AI assistant trained to help with [product]."
```

**Admit uncertainty:**
```
✅ "I'm not certain about that. Let me connect you with a human expert."
```

**Never fake human:**
```
❌ "Hi, I'm Sarah from support!"
[When it's actually AI]
```

### AI Tone

**Helpful but humble:**
- Acknowledge AI limitations
- Don't overpromise capabilities
- Offer human alternatives

**Example:**
```
✅ "I can help with common questions about pipelines, but complex issues 
may need human support. What can I help with?"
```

## Using This Framework

### For Writers

1. **Start here** - Reference this guide before writing
2. **Check examples** - Look at good/bad examples for your content type
3. **Test tone** - Read your content aloud - does it sound like our voice?
4. **Get feedback** - Have others review for voice consistency

### For Reviewers

**Voice checklist:**
- [ ] Matches our core voice attributes?
- [ ] Appropriate tone for context?
- [ ] Uses preferred terminology?
- [ ] Avoids words on "don't use" list?
- [ ] Follows grammar and mechanics rules?
- [ ] Sounds like other content in the product?

### For Teams

**Maintain consistency:**
- Regular voice reviews of new content
- Voice training for new team members
- Update this guide as product evolves
- Create pattern library of approved examples

## Evolution & Updates

**Voice should evolve:**
- User feedback and research
- Product maturity
- Market changes
- Brand evolution

**Update this guide when:**
- Adding new product areas
- Expanding to new audiences
- Receiving consistent voice feedback
- Launching major rebrand

**Version history:**
- v1.0 - [Date] - Initial framework
- v1.1 - [Date] - Added AI voice guidelines
- [Your versions]

## How leading companies define voice and tone

### Atlassian: tone that follows the person's state

Atlassian's voice has three traits: bold, optimistic, and practical with a wink. What makes it useful is the rule for flexing it:

| Person's state | Tone shift |
|---|---|
| Confident, experienced (power users, admins) | Bold and optimistic get stronger |
| Confused, anxious, or new (trials, first use of a feature) | Bold and optimistic soften; guidance gets more prescriptive |
| Stressed, blocked, facing errors or deadlines | Practical takes priority |
| Success, relief, pride | The wink appears, sparingly, and only if it works across cultures |

([Voice and tone](https://atlassian.design/foundations/content/voice-tone))

### Google Material: the tone map

Material recommends plotting each message type on two axes, such as playful to serious and concise to detailed, to make tone decisions explicit. Errors sit toward serious and detailed; onboarding can sit toward warm. ([Material communication](https://codelabs.developers.google.com/codelabs/material-communication-guidance))

```
                    DETAILED
                       │
        Errors ●       │       ● Onboarding
                       │
 SERIOUS ──────────────┼────────────── PLAYFUL
                       │
     Confirmations ●   │     ● Success
                       │
                    CONCISE
```

### Apple: tone matched to the situation

Apple's HIG contrasts two Apple Watch messages: a direct, serious tone when fall detection triggers, and a light, congratulatory tone for a record Activity streak. Same voice, very different tone. Apple also asks teams to keep a list of common terms to make language consistent. ([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing))

### Salesforce: one voice across every content type

Salesforce asks apps built on its platform to sound like Salesforce, and applies the same writing guidelines to in-app text, help, developer docs, and Trailhead training. ([SLDS voice and tone](https://spring-21.lightningdesignsystem.com/guidelines/voice-and-tone))

### Shopify: one voice, shifting tone

Shopify asks apps to keep a consistent voice that matches the Shopify admin, while letting tone shift with the situation: errors call for a more direct tone than onboarding tips. ([App content](https://shopify.dev/apps/design-guidelines/content))

### Where companies disagree: "we"

Apple avoids "we" because it's unclear who that refers to, especially in errors. Atlassian and Adobe use "we" for the system and "you" for the person, so it's clear who acts. Decide, and write the decision into this framework.

### AI voice

If an AI feature speaks in first person ("I found 3 results"), decide whether that voice is the product's or a distinct assistant's, and keep it consistent. Avoid a cheerful persona that contradicts the product's tone in serious moments. The Atlassian rule applies to AI too: when people are blocked, the AI should get practical, not chatty.

More detail: [How Leading Companies Design Content for AI](../resources/industry-examples.md)

## Resources

**Voice references:**
- [Link to brand guidelines]
- [Link to content examples]
- [Link to pattern library]

**Training:**
- [Link to onboarding doc]
- [Link to voice workshop materials]

**Questions?**
Contact: [Content team contact]

---

## Quick Reference Card

**Our Voice in 3 words:**
1. [Attribute]
2. [Attribute]
3. [Attribute]

**We are / We're NOT:**
✅ [We are] / ❌ Not [This]
✅ [We are] / ❌ Not [This]
✅ [We are] / ❌ Not [This]

**Top 3 words to avoid:**
❌ [Word 1]
❌ [Word 2]
❌ [Word 3]

**When in doubt:**
Ask: "Would our users understand this?" and "Does this sound like us?"
