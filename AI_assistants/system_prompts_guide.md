# System Prompts Guide

This guide explains the structure and usage of the Job Finding Assistant system prompts.

## Directory Structure

```
AI_assistants/
├── career_coach_assistant.system.prompt.md
├── personal_brand_development_assistant.system.prompt.md
├── job_market_positioning.system.prompt.md
├── professional_website_generator.system.prompt.md
├── job_application_interview_assistant.system.prompt.md
├── professional_networking_assistant.system.prompt.md
└── system_prompts_guide.md (this file)
```

## System Prompt Architecture

Each `.system.prompt.md` file contains a complete AI assistant specification designed for copy-paste deployment into AI platforms.

### Standard Sections

1. **System Configuration**
   - References shared configuration file
   - Defines workflow position
   - Lists dependencies

2. **Role and Mission**
   - Defines the assistant's expertise
   - States primary objectives
   - Sets operational boundaries

3. **Knowledge Base Integration**
   - Read/write permissions
   - Data access patterns
   - File handling protocols

4. **Core Capabilities**
   - Specific features and functions
   - Process methodologies
   - Output formats

5. **Platform Compatibility**
   - Works on ChatGPT, Claude, Mistral
   - No external dependencies
   - Conversation-based operation

## Technical Implementation

### Prompt Structure
Each prompt is self-contained and includes:
- Role definition and expertise areas
- Workflow stage positioning
- Knowledge base permissions
- Input/output specifications
- Platform compatibility layer

### Knowledge Base Integration
Prompts are designed to work with two configuration files:
- `job_search_knowledge_base.json` - User-specific data
- `ai_assistants_system_config.json` - System configuration

See the [Installation Guide](../INSTALLATION_GUIDE.md) for platform-specific deployment instructions.

## Workflow Integration

The assistants follow a staged workflow:

```
Stage 1: Career Coach
    ├── Gathers objectives
    └── Creates foundation

Stage 2: Personal Brand
    ├── Develops identity
    └── Documents values

Stage 3: Market Positioning
    ├── Creates strategy
    └── Defines targets

Stage 4A: Website Generator
    ├── Translates GTM to web presence
    └── Creates portfolio sites

Stage 4B: Job Application
    ├── Creates resumes
    └── Writes cover letters

Stage 4C: Professional Networking
    ├── Builds connections
    └── Creates content
```

## Customization Guidelines

### Modifying Prompts
- Maintain section structure
- Preserve variable placeholders
- Keep platform compatibility
- Test changes thoroughly

### Adding Features
- Follow existing patterns
- Update capabilities section
- Document new functions
- Maintain boundaries

### Platform-Specific Adjustments
- ChatGPT: Can enable web browsing
- Claude: Leverage project features
- Mistral: Optimize for token limits

## Best Practices

1. **Version Control**
   - Track prompt changes
   - Document modifications
   - Test before deploying

2. **Consistency**
   - Use shared configuration
   - Follow naming conventions
   - Maintain uniform structure

3. **Testing**
   - Run through complete workflow
   - Verify outputs format correctly
   - Check platform compatibility

## Standardized Components

To reduce redundancy across assistants, all prompts should reference these shared elements from the system configuration:

### Required References

All assistants MUST include:

```markdown
## System Configuration

**Note**: When available, reference the shared configuration at `inputs/knowledge-bases/ai_assistants_system_config.json` for:
- Workflow architecture and stage definitions
- Platform compatibility guidelines
- Communication standards
- Knowledge base operations
- Error handling protocols
```

### Platform Compatibility

Instead of repeating platform details, use:

```markdown
See system configuration for platform-specific capabilities and constraints.
```

### Error Handling

Reference the centralized protocols:

```markdown
Follow error handling protocols defined in system configuration under `knowledge_base_operations.error_handling`
```

### User Approval

Use the standardized process:

```markdown
Require user approval before any KB modifications per system configuration under `knowledge_base_operations.data_validation.user_approval`
```

This approach ensures consistency while reducing prompt size and maintenance burden.

## Troubleshooting

### Common Issues

**Assistant doesn't recognize role**
- Ensure complete prompt was pasted
- Check for truncation
- Restart conversation

**Knowledge base not detected**
- Verify file names exactly match
- Check file upload succeeded
- Use conversation mode as fallback

**Outputs not structured**
- Request specific format
- Reference example outputs
- Ensure all context provided

## Maintenance

### Regular Updates
- Review for accuracy quarterly
- Update platform compatibility
- Enhance based on user feedback

### Breaking Changes
- Document in changelog
- Update all dependent prompts
- Test full workflow

### Deprecation
- Mark obsolete sections clearly
- Provide migration path
- Maintain backward compatibility
