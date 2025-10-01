# Knowledge Base Management Guide

Technical documentation for managing the Job Finding Assistant data architecture.

## Overview

The system uses two JSON files with distinct responsibilities:

| File | Purpose | Modified By | Audience |
|------|---------|------------|----------|
| `job_search_knowledge_base.json` | User-specific career data | Users & AI Assistants | Job seekers |
| `ai_assistants_system_config.json` | System behavior configuration | System administrators | AI engineers |

## File Architecture

### User Knowledge Base

**File**: `job_search_knowledge_base.json`  
**Purpose**: Stores personal career information that personalizes AI responses

```json
{
  "metadata": {
    "name": "Job Finding Assistant Knowledge Base",
    "version": "1.2",
    "last_updated": "ISO-8601 timestamp"
  },
  "user_profile": {
    "basic_info": {},      // Stage 1: Career Coach writes
    "social_media_links": {} 
  },
  "career_objectives": {},  // Stage 1: Career Coach writes
  "personal_brand": {},     // Stage 2: Personal Brand writes
  "user_personality": {},   // Stage 2: Personal Brand writes
  "go_to_market_strategy": {}, // Stage 3: Market Positioning writes
  "website_configuration": {}  // Stage 4A: Website Generator writes
}
```

### System Configuration

**File**: `ai_assistants_system_config.json`  
**Purpose**: Defines assistant behavior, workflows, and standards

```json
{
  "metadata": {},
  "workflow_architecture": {
    "stages": []  // Defines 5-stage workflow
  },
  "knowledge_base_permissions": {
    // Read/write matrix per assistant
  },
  "communication_standards": {
    // Templates and guidelines
  },
  "platform_constraints": {
    // Platform-specific limits
  }
}
```

## CRUD Operations

### CREATE Operations

**When**: Section doesn't exist  
**Who**: Authorized assistant per permission matrix  
**How**:
```python
def create_section(kb_data, section_name, content):
    if section_name not in kb_data:
        kb_data[section_name] = content
        kb_data['metadata']['last_updated'] = datetime.now().isoformat()
    return kb_data
```

### READ Operations

**When**: Every assistant initialization  
**Who**: All assistants (read permissions vary)  
**How**:
```python
def read_knowledge_base(file_path):
    try:
        with open(file_path, 'r') as f:
            return json.load(f)
    except FileNotFoundError:
        return None  # Trigger conversational mode
```

### UPDATE Operations

**When**: Assistant completes data gathering  
**Who**: Only authorized assistants  
**How**:
```python
def update_section(kb_data, section_name, updates):
    if has_write_permission(current_assistant, section_name):
        kb_data[section_name].update(updates)
        kb_data['metadata']['last_updated'] = datetime.now().isoformat()
    return kb_data
```

### DELETE Operations

**Policy**: No deletion, only updates  
**Reason**: Preserve audit trail and user data

## Permission Matrix

| Assistant | Read Permissions | Write Permissions |
|-----------|-----------------|-------------------|
| Career Coach | `user_profile`, `career_objectives` | `user_profile.basic_info`, `career_objectives` |
| Personal Brand | All sections | `personal_brand`, `user_personality` |
| Market Positioning | All sections | `go_to_market_strategy` |
| Website Generator | All sections | `website_configuration` |
| Job Application | All sections | None (read-only) |
| Professional Networking | All sections | None (read-only) |

## Data Validation

### Schema Validation

```python
def validate_knowledge_base(kb_data):
    required_fields = ['metadata', 'user_profile']
    
    # Check required fields
    for field in required_fields:
        if field not in kb_data:
            raise ValidationError(f"Missing required field: {field}")
    
    # Validate metadata
    if 'version' not in kb_data['metadata']:
        kb_data['metadata']['version'] = '1.1'
    
    # Validate date format
    try:
        datetime.fromisoformat(kb_data['metadata'].get('last_updated', ''))
    except:
        kb_data['metadata']['last_updated'] = datetime.now().isoformat()
    
    return kb_data
```

### Type Checking

```python
SCHEMA = {
    'user_profile': {
        'basic_info': {
            'name': str,
            'email': str,
            'primary_location': str
        }
    },
    'career_objectives': {
        'objectives_by_category': dict,
        'timeline_constraints': dict
    },
    'website_configuration': {
        'last_updated': (str, type(None)),
        'target_platform': (str, type(None)),
        'design_preferences': dict,
        'content_sections': dict,
        'customizations': dict,
        'generated_websites': list
    }
}
```

## Integration Patterns

### Multi-Platform Knowledge Sharing

For platforms with file access (e.g., OpenAI GPTs):
```python
# Direct file operations
kb = load_json('job_search_knowledge_base.json')
config = load_json('ai_assistants_system_config.json')
```

For platforms without file access:
```python
# Conversational state management
kb_state = request_from_user("Please paste your knowledge base")
config = load_default_config()
```

### Synchronization Strategy

1. **Lock-free reads**: Multiple assistants can read simultaneously
2. **Sequential writes**: Only one assistant writes per session
3. **Version tracking**: Use `last_updated` for conflict detection
4. **Merge strategy**: Latest write wins with user confirmation

### Website Configuration Section

**Purpose**: Stores website design preferences and platform selections for portfolio website generation.

