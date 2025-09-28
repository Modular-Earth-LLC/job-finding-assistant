# Knowledge Base Management Guide

This comprehensive guide covers the data architecture, management procedures, and best practices for the Job Finding Assistant knowledge base system.

## System Architecture

The system uses two JSON files with distinct purposes:

1. **`job_search_knowledge_base.json`** - User-specific data storage
2. **`job_assistant_system_config.json`** - System-level agent configuration

### Architectural Separation

- **User Data**: Personal information that customizes assistant responses
- **System Config**: Shared rules and templates that govern assistant behavior
- **Privacy**: User data stays private, config can be open-sourced

## Knowledge Base Structure

Location: `inputs/knowledge-bases/job_search_knowledge_base.json`

### Core Sections

1. **metadata** - System information about the knowledge base
2. **usage_instructions** - How to use the knowledge base
3. **user_profile** - Basic information about the job seeker
4. **career_objectives** - Financial, career, family, and lifestyle goals
5. **personal_brand** - Mission, vision, values, and brand narratives
6. **go_to_market_strategy** - Target roles, industries, and positioning
7. **user_personality** - Character traits and communication style

### System Configuration Structure

Location: `inputs/knowledge-bases/job_assistant_system_config.json`

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

## Assistant Permissions Matrix

| Assistant | Read Access | Write Access | Primary Responsibility |
|-----------|-------------|--------------|------------------------|
| Career Coach | user_profile, career_objectives | user_profile.basic_info, career_objectives | Gather initial requirements and objectives |
| Personal Brand | All sections | personal_brand, user_personality | Develop brand elements and personality profile |
| Market Positioning | All sections | go_to_market_strategy | Create market strategy and positioning |
| Job Application | All sections | None (Read-Only) | Create resumes and application materials |
| Professional Networking | All sections | None (Read-Only) | Build networking content and relationships |

## Knowledge Base Operations

### Standard CRUD Operations

#### Create
- Check if section exists before creating
- Use provided JSON structure templates
- Validate all required fields

#### Read
- Load current state before any operations
- Check for existing data to avoid duplication
- Use data to inform decisions and outputs

#### Update
- Only modify sections within your domain
- Preserve all other existing data
- Include timestamps when appropriate
- Validate JSON syntax before saving

#### Delete
- Assistants do not delete data
- Updates can replace outdated information
- Historical data preservation is preferred

### Data Safety Protocols

1. **Domain Boundaries**: Each assistant only modifies their designated sections
2. **Data Preservation**: Never delete or modify data outside your domain
3. **Validation First**: Always validate JSON structure before updates
4. **Backup in Output**: Include critical data in session outputs
5. **Graceful Degradation**: System works without KB access

## JSON Structure Standards

### Consistent Formatting
- Use descriptive field names
- Include description fields for complex objects
- Maintain consistent nesting levels
- Use arrays for multiple values

### Example Structure
```json
{
  "section_name": {
    "description": "What this section contains",
    "field_name": "value",
    "nested_object": {
      "description": "Nested object purpose",
      "values": ["item1", "item2"]
    },
    "last_updated": "YYYY-MM-DD"
  }
}
```

## Fallback Operations

All assistants must function without knowledge base access:

1. **Request Information**: Ask user for required data
2. **Document Decisions**: Capture all information in session output
3. **Provide JSON Format**: Structure data for manual KB entry
4. **Continue Service**: Deliver full value despite KB unavailability

## Best Practices

### For Human Readability
- Use clear, descriptive field names
- Include inline documentation via description fields
- Maintain logical grouping of related data
- Format JSON with proper indentation

### For AI Agent Parsing
- Consistent structure across all sections
- Predictable field names and types
- Clear permission boundaries
- Self-documenting format

### For System Maintenance
- Simple data model with minimal nesting
- Clear ownership of each section
- Version tracking through timestamps
- No complex relationships or foreign keys

## Integration Guidelines

### When Starting a Session
1. Check KB availability
2. Load relevant sections based on permissions
3. Identify gaps or missing data
4. Plan information gathering if needed

### During Operations
1. Reference KB data for context
2. Validate against existing information
3. Update only authorized sections
4. Maintain data consistency

### When Completing Work
1. Save updates to authorized sections
2. Document changes in session output
3. Provide JSON for manual updates if needed
4. Ensure downstream assistants have required data

## Version Control and Privacy

### Git Configuration

```bash
# The .gitignore file should include:
inputs/knowledge-bases/job_search_knowledge_base.json

# The config file SHOULD be in version control:
# inputs/knowledge-bases/job_assistant_system_config.json
```

### Privacy Best Practices

- **Knowledge Base**: Contains sensitive personal information - keep private
- **Config File**: Contains no personal data - safe to share/open source
- **User Data**: Never commit real user data to public repositories
- **Test Data**: Use anonymized data for testing and examples

## Integration Patterns

### Assistant Initialization

```python
# Pseudo-code for assistant startup
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

### Data Flow

1. Assistant loads system config for behavioral rules
2. Assistant loads knowledge base for user context
3. Assistant applies permissions based on role
4. Assistant performs allowed operations
5. Changes are validated before saving

## Summary

This knowledge base management system ensures:
- **Consistency**: Standardized operations across all assistants
- **Safety**: Clear boundaries prevent data corruption
- **Flexibility**: System works with or without KB access
- **Simplicity**: Easy for humans and AI to understand
- **Maintainability**: Clear ownership and simple structure
