# Content Review Process

A structured approach to reviewing and approving content changes to ensure quality and consistency.

## Review Process Overview

```
Draft → Self-Review → Peer Review → Stakeholder Review → Publish
```

## Stage 1: Self-Review

Before sending for review, check your own work.

### Content Quality Checklist

**Clarity:**
- [ ] Main point is obvious within first sentence/paragraph
- [ ] Sentences are concise (under 25 words ideally)
- [ ] No jargon or it's explained on first use
- [ ] Active voice used throughout
- [ ] Examples provided for complex concepts

**Structure:**
- [ ] Clear heading hierarchy
- [ ] Scannable (uses bullets, short paragraphs)
- [ ] Logical flow from start to finish
- [ ] Related content linked appropriately

**Accuracy:**
- [ ] Technical details verified with engineer/SME
- [ ] Links work and point to correct destinations
- [ ] Screenshots match current UI
- [ ] Code samples tested and functional

**Consistency:**
- [ ] Follows style guide (capitalization, punctuation, terminology)
- [ ] Voice and tone appropriate for audience
- [ ] Formatting matches other similar content
- [ ] Matches existing patterns and conventions

**Accessibility:**
- [ ] Headings in proper order (no skipped levels)
- [ ] Images have alt text
- [ ] Links have descriptive text (not "click here")
- [ ] Color not used as only way to convey information
- [ ] Tables have headers

---

## Stage 2: Peer Review

Another content designer reviews your work.

### For the Author

**Prepare your content for review:**

1. **Add context in PR description:**
   ```markdown
   ## What changed
   Updated error messages to be more specific and actionable
   
   ## Why
   Users reported generic error messages didn't help them resolve issues
   
   ## Focus areas for review
   - Do error messages provide clear next steps?
   - Is tone appropriate for error situations?
   - Are examples helpful?
   ```

2. **Highlight specific concerns:**
   - "Not sure if tone is right in line 45"
   - "Need help with this transition"
   - "Alternative wording suggestions welcome"

3. **Provide preview link** if possible

**Respond to feedback:**
- Address all comments (even if just to explain why you disagree)
- Mark conversations resolved when addressed
- Ask clarifying questions if feedback unclear
- Update PR description if scope changes

### For the Reviewer

**What to review:**

**Content:**
- Is it clear and understandable?
- Does it accomplish stated goal?
- Is tone and voice appropriate?
- Are there gaps or missing information?
- Could anything be more concise?

**Quality:**
- Spelling and grammar correct?
- Style guide followed?
- Links work?
- Examples accurate?

**User Experience:**
- Will users understand this?
- Is information easy to find and scan?
- Are actions clear?
- Does it help users accomplish their goal?

**How to give feedback:**

**Be specific:**
```
❌ "This section is confusing"
✅ "The second paragraph introduces 'data sources' without defining it. 
   Consider adding: 'Data sources are the systems where your data lives,
   like databases, files, or APIs.'"
```

**Explain your reasoning:**
```
❌ "Change this"
✅ "Consider using active voice here ('Create a pipeline' instead of 
   'A pipeline can be created') to make the instruction more direct"
```

**Suggest, don't demand:**
```
❌ "Wrong. Fix this."
✅ "What if we tried: [suggestion]? I think it might be clearer because..."
```

**Use GitHub's "Suggest changes" feature:**
- Click suggestion icon in comment
- Edit the content directly
- Author can accept with one click

**Balance criticism with praise:**
- Note what works well
- Celebrate good writing
- Acknowledge improvement

---

## Stage 3: Stakeholder Review

Product managers, engineers, or subject matter experts review for accuracy and alignment.

### For the Author

**Set expectations:**
- Explain you need technical accuracy review, not copyediting
- Specify deadline
- Note any constraints (character limits, scope, etc.)

**Ask specific questions:**
- "Is this technical explanation accurate?"
- "Does this match how the feature actually works?"
- "Are there edge cases I'm missing?"

**Navigate conflicting feedback:**
- If stakeholders disagree, facilitate discussion
- Document decisions and reasoning
- Push back on feedback that harms user experience
- Explain content design principles when needed

### For Stakeholders

**Focus on:**
- Technical accuracy
- Feature completeness
- Business goals alignment
- Regulatory/legal requirements
- Missing context or caveats

**Avoid:**
- Wordsmithing (trust the content designer)
- Lengthy explanations (let content stay concise)
- Jargon insertion (users need plain language)
- Scope creep (save other ideas for future work)

---

## Stage 4: Final Check & Publish

