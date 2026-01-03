# Prompt Design Template

A framework for designing effective prompts that guide AI systems to generate useful, consistent, brand-aligned content.

## What is Prompt Design?

Prompts are instructions that tell an AI system how to generate language. Unlike traditional content where you write every word, prompt design means writing the rules that govern how AI writes.

**Prompt design includes:**
- System instructions (role, behavior, constraints)
- Context (what the AI needs to know)
- Task instructions (what to do)
- Output format (how to structure the response)
- Examples (few-shot learning)

## Prompt Design Framework

### 1. Define the Role & Behavior

Tell the AI what role it's playing and how it should behave.

```
You are a helpful data assistant for Microsoft Fabric. You provide clear, 
accurate guidance about data pipelines, transformations, and analytics.

Behavior guidelines:
- Be concise and technical when appropriate
- Use active voice
- Provide specific next steps
- Acknowledge uncertainty rather than guessing
- Escalate complex issues to human support
```

### 2. Establish Context

Provide relevant information the AI needs to generate appropriate responses.

```
Context:
- User: Data engineer with 3+ years experience
- Product: Microsoft Fabric Data Pipelines
- Current task: Troubleshooting pipeline failure
- Error type: Connection timeout
```

### 3. Define the Task

Clearly state what the AI should do.

```
Task: Generate a helpful error message that:
1. Explains what went wrong
2. Provides 2-3 specific troubleshooting steps
3. Links to relevant documentation
4. Maintains a helpful, non-blaming tone
```

### 4. Specify Output Format

Structure how the response should be formatted.

```
Output format:
**[Error Title]**
[1-2 sentence explanation]

Try these steps:
1. [First action]
2. [Second action]  
3. [Third action]

[Link to documentation]
```

### 5. Provide Examples (Optional)

Show the AI what good outputs look like.

```
Example:
Input: "Pipeline failed with error 'Connection timeout to SQL database'"

Output:
**Connection Timeout**
Your pipeline couldn't connect to the SQL database within the timeout period.

Try these steps:
1. Check your firewall allows connections from Fabric IP addresses
2. Verify the connection string is correct in pipeline settings
3. Test the connection using the "Test Connection" button

[Learn about connection troubleshooting →]
```

## Prompt Design Patterns

### Pattern 1: Content Generation
**When to use:** Creating new content from scratch

```
Role: Content designer for [Product]
Task: Write an onboarding message for first-time users

Context:
- User just signed up
- Product helps with [use case]
- Goal: Get user to complete first action

Tone: Welcoming, encouraging, brief

Output: 
- Heading (5-7 words)
- Body text (2-3 sentences)
- Primary CTA button label
- Optional secondary action

Example:
**Welcome to Data Pipelines**
You're set to move and transform data across sources. Let's create your first pipeline.

[Create pipeline] [Watch tutorial →]
```

### Pattern 2: Content Transformation
**When to use:** Adapting existing content

```
Role: Content editor

Task: Simplify this technical documentation for beginners

Input: [paste technical content]

Guidelines:
- Replace jargon with plain language
- Break long sentences into shorter ones
- Add examples for complex concepts
- Maintain technical accuracy
- Target 8th grade reading level

Output: Simplified version with same meaning
```

### Pattern 3: Content Variation
**When to use:** Creating multiple versions

```
Role: Microcopy specialist

Task: Generate 5 variations of this error message

Original: "Invalid input"

Requirements:
- Specific about what's invalid
- Actionable
- 10 words or fewer
- Maintains helpful tone
- Uses active voice

Output format:
1. [Variation]
2. [Variation]
3. [Variation]
4. [Variation]
5. [Variation]
```

### Pattern 4: Content Evaluation
**When to use:** Assessing content quality

```
Role: Content quality reviewer

Task: Evaluate this error message against our standards

Error message: [paste content]

Evaluation criteria:
- Clarity (1-5): Is it easy to understand?
- Actionability (1-5): Does it provide clear next steps?
- Tone (1-5): Is it helpful and non-blaming?
- Specificity (1-5): Does it explain what went wrong?

Output:
- Score for each criterion
- 2-3 specific improvements
- Rewritten version if needed
```

### Pattern 5: Contextual Response
**When to use:** Dynamic, situation-specific content

```
Role: Support assistant

Context: 
- User action: [what user did]
- System state: [current state]
- Error/Issue: [what happened]
- User expertise: [beginner/intermediate/expert]

Task: Generate a contextually appropriate help message

Adapt response based on:
- Beginner: More explanation, simpler language
- Intermediate: Balanced detail, assumes some knowledge
- Expert: Brief, technical, skip basics

Output: Contextual response matching user level
```

## Advanced Prompt Techniques

### Chain-of-Thought Prompting
Guide the AI through reasoning steps.

```
Before generating the content, think through:
1. What is the user trying to accomplish?
2. What obstacles might they face?
3. What information do they need most?
4. What tone is appropriate for this situation?

Then generate the response based on this analysis.
```

### Few-Shot Learning
Provide multiple examples to establish patterns.

