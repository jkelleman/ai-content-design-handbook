# Error Message Template

Write error messages that tell people what happened, why it matters to them, and what to do next, including errors from AI features, which fail in ways traditional software doesn't.

## The template

```
[Title: what failed, in 3–8 words]        ← optional for inline errors
[What happened and why, if the cause helps the person act]
[What to do next]
[Action button: specific verb]   [Secondary: cancel, dismiss, or get help]
```

Every complete error message answers three questions. Microsoft, Adobe, and Atlassian all structure their guidance around the same three:

| Question | Example |
|---|---|
| **What happened?** | "Your report didn't export." |
| **Why does it matter, or why did it happen?** | "The file is larger than the 25 MB limit." |
| **What can I do?** | "Remove some columns or export it as CSV." |

## Before you write: can you prevent it?

Adobe's Spectrum guidance starts here: the best error is one that never appears. Before writing a message, ask:

1. **Can the design prevent it?** Disable the Submit button until required fields are filled, use a date picker instead of free text, accept common spelling variants in search.
2. **Can the system fix it automatically?** Clamp an out-of-range number to the nearest valid value, trim trailing spaces, retry a failed network call once before telling anyone.
3. **Does the person need to know?** If a background sync fails and succeeds on retry, they don't.

Microsoft's error guidelines make the same point: if an action predictably causes an error, change the design so it can't.

## Step 1: Identify the error type

| Type | What happened | Who can fix it | Example |
|---|---|---|---|
| **Input** | Information is missing or in the wrong format | The person, right now | Postal code has letters in it |
| **Permission** | The person isn't allowed to do this | Someone else, usually an admin or owner | Editing a file shared as view-only |
| **Connection** | A network or service is unavailable | Often no one, so wait and retry | API timeout |
| **System** | Something broke on our side | Us | Database unavailable |
| **Limit** | A quota, size, or rate limit was hit | The person, by changing the request or plan | Upload exceeds 25 MB |
| **Conflict** | The data changed underneath the person | The person, by choosing a version | Someone else edited the record |
| **AI: system limitation** | The model can't produce an answer, or the right one | The person, by rephrasing or giving more context | Asking a data assistant about a table it can't see |
| **AI: context error** | The AI guessed wrong about what the person wanted | The person, by correcting or dismissing | An auto-generated summary focused on the wrong section |
| **AI: low confidence** | The AI has an answer but isn't sure | The person, by verifying | A citation that only partly supports the claim |

The three AI types come from Google's [People + AI Guidebook](https://pair.withgoogle.com/chapter/People%20+%20AI%20Guidebook%20-%20Errors%20+%20Graceful%20Failure.pdf), which points out that AI errors are often the system "working as intended" while still failing the person.

## Step 2: Choose where the message appears

Write the message first, then choose the component. Adobe's guidance warns against squeezing a complex error into a toast or blowing a minor one up into a dialog.

| Component | Use for | Length | Example |
|---|---|---|---|
| **Inline (field-level)** | Input errors in forms | One short sentence | "Enter a date after today." |
| **Inline alert** | A summary of several field errors | One sentence plus a list | "Fix 2 fields to continue." |
| **Banner** | Page-level or connection issues not tied to one action | 1–2 sentences | "You're offline. Changes will sync when you reconnect." |
| **Toast** | Brief, non-blocking failures from an action | Under 10 words, plus one action | "Couldn't copy link. Try again" |
| **Dialog** | Blocking, high-stakes errors that need a decision | Title + 1–2 sentences + buttons | Payment failed before a subscription renews |
| **Full-page / empty state** | The whole view can't load | Title + sentence + action | "This dashboard couldn't load" |
| **In the AI response** | AI limitations and low confidence | Part of the answer itself | "I can only see tables in this workspace." |

## Step 3: Write it

### Titles

- Say what failed: "Report didn't export," "Can't connect to the server."
- Keep titles to about 3–8 words. Atlassian suggests 3–4 and says titles shouldn't tell people what to do; that's the body's job.
- Use sentence case.
- Don't put "Error" in the title. Microsoft's guidelines say the title bar should show only the product or feature name.
- Don't use codes in titles. If a code helps support staff, put it at the end of the body or in a Details section.

### Body

- **Lead with the most likely cause or the simplest fix.** Atlassian: offer a backup option, such as contacting support, in the second sentence.
- **Be specific to the cause.** Write a different message for each known cause. Use a generic message only when the cause is unknown, and say so honestly.
- **State the requirement, not the violation.** Google's technical writing course: "Enter a valid postal code" helps more than "Invalid postal code."
- **Keep it to one or two sentences.** Link to help for multi-step fixes.

