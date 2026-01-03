# Error Message Template

Use this template to write clear, actionable error messages that help users recover quickly.

## Template Structure

```
[Clear statement of what went wrong]

[Why it happened - optional, only if it helps user understanding]

[What the user can do to fix it]
```

## Error Message Framework

### 1. Identify the Error Type

- **System error** - Something broke on our end
- **User input error** - Invalid or missing information
- **Permission error** - User lacks access
- **Connection error** - Network or service unavailable
- **Data error** - Problem with data format or state

### 2. Write the Error Message

**Error Title (H3 or dialog title):**
- Start with what failed: "Unable to [action]" or "[Feature] isn't available"
- Keep to 10 words or fewer
- Don't use technical jargon or error codes in the title

**Error Body:**
- Explain briefly what happened
- Provide a clear next step
- Use plain language
- Be specific about what the user should do

### 3. Error Message Checklist

- [ ] Uses plain language (no jargon)
- [ ] Explains what happened
- [ ] Provides a clear action
- [ ] Maintains appropriate tone (empathetic, not blaming)
- [ ] Avoids technical error codes (put those in details/logs)
- [ ] Is specific, not generic

## Examples

### System Error
```
❌ BAD:
Error 500: Internal Server Error

✅ GOOD:
**Something went wrong**
We're having trouble loading your data. Try refreshing the page, or check back in a few minutes.
```

### User Input Error
```
❌ BAD:
Invalid input

✅ GOOD:
**Email address is required**
Enter your email address to continue.
```

### Permission Error
```
❌ BAD:
Access denied

✅ GOOD:
**You don't have permission to edit this file**
Contact the file owner to request edit access.
```

### Connection Error
```
❌ BAD:
Connection timeout

✅ GOOD:
**Can't connect to the server**
Check your internet connection and try again.
```

## Tone Guidance

**For critical errors:**
- Be direct and clear
- Focus on next steps
- Provide support contact if needed

**For minor errors:**
- Stay friendly and encouraging
- Reassure the user
- Make recovery feel easy

**Never:**
- Blame the user ("You entered invalid data")
- Use technical jargon
- Create anxiety without providing solutions
- Use ALL CAPS or excessive punctuation

## Advanced: Error States

Consider these additional elements:

- **Inline errors** - Show next to the problem field
- **Banner errors** - For page-level issues
- **Toast notifications** - For background operations
- **Empty states** - When errors prevent content display
- **Recovery actions** - Buttons or links to fix the issue

## Related Templates

- [Empty State Template](../flows/empty-states.md)
- [Confirmation Dialog Template](../flows/confirmation-dialogs.md)
- [Form Validation Template](../messages/form-validation.md)
