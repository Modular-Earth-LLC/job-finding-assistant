# Knowledge Base Management Guide for Job Finding Assistants

## Overview

This guide documents the standardized knowledge base management approach implemented across all AI assistants in the job finding system. Each assistant has specific read/write permissions aligned with their expertise area.

## Knowledge Base Structure

The centralized knowledge base is located at: `inputs/knowledge-bases/job_search_knowledge_base.json`

### Core Sections

1. **metadata** - System information about the knowledge base
2. **usage_instructions** - How to use the knowledge base
3. **user_profile** - Basic information about the job seeker
4. **career_objectives** - Financial, career, family, and lifestyle goals
5. **personal_brand** - Mission, vision, values, and brand narratives
6. **go_to_market_strategy** - Target roles, industries, and positioning
7. **user_personality** - Character traits and communication style

## Assistant Permissions Matrix

| Assistant | Read Access | Write Access | Primary Responsibility |
|-----------|-------------|--------------|------------------------|
| Career Coach | user_profile, career_objectives | user_profile.basic_info, career_objectives | Gather initial requirements and objectives |
| Personal Brand | All sections | personal_brand, user_personality | Develop brand elements and personality profile |
| Market Positioning | All sections | go_to_market_strategy | Create market strategy and positioning |
| Networking Outreach | All sections | None (Read-Only) | Execute content creation based on strategy |

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

## Summary

This knowledge base management system ensures:
- **Consistency**: Standardized operations across all assistants
- **Safety**: Clear boundaries prevent data corruption
- **Flexibility**: System works with or without KB access
- **Simplicity**: Easy for humans and AI to understand
- **Maintainability**: Clear ownership and simple structure
