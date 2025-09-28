# Documentation Structure

This document outlines the documentation architecture for the Job Finding Assistant repository.

## Documentation Hierarchy

### Root Level
- **`README.md`** - Main project documentation
  - Project overview and quick start
  - User-focused content
  - Links to technical guides
  - Privacy and troubleshooting

### Technical Guides by Directory

#### `/AI_assistants/`
- **`system_prompts_guide.md`** - How system prompts work
- **`platform_compatibility_guide.md`** - Platform deployment instructions

#### `/inputs/knowledge-bases/`
- **`knowledge_base_management_guide.md`** - Comprehensive guide covering data architecture, CRUD operations, and best practices

## Design Principles

### 1. Single Source of Truth
- Only one README at root level
- Technical guides are named `*_guide.md`
- No duplicate information across documents

### 2. Locality of Documentation
- Guides live near the resources they describe
- System prompt guides with system prompts
- Knowledge base guides with knowledge base files

### 3. Clear Separation
- **README**: User journey and overview
- **Guides**: Technical implementation details
- **Config files**: System behavior definitions

### 4. Progressive Disclosure
- README provides high-level overview
- Links to guides for deeper technical information
- Guides reference each other as needed

## Document Purposes

### README.md
- First-time user orientation
- Success stories and examples
- Quick start instructions
- Links to all technical resources

### system_prompts_guide.md
- System prompt architecture
- Customization guidelines
- Deployment instructions
- Troubleshooting

### platform_compatibility_guide.md
- Platform-specific setup
- Workflow demonstration
- Testing procedures
- Compatibility matrix

### knowledge_base_config_guide.md
- File structure explanation
- Data vs. configuration separation
- Integration patterns
- Privacy considerations

### knowledge_base_management_guide.md
- CRUD operations
- Data validation
- Update procedures
- Best practices

## Navigation Flow

```
README.md
    ├── Quick Start
    ├── Platform Setup → platform_compatibility_guide.md
    ├── Data Architecture → knowledge_base_config_guide.md
    ├── System Prompts → system_prompts_guide.md
    └── KB Management → knowledge_base_management_guide.md
```

## Maintenance Guidelines

1. **Update README** for user-facing changes
2. **Update guides** for technical changes
3. **Cross-reference** when adding new features
4. **No redundancy** - information lives in one place
5. **Clear ownership** - each guide has a specific scope