Before merging/publishing:

### Pre-Publish Checklist

- [ ] All review comments addressed or resolved
- [ ] Final proofread completed
- [ ] Links verified one more time
- [ ] Preview checked in production-like environment
- [ ] Metadata updated (last_updated date, version, etc.)
- [ ] Related content updated if needed
- [ ] Search keywords/tags added
- [ ] Stakeholder sign-off received

### Publishing

1. **Merge the PR** (or deploy content)
2. **Verify in production** - Check live site immediately
3. **Update related content** if needed
4. **Announce** in team channel or release notes if significant
5. **Monitor** for issues or questions from users

### Post-Publish

- Add to content inventory/database
- Track analytics if available
- Gather user feedback
- Note improvements for next time

---

## Review Types

### Quick Review (< 30 minutes)
**For:** Minor updates, typo fixes, small clarifications

**Process:**
- Self-review with checklist
- Quick peer review or async approval
- Merge

### Standard Review (1-3 days)
**For:** New content, significant changes, user-facing updates

**Process:**
- Self-review
- Peer content review
- SME/engineer review
- Final check
- Merge

### Thorough Review (1-2 weeks)
**For:** Major features, new products, high-visibility content

**Process:**
- Self-review
- Peer content review
- SME/engineer review
- PM/leadership review
- Legal/compliance review (if needed)
- User testing (if possible)
- Final check
- Phased rollout

---

## Common Review Scenarios

### Scenario: Reviewer Requests Major Changes
**Response:**
- Understand the concern
- Discuss scope impact
- Consider splitting into multiple PRs
- Document what's deferred

### Scenario: Technical Review Comes Back with Errors
**Response:**
- Fix errors quickly
- Ask for examples to improve understanding
- Request review earlier next time
- Build better relationship with SME

### Scenario: Conflicting Feedback from Multiple Reviewers
**Response:**
- Document all perspectives
- Facilitate discussion/meeting
- Make final call based on user needs
- Document reasoning for decision

### Scenario: Review is Taking Too Long
**Response:**
- Ping reviewers with specific deadline
- Escalate to manager if blocking
- Consider reducing scope
- Offer to meet synchronously

### Scenario: Disagreement on Content Approach
**Response:**
- Explain content design principles
- Show examples or research
- Suggest A/B test if high-stakes
- Involve manager or senior content designer

---

## Review Best Practices

**For everyone:**
- Review promptly (within 1-2 days)
- Be respectful and constructive
- Focus on user needs
- Assume good intent
- Document decisions

**For authors:**
- Make review easy (provide context, preview)
- Be open to feedback
- Don't take critique personally
- Ask questions when unclear
- Improve with each review

**For reviewers:**
- Be specific and actionable
- Explain your reasoning
- Balance critique with praise
- Suggest, don't demand
- Focus on significant issues

---

## Review Templates

### PR Review Comment Template
```markdown
**What works well:**
- [Specific praise]

**Suggestions:**
- [Line 12] [Specific feedback with reasoning]
- [Line 45] [Suggestion]

**Questions:**
- [Clarifying question]

**Overall:** [Approve / Request changes / Comment]
```

### Content Feedback Form (for non-GitHub reviews)
```markdown
Content: [Title/URL]
Reviewer: [Name]
Date: [Date]

Clarity: [1-5] [Comments]
Accuracy: [1-5] [Comments]
Completeness: [1-5] [Comments]
Voice/Tone: [1-5] [Comments]

Suggested changes:
-
-

Approved: [ ] Yes [ ] Yes with changes [ ] No
```

---

## Tools for Review

**Async review:**
- GitHub Pull Requests (best for markdown/code)
- Google Docs suggestions (good for early drafts)
- Notion comments
- Figma comments (for UI content)

**Sync review:**
- Screen share + verbal feedback
- Pair writing sessions
- Content critique meetings

**Automated review:**
- Spell check / Grammarly
- Markdown linters
- Link checkers
- Readability scores
- Style guide checkers

---

## Measuring Review Effectiveness

**Track:**
- Time from draft to publish
- Number of review rounds needed
- Common feedback themes
- Post-publish issues found

**Improve:**
- Build style guide from frequent feedback
- Create templates for common patterns
- Invest in tooling/automation
- Share learnings with team

---

## Related Resources

- [Git Workflow](git-workflow.md)
- [Style Guide](../style-guides/voice-and-tone.md)
- [Templates](../templates/)
- [Accessibility Guidelines](../resources/accessibility-guidelines.md)
