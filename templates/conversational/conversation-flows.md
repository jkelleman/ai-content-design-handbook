# Chatbot Conversation Flow Template

A framework for designing clear, helpful conversational experiences for chatbots and AI assistants.

## What are Conversation Flows?

Conversation flows map out how a chatbot guides users through tasks, answers questions, and handles various scenarios. Unlike traditional UI where users click through screens, conversations are dynamic exchanges that adapt to user input.

## Conversation Flow Framework

### 1. Define the Conversation Purpose

**What can the chatbot do?**
- Answer questions
- Guide through tasks
- Troubleshoot problems
- Collect information
- Make recommendations

**What can't it do?**
- Complex judgment calls
- Highly personalized advice
- Actions requiring human approval
- Anything outside its domain

### 2. Map User Intents

Identify what users want to accomplish.

**Example intents:**
```
- get_help_with_error
- create_new_pipeline
- check_pipeline_status
- learn_about_feature
- report_problem
- get_started
- compare_options
```

### 3. Design Conversation Nodes

Each node is a point in the conversation.

**Node structure:**
```yaml
node_id: troubleshoot_connection
trigger: user_intent = get_help_with_error
  
bot_message:
  text: "I can help troubleshoot that error. What type of error are you seeing?"
  
  quick_replies:
    - label: "Connection error"
      next_node: connection_error_flow
    - label: "Permission denied"
      next_node: permission_flow
    - label: "Something else"
      next_node: describe_error
      
fallback: 
  next_node: clarify_error_type
```

### 4. Handle Edge Cases

Plan for when things don't go as expected.

**Common edge cases:**
- User gives unexpected input
- User asks unrelated question mid-flow
- User wants to start over
- User needs to escalate to human
- Bot doesn't understand
- Multiple interpretations possible

## Conversation Flow Patterns

### Pattern 1: Question-Answer Flow

**When to use:** Simple information requests

```
User: "How do I create a pipeline?"

Bot: "I can guide you through creating a pipeline. First, let's choose your data source.

Which type of data source do you want to connect?"

[Button: Database] [Button: File] [Button: API]

User: [Selects Database]

Bot: "Great! Now select your database type:"

[Button: SQL Server] [Button: PostgreSQL] [Button: MySQL]
```

**Structure:**
```yaml
flow: create_pipeline_guided

node_1:
  bot: "Let's choose your data source. Which type?"
  options: ["Database", "File", "API"]
  
node_2_database:
  bot: "Select your database type:"
  options: ["SQL Server", "PostgreSQL", "MySQL"]
  
node_3_sql:
  bot: "Enter your connection details:"
  collect: [server, database, credentials]
  validate: connection_string_format
  next: confirm_connection
```

---

### Pattern 2: Troubleshooting Flow

**When to use:** Diagnosing and solving problems

```
User: "My pipeline failed"

Bot: "I'll help you troubleshoot. Let me ask a few questions.

When did the pipeline last run successfully?"

[Button: Today] [Button: Yesterday] [Button: Over a week ago] [Button: Never]

User: [Yesterday]

Bot: "What error message are you seeing?"

User: "Connection timeout"

Bot: "Connection timeout usually happens when:
• Firewall blocking connection
• Connection string incorrect
• Server not responding

Let's check your firewall settings first. Can you access your firewall configuration?"

[Button: Yes, show me how] [Button: I don't have access] [Button: Skip this]
```

**Structure:**
```yaml
flow: troubleshoot_pipeline_failure

node_1_gather_context:
  bot: "When did the pipeline last run successfully?"
  collect: last_successful_run
  
node_2_identify_error:
  bot: "What error message are you seeing?"
  collect: error_message
  analyze: error_type
  
node_3_solution_branch:
  condition: error_type = "connection_timeout"
  bot: "Connection timeout usually happens when: [causes]"
  next: connection_troubleshooting
  
node_4_guided_fix:
  bot: "Let's check [diagnostic step]"
  options: ["Yes, show me how", "I don't have access", "Skip this"]
```

---

### Pattern 3: Form-Filling Flow

**When to use:** Collecting structured information

```
User: "I need to create a support ticket"

Bot: "I'll help you create a ticket. First, let me get some details.

What's the issue about?"

User: "Pipeline keeps failing"

Bot: "When did this start happening?"

User: "This morning"

Bot: "What's your pipeline name?"

User: "Sales Data Pipeline"

Bot: "Got it. Here's what I have:
• Issue: Pipeline keeps failing
• Started: This morning  
• Pipeline: Sales Data Pipeline

Should I create this ticket?"

[Button: Yes, create it] [Button: Edit details] [Button: Cancel]
```