### Buttons

- Name the action: **Retry**, **Choose another file**, **Request access**. Avoid **OK** when there's something to do.
- Include a way out: **Cancel**, **Close**, or **Go back**.
- Keep labels to one or two words, three at most.

## Examples by type

### Input error

```
❌ Invalid input
❌ You entered an invalid email address.

✅ Enter an email address in the format name@example.com.
```
*Why:* Apple's HIG says to show field errors next to the field and instruct rather than scold. "Use only letters for your name" beats "Don't use numbers or symbols."

### Permission error

```
❌ Access denied

✅ You can view this file but not edit it
   Ask the owner, Priya Shah, for edit access.
   [Request access]   [Close]
```
*Why:* It names who can fix it and gives a one-click way to ask.

### Connection error

```
❌ Connection timeout (ERR_NETWORK_408)

✅ Can't reach the server
   Check your internet connection. If you're connected, the service may be down. Try again in a few minutes.
   [Retry]
```

### System error, cause unknown

```
❌ Oops! Something went wrong 😬

✅ This page didn't load
   Refresh the page. If it keeps happening, contact support and mention code 5F3A.
   [Refresh]   [Contact support]
```
*Why:* Apple and Google both advise against "oops" and humor in errors. Frustrated people don't find it funny, and jokes don't translate.

### Limit error

```
❌ File too large.

✅ This file is 40 MB. The limit is 25 MB.
   Compress the file or split it into smaller parts.
   [Choose another file]
```
*Why:* Microsoft's guidelines say to avoid vague words like "bad" or "too large" and state the actual criteria.

### Conflict error

```
✅ Someone else changed this record
   Jordan Lee saved changes at 2:14 PM. Review their changes or keep yours.
   [Review changes]   [Keep mine]
```

### Data loss (the one time to apologize)

```
✅ Your last 10 minutes of changes couldn't be saved
   We're sorry. A server problem interrupted saving. Your earlier version from 2:05 PM is safe.
   [Restore 2:05 PM version]   [Contact support]
```
*Why:* Adobe and Atlassian both reserve apologies for serious, irreversible problems. Apologizing for routine errors makes them sound worse than they are.

## AI error examples

AI features need error content for failures that have no equivalent in deterministic software.

### System limitation: say what the AI can't do and what it needs

```
❌ I'm sorry, I can't help with that.

✅ I can only answer questions about data in this workspace, and I don't see a table about refunds here.
   Try asking about orders or payments, or add a refunds table to the workspace.
```
*Why:* Google PAIR says AI error messages should explain specifically what the system can't do and what input would work, and use the moment to explain how the AI works.

### Low confidence: show uncertainty, don't hide it

```
❌ Revenue grew 12% last quarter.

✅ Revenue appears to have grown about 12% last quarter, but two months of data are missing from the source table, so this may change.
   [View the query]   [See which months are missing]
```
*Why:* Microsoft's Copilot transparency documentation describes reminding people that AI content may contain errors and citing sources so people can verify.

### Context error: make correction and dismissal easy

```
✅ Summary based on the "Q3 Results" section.
   Not what you needed? [Summarize the whole document]   [Dismiss]
```
*Why:* Microsoft's Guidelines for Human-AI Interaction G8 and G9: support efficient dismissal and efficient correction.

### Refused request: be brief and offer an alternative

```
❌ As an AI language model, I cannot comply with that request because it violates our content policy.

✅ I can't write that, but I can help you draft a respectful message that makes the same point.
```
*Why:* A clear refusal with an alternative keeps the person moving. See [Content Safety](../../resources/ethical-ai/content-safety.md) for refusal patterns.

### Agent action failed partway

```
✅ 3 of 5 files were renamed
   2 files are locked by another user: budget.xlsx and forecast.xlsx. Nothing else changed.
   [Retry locked files]   [View details]
```
*Why:* When an agent acts on someone's behalf, say exactly what changed and what didn't. See [Agentic AI Experiences](../ai-content/agentic-experiences.md).

## Tone

Match tone to severity. Adobe's three tones are a useful scale:

| Severity | Tone | Sounds like |
|---|---|---|
| Low (a typo in a field) | **Instructive**: state the fix briefly | "Enter a date after today." |
| Medium (a failed upload) | **Reassuring**: signal that it's fixable | "Your file didn't upload. Your other files are fine. Try this one again." |
| High (data loss, payment failure) | **Supportive**: acknowledge impact, guide step by step | "Your payment didn't go through, so your plan will pause on May 3. Update your card to keep your projects active." |

