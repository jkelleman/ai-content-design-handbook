# Empty State Template

Use this template to guide users when a page or section has no content yet.

## Template Structure

```
[Heading: What this space is for]

[1-2 sentences: Why it's empty + what content will appear here]

[Primary action button]
[Secondary action or link - optional]
```

## Empty State Framework

### 1. Identify the Empty State Type

- **First-time use** - User hasn't created anything yet
- **No results** - Search or filter returned nothing
- **Cleared content** - User deleted or archived all items
- **No permissions** - User can't view content
- **No data yet** - Waiting for data to populate
- **Error state** - Content failed to load

### 2. Write the Empty State

**Heading:**
- Describe what belongs here
- Keep to 5-8 words
- Use title case
- Be clear and specific

**Body:**
- Explain why it's empty (if not obvious)
- Describe what will appear here
- Set expectations for next steps
- Keep to 1-2 short sentences

**Call to Action:**
- Clear, specific action button
- Use verb that describes the creation ("Create pipeline", not "Get started")

### 3. Empty State Checklist

- [ ] Heading clearly names what this space is for
- [ ] Body explains what will appear here
- [ ] Primary action is obvious and specific
- [ ] Tone is encouraging, not judgmental
- [ ] Provides educational value if first-time use

## Examples

### First-Time Use (No Items Created)
```
❌ BAD:
**Nothing here yet**
Get started by clicking the button below.

✅ GOOD:
**No data pipelines yet**
Create a pipeline to move and transform your data across sources.

[Create pipeline]
```

### No Search Results
```
❌ BAD:
**No results found**

✅ GOOD:
**No results for "sales report"**
Try different keywords or check your filters.

[Clear filters]
```

### Cleared Content (User Deleted Everything)
```
❌ BAD:
**Empty**

✅ GOOD:
**No recent files**
Files you open will appear here for quick access.
```

### No Permissions
```
❌ BAD:
**Access denied**

✅ GOOD:
**You don't have access to these reports**
Ask your workspace admin for permission, or explore the sample reports.

[View sample reports]
```

### Waiting for Data
```
❌ BAD:
**Loading...**

✅ GOOD:
**No data yet**
Your pipeline will populate data here after the first run.

[Run pipeline now]
```

## Tone Guidance

**First-time use:**
- Educational and encouraging
- Help users understand the value
- Make the first action obvious

**No results:**
- Helpful and actionable
- Suggest alternatives
- Don't make users feel stuck

**Cleared content:**
- Neutral and informative
- Explain what will appear here
- Don't assume user made a mistake

**Error states:**
- Clear and actionable
- Provide recovery steps
- See [Error Messages](error-messages.md) for more

## Visual Considerations

**Include when helpful:**
- Illustration or icon (keep simple and relevant)
- Visual example of what will appear
- Short video or animation for complex features

**Avoid:**
- Cute or overly playful imagery (unless it fits brand)
- Generic "empty box" illustrations
- Too much text or explanation

## Empty State Patterns

### Minimal Empty State
For experienced users or simple contexts:
```
**No connections**
[Add connection]
```

### Educational Empty State
For complex features or first-time users:
```
**Build your first data pipeline**
Pipelines move and transform data between your sources. Use them to automate data workflows, schedule refreshes, and keep your data in sync.

[Create pipeline] [Watch tutorial →]
```

### Filtered Empty State
When filters are applied:
```
**No pipelines match your filters**
Try adjusting your filters or [clear all filters].
```

## Related Templates

- [Error Messages](error-messages.md)
- [Onboarding Flows](../flows/onboarding.md)
- [Success Messages](success-messages.md)
