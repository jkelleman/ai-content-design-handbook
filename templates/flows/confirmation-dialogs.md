# Confirmation Dialog Template

Use this template to create clear confirmation dialogs that prevent mistakes while respecting user intent.

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
- **Primary/Destructive action**: Specific verb that matches title
- **Cancel**: Always provide escape hatch
- Order: Destructive action on right (follows Windows/web patterns)

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
- Use red or warning color
- Place on right
- Use specific verb

### Non-Destructive Confirmations
```
[Cancel] [Publish]
[Cancel] [Share]
[Cancel] [Send invite]
```
- Use primary color
- Place on right
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
Type DELETE to confirm:
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
[Delete] → Expands to: "Are you sure? [Cancel] [Yes, delete]"
```

### Strategy 4: Smart Defaults
Instead of: Confirm every time
Better: Confirm only for items with dependencies or >X age

## Accessibility Considerations

- Focus management: Set focus to primary action or Cancel based on severity
- Escape key should always close and cancel
- Clear heading hierarchy for screen readers
- Sufficient color contrast on destructive buttons

## Related Templates

- [Error Messages](../messages/error-messages.md)
- [Success Messages](../messages/success-messages.md)
- [Empty States](../messages/empty-states.md)
