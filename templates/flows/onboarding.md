# Onboarding Flow Template

Onboarding gets people to their first success as fast as possible, and teaches only what they need for it. For AI features, it also has to set honest expectations about what the AI can do and how reliable it is.

## Template Structure

```
[Welcome/Introduction]
↓
[Value Proposition]
↓
[Key Action(s)]
↓
[Success State]
```

## Onboarding Framework

### 1. Define Onboarding Goals

**User goal:** What does the user want to accomplish?
**Business goal:** What action leads to activation/retention?
**Success metric:** How do you measure effective onboarding?

### 2. Onboarding Content Types

**Welcome message:**
- Acknowledge the user
- Set expectations
- Show value quickly

**Setup steps:**
- Only include what's necessary for first success
- Defer optional setup
- Allow skipping when possible

**First success:**
- Guide to one meaningful action
- Celebrate completion
- Show path to next value

### 3. Onboarding Checklist

- [ ] Focuses on user's goal, not product features
- [ ] Minimizes steps to first value
- [ ] Allows users to skip or defer optional steps
- [ ] Uses progressive disclosure (show more as needed)
- [ ] Provides clear exit points
- [ ] Celebrates first success

## Onboarding Patterns

### Pattern 1: Product Tour
**When to use:** Complex UI, multiple features, experienced users

```
**Welcome to [Product]**
Take a quick tour to see what you can do.

[Step 1 of 3] [Skip tour]

→ Point out key features
→ Allow exploration
→ Provide tour restart option
```

**Pros:** Comprehensive overview  
**Cons:** Can be skipped, may not lead to action

---

### Pattern 2: Task-Based Onboarding
**When to use:** Clear primary use case, users want to act immediately

```
**Let's create your first pipeline**

Choose a data source to get started:
○ Upload file
○ Connect to database  
○ Use sample data

[Next]
```

**Pros:** Gets users to value quickly  
**Cons:** May skip secondary features

---

### Pattern 3: Progressive Onboarding
**When to use:** Multiple user segments, complex product

```
**What brings you here today?**

○ I want to move data between sources
○ I want to transform and clean data
○ I want to automate data workflows
○ I'm just exploring

[Contextual guidance based on selection]
```

**Pros:** Personalized experience  
**Cons:** More complex to implement

---

### Pattern 4: Checklist Onboarding
**When to use:** Multiple setup steps required

```
**Get started with [Product]**

✓ Account created
○ Connect your data source
○ Create your first pipeline
○ Invite team members [Optional]

[Next step: Connect data source]
```

**Pros:** Clear progress, allows async completion  
**Cons:** Can feel like homework

## Onboarding Copy Principles

### Welcome Messages

**Do:**
- Welcome users personally
- Acknowledge what they signed up for
- Set clear expectations
- Show enthusiasm without being fake

**Example:**
```
**Welcome to Data Pipelines**
You're all set to move and transform data across your sources. Let's build your first pipeline.
```

### Step Instructions

**Do:**
- Use action-oriented verbs
- Explain "why" briefly
- Keep instructions scannable
- Provide examples when helpful

**Example:**
```
**Connect a data source**
Choose where your data lives. You can add more sources later.

[Microsoft SQL Server]
[Azure Blob Storage]
[Upload file]
```

### Success Celebrations

**Do:**
- Confirm what was accomplished
- Provide clear next step
- Maintain momentum

**Example:**
```
**Your first pipeline is running! 🎉**
Data will appear in your workspace within a few minutes.

Next: Invite teammates to collaborate on this workspace.

[Invite team] [Go to workspace]
```

## Onboarding Flow Examples

### Example 1: Data Tool First-Time Setup
```
Screen 1: Welcome
**Welcome to Data Factory**
Build pipelines to move and transform data across sources.
[Get started]

Screen 2: Choose Source
**Connect your first data source**
○ Azure SQL Database
○ Amazon S3
○ Upload CSV file
[Continue]

Screen 3: Create Pipeline
**Create your pipeline**
Name: [                    ]
Source: Azure SQL Database
Destination: [Choose...]
[Create pipeline]

Screen 4: Success
**Pipeline created!**
Your data is now syncing every hour.
[View pipeline] [Create another]
```