**Structure**:
```json
{
  "website_configuration": {
    "description": "Website design preferences and platform selections",
    "last_updated": "2025-10-01T12:00:00Z",
    "target_platform": "Notion|Eleventy|Jekyll|Astro",
    "design_preferences": {
      "color_scheme": "professional|modern|creative",
      "layout_style": "minimalist|detailed|storytelling",
      "content_focus": "technical|business|balanced"
    },
    "content_sections": {
      "hero": true,
      "mission_vision": true,
      "value_proposition": true,
      "skills": true,
      "projects": true,
      "contact": true
    },
    "customizations": {
      "featured_projects": ["Project 1", "Project 2"],
      "highlighted_skills": ["Skill 1", "Skill 2"],
      "industry_focus": "Healthcare|FinTech|AI"
    },
    "generated_websites": [
      {
        "platform": "Notion",
        "generated_date": "2025-10-01T12:00:00Z",
        "url": "https://notion.site/...",
        "version": "1.0"
      }
    ]
  }
}
```

**Access Control**:
- **Read**: All assistants (especially Stage 4B/4C for including website links)
- **Write**: Only Website Generator (Stage 4A)
- **Scope**: Limited to `website_configuration` section only - NEVER modifies `go_to_market_strategy`, `personal_brand`, or other sections

**Safe Operations**:
```python
def update_website_config(kb_data, config_updates):
    """Safely update website configuration"""
    # Validate assistant has permission
    if current_assistant != 'website_generator':
        raise PermissionError("Only Website Generator can modify website_configuration")
    
    # Update only website_configuration section
    kb_data['website_configuration'].update(config_updates)
    kb_data['website_configuration']['last_updated'] = datetime.now().isoformat()
    
    # Preserve all other sections unchanged
    return kb_data
```

**Validation Rules**:
- `target_platform` must be one of: "Notion", "Eleventy", "Jekyll", "Astro", or null
- `design_preferences` values must match predefined options
- `content_sections` values must be boolean
- `generated_websites` must be a list of objects with required fields
- `last_updated` must be ISO-8601 format or null

## Security Considerations

### Data Privacy

```python
SENSITIVE_FIELDS = [
    'user_profile.basic_info.email',
    'user_profile.basic_info.phone',
    'career_objectives.financial'
]

def sanitize_for_sharing(kb_data):
    """Remove sensitive data before sharing"""
    sanitized = deepcopy(kb_data)
    for field_path in SENSITIVE_FIELDS:
        remove_nested_field(sanitized, field_path)
    return sanitized
```

### Access Control

```python
def check_permissions(assistant_id, operation, field):
    config = load_system_config()
    permissions = config['knowledge_base_permissions'][assistant_id]
    
    if operation == 'read':
        return field in permissions['read']
    elif operation == 'write':
        return field in permissions['write']
    return False
```

## Error Handling

Error handling protocols are defined in the system configuration file (`ai_assistants_system_config.json`) under the `knowledge_base_operations` section. All AI assistants reference these protocols directly from the system configuration.

Key error scenarios handled:
- File not found
- Invalid JSON format
- Permission errors
- Generic errors

All knowledge base modifications require explicit user approval as defined in the system configuration.

## Deployment Architectures

### Single User (Local)
```
User Machine
├── job_search_knowledge_base.json (git-ignored)
├── ai_assistants_system_config.json (version controlled)
└── AI Platform Sessions (ephemeral)
```

### Multi-User (Cloud)
```
Cloud Storage (User-Specific)
├── users/
│   ├── user_001/kb.json
│   ├── user_002/kb.json
│   └── ...
└── shared/
    └── system_config.json (cached globally)
```

### Enterprise Deployment
```python
class KnowledgeBaseService:
    def __init__(self, storage_backend):
        self.storage = storage_backend  # S3, Azure, GCS
        self.cache = Redis()
        
    async def get_user_kb(self, user_id):
        # Check cache first
        if cached := self.cache.get(f"kb:{user_id}"):
            return json.loads(cached)
        
        # Load from storage
        kb = await self.storage.get(f"users/{user_id}/kb.json")
        self.cache.set(f"kb:{user_id}", json.dumps(kb), ex=3600)
        return kb
```

## Monitoring and Debugging

### Audit Logging
```python
def log_kb_operation(user_id, assistant_id, operation, field):
    log_entry = {
        'timestamp': datetime.now().isoformat(),
        'user_id': user_id,
        'assistant_id': assistant_id,
        'operation': operation,
        'field': field
    }
    append_to_audit_log(log_entry)
```

### Common Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| Missing fields | Incomplete workflow | Run missing assistant stages |
| Permission denied | Wrong assistant | Check permission matrix |
| Validation errors | Schema mismatch | Update to latest version |
| Sync conflicts | Concurrent edits | Use timestamp-based merge |

## Best Practices

### For System Administrators

1. **Version Control**: Keep system config in git
2. **Backup Strategy**: Regular snapshots of user KBs
3. **Migration Planning**: Version upgrade paths
4. **Monitoring**: Track usage and errors

### For Developers

1. **Atomic Updates**: Write complete sections
2. **Validation First**: Check before writing
3. **Graceful Degradation**: Handle missing KB
4. **Clear Errors**: User-friendly messages

### For Data Engineers

1. **Schema Evolution**: Backward compatibility
2. **Data Pipeline**: ETL for analytics
3. **Privacy Compliance**: GDPR/CCPA considerations
4. **Performance**: Optimize for read-heavy workload

## API Reference

### Core Functions
```python
load_knowledge_base(path: str) -> dict
save_knowledge_base(path: str, data: dict) -> bool
validate_schema(data: dict) -> bool
check_permissions(assistant: str, op: str, field: str) -> bool
merge_updates(base: dict, updates: dict) -> dict
```

### Error Codes
- `KB001`: File not found
- `KB002`: Invalid JSON
- `KB003`: Schema validation failed
- `KB004`: Permission denied
- `KB005`: Merge conflict

---
*For implementation examples, see the system prompts in `AI_assistants/` directory.*