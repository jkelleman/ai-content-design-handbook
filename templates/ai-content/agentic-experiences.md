# Agentic AI Experiences

Content patterns for AI that takes actions on someone's behalf: sending messages, editing files, booking meetings, running queries, changing settings. When AI only answers, a bad answer costs a moment. When it acts, a bad action can be sent, deleted, or paid for. The content around agent actions is what keeps people in control.

## What's different about agents

| Chat assistant | Agent |
|---|---|
| Produces words the person reads | Produces actions with real consequences |
| The person decides what to do with the output | The person delegates the decision |
| Errors are visible in the answer | Errors can happen out of sight, several steps in |
| One turn at a time | Multi-step plans that run for seconds or hours |
| "Is this answer right?" | "What did it do, with what, and can I undo it?" |

## The four content moments

Every agent action passes through up to four moments, and each needs its own content.

```
1. PLAN      →   2. APPROVE    →   3. PROGRESS    →   4. RECEIPT
"Here's what      "Send 48           "Sending… 31        "Sent 48 emails.
 I'll do"          emails?"           of 48 sent"         2 bounced. [Undo]"
```

### 1. Plan: say what will happen before it happens

For multi-step work, show the plan in plain language before starting, so people can catch a misunderstanding early.

```
✅ Here's my plan:
   1. Find invoices more than 30 days overdue (read only)
   2. Draft a reminder for each customer
   3. Send the reminders from dana@acme.com. I'll ask before this step.
   [Start]   [Edit plan]
```

Mark which steps only read and which change something. People relax about the first kind and focus on the second.

### 2. Approve: ask before consequential actions

Scale the friction to the risk. Not every action needs a dialog; some need more than one.

| Risk level | Examples | Pattern |
|---|---|---|
| **Read-only** | Search, summarize, analyze | Act without asking |
| **Reversible, private** | Draft a doc, add a tentative calendar hold | Act, then show a receipt with Undo |
| **Visible to others** | Send a message, post, invite, share | Ask once, showing exact details |
| **Irreversible or high impact** | Delete data, move money, change permissions, sign | Ask every time, show scope, consider type-to-confirm |

An approval must say **what** will happen, **with which details**, **from whose account**, **whether it can be undone**, and **why** the agent chose this. See [Confirmation Dialogs](../flows/confirmation-dialogs.md#approving-ai-agent-actions) for examples.

```
❌ Allow the agent to call update_permissions?
   [Allow]  [Deny]

✅ Give the Contractors group edit access to "Q3 Budget"?
   7 people would be able to change figures and share the file.
   I'm suggesting this because you asked to let the agency update the forecast.
   You can remove access later in Share settings.
   [Cancel]   [Give edit access]
```

### 3. Progress: show what's happening and let people stop it

- Say what step it's on, in human terms: "Checking 48 invoices," not "Calling tool 3 of 7."
- Show counts for batch work: "31 of 48 sent."
- Always offer **Stop**, and say what stopping does: "Stopping now leaves 17 reminders unsent. Sent reminders can't be recalled."
- For long work, let people leave: "This takes about 10 minutes. I'll notify you when it's done."

### 4. Receipt: report exactly what changed

The receipt is the most important agent content. Write it like a transaction record.

```
✅ Sent 46 of 48 reminders
   From dana@acme.com · Subject: "Your invoice is past due"
   2 bounced: billing@oldco.com, ap@northwind.io
   Nothing else changed. Drafts are saved in "Agent drafts."
   [View sent]   [Fix bounced addresses]
```

A good receipt:

- Leads with the outcome, including partial success ("46 of 48")
- Names the identity used ("from dana@acme.com")
- Lists failures specifically
- Says what *didn't* change ("Nothing else changed")
- Offers undo or a fix when possible

## Failure and recovery

Agents fail partway through. The worst content outcome is a vague error that leaves people unsure what state things are in.

```
❌ The task failed. Please try again.

✅ Stopped after step 2 of 3
   I drafted 48 reminders but didn't send any, because your email connection expired.
   [Reconnect email and send]   [Review drafts]
```

Rules for agent failures:

1. **Say what state things are in now.** Which steps finished, which didn't, and what was left half-done.
2. **Never leave people guessing whether an action happened.** If you can't tell whether an email was sent, say so and help them check.
3. **Offer the fix in one step** where possible: "Reconnect and continue."
4. **Don't retry consequential actions silently.** A retried payment or message can happen twice.

## Identity and voice

- **Use "I" for the agent consistently** if your product gives the agent a voice, and keep "you" for the person. Don't mix "we," "I," and "the assistant."
- **Make delegated identity visible.** Messages sent by an agent go out under someone's name. Tell the person, and consider telling recipients: "Sent by Dana's assistant."
- **Don't overstate autonomy or understanding.** "I'll handle it" promises more than "I'll draft replies for you to review."

## Transparency

- Mark agent-created content with your product's AI label until a person edits it. IBM's Carbon design system removes the AI marking when someone edits AI content and offers a revert control.
- Keep a history people can review: what the agent did, when, and why.
- In the EU, AI Act Article 50 requires telling people when they're interacting with an AI system, at the latest at their first interaction, unless it's obvious from context. See [Transparency Guidelines](../../resources/ethical-ai/transparency-guidelines.md).

## Checklist

- [ ] Multi-step work shows a plan first, marking read-only and changing steps
- [ ] Approval friction matches risk; read-only actions don't ask
- [ ] Approvals show what, which details, whose account, reversibility, and why
- [ ] Progress uses human terms and counts, and Stop is always available
- [ ] Stop explains what stopping leaves done and undone
- [ ] Receipts state the outcome, identity used, failures, what didn't change, and undo
- [ ] Failures say exactly what state things are in
- [ ] Consequential actions are never retried silently
- [ ] Agent-created content is labeled, and there's a reviewable history

## How leading companies do it

| Company | What they teach |
|---|---|
| **Microsoft** | Take extra care with agentic AI whose actions are irreversible; make sure affected people can understand and appeal consequential decisions. Convey the consequences of user actions (G16) and make clear why the system did what it did (G11). ([Copilot transparency note](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-transparency-note), [Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/)) |
| **Salesforce** | Keep humans in control of AI decisions; mask sensitive data before it reaches the model and check output before people see it. ([Trusted AI](https://salesforce.com/uk/artificial-intelligence/trusted-ai/)) |
| **Google** | When AI fails, return control to people smoothly, with the context they need to continue, and make failure safe and uneventful. ([PAIR: Errors + Graceful Failure](https://pair.withgoogle.com/chapter/People%20+%20AI%20Guidebook%20-%20Errors%20+%20Graceful%20Failure.pdf)) |
| **IBM** | Label AI-created content consistently; when a person overrides it, remove the AI styling and offer a revert. ([AI label](https://carbondesignsystem.com/components/ai-label/usage/)) |
| **Amazon** | Document what each AI service is for, its limitations, and how it was designed and tested, in a consistent format. ([AI Service Cards](https://aws.amazon.com/blogs/machine-learning/introducing-aws-ai-service-cards-a-new-resource-to-enhance-transparency-and-advance-responsible-ai)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related templates

- [Confirmation Dialogs](../flows/confirmation-dialogs.md)
- [Success Messages](../messages/success-messages.md)
- [Error Messages](../messages/error-messages.md)
- [Prompt Design](prompt-design.md)
- [Transparency Guidelines](../../resources/ethical-ai/transparency-guidelines.md)
