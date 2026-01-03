# Release Notes Template

Use this template to write clear, user-focused release notes that highlight value and changes.

## Template Structure

```
# [Product Name] - [Month Year] Release

## What's New
[New features with user benefits]

## Improvements
[Enhancements to existing features]

## Bug Fixes
[Issues resolved]
```

## Release Notes Framework

### 1. Writing Principles

**User-focused:**
- Lead with benefits, not technical details
- Explain "what" and "why", not just "how"
- Use plain language

**Scannable:**
- Use clear headings
- Keep entries brief (1-2 sentences)
- Bullet points over paragraphs

**Honest:**
- Call out breaking changes clearly
- Note deprecations early
- Acknowledge known issues

### 2. Entry Format

```
**[Feature Name]**
[1 sentence describing what it does and why it matters]

[Optional: Screenshot, GIF, or link to documentation]
```

## Examples

### New Feature Entry
```
❌ BAD:
- Added pipeline scheduling functionality

✅ GOOD:
**Schedule pipelines to run automatically**
Set pipelines to run on a schedule so your data stays up to date without manual triggers. Perfect for daily reports and automated workflows.

[Learn about scheduling →]
```

### Improvement Entry
```
❌ BAD:
- Improved performance of data refresh

✅ GOOD:
**Faster data refresh**
Large datasets now refresh up to 3x faster, reducing wait times for big reports.
```

### Bug Fix Entry
```
❌ BAD:
- Fixed bug #1234

✅ GOOD:
**Fixed: Connection errors with Azure SQL Database**
Resolved an issue where connections to Azure SQL would time out during large data transfers.
```

## Release Note Sections

### What's New
For major features, new capabilities, new integrations

```
## What's New

**AI-powered error suggestions**
Get intelligent recommendations to fix pipeline errors. When a pipeline fails, we'll suggest specific fixes based on the error type and your configuration.

**New connector: Salesforce**
Connect to Salesforce data with our new pre-built connector. Supports custom objects, bulk queries, and incremental refresh.
```

### Improvements
For enhancements, performance boosts, UX refinements

```
## Improvements

**Faster search across workspaces**
Search results now load 5x faster, even in workspaces with thousands of pipelines.

**Simplified connection setup**
Reduced connection setup from 5 steps to 3, with auto-detected settings for common configurations.

**Better error messages**
Error messages now include specific next steps and links to relevant documentation.
```

### Bug Fixes
For resolved issues, especially customer-impacting ones

```
## Bug Fixes

**Fixed: Pipeline runs not appearing in history**
Resolved an issue where completed pipeline runs weren't showing in run history for workspaces created before October 2025.

**Fixed: Schedule conflicts when changing time zones**
Pipeline schedules now correctly adjust when you change workspace time zones.
```

### Breaking Changes
For changes that require user action

```
## Breaking Changes

**Updated API authentication**
API keys created before January 2026 will expire on March 1, 2026. [Generate new API keys](link) to maintain access.

**Removed: Legacy import format**
The .v1 import format is no longer supported. Use the migration tool to convert legacy imports to the new format.

[Migration guide →]
```

### Deprecations
For features being phased out

```
## Deprecations

**Classic editor will be retired June 2026**
The classic pipeline editor will be removed in June 2026. We recommend migrating to the new editor, which offers better performance and new features.

[Switch to new editor →]
```

### Known Issues
For problems being worked on

```
## Known Issues

- **Large file uploads may time out**: Working on a fix for uploads over 1GB. Workaround: split files into smaller chunks.
- **Dashboard refresh delays**: Some dashboards may take longer to refresh during peak hours. Fix targeted for next release.
```

## Tone and Voice

**Do:**
- Use "you" and "your"
- Lead with user benefits
- Be conversational but professional
- Use active voice
- Celebrate wins ("Now you can...")

**Don't:**
- Use technical jargon
- Lead with implementation details
- Be overly promotional
- Use passive voice
- Bury important changes

## Release Note Examples by Audience

### For End Users
Focus on value, benefits, how it affects their work

```
**New: Reusable pipeline templates**
Save time by creating templates from your best pipelines. Share templates across your team so everyone can build pipelines faster with proven patterns.
```

### For Developers/Technical Users
Include more technical detail, APIs, code examples

```
**New: REST API for pipeline management**
Programmatically create, update, and monitor pipelines via our new REST API. Includes endpoints for scheduling, run history, and error logs.

[View API documentation →]
```

### For Administrators
Focus on management, security, compliance impacts

```
**Enhanced audit logging**
New audit logs capture all pipeline configuration changes, including who made the change and when. Logs are available in the Admin Center and can be exported for compliance reporting.
```

## Formatting Best Practices

### Use Visual Hierarchy
```
# Product Name - January 2026

## What's New
### AI-powered error suggestions
Get intelligent recommendations...

### New connector: Salesforce
Connect to Salesforce data...

## Improvements
...
```

### Add Visual Assets
- Screenshots for UI changes
- GIFs for interactions
- Icons for feature categories
- Videos for complex features

### Include Links
- Documentation
- Tutorials
- Migration guides
- Related features

## Release Cadence Patterns

### Monthly Releases
```
# Data Factory - January 2026
Full release notes with all sections

# Data Factory - February 2026
Full release notes with all sections
```

### Continuous Deployment
```
# Week of January 15, 2026
- Feature 1
- Feature 2
- Bug fixes

# Week of January 22, 2026
- Feature 3
- Improvements
```

### Version-Based
```
# v2.5.0 - January 15, 2026
Major release notes

# v2.5.1 - January 20, 2026
Patch notes (bug fixes only)
```

## Distribution Strategies

**In-product:**
- "What's New" panel on dashboard
- Badge on navigation for new features
- Inline tooltips for new UI elements

**External:**
- Email to users
- Blog post for major releases
- Social media highlights
- Documentation updates

## Checklist

- [ ] User benefit leads each entry
- [ ] Plain language (no jargon)
- [ ] Proper headings and structure
- [ ] Breaking changes clearly called out
- [ ] Links to documentation included
- [ ] Visual assets where helpful
- [ ] Tone appropriate for audience
- [ ] Known issues acknowledged
- [ ] Clear date and version

## Related Templates

- [Feature Announcement](feature-announcement.md)
- [Documentation](../documentation/help-documentation.md)