**Structure:**
```yaml
flow: create_support_ticket

required_fields:
  - issue_description
  - when_started
  - affected_resource
  
node_1:
  bot: "What's the issue about?"
  collect: issue_description
  
node_2:
  bot: "When did this start happening?"
  collect: when_started
  
node_3:
  bot: "What's your pipeline name?"
  collect: affected_resource
  
node_4_confirm:
  bot: "Here's what I have: [summary]. Should I create this ticket?"
  options: ["Yes, create it", "Edit details", "Cancel"]
```

---

### Pattern 4: Recommendation Flow

**When to use:** Helping users choose from options

```
User: "Which pipeline template should I use?"

Bot: "I can help you choose. What type of data are you working with?"

User: "Sales data from Salesforce"

Bot: "And what do you want to do with it?"

[Button: Store in data warehouse]
[Button: Create real-time dashboard]
[Button: Send to another system]

User: [Store in data warehouse]

Bot: "Based on your needs, I recommend the 'Salesforce to Warehouse' template.

This template:
✓ Connects to Salesforce automatically
✓ Transforms data for analytics
✓ Loads to your data warehouse on a schedule

Would you like to use this template?"

[Button: Yes, create from template] [Button: Show other options]
```

**Structure:**
```yaml
flow: recommend_template

node_1_gather_requirements:
  bot: "What type of data are you working with?"
  collect: data_source
  
node_2_intended_use:
  bot: "What do you want to do with it?"
  options: ["Store in warehouse", "Create dashboard", "Send to system"]
  collect: intended_use
  
node_3_generate_recommendation:
  logic: match_template(data_source, intended_use)
  bot: "I recommend [template_name]. [benefits]"
  
node_4_confirm:
  options: ["Yes, create from template", "Show other options"]
```

---

### Pattern 5: Escalation Flow

**When to use:** Transitioning to human support

```
Bot: "I'm not able to resolve this issue. Let me connect you with a support specialist.

Can I get your email to follow up?"

User: "sarah@company.com"

Bot: "Thanks! I've created ticket #12345 and assigned it to our support team.

You should hear back within 4 hours.

Is there anything else I can help with?"

[Button: Yes, something else] [Button: No, that's all]
```

**Structure:**
```yaml
flow: escalate_to_human

node_1_acknowledge_limitation:
  bot: "I'm not able to resolve this. Let me connect you with support."
  
node_2_collect_contact:
  bot: "Can I get your email to follow up?"
  collect: email
  validate: email_format
  
node_3_create_ticket:
  action: create_support_ticket
  bot: "I've created ticket #{ticket_id}. You should hear back within {sla}."
  
node_4_close:
  bot: "Is there anything else I can help with?"
  options: ["Yes, something else", "No, that's all"]
```

## Conversation Design Principles

### 1. Be Conversational, Not Robotic

**❌ Robotic:**
```
"Initiate pipeline creation process"
"Please provide required input parameters"
"Process completed successfully"
```

**✅ Conversational:**
```
"Let's create a pipeline"
"I'll need a few details from you"
"All set! Your pipeline is ready"
```

### 2. Provide Clear Options

**❌ Open-ended (when guidance needed):**
```
Bot: "What would you like to do?"
```

**✅ Structured options:**
```
Bot: "What would you like to do?"
[Button: Create pipeline]
[Button: Check status]
[Button: Get help]
```

### 3. Confirm Understanding

**❌ Assumes understanding:**
```
User: "My pipeline is broken"
Bot: [Launches into troubleshooting]
```

**✅ Confirms:**
```
User: "My pipeline is broken"
Bot: "I'll help you fix that. Is your pipeline failing with an error, or is it not running at all?"
```

### 4. Handle Uncertainty Gracefully

**❌ Pretends to understand:**
```
User: "The thing isn't working"
Bot: "Let me help you fix the connection issue"
```

**✅ Asks for clarification:**
```
User: "The thing isn't working"
Bot: "I want to help! Can you tell me what's not working? For example:
• A pipeline
• A connection
• A dashboard
• Something else"
```

### 5. Provide Escape Hatches

Always let users:
- Start over
- Go back
- Cancel
- Talk to a human
- Exit the conversation

```yaml
global_commands:
  - command: "start over"
    action: reset_to_beginning
  - command: "go back"
    action: previous_node
  - command: "cancel"
    action: exit_flow
  - command: "talk to a human"
    action: escalate_to_support
```

## Conversation Components

### Greeting Messages

