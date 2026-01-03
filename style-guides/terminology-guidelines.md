# Terminology Guidelines

A framework for establishing consistent word choice and terminology across your product.

## Why Terminology Matters

**Consistency builds trust:**
- Users learn your interface faster
- Reduces cognitive load
- Appears more professional
- Prevents confusion

**Inconsistent terminology:**
```
Button 1: "Submit"
Button 2: "Send"  
Button 3: "Post"
Button 4: "Publish"

All meaning the same thing = Confusing!
```

## Creating Your Terminology Guide

### Product-Specific Terms

Define the exact terms used in your product:

| Term | Definition | Usage | Don't Use |
|------|------------|-------|-----------|
| [Term] | [What it means] | [How to use it] | [Alternatives to avoid] |

**Example:**

| Term | Definition | Usage | Don't Use |
|------|------------|-------|-----------|
| Pipeline | Automated workflow that moves and transforms data | "Create a pipeline to sync your data" | workflow, job, process, automation |
| Workspace | Container for all your pipelines and datasets | "Switch to the Sales workspace" | project, folder, environment, tenant |
| Dataset | Collection of structured data | "Upload your dataset" | data source, table, file, data |

### UI Actions

Consistent verbs for common actions:

| Action | Verb to Use | Context | Don't Use |
|--------|-------------|---------|-----------|
| Open an item | Select, Open | "Select the pipeline" | Click, tap, hit, press |
| Create something new | Create, Add | "Create workspace" | New, make, build |
| Remove something | Delete, Remove | "Delete permanently" vs "Remove from list" | Erase, kill, trash |
| Save changes | Save | "Save changes" | Submit, apply, commit |
| Cancel action | Cancel | "Cancel operation" | Stop, quit, close, abort |
| Close window/dialog | Close | "Close dialog" | Exit, dismiss, cancel |

### Status States

Consistent language for system states:

| State | Term | Example | Don't Use |
|-------|------|---------|-----------|
| In progress | Running | "Pipeline running" | Processing, executing, in progress |
| Completed successfully | Succeeded, Completed | "Pipeline succeeded" | Finished, done, successful |
| Failed | Failed | "Pipeline failed" | Error, broke, unsuccessful |
| Not started | Not started, Pending | "Pipeline pending" | Queued, waiting, paused |
| Stopped by user | Canceled | "Pipeline canceled" | Stopped, terminated, killed |

### Data States

| State | Term | Example |
|-------|------|---------|
| No data | Empty | "Workspace is empty" |
| Loading data | Loading | "Loading workspace..." |
| Data ready | Ready | "Dataset ready" |
| Out of date | Outdated | "Data outdated" |
| Up to date | Current | "Data current" |

## Universal vs. Product-Specific

### Use Universal Terms When Possible

✅ **Universal (widely understood):**
- User
- Settings
- Help
- Account
- Dashboard
- Filter
- Search
- Export
- Import

❌ **Avoid inventing new terms for common concepts:**
- "Crew member" instead of "user"
- "Control center" instead of "settings"
- "Quick finder" instead of "search"

### When to Create Product-Specific Terms

✅ **Create new terms when:**
- Concept is unique to your product
- Industry-standard term is confusing
- Need to differentiate from competitors
- Existing terms have baggage

**Example:**
- Salesforce: "Lightning" (their UI framework)
- Microsoft: "Copilot" (AI assistant)
- Slack: "Workspace" (team environment)

## Word Choice Guidelines

### Preferred Terms

**General UI:**

| Use | Instead of |
|-----|------------|
| Select | Click, tap, press, hit |
| Choose | Pick |
| Enter | Type, input, key in |
| Clear | Erase, remove, delete |
| Required | Mandatory, necessary |
| Optional | Not required |
| Sign in | Log in, login |
| Sign out | Log out, logout |

**Actions:**

| Use | Instead of |
|-----|------------|
| Create | Make, build, add new |
| Edit | Modify, change, update |
| Delete | Remove, erase, kill |
| Duplicate | Copy, clone |
| Search | Find, look for |
| Filter | Narrow, refine |
| Sort | Order, arrange |

