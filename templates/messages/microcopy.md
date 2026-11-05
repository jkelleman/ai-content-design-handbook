# Microcopy Template

Use this template to write the small but mighty words that guide users through your product.

## What is Microcopy?

Microcopy includes:
- Button labels
- Link text
- Input placeholders
- Tooltips
- Helper text
- Labels
- Navigation items

## Microcopy Principles

**1. Be specific, not generic**
❌ Submit | ✅ Create pipeline

**2. Use active verbs**
❌ Deletion | ✅ Delete

**3. Match user mental models**
❌ Terminate | ✅ Stop

**4. Keep it concise**
❌ Click here to save your changes | ✅ Save changes

**5. Front-load important words**
❌ Learn more about pipelines | ✅ Pipeline documentation

## Button Labels

### Primary Actions
```
✅ GOOD:
- Create pipeline
- Send invite
- Publish report
- Save changes
- Start trial
- Upload file

❌ BAD:
- Submit
- OK
- Go
- Click here
- Continue
```

### Secondary Actions
```
✅ GOOD:
- Cancel
- Go back
- Skip for now
- Learn more
- Not now

❌ BAD:
- No
- Exit
- Dismiss
```

### Destructive Actions
```
✅ GOOD:
- Delete pipeline
- Remove user
- Discard changes
- Archive workspace

❌ BAD:
- Yes, delete
- Are you sure? OK
- Confirm
```

## Link Text

### Action Links
Front-load the action, make destination clear

```
✅ GOOD:
- View all pipelines
- Edit connection settings
- Download as CSV
- Read documentation

❌ BAD:
- Click here
- Learn more
- See all
- Read more
```

### Navigational Links
Match user expectations, use consistent language

```
✅ GOOD:
- Back to workspace
- Return to dashboard
- Go to settings

❌ BAD:
- Go back
- Previous
- Navigate
```

## Input Fields

### Labels
Clear, specific, no trailing colons

```
✅ GOOD:
- Email address
- Pipeline name
- Connection string
- Workspace description

❌ BAD:
- Email:
- Name:
- Enter your...
```

### Placeholders
Show format or provide example

```
✅ GOOD:
- name@example.com
- My Sales Pipeline
- Server=myserver;Database=mydb
- Describe what this workspace is for

❌ BAD:
- Enter email
- Type here
- ...
```

### Helper Text
Provide context or requirements

```
✅ GOOD:
- Passwords must be at least 8 characters
- You'll use this name to identify your pipeline later
- Choose a unique name that describes your data source

❌ BAD:
- Required field
- See help for more information
```

## Tooltips

### Informational Tooltips
Clarify meaning, provide context

```
✅ GOOD:
- Incremental refresh: Only sync data that changed since the last run
- Batch size: Number of rows processed at once. Higher numbers = faster but more memory
- TTL: How long cached data remains valid before refreshing

❌ BAD:
- More info
- See documentation
- Help
```

### Action Tooltips (for icon buttons)
Describe what happens when clicked

```
✅ GOOD:
- Refresh data
- Edit pipeline
- Delete connection
- Copy to clipboard

❌ BAD:
- Refresh
- Edit
- More
```

## Navigation Items

Keep short, front-load key words, use parallel structure

```
✅ GOOD:
- Pipelines
- Data sources
- Settings
- Activity log

❌ BAD:
- View all pipelines
- Manage your data sources
- Configuration and settings
- See activity
```

## Status Messages

### Loading States
```
✅ GOOD:
- Loading pipelines...
- Connecting to database...
- Uploading file... (45%)

❌ BAD:
- Please wait...
- Loading...
- Processing...
```

### Inline Validation
```
✅ GOOD:
- ✓ Available
- ✗ Name already taken
- ✓ Valid email format

❌ BAD:
- OK
- Error
- Invalid
```

## Checkbox and Radio Button Labels

Be direct, describe the choice clearly

```
✅ GOOD:
☐ Send me email notifications
☐ Make this workspace private
○ Run once
○ Run on schedule
○ Run manually

❌ BAD:
☐ Notifications
☐ Private
○ Option 1
○ Option 2
```

## Empty State Links

Provide clear next action

```
✅ GOOD:
- Create your first pipeline
- Add a data source
- Import sample data

❌ BAD:
- Get started
- Click here
- Begin
```

## Microcopy by Context

### Forms
- Label: "Workspace name"
- Placeholder: "e.g., Q4 Sales Analytics"
- Helper: "Use a descriptive name that your team will recognize"
- Error: "Workspace name is required"

