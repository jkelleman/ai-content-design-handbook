# Success Message Template

Use this template to confirm actions and celebrate user success with clear, concise messaging.

## Template Structure

```
[Confirmation of what succeeded]

[Next step or related action - optional]
```

## Success Message Framework

### 1. Identify the Success Type

- **Completion** - Task or process finished
- **Creation** - New item created
- **Update** - Changes saved
- **Deletion** - Item removed
- **Upload** - File successfully uploaded
- **Send** - Message or data sent

### 2. Write the Success Message

**Success Title:**
- Confirm what was accomplished
- Use active, specific verbs
- Keep to 5-8 words

**Success Body (optional):**
- Provide relevant next steps
- Surface related actions
- Keep brief - don't interrupt flow

### 3. Success Message Checklist

- [ ] Confirms specific action taken
- [ ] Uses active voice
- [ ] Feels encouraging without being excessive
- [ ] Provides next step if relevant
- [ ] Doesn't block user unnecessarily

## Examples

### Item Created
```
❌ BAD:
Success!

✅ GOOD:
**Pipeline created**
Your data pipeline is ready to run.
```

### Changes Saved
```
❌ BAD:
Your changes have been saved successfully to the database.

✅ GOOD:
**Changes saved**
```

### File Uploaded
```
❌ BAD:
File upload complete

✅ GOOD:
**3 files uploaded**
Ready to transform your data.
```

### Message Sent
```
❌ BAD:
Your message was sent successfully!

✅ GOOD:
**Message sent**
```

## Tone Guidance

**Do:**
- Be specific about what succeeded
- Keep it brief
- Use positive, active language
- Provide clear next steps when helpful

**Don't:**
- Overuse exclamation marks
- Be overly enthusiastic ("Yay! Success!")
- Block workflow with unnecessary confirmations
- Repeat information the user already knows

## Success Message Patterns

### Inline Success
Shows within the page flow, minimal disruption:
```
✓ Workspace created
```

### Toast/Snackbar
Brief notification that auto-dismisses:
```
**Dataset published**
View in workspace →
```

### Modal Success
For critical confirmations that warrant full attention:
```
**Payment processed**
Your subscription is now active. Receipt sent to email@example.com.
```

## When to Show Success Messages

**Always show for:**
- Destructive actions (deletion, archiving)
- Long-running processes (uploads, imports)
- Background operations user may have forgotten
- Critical state changes (published, deployed)

**Consider skipping for:**
- Auto-save functionality
- Simple navigation
- Expected, immediate feedback (button click → form submit)
- Frequent repeated actions

## Related Templates

- [Error Messages](error-messages.md)
- [Empty States](../flows/empty-states.md)
- [Onboarding Flows](../flows/onboarding.md)