Atlassian adds that tone should follow the person's state: practical and direct when they're stressed or blocked, with no jokes.

### Words to avoid

| Avoid | Why | Instead |
|---|---|---|
| "Error," "failure," "fatal" | Alarming and vague | Say what didn't work |
| "Invalid," "illegal" | Sounds like blame | State the requirement |
| "You failed to…," "You must…" | Blames the person | "Enter…," "Choose…" |
| "Oops," "Uh-oh," "Whoops" | Insincere when someone is frustrated | Plain statement |
| "Please" | Can make a required step sound optional (Microsoft) | Just give the instruction |
| "Sorry" for routine errors | Makes small problems sound serious | Save it for data loss or other serious harm |
| "Something went wrong" alone | Gives no path forward | Add a next step and a way to get help |
| "The system thinks…" | Anthropomorphizes software (Microsoft) | Describe what happened |

### "We" or no "we"?

Companies disagree. Apple avoids "we" because it's unclear who that is ("Unable to load content," not "We're having trouble loading this content"). Atlassian and Adobe use "we" for the system and "you" for the person, to make clear who needs to act. Either works. Pick one, write it into your [voice and tone framework](../../style-guides/voice-and-tone-framework.md), and use it everywhere.

## Writing for different audiences

When end users, admins, and developers see the same failure, Microsoft recommends writing separate text for each:

| Audience | Message |
|---|---|
| End user | "You can't share files outside your organization. Ask your admin if you need to." |
| Admin | "External sharing is turned off for this tenant. Turn it on in Admin center > Sharing." |
| Developer (API) | `403 EXTERNAL_SHARING_DISABLED: Tenant policy blocks sharing with external domains.` |

## Accessibility

- Don't rely on color alone; pair red with an icon and text.
- Connect field errors to their inputs (`aria-describedby`) so screen readers announce them.
- Move focus to the error summary when a form fails to submit.
- Write link text that makes sense alone ("Learn about file limits," not "Learn more").
- Keep errors visible until they're fixed; don't auto-dismiss them.

See [Accessibility Guidelines](../../resources/accessibility-guidelines.md).

## Checklist

- [ ] Could the design prevent this, or the system fix it automatically?
- [ ] Says what happened in plain language
- [ ] Explains why, if that helps the person act
- [ ] Gives a specific next step
- [ ] Doesn't blame the person
- [ ] No jargon, error codes, or "error" in the title
- [ ] No "oops," humor, or routine apologies
- [ ] Button names the action, and there's a way out
- [ ] Shown in the right component for its severity
- [ ] Specific to the cause, not generic
- [ ] For AI errors: says what the AI can't do and what would work instead
- [ ] Accessible: not color-only, announced to screen readers, persistent

## How leading companies do it

| Company | What they teach |
|---|---|
| **Microsoft** | What happened, the result for the person, and what to do. A specific message per cause; never blame the user; avoid "please" and "bad." ([Guidelines](https://learn.microsoft.com/en-us/windows/win32/debug/error-message-guidelines)) |
| **Google** | Be instructive, skip apologies and humor, describe what happened instead of what the user did. For AI, name the error type and offer a path forward. ([Tech writing](https://developers.google.com/tech-writing/error-messages/set-tone), [PAIR](https://pair.withgoogle.com/chapter/People%20+%20AI%20Guidebook%20-%20Errors%20+%20Graceful%20Failure.pdf)) |
| **Apple** | Show errors next to the problem, say how to fix it, avoid "oops." If wording can't fix a common error, rethink the interaction. ([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing)) |
| **Adobe** | Prevent first, auto-fix second, write the message before choosing the component, and scale tone with severity. ([Spectrum](https://spectrum.adobe.com/page/writing-for-errors)) |
| **Atlassian** | Cause, action, and consequence in one or two sentences; specific buttons; save "sorry" for severe, irreversible problems. ([Error messages](https://atlassian.design/foundations/content/designing-messages/error-messages)) |
| **Shopify** | Errors take a more direct tone than tips and onboarding; plain language for a global audience. ([App content](https://shopify.dev/apps/design-guidelines/content)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related templates

- [Empty States](empty-states.md)
- [Success Messages](success-messages.md)
- [Confirmation Dialogs](../flows/confirmation-dialogs.md)
- [Microcopy](microcopy.md)
- [Conversation Flows](../conversational/conversation-flows.md)
