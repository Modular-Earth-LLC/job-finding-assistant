# Detailed Installation Guide

A complete guide to setting up your AI career team on ChatGPT, Claude, or Mistral.

## Understanding Multi-Agent AI Systems

### What Are AI Agents?
Think of AI agents as specialized experts. Instead of one general AI trying to do everything, you have:
- **Specialists** - Each agent is an expert in one area
- **Team Work** - They share information and build on each other's work
- **Better Results** - Specialized agents give more focused, higher quality help

### Why Multiple Agents?
Just like you wouldn't ask your doctor to fix your car, different career tasks need different expertise:
- Career planning needs coaching skills
- Resume writing needs application expertise  
- Networking needs relationship-building knowledge

### The Knowledge Base Advantage
The knowledge base acts like a shared notebook between your AI agents:
- **No Repetition** - Tell your story once, use it everywhere
- **Consistency** - All agents work from the same information
- **Evolution** - Each agent adds to your profile

## Platform Setup Guides

### ChatGPT (OpenAI) - Recommended

**Requirements**: ChatGPT Plus subscription ($20/month)

#### Setting Up Your First Agent

1. **Access Custom GPTs**
   - Go to [chat.openai.com](https://chat.openai.com)
   - Look for "Explore" in the left sidebar
   - Click "Create a GPT"

2. **Configure the Agent**
   - Click "Configure" tab
   - In "Name": Enter "Career Coach" (or any name)
   - In "Description": Enter "Helps define career goals and objectives"
   - In "Instructions": 
     - Go to `AI_assistants/career_coach_assistant.system.prompt.md`
     - Select all text (Ctrl+A or Cmd+A)
     - Copy (Ctrl+C or Cmd+C)
     - Paste into Instructions box

3. **Add Knowledge Base (Optional)**
   - Click "Upload files" under Knowledge
   - Upload `job_search_knowledge_base.json`
   - Upload `ai_assistants_system_config.json`
   - This allows the agent to remember your information

4. **Save and Test**
   - Click "Save" in top right
   - Choose "Only me" for privacy
   - Click "Confirm"
   - Start chatting!

#### Adding More Agents

Repeat the above process for each assistant:
1. **Personal Brand Assistant** - Use `personal_brand_development_assistant.system.prompt.md`
2. **Market Positioning** - Use `job_market_positioning.system.prompt.md`
3. **Website Generator** - Use `professional_website_generator.system.prompt.md`
4. **Job Application** - Use `job_application_interview_assistant.system.prompt.md`
5. **Professional Networking** - Use `professional_networking_assistant.system.prompt.md`

#### Using Multiple Agents Together

1. **Start with Career Coach GPT**
   - Have your consultation
   - Copy the summary it provides

2. **Move to Personal Brand GPT**
   - Start with: "Here's my career objectives from the Career Coach:"
   - Paste the summary
   - Continue the conversation

3. **Continue Through the Workflow**
   - Each agent builds on the previous
   - Always paste the summaries from earlier agents

### Claude (Anthropic)

**Requirements**: Claude Pro subscription ($20/month)

#### Setting Up Your Project

1. **Create a Project**
   - Go to [claude.ai](https://claude.ai)
   - Click "Projects" in sidebar
   - Click "Create project"
   - Name it "Job Search Assistant"

2. **Add First Assistant**
   - Click "Edit project instructions"
   - Copy text from `career_coach_assistant.system.prompt.md`
   - Paste as instructions
   - Save

3. **Add Knowledge Files**
   - Click "Add content" in project
   - Upload knowledge base files
   - Upload any career documents

4. **Start Conversations**
   - Click "New chat" within the project
   - The assistant remembers your project context

#### Managing Multiple Assistants in Claude

Since Claude uses projects, you have options:

**Option 1: One Project, Switch Instructions**
- Edit project instructions for each assistant as needed
- Good for maintaining context
- Requires manual switching

**Option 2: Multiple Projects**
- Create separate project for each assistant
- Switch between projects
- Clearer separation but more setup

### Mistral Le Chat

**Requirements**: Free or Pro account

#### Creating Agents

1. **Access Agents**
   - Go to [chat.mistral.ai](https://chat.mistral.ai)
   - Click "Agents" in sidebar
   - Click "Create new agent"

2. **Configure Agent**
   - Name: "Career Coach" (or your choice)
   - Description: Brief purpose statement
   - Instructions: Paste from system prompt file
   - Model: Choose available model
   - Temperature: Keep at 0.7

3. **Save and Activate**
   - Click "Create agent"
   - Agent appears in your list
   - Click to start conversation

#### Working with Multiple Agents

- Create each agent separately
- Switch between them using the Agents menu
- Copy/paste summaries between conversations

## Using Your AI Career Team

### Workflow Best Practices

#### Day 1: Foundation (1 hour)
1. **Career Coach** (20 min)
   - Define your goals
   - Identify constraints
   - Get objectives summary

2. **Personal Brand** (30 min)  
   - Discover your values
   - Define your mission
   - Create brand profile

#### Day 2: Strategy (1 hour)
3. **Market Positioning** (30 min)
   - Analyze target markets
   - Create positioning strategy
   - Define target companies

#### Day 2.5: Web Presence (30 min - Optional but Recommended)
3.5. **Website Generator** (30 min)
   - Select platform (Notion, Eleventy, Jekyll, Astro)
   - Generate portfolio website from GTM strategy
   - Deploy web presence
   - Get shareable link for applications and networking

**Why build a website?**
- Provides professional "learn more" link for applications and networking messages
- Demonstrates technical competency and attention to detail
- Converts hiring manager visits to interview requests
- Serves as living portfolio that evolves with your career

#### Day 3+: Execution (As needed)
4. **Applications** (15 min per job)
   - Provide job description
   - Get customized resume
   - Receive cover letter

5. **Networking** (10 min per outreach)
   - Identify target connections
   - Get personalized messages
   - Create follow-up sequences

### Prerequisites Validation (New in v1.1)

The system now includes automatic validation to ensure you follow the optimal workflow:

**What happens if you skip ahead?**
- Stage 4 assistants check for required information
- They guide you to complete missing stages
- You can still proceed with manual information if needed

**Example validation message:**
```
"I notice we're missing your personal brand profile. While I can create basic 
application materials, they'll be much more effective with:

- Career objectives: Ensures materials align with your goals
- Personal brand: Creates authentic, consistent messaging
- Market strategy: Targets the right opportunities

Would you like to:
1. Visit the Personal Brand Assistant first (recommended)
2. Proceed with limited information
3. Provide the missing information manually?"
```

This ensures you get the best results while maintaining flexibility.

### Knowledge Base Management

#### Understanding the Files

**Your Data File** (`job_search_knowledge_base.json`):
- Contains YOUR information
- Built progressively by assistants
- Keep this private!

**System Config** (`ai_assistants_system_config.json`):
- Technical settings for assistants
- Don't modify this
- Same for all users

#### How It Works

1. **First Use**: Career Coach asks questions, creates initial data
2. **Building**: Each assistant adds their section
3. **Reading**: Later assistants read all previous sections
4. **Consistency**: Everyone works from same information

#### Manual Updates

If an assistant can't save automatically:
1. It will provide JSON formatted data
2. Copy this data
3. Open your knowledge base file
4. Paste in the appropriate section
5. Save the file

## Troubleshooting

### Common Issues

**"I don't see the option to create GPTs/Agents"**
- Verify you have a paid subscription
- Try logging out and back in
- Check if feature is available in your region

**"The assistant doesn't remember previous conversations"**
- Upload the knowledge base files
- Paste summaries from previous assistants
- Use projects/GPTs to maintain context

**"Instructions are too long"**
- Split into multiple messages
- Focus on core sections first
- Remove optional sections if needed

**"Agents aren't working together"**
- Always paste summaries between agents
- Start each conversation with context
- Reference previous agent outputs

### Getting Help

1. **Check Examples**: Each assistant provides examples when asked
2. **Ask the Assistant**: They can explain their own functions
3. **Simplify**: Start with just Career Coach, add others later
4. **Community**: Open an issue on GitHub for support

## Tips for Success

### Start Simple
- Don't try to set up everything at once
- Begin with Career Coach only
- Add other agents as you need them

### Save Everything
- Download chat transcripts
- Save summaries in a document
- Keep your knowledge base backed up

### Iterate and Improve
- Agents get better with more context
- Update your knowledge base as you progress
- Refine outputs before using

### Privacy First
- Review what you share with AI platforms
- Use generic company names if concerned
- Download and delete sensitive conversations

## Next Steps

1. **Install Career Coach** first
2. **Have your consultation** (20 minutes)
3. **Save the summary** provided
4. **Move to Personal Brand** when ready
5. **Continue through workflow** at your pace

Remember: These are tools to enhance your job search. You're always in control, and you can use as much or as little as helps you succeed.

---
*Questions? Each assistant can explain itself - just ask "How do you work?" or "What can you help me with?"*
