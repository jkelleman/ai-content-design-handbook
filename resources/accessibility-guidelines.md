# Accessibility Guidelines for Content Designers

Creating content that everyone can access, understand, and use—regardless of ability, device, or context.

## Why Accessibility Matters

**It's the law:** Many regions require digital accessibility (ADA, Section 508, WCAG)

**It's good design:** Accessibility improvements help everyone
- Captions help people in noisy environments
- Clear language helps non-native speakers
- Simple navigation helps people in a hurry

**It's inclusive:** ~15% of the world has a disability
- Vision impairments
- Hearing impairments
- Motor impairments
- Cognitive disabilities

## WCAG Principles (POUR)

### Perceivable
Information must be presentable to users in ways they can perceive

### Operable
UI components must be operable by all users

### Understandable
Information and operation must be understandable

### Robust
Content must work with current and future assistive technologies

---

## Content Accessibility Guidelines

### 1. Write Clear, Simple Content

**Use plain language:**
```
❌ "Utilize the aforementioned methodology"
✅ "Use this method"

❌ "Facilitate the implementation"
✅ "Help set it up"
```

**Keep sentences short:**
- Aim for 15-25 words per sentence
- One idea per sentence
- Break complex information into steps

**Use active voice:**
```
❌ "The file was uploaded by the user"
✅ "User uploaded the file"
✅ "Upload the file"
```

**Define jargon and acronyms:**
```
✅ "TTL (Time to Live) determines how long cached data remains valid"
```

---

### 2. Structure Content Properly

**Use semantic headings:**
```html
# Page Title (H1 - one per page)
## Main Section (H2)
### Subsection (H3)
#### Detail (H4)
```

**Don't skip heading levels:**
```
❌ H1 → H3 (skipped H2)
✅ H1 → H2 → H3
```

**Use headings for structure, not styling:**
```
❌ Using H3 because it "looks good"
✅ Using H3 because it's a subsection of H2
```

**Use lists for lists:**
```html
✅ Unordered lists for non-sequential items:
- Apple
- Orange
- Banana

✅ Ordered lists for sequential items:
1. First, open the file
2. Then, make changes
3. Finally, save
```

---

### 3. Write Descriptive Links

**Link text should describe the destination:**
```
❌ "Click [here](url) for documentation"
❌ "Learn more [→](url)"
❌ "[Read more](url)"

✅ "Read the [API documentation](url)"
✅ "Learn about [data pipeline scheduling](url)"
✅ "See [examples of error messages](url)"
```

**Links should make sense out of context:**
Screen readers can list all links on a page. Each should be understandable alone.

```
❌ List of links:
- "Click here"
- "Learn more"
- "Documentation"

✅ List of links:
- "API authentication guide"
- "Tutorial: Create your first pipeline"
- "Error message documentation"
```

**Button text should describe the action:**
```
❌ "Submit"
❌ "OK"
❌ "Click here"

✅ "Create pipeline"
✅ "Save changes"
✅ "Delete workspace"
```

---

### 4. Provide Alternative Text for Images

**Every meaningful image needs alt text:**

```markdown
✅ Informative image:
![Dashboard showing 5 active pipelines and 2 errors](dashboard.png)

✅ Decorative image (empty alt):
![](decorative-graphic.png)

❌ Missing alt:
![](important-diagram.png)
```

**Write good alt text:**
- Describe the content and function
- Be specific and concise
- Don't start with "Image of" or "Picture of"
- Include text that appears in the image

```
❌ "Screenshot"
❌ "Image of dashboard"

✅ "Pipeline dashboard with 5 successful runs and 2 failures"
✅ "Error message: 'Connection timed out. Check your internet connection and try again.'"
```

**For complex images:**
- Provide longer description in surrounding text
- Link to detailed explanation
- Use figure captions

---

### 5. Make Tables Accessible

**Use table headers:**
```markdown
| Name | Status | Last Run |
|------|--------|----------|
| Sales Pipeline | Running | 2 hours ago |
| Marketing Data | Failed | 1 day ago |
```

**Keep tables simple:**
- Avoid nested tables
- Avoid merged cells
- Use tables for data, not layout

**Provide table captions:**
```markdown
**Table 1: Pipeline status overview**

| Name | Status | Last Run |
...
```

---

### 6. Write Accessible Forms

**Every input needs a visible label:**
```html
✅
<label for="email">Email address</label>
<input type="email" id="email" name="email">

❌ Placeholder as label (disappears when typing)
<input type="email" placeholder="Email address">
```

**Provide clear instructions:**
```markdown
**Password**
Must be at least 8 characters and include a number

[password input]
```

**Write helpful error messages:**
```
❌ "Invalid input"
❌ "Error"

✅ "Email address is required"
✅ "Password must be at least 8 characters"
```

**Group related fields:**
```markdown
**Shipping Address**

Street:
City:
State:
ZIP:
```

---

### 7. Use Color Appropriately

**Don't rely on color alone:**
```
❌ "Click the green button to continue"
✅ "Click Continue to proceed"

❌ Red text for errors, green for success (color only)
✅ ✗ Error message | ✓ Success message (icon + color)
```

**Ensure sufficient contrast:**
- Text: 4.5:1 contrast ratio minimum
- Large text (18pt+): 3:1 minimum
- UI components: 3:1 minimum

**Test with color blindness simulators**

---

### 8. Make Content Scannable

**Use descriptive headings:**
```
❌ "Introduction" "Details" "More Information"
✅ "What are data pipelines?" "How to create a pipeline" "Common pipeline patterns"
```

**Front-load important information:**
```
❌ "To connect to your database, after setting up authentication and configuring network settings, you need to..."

✅ "Connect to your database:
1. Set up authentication
2. Configure network settings
3. ..."
```

