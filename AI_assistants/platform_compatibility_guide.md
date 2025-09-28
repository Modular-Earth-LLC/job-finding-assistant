# Platform Compatibility Guide

This guide provides technical instructions for deploying the Job Finding Assistant system prompts across different AI platforms.

## System Architecture

The system consists of five specialized assistants designed to work as standalone agents without file system dependencies. Each operates through conversational interfaces, accepting pasted inputs and providing structured outputs.

## Supported Platforms

### ✅ Fully Compatible
- **OpenAI ChatGPT** (GPT-4, GPT-4 Turbo)
- **Anthropic Claude** (Claude 3 Opus, Sonnet, Haiku)
- **Mistral Le Chat Pro**

## Assistant Workflow

### Stage 1: Career Coach Assistant
**Input**: None required (starts fresh)
**Process**: Conversational consultation
**Output**: Career objectives summary (markdown + JSON)

### Stage 2: Personal Brand Development Assistant
**Input**: Paste career objectives from Stage 1
**Process**: Brand discovery workshops
**Output**: Personal brand profile (markdown + JSON)

### Stage 3: Job Market Positioning Assistant
**Input**: Paste outputs from Stages 1 & 2
**Process**: Strategy development dialogue
**Output**: Go-to-market strategy (markdown + JSON)

### Stage 4A: Job Application & Interview Assistant
**Input**: Paste outputs from Stages 1-3 + job description
**Process**: Application material creation
**Output**: ATS-optimized resumes, cover letters, interview materials

### Stage 4B: Professional Networking Assistant
**Input**: Paste outputs from Stages 1-3 + target information
**Process**: Relationship building content
**Output**: LinkedIn messages, connection requests, thought leadership

## Data Flow Architecture

```
[Career Coach Assistant] 
    ↓ (objectives summary)
[Personal Brand Development]
    ↓ (brand profile)
[Job Market Positioning]
    ↓ (go-to-market strategy)
    ├─→ [Job Application Assistant]
    │      ↓
    │   [Resumes, Cover Letters]
    │
    └─→ [Professional Networking Assistant]
           ↓
       [Networking Content]
```

## Setting Up Custom GPTs/Agents

### OpenAI ChatGPT Custom GPTs
1. Go to "Explore GPTs" → "Create a GPT"
2. Copy the entire system prompt into the Instructions field
3. Set capabilities (web browsing, etc. as needed)
4. No additional actions or knowledge files required
5. Test with sample conversations

### Anthropic Claude Projects
1. Create a new Project
2. Add the system prompt as Project Instructions
3. No file uploads needed
4. Test the conversational flow

### Mistral Le Chat Agents
1. Create new Agent
2. Paste system prompt as instructions
3. Configure agent settings
4. Test with sample inputs

## Testing Your Setup

### Test Script for Each Assistant

#### Career Coach Test
```
User: "I need help defining my career objectives for a job search."
[Assistant should start consultation process]
```

#### Personal Brand Test
```
User: "I have my career objectives from a previous session. Here they are: [paste sample]. Can you help me develop my personal brand?"
[Assistant should begin brand workshops]
```

#### Market Positioning Test
```
User: "I have my career objectives and personal brand documentation. Can you help me create a go-to-market strategy?"
[Assistant should ask for the documents]
```

#### Job Application Test
```
User: "I need a resume and cover letter for a Director of AI role at a healthcare company. I have my strategy documentation ready."
[Assistant should ask for documents and job description]
```

#### Professional Networking Test
```
User: "I need LinkedIn outreach messages to connect with AI leaders in healthcare. I have my strategy documentation ready."
[Assistant should ask for documents and target details]
```

## Common Issues and Solutions

### Issue: Assistant asks for file access
**Solution**: Remind it to work in conversation mode: "Please work through our conversation without file access"

### Issue: Output too complex to copy
**Solution**: Ask for simplified version: "Please provide a simplified version that's easy to copy and paste"

### Issue: Assistant forgets context
**Solution**: Re-paste the key information and continue

### Issue: Character limits exceeded
**Solution**: Ask for platform-specific version: "Please provide a version under 300 characters for LinkedIn"

## Best Practices

### For Users
1. Save outputs from each assistant in a document
2. Copy entire sections when moving between assistants
3. Be specific about what type of content you need
4. Provide job descriptions as text, not links

### For Implementations
1. Test each assistant independently first
2. Run through complete workflow with sample data
3. Verify outputs are properly formatted
4. Check that sharing instructions are clear

## Validation Checklist

Before considering setup complete:

- [ ] Each assistant works independently
- [ ] Outputs are formatted for easy copying
- [ ] Sharing instructions are included in outputs
- [ ] No file system dependencies remain
- [ ] Platform constraints are respected
- [ ] Workflow progression is smooth

## Complete Workflow Example

1. **Stage 1: Career Coach**
   - Complete consultation
   - Copy objectives summary

2. **Stage 2: Personal Brand Development**
   - Paste objectives
   - Complete brand workshops
   - Copy brand profile

3. **Stage 3: Market Positioning**
   - Paste objectives and brand
   - Develop strategy
   - Copy strategy document

4. **Stage 4A: Job Applications** (when applying to specific roles)
   - Paste all previous outputs
   - Provide job description
   - Receive optimized resume and cover letter

5. **Stage 4B: Professional Networking** (for relationship building)
   - Paste all previous outputs
   - Provide target information
   - Receive networking content

## Summary

These assistants are designed for maximum compatibility across AI platforms. They require no special setup, no file access, and no external dependencies. Everything operates through natural conversation with structured outputs for seamless workflow progression.
