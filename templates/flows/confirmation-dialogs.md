# Confirmation Dialog Template

Use confirmation dialogs to stop people before a consequential mistake, without slowing down the decisions they make every day. A confirmation that appears too often stops protecting anyone: people learn to click through it without reading.

The same pattern now covers a new case: **approving an action an AI agent wants to take**. See [Approving AI agent actions](#approving-ai-agent-actions).

## Template Structure

```
[Dialog Title: What's about to happen]

[Body: Consequences or important details]

[Destructive/Primary Action Button] [Cancel Button]
```

## Confirmation Dialog Framework

### 1. When to Use Confirmation Dialogs

**Use confirmations for:**
- Destructive actions (delete, remove, archive)
- Irreversible changes
- High-risk operations
- Actions that affect others
- Operations with significant consequences

**Don't use confirmations for:**
- Easily reversible actions
- Low-stakes decisions
- Frequent operations (creates friction)
- Actions that already have clear undo

### 2. Dialog Components

**Title (H2 or dialog heading):**
- Ask a direct question or state the action
- Use 5-8 words
- Be specific, not generic

**Body:**
- Explain the consequence
- Mention what will be affected
- Keep to 1-2 sentences
- Only include essential information

**Buttons:**
- **Primary/Destructive action**: Specific verb that matches the title ("Delete pipeline," not "OK" or "Yes")
- **Cancel**: Always provide a way out
- **Order: follow your platform.** Button order differs by platform convention, so match the system your product runs on and stay consistent. Apple's HIG and many web design systems put the primary action on the right; Windows has traditionally put the confirming button first. Consistency matters more than which side you choose.

### 3. Confirmation Dialog Checklist

- [ ] Only asks for confirmation when truly necessary
- [ ] Title clearly states what will happen
- [ ] Body explains consequences concisely
- [ ] Action button uses specific, clear verb
- [ ] Cancel button is always present
- [ ] Uses appropriate visual treatment (red for destructive)

## Examples

### Delete Confirmation
```
❌ BAD:
**Are you sure?**
This action cannot be undone.
[OK] [Cancel]

✅ GOOD:
**Delete "Sales Pipeline"?**
This pipeline and its run history will be permanently deleted.
[Cancel] [Delete pipeline]
```

### Remove User Confirmation
```
❌ BAD:
**Warning**
Do you want to proceed?
[Yes] [No]

✅ GOOD:
**Remove Sarah Chen from workspace?**
Sarah will lose access to all projects and data in this workspace.
[Cancel] [Remove user]
```

### Archive Confirmation
```
❌ BAD:
**Confirm**
Click OK to continue.
[OK] [Cancel]

✅ GOOD:
**Archive this workspace?**
Archived workspaces are read-only. You can restore it later from settings.
[Cancel] [Archive]
```

### Publish Confirmation
```
❌ BAD:
**Publish**
Are you ready to publish?
[Yes] [No]

✅ GOOD:
**Publish report to production?**
This report will be visible to all users in your organization.
[Cancel] [Publish]
```

## Button Patterns

### Destructive Actions
```
[Cancel] [Delete]
[Cancel] [Remove]
[Cancel] [Permanently delete]
```
- Use red or warning color, plus an icon or the verb itself so it doesn't rely on color
- Place it where your platform puts primary actions
- Use a specific verb

### Non-Destructive Confirmations
```
[Cancel] [Publish]
[Cancel] [Share]
[Cancel] [Send invite]
```
- Use primary color
- Place it where your platform puts primary actions
- Action verb matches consequence

### With Undo Available
```
[Cancel] [Archive]

→ Shows toast after: "Workspace archived. [Undo]"
```

## Confirmation Dialog Patterns

### Pattern 1: Simple Yes/No
**When to use:** Single, clear decision

```
**Delete this connection?**
You can recreate it later if needed.

[Cancel] [Delete]
```

---

### Pattern 2: With Additional Context
**When to use:** User needs to understand scope

```
**Delete workspace "Q4 Analytics"?**
This will permanently delete:
• 12 pipelines
• 45 GB of data
• All run history

[Cancel] [Delete workspace]
```

---

### Pattern 3: With Input Verification
**When to use:** Highly destructive, requires extra confirmation

```
**Delete production workspace?**
Type the workspace name, **prod-analytics**, to confirm:
[                    ]

This will permanently delete all data and cannot be undone.

[Cancel] [Delete workspace]
```

---

### Pattern 4: Choice Between Actions
**When to use:** Multiple valid paths forward

```
**This pipeline is still running**
○ Cancel run and delete pipeline
○ Wait for run to complete, then delete

[Back] [Continue]
```

## Tone Guidance

**Do:**
- Be direct and clear
- State consequences factually
- Use active voice
- Make severity clear through language and color

**Don't:**
- Use vague warnings ("This is permanent!")
- Be overly dramatic
- Hide important details
- Use technical jargon

## Reducing Confirmation Fatigue

### Strategy 1: Make Actions Reversible
Instead of: Delete confirmation
Better: Move to trash with undo

### Strategy 2: Provide Alternative Paths
Instead of: Confirm before every delete
Better: Bulk actions with single confirmation

### Strategy 3: Use Inline Confirmation
Instead of: Modal dialog
Better: Inline expansion with confirm button

```
[Delete] → Expands to: "Delete 3 files? [Cancel] [Delete files]"
```
Even inline, name the action and the object instead of asking "Are you sure?"

### Strategy 4: Smart Defaults
Instead of: Confirm every time
Better: Confirm only for items with dependencies or >X age

## Accessibility Considerations

- Focus management: Set focus to primary action or Cancel based on severity
- Escape key should always close and cancel
- Clear heading hierarchy for screen readers
- Sufficient color contrast on destructive buttons

## Approving AI agent actions

When an AI agent proposes an action, the confirmation becomes an **approval**. The person isn't double-checking their own decision; they're deciding whether to let software act on their behalf. That changes what the dialog needs to say.

### What an approval must include

| Element | Why | Example |
|---|---|---|
| **What the agent will do**, in plain language | People approve outcomes, not tool calls | "Send this email to 48 customers" |
| **The exact details** that will be used | Agents can misread instructions | Recipient list, subject line, send time |
| **Whose account or permissions it uses** | Actions carry the person's identity | "From dana@acme.com" |
| **Whether it can be undone** | Sets the level of care | "Emails can't be unsent." |
| **Why the agent thinks this is right** | Lets people catch a misunderstanding | "Because you asked me to notify everyone with an overdue invoice" |
| **A way to edit before approving** | Approve-or-reject is too blunt | [Edit list] |

### Example

```
❌ The agent wants to run send_email(recipients=48). Allow?
   [Allow]   [Deny]

✅ Send overdue-invoice reminders to 48 customers?
   From: dana@acme.com · Subject: "Your invoice is past due"
   I chose customers with invoices more than 30 days overdue, based on your request.
   Emails can't be unsent.
   [Review recipients]   [Cancel]   [Send 48 emails]
```

### Scale the friction to the risk

| Risk | Approval pattern |
|---|---|
| Read-only (search, summarize) | No approval needed |
| Reversible, low impact (draft a doc, add a calendar hold) | Act, then show a receipt with Undo |
| Visible to others or hard to reverse (send, post, invite) | Approve once per action, showing exact details |
| Irreversible or high impact (delete data, move money, change permissions) | Approve per action, show scope, consider type-to-confirm |

Microsoft's Microsoft 365 Copilot transparency documentation calls out extra care for agentic AI whose actions are irreversible. Microsoft's Guidelines for Human-AI Interaction also ask designers to convey the consequences of user actions (G16) and to make clear why the system did what it did (G11). See [Agentic AI Experiences](../ai-content/agentic-experiences.md) for the full pattern.

## How leading companies do it

| Company | What they teach |
|---|---|
| **Apple** | Label buttons with specific verbs; plain words like "Send" work better than clever ones. ([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing)) |
| **Google** | Make a dialog's purpose clear from its title and buttons alone, and never hide the consequences of irreversible actions. ([Material communication](https://codelabs.developers.google.com/codelabs/material-communication-guidance)) |
| **Atlassian** | Calls to action name a specific action, such as save, remove, or create, instead of "OK," and always include a way to cancel. ([Error messages](https://atlassian.design/foundations/content/designing-messages/error-messages)) |
| **Microsoft** | Yes and No buttons must answer a question; use Cancel to stop an operation and Close to dismiss. For AI agents, take extra care with irreversible actions. ([Error message guidelines](https://learn.microsoft.com/en-us/windows/win32/debug/error-message-guidelines), [Copilot transparency note](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-transparency-note)) |
| **IBM** | When people override AI output, remove the AI marking and offer a way to revert. ([AI label](https://carbondesignsystem.com/components/ai-label/usage/)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related Templates

- [Error Messages](../messages/error-messages.md)
- [Success Messages](../messages/success-messages.md)
- [Empty States](../messages/empty-states.md)
- [Agentic AI Experiences](../ai-content/agentic-experiences.md)