**Use bullets and numbers:**
- Bullets for non-sequential items
- Numbers for steps or sequences
- Keep bullets parallel in structure

**Keep paragraphs short:**
- 2-4 sentences per paragraph
- White space aids comprehension
- Break up long blocks of text

---

### 9. Write for Screen Readers

**Screen readers read:**
- Text content
- Alt text for images
- Link text
- Button labels
- Form labels
- Heading structure
- Table headers

**Optimize for screen readers:**
- Use semantic HTML/markdown
- Don't hide important text in images
- Make link text descriptive
- Ensure logical reading order
- Test with actual screen readers

**Common screen readers:**
- JAWS (Windows)
- NVDA (Windows, free)
- VoiceOver (Mac, iOS)
- TalkBack (Android)

---

### 10. Consider Cognitive Accessibility

**Keep it simple:**
- One main idea per sentence
- Short sentences and paragraphs
- Common words over complex terms

**Be consistent:**
- Use same terms throughout
- Follow established patterns
- Maintain predictable structure

**Provide context:**
- Explain what will happen before it happens
- Show where users are in multi-step processes
- Provide clear next steps

**Allow enough time:**
- Don't auto-advance content
- Allow pausing or extending timeouts
- Provide clear warnings before timeouts

**Avoid flashing or moving content:**
- Can trigger seizures
- Distracting for cognitive disabilities
- Provide pause controls for animations

---

## Accessibility Checklist

**Content:**
- [ ] Written in plain, clear language
- [ ] Sentences under 25 words
- [ ] Active voice used
- [ ] Jargon defined or avoided
- [ ] Reading level appropriate for audience

**Structure:**
- [ ] Proper heading hierarchy (no skipped levels)
- [ ] Lists used appropriately
- [ ] Content scannable (headings, bullets, short paragraphs)
- [ ] Logical reading order

**Links:**
- [ ] Link text describes destination
- [ ] Links make sense out of context
- [ ] No "click here" or "learn more" links
- [ ] Button text describes action

**Images:**
- [ ] All meaningful images have alt text
- [ ] Alt text is descriptive and concise
- [ ] Decorative images have empty alt text
- [ ] Complex images have full descriptions

**Tables:**
- [ ] Tables have headers
- [ ] Tables are simple (no nesting or merging)
- [ ] Tables have captions

**Forms:**
- [ ] Every input has a visible label
- [ ] Instructions are clear
- [ ] Error messages are specific and helpful
- [ ] Related fields are grouped

**Color:**
- [ ] Color not used as only indicator
- [ ] Sufficient contrast ratios
- [ ] Content understandable without color

**General:**
- [ ] Tested with keyboard only
- [ ] Tested with screen reader
- [ ] Checked with accessibility tools
- [ ] No auto-playing media
- [ ] No flashing content

---

## Testing for Accessibility

### Automated Tools
- **axe DevTools** (browser extension)
- **WAVE** (web accessibility evaluation tool)
- **Lighthouse** (in Chrome DevTools)
- **Pa11y** (command line tool)

*Note: Automated tools catch only ~30-40% of issues*

### Manual Testing

**Keyboard testing:**
- Can you navigate without a mouse?
- Is focus visible?
- Is tab order logical?
- Can you activate all interactive elements?

**Screen reader testing:**
- Turn on screen reader
- Navigate through content
- Do headings make sense?
- Are links understandable?
- Is all content announced?

**Zoom testing:**
- Zoom to 200%
- Does content reflow?
- Is text still readable?
- Are controls still usable?

### User Testing
- Test with people who use assistive tech
- Learn about real usage patterns
- Discover issues tools miss

---

## Common Accessibility Mistakes

**1. Using placeholder as label**
```html
❌ <input placeholder="Email address">
✅ <label>Email address</label>
   <input placeholder="name@example.com">
```

**2. Skipping heading levels**
```
❌ H1 → H3 → H2
✅ H1 → H2 → H3
```

**3. Generic link text**
```
❌ "Click here for more information"
✅ "Read the getting started guide"
```

**4. Missing alt text**
```
❌ ![](important-diagram.png)
✅ ![Diagram showing data flow from source to destination through transformation pipeline](diagram.png)
```

**5. Color-only indicators**
```
❌ "Green = success, Red = error"
✅ "✓ Success" "✗ Error"
```

**6. Non-descriptive buttons**
```
❌ "Submit" "OK" "Cancel"
✅ "Create pipeline" "Save changes" "Cancel edit"
```

**7. Complex language**
```
❌ "Utilize the aforementioned configuration parameters"
✅ "Use these settings"
```

**8. No keyboard access**
```
❌ Click-only interactions
✅ Works with mouse, keyboard, and touch
```

---

## Resources

**Standards:**
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [Section 508](https://www.section508.gov/)
- [ADA Digital Accessibility](https://www.ada.gov/)

**Tools:**
- [axe DevTools](https://www.deque.com/axe/)
- [WAVE](https://wave.webaim.org/)
- [Contrast Checker](https://webaim.org/resources/contrastchecker/)

**Learning:**
- [A11ycasts (YouTube)](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)
- [WebAIM](https://webaim.org/)
- [The A11Y Project](https://www.a11yproject.com/)

**Style Guides:**
- [Microsoft Style Guide - Accessibility terms](https://docs.microsoft.com/en-us/style-guide/a-z-word-list-term-collections/term-collections/accessibility-terms)
- [MailChimp Content Style Guide - Writing for Accessibility](https://styleguide.mailchimp.com/writing-for-accessibility/)

---

## Related Resources

- [Voice and Tone Guide](../style-guides/voice-and-tone.md)
- [Content Review Process](../workflows/content-review-process.md)
- [Microcopy Template](../templates/messages/microcopy.md)