```
Generate error messages in this style:

Example 1:
Input: "File not found"
Output: "Can't find '[filename]'" 
        "Check that the file exists and you have permission to access it."

Example 2:
Input: "Network error"
Output: "Can't connect to the server"
        "Check your internet connection and try again."

Example 3:
Input: "Invalid password"
Output: "Password is incorrect"
        "Try again or reset your password."

Now generate: [your input]
```

### Constraint-Based Prompting
Set clear boundaries and limitations.

```
Constraints:
- Maximum 280 characters (Twitter length)
- No technical jargon
- No exclamation marks
- Must include one actionable verb
- Cannot mention competitors
- Must be accessible to non-native English speakers

Generate: [task]
```

### Iterative Refinement
Build prompts that improve outputs through conversation.

```
Initial prompt: Generate an error message for [scenario]

If output is too technical: "Simplify this for a non-technical user"
If output is too vague: "Be more specific about what went wrong"
If output is too long: "Reduce to under 100 characters"
If tone is off: "Make the tone more [empathetic/professional/casual]"
```

## Prompt Design Checklist

**Role & Behavior:**
- [ ] Clear role definition
- [ ] Behavior guidelines specified
- [ ] Tone and voice established
- [ ] Constraints defined

**Context:**
- [ ] User type identified
- [ ] Product/feature specified
- [ ] Situation described
- [ ] Relevant data provided

**Task:**
- [ ] Clear instruction
- [ ] Success criteria defined
- [ ] Edge cases considered
- [ ] Output requirements specified

**Examples:**
- [ ] Relevant examples provided
- [ ] Good and bad examples shown
- [ ] Patterns demonstrated
- [ ] Variations covered

**Quality:**
- [ ] Prompt is clear and unambiguous
- [ ] Prompt is concise (not overly verbose)
- [ ] Prompt anticipates misinterpretation
- [ ] Prompt includes error handling

## Testing Your Prompts

### Test for Consistency
Run the same prompt multiple times. Do you get consistent quality and format?

### Test for Edge Cases
Try boundary conditions:
- Empty input
- Very long input
- Unexpected formats
- Extreme scenarios

### Test for Bias
Check if outputs show:
- Gender bias
- Cultural bias
- Accessibility issues
- Assumptions about users

### Test for Safety
Verify outputs don't:
- Provide harmful advice
- Share sensitive information
- Make inappropriate suggestions
- Violate policies

## Common Prompt Design Mistakes

**❌ Too Vague**
```
"Write something helpful"
```

**✅ Specific**
```
"Write a 2-sentence tooltip explaining what 'incremental refresh' means, 
targeted at data analysts who are new to the product"
```

---

**❌ Conflicting Instructions**
```
"Be very brief but provide detailed explanations"
```

**✅ Clear Priorities**
```
"Be concise (under 100 words). Prioritize actionability over completeness."
```

---

**❌ Assumes Too Much**
```
"Generate the standard response"
```

**✅ Explicit**
```
"Generate an error message following this format: [format]. Use this tone: [tone]."
```

---

**❌ No Examples**
```
"Match our brand voice"
```

**✅ Examples Provided**
```
"Match this brand voice:
Example 1: [good example]
Example 2: [good example]
Now generate: [task]"
```

## Prompt Libraries

Organize reusable prompts by category:

**Error Messages**
- Connection errors
- Permission errors
- Validation errors
- System errors

**Success Messages**
- Creation confirmation
- Update confirmation
- Deletion confirmation

**Help Content**
- Tooltips
- Inline help
- Getting started guides

**Microcopy**
- Button labels
- Link text
- Form labels
- Placeholder text

## Prompt Versioning

Track prompt changes like code:

```
Version: 2.1
Date: 2026-01-02
Changes: Added constraint for 280 char limit, updated examples

Previous version: 2.0
Reason for change: Outputs were too verbose for mobile
```

## Collaboration with Engineers

### Handoff Format

Provide prompts in engineer-friendly format:

```json
{
  "prompt_id": "error_connection_timeout",
  "version": "1.0",
  "system_instruction": "You are a helpful assistant...",
  "context": {
    "user_type": "data_engineer",
    "error_type": "connection_timeout"
  },
  "template": "**{error_title}**\n{explanation}\n\nTry these steps:\n1. {step1}\n2. {step2}",
  "parameters": {
    "max_tokens": 200,
    "temperature": 0.3
  }
}
```

### Testing Criteria

Define success metrics with engineering:
- Response time (< 500ms)
- Token usage (< 150 tokens)
- Consistency (90%+ similar responses)
- Safety (0% policy violations)

## Resources

**Prompt Engineering Guides:**
- [OpenAI Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering)
- [Anthropic Prompt Guide](https://docs.anthropic.com/claude/docs/prompt-engineering)
- [Google AI Prompt Best Practices](https://ai.google.dev/docs/prompt_best_practices)

**Tools:**
- Prompt testing platforms
- Version control for prompts
- A/B testing for prompt variations

## Related Templates

- [Conversational UI Patterns](../conversational/conversation-flows.md)
- [AI Content Strategy](ai-content-strategy.md)
- [Content Evaluation](../../workflows/content-evaluation.md)