### Example 2: Collaborative Tool
```
Screen 1: Account Setup
**Set up your workspace**
Workspace name: [              ]
[Continue]

Screen 2: Invite Team (Optional)
**Invite your team**
Add teammates by email: [           ] [+ Add]
[Send invites] [Skip for now]

Screen 3: First Action
**Create your first project**
[Import from template] [Start from scratch]

Screen 4: Success
**Project created!**
You're ready to collaborate.
[Invite more teammates] [Start working]
```

## When to Show Onboarding

**Always show for:**
- Brand new users
- New major features
- Significant UI changes

**Consider showing for:**
- Users who abandoned initial setup
- Users who haven't taken key actions
- Users moving between tiers/plans

**Don't show again for:**
- Returning users who completed onboarding
- Users who explicitly skipped
- Users demonstrating product mastery

## Writing the flow: labels and steps

Consistent step labels tell people where they are. Apple's HIG suggests starting a multi-step flow with language like **Get Started**, moving through it with **Continue** or **Next** (pick one and keep it), and ending with **Done** so it's clear the flow is complete.

| Step | Label pattern | Example |
|---|---|---|
| Start | "Get started," "Set up [thing]" | [Set up workspace] |
| Middle | "Continue" or "Next" (choose one), or a label that previews the next step | [Continue] or [Connect data] |
| Optional | "Skip for now," never just "Skip" when it can be done later | [Skip for now] |
| End | "Done," or the first real action | [Done] or [Open dashboard] |

Show progress honestly ("Step 2 of 3") and never add steps after promising a number.

## Onboarding returning users

Not everyone who sees onboarding is new. Amazon's Alexa dialog guidance recommends adapting to how familiar someone is and how long they've been away: skip the introduction after a short gap, and mention what's new after a long one.

| Returning after… | Show |
|---|---|
| A few days | Nothing; take them where they left off |
| Several weeks | A one-line "What's new" with a link |
| An abandoned setup | "Pick up where you left off" with the remaining steps |
| A major redesign | A short, skippable tour of what moved |

## Onboarding to an AI feature

AI features need different onboarding, because people's main question isn't "where is it?" but "what can it do, and can I trust it?" Microsoft's Guidelines for Human-AI Interaction open with exactly these two: make clear what the system can do (G1), and make clear how well it can do it (G2).

**Cover four things, briefly:**

1. **What it does,** in concrete terms: "Ask questions about your sales data in plain language."
2. **What it can't do:** "It can't see data outside this workspace or change your data."
3. **How reliable it is:** "Answers can contain mistakes. Each one shows the query it used so you can check."
4. **How to start:** two or three example prompts that are likely to work well.

```
❌ Meet your new AI assistant! ✨ It can help you with anything.

✅ Ask questions about your sales data
   Get answers in plain language, with the query behind each one so you can check it.
   It can't see other workspaces or change your data.
   Try: "Which products sold best last month?"
   [Ask a question]   [Not now]
```

Google's People + AI Guidebook adds that early errors shape people's mental model of an AI feature, so onboarding should set expectations before the first mistake happens, not after.

**Announce changes later, too.** G18, notify users about changes, applies after onboarding. When the AI gains a capability or behaves differently, tell people. See [Release Notes](../documentation/release-notes.md).

## Measuring Onboarding Success

**Key metrics:**
- Completion rate
- Time to first value
- Activation rate
- Drop-off points
- Feature adoption post-onboarding

## How leading companies do it

| Company | What they teach |
|---|---|
| **Apple** | Use consistent labels through multi-step flows (Get Started → Continue or Next → Done), and consider each screen's purpose, putting the most important information first. ([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing)) |
| **Amazon** | Adapt to returning users: skip onboarding after a short absence, mention new features after a long one. ([Writing great dialogs](https://developer.amazon.com/blogs/alexa/post/9c5f66b0-9514-423a-827e-a2e71a68b456/how-to-write-great-dialogs-for-alexa-skills)) |
| **Microsoft** | For AI features, make clear what the system can do and how well it can do it, from the first screen. ([Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/)) |
| **Atlassian** | Soften confident tone for new or anxious users and give more prescriptive guidance; teach at key moments and suggest next steps. ([Voice and tone](https://atlassian.design/foundations/content/voice-tone)) |
| **Shopify** | Split complex tasks into steps that each focus on one action, and put the most important tasks first. ([App content](https://shopify.dev/apps/design-guidelines/content)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related Templates

- [Empty States](../messages/empty-states.md)
- [Success Messages](../messages/success-messages.md)
- [Confirmation Dialogs](confirmation-dialogs.md)
- [Agentic AI Experiences](../ai-content/agentic-experiences.md)
