# Content Design Examples

Real-world before/after examples showing content improvements across different types.

## Error Messages

### Example 1: Network Error

**❌ Before:**
```
Error 504: Gateway Timeout
The request could not be processed at this time due to a timeout condition.
Please try your request again.
```

**Problems:**
- Technical error code first
- Jargon ("gateway timeout")
- No clear cause
- Vague action

**✅ After:**
```
Connection timeout

Your request took too long to complete. This usually happens when:
• Your internet connection is slow or unstable
• Our servers are experiencing high traffic

What to do:
1. Check your internet connection
2. Wait a minute and try again
3. If the problem continues, contact support

Error code: 504 (for support reference)
```

**Improvements:**
- Plain language title
- Explains what happened
- Lists common causes
- Clear, numbered steps
- Technical code moved to bottom

---

### Example 2: Validation Error

**❌ Before:**
```
Invalid input in field 'workspaceName'
Value does not match required pattern: ^[a-zA-Z0-9_-]{3,64}$
```

**Problems:**
- Technical field name
- Regex shown to user
- No explanation of rules
- Unhelpful

**✅ After:**
```
Workspace name is invalid

Names must:
• Be 3-64 characters long
• Use only letters, numbers, hyphens, or underscores
• Example: my-workspace-123

Current name: "@my workspace!" 
Issues: Contains '@' and '!' (not allowed), has a space
```

**Improvements:**
- Clear requirements
- Friendly example
- Shows what's wrong
- Actionable feedback

---

## Success Messages

### Example 3: Pipeline Created

**❌ Before:**
```
✓ Success

Your pipeline has been successfully created and is now available 
in your workspace. You may now proceed to configure it.
```

**Problems:**
- Overly formal
- Too wordy
- Vague next step

**✅ After:**
```
Pipeline created!

What's next?
• Add activities to build your workflow
• Schedule when it runs
• Test it with sample data

[Configure pipeline] [View all pipelines]
```

**Improvements:**
- Enthusiastic but professional
- Specific next steps
- Action buttons included
- Shorter, scannable

---

### Example 4: Data Upload

**❌ Before:**
```
File upload operation completed successfully.
```

**Problems:**
- Too formal/technical
- No context
- No next step

**✅ After:**
```
Dataset uploaded (2.3 GB)

Your data is ready to use. Preview it below or add it to a pipeline.

[Preview data] [Create pipeline]
```

**Improvements:**
- Includes useful details (file size)
- States outcome clearly
- Suggests next actions
- Provides buttons

---

## Empty States

### Example 5: No Pipelines

**❌ Before:**
```
You have no pipelines.
```

**Problems:**
- States obvious
- Not helpful
- No guidance

**✅ After:**
```
No pipelines yet

Pipelines automate data workflows—move data, transform it, 
and schedule updates automatically.

Ready to create your first one?

[Create pipeline] [Watch tutorial] [View examples]
```

**Improvements:**
- Positive framing ("yet")
- Explains what feature does
- Encouraging question
- Multiple paths forward
- Educational resources

---

### Example 6: Empty Dashboard

**❌ Before:**
```
No data available to display.
```

**Problems:**
- Negative framing
- No explanation
- Dead end

**✅ After:**
```
Your dashboard is empty

Add widgets to monitor:
• Pipeline performance
• Data usage
• Recent activity
• System health

[Add widget] [Use template]
```

**Improvements:**
- Neutral framing
- Shows what's possible
- Specific options
- Quick actions

---

## Onboarding

### Example 7: Welcome Screen

**❌ Before:**
```
Welcome to DataFlow Platform v2.0

This application enables enterprise-grade data integration 
and orchestration capabilities through a visual workflow designer.

[Continue]
```

**Problems:**
- Version number unnecessary
- Too technical
- Doesn't address user
- One vague button