**States:**

| Use | Instead of |
|-----|------------|
| Enabled | On, active, turned on |
| Disabled | Off, inactive, turned off |
| Available | Ready, accessible |
| Unavailable | Not available, locked |

### Words to Avoid

❌ **Technical jargon without explanation:**
- API (unless your audience is developers)
- Deprecated
- Instantiate
- Utilize (use "use")
- Execute (use "run")

❌ **Vague language:**
- Stuff
- Things
- Items (be specific)
- Various

❌ **Unnecessarily complex:**
- Utilize → use
- Commence → start
- Terminate → end/stop
- Obtain → get
- Purchase → buy
- Facilitate → help

❌ **Colloquial/Slang:**
- ASAP → quickly, immediately
- Info → information
- Pics → images, photos
- Probs → problems

## Inclusive Language

### Gender-Neutral

✅ **Use:**
- They/them (singular)
- People, everyone, users
- Humanity, humankind
- Staffing
- Synthetic, artificial

❌ **Avoid:**
- He/him, she/her (generic)
- Guys, mankind
- Manpower, man-hours
- Manned

### Ability-Inclusive

✅ **Use:**
- People with disabilities
- Person who is blind/deaf
- Wheelchair user
- Cognitive impairment

❌ **Avoid:**
- Disabled person
- The blind, the deaf
- Wheelchair-bound
- Crazy, insane, lame

### Global-Friendly

✅ **Use:**
- Clear, simple language
- Define acronyms
- Explain idioms
- Universal examples

❌ **Avoid:**
- US-only idioms ("home run")
- Cultural references
- Puns that don't translate
- Regional slang

## Technical Terms

### When to Use Technical Terms

✅ **Use technical terms when:**
- Audience is technical
- Term is industry-standard
- Simpler alternative doesn't exist
- Context makes meaning clear

**Example for developers:**
```
✅ "Configure OAuth 2.0 authentication"
(Developers know OAuth)
```

**Example for general users:**
```
✅ "Sign in with Google"
(User doesn't need to know it's OAuth)
```

### Explaining Technical Terms

When you must use technical terms:

**First use: Define it**
```
"A pipeline is an automated workflow that moves and transforms your data."
```

**Provide context:**
```
"Your workspace (where you store pipelines and datasets) is ready."
```

**Link to more info:**
```
"Configure your API connection (learn about APIs)"
```

## Abbreviations & Acronyms

### General Rules

**First mention:** Spell out + abbreviation
```
✅ "Application Programming Interface (API)"
Then: "API" in subsequent uses
```

**Common acronyms:** Can use without spelling out
```
✅ "PDF", "URL", "FAQ"
(Most users know these)
```

**Product-specific:** Always spell out first
```
✅ "Real-time Data Integration (RDI)"
Then: "RDI"
```

### When NOT to Abbreviate

❌ **Don't abbreviate:**
- When it makes text harder to read
- In headings (usually)
- In navigation labels
- When abbreviation is unclear

## Capitalization Rules

### Product Names

**Your product:** [Your capitalization rule]
- Example: "Microsoft Fabric" (title case)
- Example: "GitHub" (specific capitalization)

### Features & Capabilities

[Your rule]
- Example: Sentence case for features: "Data pipelines"
- Example: Title case for major features: "AI Copilot"

### UI Elements

| Element | Capitalization | Example |
|---------|----------------|---------|
| Buttons | Sentence case | "Create pipeline" |
| Page titles | Title case | "Pipeline Settings" |
| Section headers | Sentence case | "Recent activity" |
| Field labels | Sentence case | "Workspace name" |
| Navigation items | Title case or sentence case | [Your choice] |

### General Text

**Sentence case for:**
- Body text
- Descriptions
- Helper text
- Error messages

**Title case for:**
- Major headings
- Document titles
- Product names

**ALL CAPS:**
- Only for emphasis (sparingly)
- Acronyms (FAQ, API)

## Numbers & Units

### Numbers

**Spell out or use numerals?**

✅ **Spell out:**
- Numbers one through nine in body text
- Numbers at start of sentence

