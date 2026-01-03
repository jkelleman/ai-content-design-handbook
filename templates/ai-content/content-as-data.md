# Content as Data Template

A framework for structuring content so AI systems can retrieve, understand, and generate appropriate responses at scale.

## What is Content as Data?

Traditional content is written for humans to read. Content as data is structured so machines can process, retrieve, and reason about it. This enables AI systems to:
- Find the right content dynamically
- Combine content in new ways
- Generate contextually appropriate responses
- Scale content without writing every variation

## Why Structure Content for AI?

**Traditional approach:**
```
Write 100 variations of an error message for different scenarios
Store each as static text
Display based on if/then logic
```

**Content as data approach:**
```
Define error message components: [issue] + [cause] + [solution]
Structure them as retrievable data
Let AI compose appropriate message based on context
```

**Benefits:**
- Scales better (reusable components)
- More consistent (structured patterns)
- More maintainable (update once, applies everywhere)
- More contextual (adapts to situation)

## Content as Data Framework

### 1. Identify Content Types

Categorize your content by type and purpose.

**Example content types:**
- Error messages
- Help articles
- Product descriptions
- User instructions
- FAQs
- Tooltips
- Success messages

### 2. Define Content Models

Create schemas that structure how content is organized.

**Basic content model:**
```yaml
content_type: error_message
fields:
  - title: string (required, max 60 chars)
  - explanation: string (required, max 200 chars)
  - solution_steps: array[string] (required, 1-3 items)
  - documentation_link: url (optional)
  - severity: enum[info, warning, error, critical]
  - category: enum[connection, permission, validation, system]
  
metadata:
  - id: unique_identifier
  - created: timestamp
  - updated: timestamp
  - author: string
  - status: enum[draft, review, published, archived]
```

**Example instance:**
```yaml
id: err_connection_timeout_sql
content_type: error_message
title: "Connection Timeout"
explanation: "Your pipeline couldn't connect to the SQL database within the timeout period."
solution_steps:
  - "Check your firewall allows connections from Fabric IP addresses"
  - "Verify the connection string is correct in pipeline settings"
  - "Test the connection using the Test Connection button"
documentation_link: "https://docs.example.com/troubleshooting/connections"
severity: error
category: connection
created: 2026-01-02
status: published
```

### 3. Create Content Components

Break content into reusable pieces.

**Component-based structure:**
```
Error Message Components:
├── Issue Statement
│   ├── "Can't connect to [service]"
│   ├── "Unable to load [resource]"
│   └── "[Action] failed"
│
├── Causes
│   ├── "Network connection lost"
│   ├── "Permission denied"
│   └── "Resource not found"
│
└── Solutions
    ├── "Check your internet connection"
    ├── "Verify your permissions"
    └── "Confirm the [resource] exists"
```

**Composition at runtime:**
```
Context: User trying to load dashboard, network error detected

AI composes:
- Issue: "Can't connect to data source"
- Cause: "Network connection lost"
- Solution: "Check your internet connection"

Output:
"Can't connect to data source. Network connection lost. 
Check your internet connection and try again."
```

### 4. Add Metadata for Retrieval

Tag content so AI can find the right piece at the right time.

**Metadata examples:**
```yaml
tags:
  - connection_error
  - sql_database
  - timeout
  - troubleshooting

user_type:
  - data_engineer
  - analyst

experience_level:
  - beginner
  - intermediate

context:
  - pipeline_execution
  - data_refresh

related_concepts:
  - firewall_configuration
  - connection_strings
  - authentication
```

### 5. Design for Retrieval-Augmented Generation (RAG)

Structure content so AI can find and use it.

**RAG-optimized structure:**
```markdown
## Connection Timeout Errors

### Problem
Pipeline fails with "Connection timeout" when connecting to SQL database

### Causes
1. Firewall blocking Fabric IP addresses
2. Incorrect connection string format
3. Database server not responding
4. Network connectivity issues

### Solutions
**Check firewall settings:**
Ensure these IP ranges are allowed: [list]

**Verify connection string:**
Format: Server=myserver;Database=mydb;User Id=myuser;Password=mypass

**Test connectivity:**
Use the Test Connection button before saving pipeline

### Related
- Connection string formats
- Firewall configuration
- Network troubleshooting
```