### Tables
- Column header: "Last run"
- Empty state: "No pipelines yet"
- Action: "Create pipeline"

### Cards
- Title: "Sales Pipeline"
- Subtitle: "Last run 2 hours ago"
- Action: "View details"

### Settings
- Section: "Email notifications"
- Toggle: "Send daily summary"
- Description: "Get a daily email with pipeline status and errors"

## Microcopy for AI features

AI features add a new set of small strings that need the same care as buttons and labels.

| Element | Guidance | Example |
|---|---|---|
| **AI label** | Mark AI-generated content consistently, and make the label open an explanation | `AI` label → "Summary generated from 12 comments. [How this works]" |
| **Prompt box placeholder** | Suggest a task, not a personality | "Ask about orders, revenue, or customers" (not "Ask me anything!") |
| **Example prompts** | 2–3 that reliably work well | "Which region grew fastest last quarter?" |
| **Regenerate** | Its own button, separate from the AI label | [Regenerate] |
| **Feedback** | Ask about the specific output | 👍 / 👎 "Was this summary accurate?" |
| **Disclaimers** | Short, placed at the output, specific to the risk | "Check figures before sharing. AI can make mistakes." |
| **Stop / cancel** | Always available while generating | [Stop generating] |
| **Citations** | Point to the source, not the model | "From Q3-report.pdf, page 4" |

IBM's Carbon design system says the AI label shouldn't double as an action button. Regenerate and similar actions get their own controls, so the label stays a reliable signal.

## Settings descriptions

Apple's HIG gives a useful rule: describe what a setting does **when it's on**, and people will infer the opposite. Its example is the Apple Watch Handwashing Timer, whose description explains that the watch can start a 20-second timer when it detects handwashing, with no need to explain what happens when it's off.

```
❌ Enable or disable AI suggestions in this workspace.
✅ Suggest replies based on the conversation. Suggestions are only visible to you.
```

## Tone Guidance

**Be conversational:**
- "Let's get started" not "Commence initialization"
- "Choose a data source" not "Select data origin"

**Be helpful:**
- "Need help? Contact support" not "For assistance, navigate to support portal"
- "Try these keywords: sales, report, Q4" not "Revise search parameters"

**Be confident:**
- "Create pipeline" not "Try creating a pipeline"
- "Delete workspace" not "Do you want to delete?"

## Common Microcopy Mistakes

❌ **Using "Click here"**
Links should describe destination, not action

❌ **Trailing colons on labels**
Modern forms don't need them

❌ **Vague button labels**
"Submit", "OK", "Continue" don't describe action

❌ **Long placeholder text**
Keep placeholders short and example-based

❌ **Redundant text**
"Enter your email address" label + "Enter email" placeholder

❌ **ALL CAPS**
Use title case or sentence case

❌ **Exclamation marks everywhere!!**
Use sparingly, only for genuine celebration

## Microcopy Checklist

- [ ] Specific and action-oriented
- [ ] Front-loads important words
- [ ] Uses user's vocabulary (not technical jargon)
- [ ] Concise (removes unnecessary words)
- [ ] Grammatically consistent across similar elements
- [ ] Accessible (works with screen readers)
- [ ] Culturally appropriate and inclusive

## How leading companies do it

| Company | What they teach |
|---|---|
| **Apple** | Use verbs for buttons; plain "Send" beats cute "Let's do it!"; avoid "Click here"; use possessives like "your" sparingly; say "tap," not "click," on touch devices. ([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing)) |
| **Shopify** | Calls to action open with a strong verb ("Create template"); pick one term per concept and never alternate between synonyms like "Upload image" and "Add photos." ([App content](https://shopify.dev/apps/design-guidelines/content)) |
| **Google** | Refer to controls by their label text, address people as "you," and don't mix "my" and "your" in one phrase. ([Material communication](https://codelabs.developers.google.com/codelabs/material-communication-guidance)) |
| **Atlassian** | Keep calls to action to one or two words and make them specific. ([Error messages](https://atlassian.design/foundations/content/designing-messages/error-messages)) |
| **IBM** | Keep the AI label separate from actions like regenerate, and never disable it. ([AI label](https://carbondesignsystem.com/components/ai-label/usage/)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related Resources

- [Voice and Tone Guide](../../style-guides/voice-and-tone-framework.md)
- [Writing for Accessibility](../../resources/accessibility-guidelines.md)
- [Before and After Examples](../../examples/before-after-examples.md)