**✅ After:**
```
Welcome to DataFlow! 👋

Let's get you set up in 3 quick steps:
1. Create your workspace (30 seconds)
2. Connect your data (2 minutes)
3. Build your first pipeline (5 minutes)

Ready? This will take about 7 minutes total.

[Get started] [Skip for now]
```

**Improvements:**
- Friendly greeting
- Clear time expectations
- Specific steps
- Progress indicated
- Skip option provided

---

### Example 8: Feature Introduction

**❌ Before:**
```
New Feature: Automated Scheduling

The system now supports automated scheduling capabilities 
for pipeline execution. Access this via Settings > Automation.

[OK]
```

**Problems:**
- Technical language
- Doesn't explain benefit
- Vague location
- Dismissive button

**✅ After:**
```
✨ New: Scheduled pipelines

Run pipelines automatically—daily, weekly, or on a custom schedule. 
No more manual runs!

Example: Schedule a pipeline to run every morning at 6 AM.

[Set up a schedule] [Learn more] [Maybe later]
```

**Improvements:**
- Shows benefit clearly
- Concrete example
- Multiple options
- Optional engagement

---

## Confirmation Dialogs

### Example 9: Delete Confirmation

**❌ Before:**
```
Are you sure you want to delete this workspace?
This action cannot be undone.

[Yes] [No]
```

**Problems:**
- Vague "this"
- Yes/No buttons ambiguous
- Doesn't show impact

**✅ After:**
```
Delete "Sales Data" workspace?

This will permanently delete:
• 12 pipelines
• 5 datasets
• All activity history

⚠️ This action cannot be undone.

Type the workspace name to confirm: [_____]

[Cancel] [Delete workspace]
```

**Improvements:**
- Shows specific item
- Lists what will be deleted
- Requires intentional confirmation
- Clear button labels
- Prominent warning

---

### Example 10: Discard Changes

**❌ Before:**
```
You have unsaved changes. Discard?

[OK] [Cancel]
```

**Problems:**
- Question lacks context
- OK/Cancel confusing
- Doesn't show what changes

**✅ After:**
```
Discard unsaved changes?

You've edited:
• Pipeline name
• 3 activity settings

If you leave now, these changes won't be saved.

[Keep editing] [Discard changes]
```

**Improvements:**
- Shows what will be lost
- Lists specific changes
- Clear action labels
- Safe option first

---

## Microcopy

### Example 11: Button Labels

**❌ Before:**
```
[Submit]
[OK]  
[Continue]
[Next]
```

**Problems:**
- Vague, context-free
- User doesn't know what happens

**✅ After:**
```
[Create pipeline]
[Save changes]  
[Connect to database]
[Schedule pipeline]
```

**Improvements:**
- Specific actions
- Clear outcomes
- Builds confidence

---

### Example 12: Form Helper Text

**❌ Before:**
```
Name: [_____]
```

**Problems:**
- No guidance
- User uncertain what to enter

**✅ After:**
```
Workspace name: [_____]
Choose a name that describes this workspace's purpose
Example: "Sales Analytics" or "Marketing Data"
```

**Improvements:**
- Context provided
- Examples given
- Purpose clear

---

## Documentation

### Example 13: Getting Started Guide

**❌ Before:**
```
Getting Started

To begin using the platform, users must first provision a 
workspace entity within the system. Navigate to the workspace 
creation interface and input the required parameters.
```

**Problems:**
- Overly formal
- Technical jargon
- No clear steps
- Not actionable

**✅ After:**
```
Getting Started

Create your first workspace in 3 steps:

1. Select "Create Workspace" from the home screen
2. Enter a name (like "My First Workspace")
3. Select "Create"

That's it! You're ready to start building pipelines.

Next: [Connect your data →]
```

**Improvements:**
- Direct address
- Numbered steps
- Concrete example
- Clear next step

---

### Example 14: Error Troubleshooting

