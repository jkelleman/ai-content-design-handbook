# Success Message Template

Confirm that something worked, say what happens next, and get out of the way. Good success messages build trust because they're specific; vague ones ("Success!") make people wonder what actually happened.

## The template

```
[What succeeded: past-tense verb + object]      e.g. "Report exported"
[What it means or what happens next: optional]  e.g. "It's in your Downloads folder."
[Next action: optional]                          e.g. [Open report]   [Undo]
```

## When to show a success message

The best confirmation is often the change itself. A new row appearing in a table, a toggle flipping, or a card moving columns already tells people it worked.

| Situation | Show a message? | Why |
|---|---|---|
| The result is visible immediately (toggle, inline edit) | **No** | The UI change is the confirmation |
| Auto-save | **No, or a quiet "Saved" status** | Interrupting every few seconds trains people to ignore messages |
| The result is off-screen (sent email, scheduled post) | **Yes** | People can't see it happened |
| Long-running or background work (export, import, deploy) | **Yes, when it finishes** | People have moved on and need to be told |
| Destructive actions (delete, archive) | **Yes, with Undo** | Reassurance plus a safety net |
| Money or legal commitments (payment, signature) | **Yes, with details and a receipt** | People need proof |
| An AI agent completed a task for someone | **Yes, with a summary of what changed** | People need to verify delegated work |

## Choose the right component

| Component | Use for | Example |
|---|---|---|
| **Inline status** | Low-stakes, in-place confirmations | `✓ Saved` next to a form |
| **Toast / snackbar** | Actions whose result is off-screen; auto-dismisses | "Message sent · Undo" |
| **Banner** | Page-level results that need to stay visible | "Your domain is verified. Email from @acme.com will now be delivered." |
| **Dialog or full page** | Major milestones and commitments | Order confirmation with order number and delivery date |
| **Notification** | Results from work that finished while the person was elsewhere | "Your export of 2,400 rows is ready." |

Material Design's guidance is that a snackbar's action should relate directly to the process that just happened, such as **Undo** after deleting or **View** after creating. Snackbars shouldn't carry actions unrelated to what the person just did.

## Writing it

**Lead with what happened, in past tense.** "Invoice sent," "3 files uploaded," "Workspace created." Put the object people care about first when you can.

**Be specific with counts and names.** "3 files uploaded" beats "Upload complete." "Invoice #1042 sent to Dana Ruiz" beats "Invoice sent" when people send many.

**Say what happens next, if it isn't obvious.** "Payment received. Your order ships within 2 business days."

**Keep it short.** Toasts should be readable in about two seconds, roughly 3–8 words plus an action.

**Hold back on enthusiasm.** Atlassian reserves its playful "wink" for moments of success, relief, or pride, and even then uses it sparingly and only where it will be understood across cultures. Apple's example of a congratulatory tone is an Apple Watch message for a personal-record Move streak: a real achievement, not a saved form.

| Moment | Appropriate tone | Example |
|---|---|---|
| Routine action | Neutral, brief | "Changes saved" |
| Completing a setup | Warm, forward-looking | "Your workspace is ready. Invite your team to get started." |
| A real milestone | Celebratory, still specific | "You published your first app. It's live at acme.app/store." |
| After recovering from an error | Reassuring | "Connection restored. Your changes are synced." |

## Examples

### Created

```
❌ Success!
✅ Pipeline created
   It runs daily at 6:00 AM. [View pipeline]
```

### Saved

```
❌ Your changes have been saved successfully to the database!
✅ Changes saved
```
"Successfully" adds nothing, and people don't know or care that there's a database.

### Sent

```
❌ Message sent successfully!!
✅ Message sent · [Undo]
```

### Deleted, with undo

```
✅ Project archived · [Undo]
```
Undo is better than "Are you sure?" for reversible actions. See [Confirmation Dialogs](../flows/confirmation-dialogs.md).

### Long-running job

```
✅ Your export is ready
   2,400 rows from "Q3 orders" · CSV, 1.2 MB
   [Download]
```

### Payment

```
✅ Payment received
   $49.00 charged to Visa ending 4242. Receipt sent to dana@example.com.
   Your Pro plan renews on June 3, 2026.
   [View receipt]
```

### Partial success

When some items worked and some didn't, say both, and never hide failures inside a success message.

```
❌ Upload complete
✅ 8 of 10 files uploaded
   2 files are over the 25 MB limit: video.mov, raw-data.zip
   [Choose smaller files]
```

## AI success messages

AI work needs more than "Done," because people need to check it.

### Generated content

```
✅ Draft created from your notes
   Review it before sending. AI-generated text can contain mistakes.
   [Edit draft]   [Regenerate]
```
Microsoft's Copilot transparency documentation describes pairing AI-generated content with a reminder that it may contain errors, and IBM's Carbon for AI marks AI-generated content with an AI label until a person edits it.

### Agent completed a task

```
✅ Meeting scheduled
   "Q3 planning" · Thursday, June 5, 2:00–2:30 PM · 4 attendees invited
   I sent invites from your calendar and added the agenda you wrote.
   [Open event]   [Undo]
```
When an agent acts for someone, the confirmation is a receipt: what it did, with which details, from whose account, and how to reverse it. See [Agentic AI Experiences](../ai-content/agentic-experiences.md).

### Bulk AI action

```
✅ 142 product descriptions rewritten
   12 were flagged for review because they mention pricing. [Review flagged]
```

## Accessibility

- Announce toasts with an ARIA live region (`role="status"`), so screen reader users hear them.
- Give people enough time: don't auto-dismiss a toast with an action in under about 6 seconds, and pause the timer on hover or focus.
- Don't use color alone; pair green with a check icon and text.
- Put important information (receipts, confirmation numbers) somewhere persistent, not only in a toast.

## Checklist

- [ ] Is a message needed, or does the UI change already confirm it?
- [ ] Past-tense verb plus the specific object
- [ ] Counts and names where they help
- [ ] Says what happens next, if that isn't obvious
- [ ] Includes Undo for reversible destructive actions
- [ ] Reports partial failures honestly
- [ ] No "successfully," and no more than one exclamation point, saved for real milestones
- [ ] AI-generated results tell people to review them
- [ ] Agent actions include a receipt of what changed
- [ ] Announced to screen readers, and persistent where it matters

## How leading companies do it

| Company | What they teach |
|---|---|
| **Atlassian** | Save playful moments for success, relief, or pride, and use them sparingly and only where they'll be understood across cultures. ([Voice and tone](https://atlassian.design/foundations/content/voice-tone)) |
| **Apple** | Match tone to the moment: celebrate real achievements, like a record Move streak, and stay direct otherwise. ([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing)) |
| **Google** | Snackbar actions should relate directly to the process that just happened. ([Material communication](https://codelabs.developers.google.com/codelabs/material-communication-guidance)) |
| **IBM** | Mark AI-generated results with the AI label until a person edits them, and offer a revert control. ([AI label](https://carbondesignsystem.com/components/ai-label/usage/)) |
| **Microsoft** | Pair AI-generated content with a reminder that it may contain errors, and cite sources so people can verify. ([Copilot transparency note](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-transparency-note)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related templates

- [Error Messages](error-messages.md)
- [Empty States](empty-states.md)
- [Confirmation Dialogs](../flows/confirmation-dialogs.md)
- [Onboarding](../flows/onboarding.md)