**First-time user:**
```
"Hi! I'm the Fabric Assistant. I can help you:
• Create and manage pipelines
• Troubleshoot errors
• Learn about features

What would you like to do?"
```

**Returning user:**
```
"Welcome back! Last time we were setting up your Sales Pipeline.
Want to continue where we left off?"

[Continue setup] [Start something new]
```

### Quick Replies

Suggested responses the user can tap/click:

```yaml
quick_replies:
  - label: "Connection error"
    value: "I'm seeing a connection error"
  - label: "Permission denied"
    value: "I got a permission denied error"
  - label: "Something else"
    value: "My error is different"
```

### Typing Indicators

Show the bot is "thinking":

```
User: "Why did my pipeline fail?"
[Bot is typing...]
Bot: "Let me check your pipeline status..."
[Bot is typing...]
Bot: "I found the issue. Your connection timed out..."
```

### Adaptive Cards / Rich Responses

Go beyond text with interactive elements:

```yaml
card:
  type: adaptive
  title: "Pipeline Status"
  body:
    - Pipeline: Sales Data
    - Status: Failed
    - Error: Connection timeout
    - Last run: 2 hours ago
  actions:
    - button: "Retry now"
      action: retry_pipeline
    - button: "View logs"
      action: open_logs
```

### Confirmations

Always confirm before destructive actions:

```
User: "Delete my pipeline"

Bot: "Just to confirm: you want to delete the 'Sales Data Pipeline'?

This will permanently remove:
• The pipeline configuration
• All run history
• Scheduled runs

This can't be undone."

[Yes, delete it] [No, cancel]
```

## Error Handling

### Bot Doesn't Understand

```
User: "asldfkj aslkdfj"

Bot: "I didn't quite catch that. Could you rephrase?

I can help with:
• Creating pipelines
• Troubleshooting errors
• Checking status"
```

### Disambiguation

```
User: "Check my pipeline"

Bot: "You have 3 pipelines. Which one?
• Sales Data Pipeline
• Marketing Analytics
• Customer Reports"
```

### Out of Scope

```
User: "What's the weather?"

Bot: "I can't help with that, but I'm great at helping with data pipelines!

Would you like to:
• Create a pipeline
• Check pipeline status
• Get help with an error"
```

## Conversation Flow Documentation

### Flow Map Template

```yaml
flow_name: create_pipeline_guided
description: Guides user through creating their first pipeline
entry_points: 
  - user_says: "create pipeline"
  - button_click: "Create new pipeline"
  - intent: create_pipeline

nodes:
  - id: welcome
    type: greeting
    message: "Let's create a pipeline together!"
    next: choose_source
    
  - id: choose_source
    type: question_with_options
    message: "First, choose your data source:"
    options: ["Database", "File", "API"]
    next_mapping:
      Database: database_type
      File: file_type
      API: api_type
      
  - id: database_type
    type: question_with_options
    message: "Select your database:"
    options: ["SQL Server", "PostgreSQL", "MySQL"]
    next: connection_details
    
exit_points:
  - success: pipeline_created
  - cancel: conversation_ended
  - escalate: human_handoff

average_completion_time: "3-5 minutes"
success_rate: 85%
```

## Testing Conversation Flows

### Test Scenarios

**Happy path:**
- User follows intended flow
- Provides expected inputs
- Reaches successful completion

**Alternate paths:**
- User chooses different options
- Uses global commands (cancel, go back)
- Asks clarifying questions mid-flow

**Edge cases:**
- Provides unexpected input
- Asks off-topic questions
- Tries to skip required steps
- Abandons mid-conversation

### Sample Dialogues

Document actual conversation examples:

```
=== Test: Create Pipeline - Happy Path ===

User: "I want to create a pipeline"
Bot: "Let's create a pipeline together! First, choose your data source:"
     [Database] [File] [API]
User: [Clicks Database]
Bot: "Select your database:"
     [SQL Server] [PostgreSQL] [MySQL]
User: [Clicks SQL Server]
Bot: "Great! Now I'll need your connection details..."

Result: ✓ Success
Time: 2min 15sec
```

## Conversation Metrics

Track conversation effectiveness:

- **Completion rate**: % who finish the flow
- **Abandonment points**: Where users drop off
- **Clarification rate**: How often bot asks for clarification
- **Escalation rate**: % escalated to human
- **User satisfaction**: Ratings/feedback

## Related Resources

- [Prompt Design](../ai-content/prompt-design.md)
- [Error Messages](../messages/error-messages.md)
- [Conversational UI Patterns](conversational-ui-patterns.md)
- [Voice and Tone for Chatbots](../../style-guides/chatbot-voice-tone.md)