**❌ Before:**
```
Error Code: ERR_AUTH_FAILED

Cause: Authentication credentials are invalid or have expired.

Resolution: Verify credentials and re-authenticate if necessary.
```

**Problems:**
- Technical language
- Not specific enough
- Vague resolution

**✅ After:**
```
Connection authentication failed

What this means:
Your username or password is incorrect, or your access has expired.

How to fix it:
1. Double-check your username and password
2. If you recently changed your password, update it here
3. If your account is locked, contact your admin
4. Still stuck? [Contact support] with error code: ERR_AUTH_FAILED

Common causes:
• Typing error in password
• Password expired (change it every 90 days)
• Account deactivated by admin
```

**Improvements:**
- Plain language explanation
- Specific steps
- Common causes listed
- Support option clear

---

## Release Notes

### Example 15: Feature Announcement

**❌ Before:**
```
Version 2.4.0 Release Notes

- Added support for OAuth 2.0 authentication protocol
- Implemented pipeline dependency management
- Fixed bug in data transformation engine
- Performance improvements and bug fixes
```

**Problems:**
- Technical jargon
- Doesn't explain benefits
- Boring list format
- No context

**✅ After:**
```
What's New in DataFlow (January 2026)

🔐 Sign in with your work account
You can now sign in using your Google or Microsoft account—
no need to create a separate password!
[Set up single sign-on →]

⛓️ Chain pipelines together
Link pipelines so one starts automatically when another finishes.
Great for complex workflows that need to run in sequence.
[Learn about pipeline dependencies →]

⚡ Faster data transformations
Data transformations now run up to 40% faster, especially for
large datasets over 1 GB.

🐛 Bug fixes
Fixed an issue where scheduled pipelines sometimes skipped runs.
If this affected you, please reschedule your pipelines.
```

**Improvements:**
- User-benefit focused
- Plain language
- Emoji visual markers
- Links to learn more
- Quantified improvements

---

## AI Content

### Example 16: AI Chatbot Response

**❌ Before:**
```
I can help you with that. Please provide more details about
your query so I can assist you better.
```

**Problems:**
- Generic
- Doesn't acknowledge user
- Vague

**✅ After:**
```
I can help you troubleshoot pipeline errors!

To give you the most accurate help, I'll need a few details:
• Which pipeline is having issues?
• What error message are you seeing?
• When did this start happening?

Or, describe the problem in your own words and I'll do my best to help.
```

**Improvements:**
- Specific capability stated
- Asks for concrete info
- Multiple ways to respond
- Encouraging tone

---

### Example 17: AI Disclosure

**❌ Before:**
```
Hello! How can I help you today?
```

**Problems:**
- Doesn't disclose AI
- Implies human
- Not transparent

**✅ After:**
```
👋 Hi! I'm an AI assistant for DataFlow

I can help with:
• Questions about features
• Troubleshooting common issues  
• Finding documentation

I might not always have the answer. When that happens, I'll
connect you with our human support team.

How can I help you today?
```

**Improvements:**
- Clearly discloses AI
- States capabilities
- Admits limitations
- Offers human alternative

---

## Key Takeaways

### What Makes Good Content

✅ **Do:**
- Use plain language
- Be specific and concrete
- Provide clear next steps
- Anticipate questions
- Show empathy
- Give examples
- State limitations honestly

❌ **Don't:**
- Use jargon without explanation
- Be vague or generic
- Leave users stuck
- Hide information
- Sound robotic
- Assume knowledge
- Overpromise

### Common Patterns

**Error messages:** [What happened] + [Why] + [What to do]

**Success messages:** [Confirmation] + [What's next]

**Empty states:** [Positive frame] + [Explanation] + [Clear action]

**Buttons:** [Specific action verb] + [Object]

**Helper text:** [Context] + [Example]

**Confirmations:** [Specific item] + [What will happen] + [Clear choices]

---

*These examples are based on real content design work but have been generalized for educational purposes.*
