# Onboarding Flow Template

Use this template to design effective onboarding experiences that help users get started quickly.

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

## Measuring Onboarding Success

**Key metrics:**
- Completion rate
- Time to first value
- Activation rate
- Drop-off points
- Feature adoption post-onboarding

## Related Templates

- [Empty States](../messages/empty-states.md)
- [Success Messages](../messages/success-messages.md)
- [Confirmation Dialogs](confirmation-dialogs.md)
