# Empty State Template

An empty state is the screen people see when there's nothing to show yet. It's one of the few moments when you have someone's full attention and no competing content, so use it to explain what belongs here and how to get started.

## The template

```
[Heading: what belongs here, or why it's empty]
[1–2 sentences: what will appear and how it gets here]
[Primary action: specific verb + object]
[Secondary: sample data, a template, or a help link (optional)]
```

## Identify the type first

The right message depends entirely on *why* the space is empty. A first-time user and someone whose search found nothing need opposite things.

| Type | Why it's empty | What the person needs | Primary action |
|---|---|---|---|
| **First use** | Nothing has been created yet | To understand the value and take the first step | Create the first item, or start from a template |
| **No results** | A search or filter matched nothing | To recover quickly | Clear filters, broaden the search |
| **Cleared** | The person finished or deleted everything | Reassurance, maybe a small celebration | Often none, or create new |
| **Waiting for data** | Something is processing or hasn't run yet | To know when it'll fill and whether to act | Run now, or nothing |
| **No access** | The content exists but is hidden from them | Who to ask | Request access |
| **Load failure** | The content didn't load | Recovery | Retry (see [Error Messages](error-messages.md)) |
| **AI: nothing to suggest** | An AI feature has no output for this context | To know why and what would help | Add context, or try a prompt |

## Write it

**Heading: say what belongs here or what happened.** "No pipelines yet," "No results for 'sales report,'" "You're all caught up." Use the same capitalization style as other headings in your product. Apple's HIG says to pick a style per element type and apply it everywhere.

**Body: explain what will appear and how.** One or two sentences. "Pipelines move and transform data between sources. Create one to schedule your first refresh."

**Action: name what it creates.** "Create pipeline" beats "Get started." Apple's HIG says empty states should give a clear next step, ideally with a button or link that does it.

**Don't put anything crucial here.** Apple notes that empty states are temporary. Once content arrives, the guidance disappears, so don't hide setup steps or warnings in it.

## Examples by type

### First use

```
❌ Nothing here yet
   Click the button below to get started.

✅ No pipelines yet
   Pipelines move and transform data between your sources on a schedule.
   [Create pipeline]   [Start from a template]
```
*Why:* It explains what a pipeline is, for someone who may not know, and offers a template for people who don't want to start from scratch.

### First use, with sample data

```
✅ Your dashboard will show sales by region
   Connect a data source to see your numbers, or explore with sample data first.
   [Connect data]   [Use sample data]
```
Sample data lets people see the value before doing setup work. It's especially useful for analytics and AI features, where an empty canvas tells people nothing.

### No results

```
❌ No results found

✅ No results for "sales reprot"
   Check the spelling or try a broader term. Showing 3 filters: Region, Owner, Last 30 days.
   [Clear filters]
```
*Why:* It repeats the query so people spot typos, and shows which filters are narrowing results. Better still, Adobe's Spectrum guidance suggests accepting common spelling variants in search, so this state appears less often.

### Cleared, a moment of completion

```
✅ You're all caught up
   New notifications will appear here.
```
This is one of the few places a light touch fits. Atlassian reserves its playful "wink" for moments of success and relief.

### Waiting for data

```
❌ Loading…   (shown for 10 minutes)

✅ Your first sync is running
   This usually takes 5–10 minutes for a workspace this size. We'll email you when it's done.
```
*Why:* It sets an expectation and lets people leave. A spinner with no end is not an empty state; it's a worry.

### No access

```
✅ This folder is restricted
   Only members of the Finance team can see its reports. Ask Priya Shah, the folder owner, for access.
   [Request access]
```

### AI feature with nothing to suggest

```
❌ No suggestions available.

✅ No suggestions for this document yet
   Suggestions appear once a document has at least a few paragraphs. You can also ask a question directly.
   [Ask a question]
```
*Why:* Google's People + AI Guidebook treats this as a "system limitation" and recommends explaining what the AI needs instead of going silent.

### AI chat, first open

```
✅ Ask about your sales data
   I can answer questions about orders, revenue, and customers in this workspace, and show the query I used.
   Try: "Which region grew fastest last quarter?"
   [Example prompt 1]  [Example prompt 2]  [Example prompt 3]
```
*Why:* An empty chat box is the hardest empty state there is. Microsoft's Guidelines for Human-AI Interaction start with G1, make clear what the system can do, and G2, make clear how well it can do it. Example prompts do both.

## Levels of detail

| Context | Approach | Example |
|---|---|---|
| Experienced users, simple feature | **Minimal**: heading and action | "No connections · [Add connection]" |
| New users or complex features | **Educational**: what it is, why it's useful, how to start | Heading, two sentences, action, tutorial link |
| Filtered or searched views | **Recovery**: show what's narrowing results | "No pipelines match 3 filters · [Clear filters]" |

## Visuals

- Use an illustration only if it explains something: an example of what will appear works better than a generic empty box.
- Keep illustrations decorative to screen readers (`alt=""`) unless they carry meaning.
- Don't let the illustration push the action below the fold on small screens.

## Tone

| Type | Tone |
|---|---|
| First use | Welcoming, educational, confident about the value |
| No results | Practical and fast; don't make people read |
| Cleared | Calm; a light touch is fine |
| Waiting | Reassuring, with a time estimate |
| No access | Neutral and specific about who can help |
| AI, nothing to suggest | Honest about the limitation, then helpful |

## Checklist

- [ ] Identified why it's empty, and wrote for that reason
- [ ] Heading says what belongs here or what happened
- [ ] Body explains what will appear and how
- [ ] Action names what it creates, not "Get started"
- [ ] Offers a template or sample data where setup is heavy
- [ ] No crucial information that disappears once content arrives
- [ ] Search states repeat the query and show active filters
- [ ] Waiting states give a time estimate
- [ ] AI empty states say what the AI can do and offer example prompts

## How leading companies do it

| Company | What they teach |
|---|---|
| **Apple** | Give clear next steps on any blank screen, with a button where possible; remember empty states are temporary, so don't put crucial information there. ([HIG: Writing](https://developer.apple.com/design/human-interface-guidelines/writing)) |
| **Microsoft** | For AI features, make clear what the system can do and how well (G1, G2) from the first screen. ([Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/)) |
| **Google** | When AI has nothing to offer, treat it as a system limitation: say what the AI needs and offer a path forward. ([PAIR](https://pair.withgoogle.com/chapter/People%20+%20AI%20Guidebook%20-%20Errors%20+%20Graceful%20Failure.pdf)) |
| **Adobe** | Prevent no-results states by accepting common spelling variants in search. ([Spectrum](https://spectrum.adobe.com/page/writing-for-errors)) |
| **Atlassian** | Save playful tone for moments of success and relief, like clearing a queue. ([Voice and tone](https://atlassian.design/foundations/content/voice-tone)) |

More detail: [How Leading Companies Design Content for AI](../../resources/industry-examples.md)

## Related templates

- [Error Messages](error-messages.md)
- [Onboarding](../flows/onboarding.md)
- [Success Messages](success-messages.md)
- [Microcopy](microcopy.md)