**Why this works for RAG:**
- Clear heading hierarchy
- Structured sections (Problem, Causes, Solutions)
- Scannable format
- Related concepts linked
- Specific, actionable information

## Content Modeling Patterns

### Pattern 1: Templated Content

Define templates with variables.

```yaml
template: error_message_connection
structure: |
  **Can't connect to {service_name}**
  {explanation}
  
  Try these steps:
  {solutions}
  
  {documentation_link}

variables:
  service_name:
    type: string
    source: context.service
  explanation:
    type: string
    source: error_metadata.description
  solutions:
    type: array
    source: knowledge_base.solutions
    filter: category=connection, service={service_name}
  documentation_link:
    type: url
    source: docs.links
    filter: topic=troubleshooting
```

### Pattern 2: Hierarchical Content

Organize content in parent-child relationships.

```yaml
parent: Data Pipelines
├── child: Creating Pipelines
│   ├── child: Choosing Data Sources
│   ├── child: Configuring Transformations
│   └── child: Setting Up Schedules
├── child: Running Pipelines
│   ├── child: Manual Runs
│   ├── child: Scheduled Runs
│   └── child: Monitoring Status
└── child: Troubleshooting Pipelines
    ├── child: Connection Errors
    ├── child: Permission Issues
    └── child: Performance Problems
```

### Pattern 3: Intent-Based Content

Map content to user intents.

```yaml
intent: troubleshoot_connection_error
content_pieces:
  - type: diagnostic_question
    text: "Are you seeing a timeout error or permission denied?"
    
  - type: conditional_response
    condition: timeout
    content: connection_timeout_guide
    
  - type: conditional_response
    condition: permission
    content: permission_error_guide
    
  - type: escalation
    condition: not_resolved_after_3_attempts
    action: suggest_support_contact
```

### Pattern 4: Variation by Context

Same content, different contexts.

```yaml
base_content: pipeline_creation_guide

variations:
  - context: first_time_user
    emphasis: basic_concepts
    detail_level: high
    examples: simple
    
  - context: experienced_user
    emphasis: advanced_features
    detail_level: low
    examples: complex
    
  - context: migration_scenario
    emphasis: differences_from_previous_tool
    detail_level: medium
    examples: comparison
```

### Pattern 5: Chunked Content

Break long content into AI-digestible pieces.

```yaml
document: data_pipeline_documentation
chunks:
  - chunk_id: 1
    topic: introduction
    content: "Data pipelines move and transform..."
    tokens: 150
    embedding: [vector]
    
  - chunk_id: 2
    topic: data_sources
    content: "Connect to databases, files..."
    tokens: 200
    embedding: [vector]
    
  - chunk_id: 3
    topic: transformations
    content: "Transform data using..."
    tokens: 180
    embedding: [vector]

chunking_strategy:
  method: semantic
  max_tokens: 250
  overlap: 50
  preserve_boundaries: [paragraphs, code_blocks]
```

## Content Schema Examples

### Error Message Schema
```json
{
  "id": "error_001",
  "type": "error_message",
  "title": "Connection Timeout",
  "severity": "error",
  "category": "connection",
  "explanation": "Couldn't connect within timeout period",
  "solutions": [
    {
      "step": 1,
      "action": "Check firewall settings",
      "detail": "Ensure IP ranges are allowed"
    },
    {
      "step": 2,
      "action": "Verify connection string",
      "detail": "Check format and credentials"
    }
  ],
  "related_errors": ["error_002", "error_015"],
  "docs_link": "https://docs.example.com/errors/connection",
  "tags": ["connection", "timeout", "network"]
}
```

### Help Article Schema
```json
{
  "id": "help_123",
  "type": "help_article",
  "title": "How to Create a Data Pipeline",
  "summary": "Learn to move data between sources",
  "difficulty": "beginner",
  "time_to_complete": "5 minutes",
  "prerequisites": ["account_setup"],
  "steps": [
    {
      "number": 1,
      "title": "Choose data source",
      "content": "Select where your data lives...",
      "screenshot": "step1.png"
    }
  ],
  "related_articles": ["help_124", "help_125"],
  "tags": ["getting-started", "pipelines", "tutorial"]
}
```

