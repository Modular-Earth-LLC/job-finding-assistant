# Knowledge Base and Configuration Files

## Overview

This directory contains two critical files that power the Job Finding Assistant system:

1. **`job_search_knowledge_base.json`** - User-specific data
2. **`job_assistant_system_config.json`** - System-level configuration

## Separation of Concerns

### job_search_knowledge_base.json

**Purpose**: Stores all user-specific data collected by assistants

**Contains**:
- User profile information (name, email, location)
- Career objectives and goals
- Personal brand elements (mission, vision, values)
- Market positioning strategy
- User personality traits

**Updated by**:
- Career Coach Assistant (Stage 1)
- Personal Brand Development Assistant (Stage 2)
- Job Market Positioning Assistant (Stage 3)

**Read by**:
- All assistants for personalization

### job_assistant_system_config.json

**Purpose**: Defines system-level behavior shared across assistants

**Contains**:
- Workflow architecture and stages
- Communication standards and templates
- Platform compatibility guidelines
- Audience frameworks
- Knowledge base permissions
- Quality standards
- Shared boundaries

**Updated by**:
- System administrators only
- Never contains user data

## Usage Guidelines

### For AI Assistants

1. **Always check for both files** when starting a session
2. **Use the config file** for system behavior and templates
3. **Use the knowledge base** for user personalization
4. **Never mix** user data into the config file

### For Users

1. **Knowledge Base**: Your personal data that makes responses unique to you
2. **Config File**: System rules that ensure consistent, quality assistance

### Example Integration

```python
# Pseudo-code for assistant initialization
if exists("job_assistant_system_config.json"):
    load_system_config()
    apply_workflow_rules()
    set_boundaries()
else:
    use_built_in_defaults()

if exists("job_search_knowledge_base.json"):
    load_user_data()
    personalize_responses()
else:
    ask_user_for_context()
```

## Data Privacy

- **Knowledge Base**: Contains sensitive personal information
- **Config File**: Contains no personal data, safe to share
- **Best Practice**: Keep knowledge base private, config can be open source

## File Structure

### Knowledge Base Structure
```json
{
  "metadata": {...},
  "user_profile": {...},
  "career_objectives": {...},
  "personal_brand": {...},
  "go_to_market_strategy": {...},
  "user_personality": {...}
}
```

### Config File Structure
```json
{
  "metadata": {...},
  "knowledge_base_usage": {...},
  "workflow_architecture": {...},
  "communication_standards": {...},
  "platform_constraints": {...},
  "shared_boundaries": {...},
  "quality_standards": {...}
}
```

## Maintenance

- **Knowledge Base**: Updated frequently by user sessions
- **Config File**: Updated rarely, only for system improvements
- **Version Control**: Config file should be in git, knowledge base should not