✅ **Use numerals:**
- Numbers 10 and above
- Measurements (5 MB, 3 minutes)
- Percentages (5%)
- Version numbers (v2.0)

**Examples:**
```
✅ "You have five datasets"
✅ "Upload up to 100 MB"
✅ "Processing takes 3-5 minutes"
```

### Units of Measurement

**Data sizes:**
- Use: GB, MB, KB, TB
- Not: Gb, Mb, Kb

**Time:**
- Use: seconds, minutes, hours, days
- Abbreviate in limited space: sec, min, hr

**Currency:**
- Use: $ symbol with amount ($10)
- Spell out for accessibility: "10 US dollars"

## Punctuation

### Periods

✅ **Use periods:**
- Complete sentences
- Body text
- Multi-sentence descriptions

❌ **Don't use periods:**
- Button labels ("Save changes")
- Single-sentence field labels
- Navigation items
- Tooltips (usually)

### Commas

**Oxford comma:** [Your rule]
- Example: Use it: "pipelines, datasets, and workspaces"
- Example: Don't use: "pipelines, datasets and workspaces"

**Lists:**
```
✅ "Enter your name, email, and password"
```

### Colons

**Use for introducing:**
```
✅ "Required fields: Name, Email, Password"
```

**Don't use in field labels:**
```
❌ "Name:"
✅ "Name"
```

## Tone Consistency in Terminology

### Formality Level

[Your product's approach]

**Formal:**
```
✅ "Select 'Create Workspace' to begin"
```

**Casual:**
```
✅ "Let's create a workspace"
```

**Mixed (context-dependent):**
```
Errors: Formal and clear
Success: Can be warmer
Settings: Professional
Marketing: Can be casual
```

## Terminology Checklist

Before publishing content, check:

- [ ] Uses approved product terms consistently
- [ ] UI action verbs match guidelines
- [ ] No technical jargon without explanation
- [ ] Inclusive language throughout
- [ ] Capitalization follows rules
- [ ] Abbreviations spelled out on first use
- [ ] Numbers formatted correctly
- [ ] Punctuation matches guidelines
- [ ] Tone appropriate for context

## Pattern Library Examples

### Common Patterns

**Creating something:**
```
✅ "Create [item]"
Not: "New [item]", "Add [item]"
```

**Confirming deletion:**
```
✅ "Delete [item]? This action cannot be undone."
Not: "Are you sure?", "Really delete?"
```

**Empty states:**
```
✅ "No [items] yet. Create your first one?"
Not: "There are no [items] here"
```

**Success:**
```
✅ "[Item] created successfully"
Not: "Success!", "[Item] has been created"
```

**Errors:**
```
✅ "[Action] failed. [Reason]. [What to do]."
Not: "Error occurred", "Something went wrong"
```

## Maintaining Your Terminology Guide

### Regular Reviews

**Monthly:**
- Review new content for consistency
- Note new terms being introduced
- Update guide as needed

**Quarterly:**
- Audit product for inconsistencies
- Get feedback from users/support
- Revise based on learnings

**Annually:**
- Comprehensive terminology review
- Align with brand evolution
- Document major changes

### Adding New Terms

**Process:**
1. Identify need for new term
2. Research alternatives
3. Get stakeholder input
4. Test with users
5. Document decision
6. Update all content
7. Add to this guide

### Version Control

**Track changes:**
- Date of updates
- What changed
- Why it changed
- Who approved

**Example:**
```
v1.0 - 2024-01-15 - Initial terminology guide
v1.1 - 2024-03-20 - Added AI feature terms
v1.2 - 2024-06-10 - Updated inclusive language section
```

## Resources

**Style guides to reference:**
- [Microsoft Style Guide](https://docs.microsoft.com/style-guide/)
- [Google Developer Style Guide](https://developers.google.com/style)
- [Apple Style Guide](https://support.apple.com/guide/applestyleguide/)
- [Mailchimp Content Style Guide](https://styleguide.mailchimp.com/)

**Your internal resources:**
- [Link to pattern library]
- [Link to UI inventory]
- [Link to brand guidelines]

**Questions?**
Contact: [Content team contact]
