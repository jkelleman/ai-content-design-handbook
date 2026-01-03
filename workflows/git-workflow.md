# Git Workflow for Content Designers

A practical guide to using Git and GitHub for content design work, even if you've never used version control before.

## Why Use Git for Content?

**Version control benefits:**
- Track changes over time
- Collaborate without overwriting each other's work
- Revert to previous versions if needed
- Document why changes were made
- Review content before publishing

**GitHub benefits:**
- Centralized location for all content files
- Built-in review and approval process
- Integration with documentation sites
- Change history and blame functionality

## Basic Git Concepts

**Repository (repo):** Folder containing your content and its history

**Commit:** Snapshot of your content at a specific time

**Branch:** Independent line of development (like a parallel timeline)

**Pull Request (PR):** Proposed changes for review

**Merge:** Combining changes from one branch into another

## Daily Workflow

### 1. Get Latest Changes
Before starting work, pull the latest changes:

```bash
git pull origin main
```

**What this does:** Downloads any changes your team made

---

### 2. Create a Branch
Create a branch for your work:

```bash
git checkout -b update-error-messages
```

**Naming convention:**
- Use lowercase with hyphens
- Be descriptive: `update-onboarding-flow`, `fix-typos-in-docs`
- Include issue number if applicable: `123-improve-empty-states`

---

### 3. Make Your Changes
Edit your content files in VS Code or your preferred editor.

---

### 4. Check What Changed
See what files you modified:

```bash
git status
```

See specific changes:

```bash
git diff
```

---

### 5. Stage Your Changes
Add files to commit:

```bash
# Add specific file
git add error-messages.md

# Add all changed files
git add .

# Add all markdown files
git add *.md
```

---

### 6. Commit Your Changes
Save your changes with a descriptive message:

```bash
git commit -m "Update error messages to be more specific and actionable"
```

**Good commit messages:**
- Start with a verb: Update, Add, Fix, Remove
- Be specific about what changed
- Explain why if not obvious

```
✅ GOOD:
- "Add empty state template with examples"
- "Fix typos in onboarding flow section"
- "Update button labels to use active verbs"

❌ BAD:
- "Changes"
- "Update"
- "Fixed stuff"
```

---

### 7. Push Your Branch
Upload your branch to GitHub:

```bash
git push origin update-error-messages
```

---

### 8. Create a Pull Request
Go to GitHub and create a Pull Request (PR):

1. Navigate to your repository
2. Click "Pull requests" → "New pull request"
3. Select your branch
4. Add title and description
5. Request reviewers
6. Create pull request

**PR description template:**
```markdown
## What changed
Brief description of your changes

## Why
Reason for the change

## Preview
Link to preview if applicable

## Checklist
- [ ] Content follows style guide
- [ ] All links work
- [ ] Spelling and grammar checked
- [ ] Tested in preview environment
```

---

### 9. Address Review Feedback
If reviewers request changes:

1. Make the changes in your branch
2. Commit and push again
3. PR updates automatically

---

### 10. Merge Your PR
Once approved:

1. Click "Merge pull request"
2. Delete your branch (keeps repo clean)
3. Pull latest changes to your local repo

---

## Common Scenarios

### Scenario 1: Working on Multiple Things
Create separate branches for each piece of work:

```bash
git checkout -b update-error-messages
# Work on error messages, commit, push, create PR

git checkout main
git pull
git checkout -b add-onboarding-template
# Work on onboarding, commit, push, create PR
```

### Scenario 2: Need to Make Urgent Fix
Stash your current work, fix the issue, then return:

```bash
# Save current work temporarily
git stash

# Make urgent fix
git checkout main
git pull
git checkout -b urgent-fix
# Make changes, commit, push, create PR

# Return to your work
git checkout your-branch
git stash pop
```

### Scenario 3: Accidentally Committed to Wrong Branch
Move your commit to a new branch:

```bash
# Create new branch from current position
git branch correct-branch-name

# Reset current branch
git reset --hard HEAD~1

# Switch to new branch
git checkout correct-branch-name
```

### Scenario 4: Need to Update Branch with Latest Main
Keep your branch up to date:

```bash
git checkout main
git pull
git checkout your-branch
git merge main
```

Or use rebase for cleaner history:

```bash
git checkout your-branch
git rebase main
```

### Scenario 5: Made a Mistake in Last Commit
Fix your most recent commit:

```bash
# Make your fixes
git add .
git commit --amend -m "Updated commit message"

# If already pushed, need to force push (use carefully!)
git push --force origin your-branch
```

## Working with Content Files

### Organize Content Files
```
docs/
├── README.md
├── getting-started/
│   ├── index.md
│   └── quickstart.md
├── guides/
│   ├── error-handling.md
│   └── onboarding.md
└── reference/
    ├── api.md
    └── glossary.md
```

### Use Markdown Consistently
- One sentence per line (easier to see changes)
- Consistent heading hierarchy
- Links as references at bottom when used multiple times

### Include Metadata
Add frontmatter to track content:

```markdown
---
title: Error Message Guidelines
author: Your Name
last_updated: 2026-01-02
status: draft
---
```

## Collaboration Tips

### Reviewing Content PRs

**As a reviewer:**
- Check for clarity and consistency
- Verify links work
- Test in preview environment
- Comment on specific lines for precise feedback
- Use "Suggest changes" feature for quick fixes

**GitHub comment types:**
- **Comment:** General feedback
- **Approve:** Ready to merge
- **Request changes:** Needs work before merging

### Resolving Conflicts

If two people edited the same file:

1. Git will mark conflicts:
```markdown
<<<<<<< HEAD
Your version
=======
Their version
>>>>>>> branch-name
```

2. Edit the file to keep the right content
3. Remove conflict markers
4. Commit the resolution

### Using Templates

Create PR and commit message templates:

**.github/pull_request_template.md**
```markdown
## What changed

## Why

## Checklist
- [ ] Content reviewed
- [ ] Links tested
- [ ] Follows style guide
```

## Git Commands Cheat Sheet

```bash
# Setup
git clone <url>                    # Download repository
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

# Daily workflow
git pull origin main               # Get latest changes
git checkout -b branch-name        # Create new branch
git status                         # See what changed
git diff                          # See specific changes
git add file.md                   # Stage file
git add .                         # Stage all changes
git commit -m "message"           # Commit changes
git push origin branch-name       # Push branch

# Branch management
git branch                        # List branches
git checkout branch-name          # Switch branches
git branch -d branch-name         # Delete branch
git merge branch-name             # Merge branch

# Undoing
git restore file.md               # Discard changes
git reset HEAD~1                  # Undo last commit (keep changes)
git reset --hard HEAD~1           # Undo last commit (discard changes)
git revert commit-hash            # Create new commit undoing previous

# History
git log                           # See commit history
git log --oneline                 # Condensed history
git blame file.md                 # See who changed each line
```

## VS Code Git Integration

**Built-in Git features:**
- Source Control panel (Ctrl+Shift+G)
- Visual diff viewer
- Inline change indicators
- Commit and push from UI
- Branch switcher in status bar

**Recommended extensions:**
- GitLens - Enhanced Git capabilities
- GitHub Pull Requests - Manage PRs from VS Code

## Best Practices

**Do:**
- Commit often with clear messages
- Pull before starting new work
- Create branches for all changes
- Write descriptive PR descriptions
- Review your own changes before requesting review

**Don't:**
- Commit directly to main
- Use vague commit messages
- Push untested changes
- Force push to shared branches
- Commit sensitive information

## Getting Help

**Common issues:**
- Merge conflicts → Ask teammate to pair on resolution
- Accidentally committed to main → Create branch and reset main
- Lost changes → Check `git reflog` to find them
- Pushed wrong thing → Revert with new commit

**Resources:**
- [GitHub Docs](https://docs.github.com)
- [Git Documentation](https://git-scm.com/doc)
- Ask your team's Git expert

## Related Resources

- [Content Review Process](content-review-process.md)
- [Documentation Structure](../resources/documentation-structure.md)
- [Style Guide](../style-guides/voice-and-tone.md)