### Tooltip Schema
```json
{
  "id": "tooltip_45",
  "type": "tooltip",
  "element": "incremental_refresh_toggle",
  "short_description": "Only sync changed data",
  "full_description": "Incremental refresh syncs only data that changed since the last run, reducing processing time and costs",
  "learn_more_link": "https://docs.example.com/incremental-refresh",
  "character_limit": 280,
  "context": ["pipeline_settings", "performance_optimization"]
}
```

## Structuring Content for Different AI Use Cases

### For Chatbots / Conversational UI
```yaml
conversation_node:
  id: troubleshoot_pipeline_failure
  user_intent: get_help_with_error
  
  bot_response:
    text: "I can help with that. What error are you seeing?"
    quick_replies:
      - "Connection error"
      - "Permission denied"
      - "Something else"
  
  next_nodes:
    - condition: user_selects_connection_error
      next: connection_error_flow
    - condition: user_selects_permission
      next: permission_error_flow
    - condition: user_selects_something_else
      next: open_ended_troubleshooting
```

### For Semantic Search
```yaml
searchable_content:
  title: "Connection Timeout Errors"
  content: "Full article text..."
  embedding: [vector representation]
  
  metadata:
    keywords: ["timeout", "connection", "SQL", "firewall"]
    topics: ["troubleshooting", "connections", "errors"]
    user_types: ["data_engineer", "analyst"]
    
  retrieval_hints:
    boost_for_queries: ["can't connect", "timeout error", "SQL connection"]
    rank_higher_when: ["user_has_connection_error", "recent_pipeline_failure"]
```

### For Dynamic Content Generation
```yaml
content_template:
  id: personalized_welcome
  
  variables:
    user_name: from_user_profile
    last_login: from_user_activity
    next_task: from_onboarding_state
    
  generation_rules:
    - if: first_time_user
      include: product_overview
    - if: returning_user
      include: whats_new_since_last_visit
    - if: has_incomplete_onboarding
      include: resume_onboarding_cta
      
  output_format: |
    Hi {user_name}, welcome back!
    {conditional_content}
    {next_task_cta}
```

## Implementation Checklist

**Content Modeling:**
- [ ] Content types identified
- [ ] Schemas defined for each type
- [ ] Fields and data types specified
- [ ] Required vs optional fields marked
- [ ] Validation rules established

**Metadata:**
- [ ] Tags defined
- [ ] Categories established
- [ ] User types mapped
- [ ] Context indicators added
- [ ] Relationships specified

**Retrieval:**
- [ ] Content chunked appropriately
- [ ] Embeddings generated
- [ ] Search keywords defined
- [ ] Relevance signals added
- [ ] Related content linked

**Quality:**
- [ ] Content validated against schema
- [ ] No orphaned content
- [ ] All required fields populated
- [ ] Links verified
- [ ] Duplicates removed

## Tools & Technologies

**Content Management:**
- Headless CMS (Contentful, Sanity)
- Structured content editors
- Version control for content

**AI/ML Integration:**
- Vector databases (Pinecone, Weaviate)
- Embedding models
- RAG frameworks (LangChain, LlamaIndex)

**Validation:**
- Schema validators (JSON Schema)
- Content linters
- Automated testing

## Common Mistakes

**❌ Too granular**
```yaml
# Creating separate entry for every tiny variation
error_001: "Can't connect"
error_002: "Cannot connect"
error_003: "Unable to connect"
```

**✅ Use variables**
```yaml
template: "{connection_verb} to {service}"
variables:
  connection_verb: ["Can't connect", "Unable to connect"]
  service: [from_context]
```

---

**❌ No metadata**
```yaml
# Just storing content without context
content: "Check your connection settings"
```

**✅ Rich metadata**
```yaml
content: "Check your connection settings"
tags: ["troubleshooting", "connection", "settings"]
applies_to: ["sql_database", "api", "file_storage"]
user_level: "beginner"
```

---

**❌ Unstructured content**
```
Long paragraph mixing problems, causes, and solutions all together
making it hard for AI to extract relevant pieces...
```

**✅ Structured sections**
```yaml
problem: "Pipeline fails with timeout"
causes: ["Network issue", "Firewall blocking", "Server down"]
solutions: [
  "Check network connectivity",
  "Verify firewall rules",
  "Confirm server status"
]
```

## Related Resources

- [Prompt Design](prompt-design.md)
- [RAG Content Strategy](rag-content-strategy.md)
- [Content Models](../../resources/content-models.md)
- [Semantic Search Optimization](../../resources/semantic-search.md)
