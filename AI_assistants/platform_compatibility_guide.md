# Platform Compatibility Guide for Job Finding Assistants

## Overview

All four job finding assistants are designed to work as standalone agents in popular AI platforms without requiring file system access. They operate through conversation, accepting pasted inputs and providing copy-ready outputs.

## Supported Platforms

### ✅ Fully Compatible
- **OpenAI ChatGPT** (GPT-4, GPT-4 Turbo)
- **Anthropic Claude** (Claude 3 Opus, Sonnet, Haiku)
- **Mistral Le Chat Pro**
- **Perplexity AI**
- **Google Gemini**
- **Any chat-based AI interface**

### Platform-Specific Features

| Platform | Web Search | File Upload | Code Execution | Image Generation |
|----------|------------|-------------|----------------|------------------|
| ChatGPT Plus | ✅ (if enabled) | ✅ | ✅ | ✅ |
| Claude | ❌ | ✅ | ❌ | ❌ |
| Mistral | ❌ | ❌ | ❌ | ❌ |

## How the Workflow Operates

### Step 1: Career Coach Assistant
**Input**: None required (starts fresh)
**Process**: Conversational consultation
**Output**: Career objectives summary (markdown + JSON)

### Step 2: Personal Brand Assistant
**Input**: Paste career objectives from Step 1
**Process**: Brand discovery workshops
**Output**: Personal brand profile (markdown + JSON)

### Step 3: Market Positioning Assistant
**Input**: Paste outputs from Steps 1 & 2
**Process**: Strategy development dialogue
**Output**: Go-to-market strategy (markdown + JSON)

### Step 4: Networking Outreach Assistant
**Input**: Paste outputs from Steps 1-3 + job description
**Process**: Content creation
**Output**: Copy-ready messages/letters

## Data Flow Between Assistants

```
[Career Coach] 
    ↓ (copy/paste summary)
[Personal Brand]
    ↓ (copy/paste profile)
[Market Positioning]
    ↓ (copy/paste strategy)
[Networking Outreach]
    ↓
[Ready-to-send content]
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

#### Networking Outreach Test
```
User: "I need a LinkedIn message for a Director of AI role at a healthcare company. I have my strategy documentation ready."
[Assistant should ask for documents and job description]
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

## Sample Complete Workflow

1. **Start with Career Coach**
   - Complete consultation
   - Copy objectives summary

2. **Move to Personal Brand**
   - Paste objectives
   - Complete brand workshops
   - Copy brand profile

3. **Continue to Market Positioning**
   - Paste objectives and brand
   - Develop strategy
   - Copy strategy document

4. **Finish with Networking Outreach**
   - Paste all previous outputs
   - Provide job description
   - Receive ready-to-send content

## Summary

These assistants are designed for maximum compatibility across AI platforms. They require no special setup, no file access, and no external dependencies. Everything operates through natural conversation with structured outputs for seamless workflow progression.
