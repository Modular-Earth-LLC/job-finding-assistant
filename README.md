# Job Finding Assistant

An AI-powered career coach that helps professionals create personalized job search strategies, branded content, and networking outreach materials. This system treats your career like a business, helping you market yourself effectively to land your dream job.

## What This Project Does

This assistant helps you:

- **Build a comprehensive personal brand** aligned with your career goals
- **Create targeted outreach messages** to grow your network
- **Develop personalized cover letters** for specific job descriptions
- **Generate professional website content** for platforms like Notion
- **Craft follow-up messages** tailored to recruiters and hiring managers

## Understanding AI Concepts for Job Search

### Key AI Technologies Used

**System Prompts:**

- Detailed instructions that tell the AI how to act as your career coach
- Like giving a human assistant a comprehensive job description and training manual
- The prompts in this project contain expert job search strategies and best practices

This [System Prompt](/job_finding_assistant.system.prompt.md) defines your job finding assistant's role and behavior.

**Knowledge Base:**

- A structured file containing your career information
- Includes your skills, preferences, target roles, and personal brand
- Acts as the "source of truth" for all AI-generated content

Your job finding assistant will guide you on how to create and update this [knowledge base](/inputs/knowledge-bases/job_search_knowledge_base.yaml) (formatted as YAML).

**Retrieval Augmented Generation (RAG):**

- Think of this as giving the AI access to your personal "filing cabinet" of career information
- The AI can reference your resume, projects, and preferences to create personalized content
- This ensures every message reflects your actual experience and goals

### Modern Job Search Strategy

**Why This Approach Works:**

1. **Personalization at Scale**: Instantly create dozens of tailored messages without starting from scratch
2. **Consistency**: Maintain your personal brand across all communications
3. **Data-Driven**: Use structured information to ensure accuracy and relevance
4. **Professional Quality**: Generate content that matches industry standards and exceeds most human capabilities

## Quick Start Guide

### Step 1: Set Up Your AI Assistant

1. **Choose an AI Platform**:
   - Recommended: Claude (Anthropic), ChatGPT Plus, or Mistral Le Chat Pro
   - These platforms support file uploads and custom instructions

2. **Copy the System Prompt**:
   - Go to [`job_finding_assistant.system.prompt.md`](job_finding_assistant.system.prompt.md)
   - Copy the entire content
   - Paste it into your AI platform's "Custom Instructions" or "System Prompt" field

3. **Test the Setup**:
   - Ask: "Can you help me create a LinkedIn message for a software engineering role?"
   - The AI should respond as a career coach, asking for job details and your background

### Step 2: Create Your Knowledge Base

1. **Use the Template**:
   - Open [`inputs/knowledge-bases/job_search_knowledge_base.yaml`](inputs/knowledge-bases/job_search_knowledge_base.yaml)
   - This file contains example data - replace it with your information

2. **Fill in Your Information**:
   - **Basic Info**: Name, email, location, social media links
   - **Target Roles**: Specific job titles you're seeking
   - **Skills**: Technical and soft skills relevant to your goals
   - **Career Objectives**: Financial goals, timeline, preferred work arrangements
   - **Personal Brand**: Your mission, values, and unique value proposition

3. **Upload to AI**: Attach this file when chatting with your assistant

### Step 3: Generate Job Search Content

**For Networking Messages**:

```text
"Create a LinkedIn connection request for a Senior Software Engineer role at [Company]. 
I'm interested in their AI/ML team. Keep it under 200 characters."
```

**For Cover Letters**:

```text
"Generate a cover letter for this job posting: [paste job description]. 
Focus on my Python and machine learning experience."
```

**For Personal Website**:

```text
"Create a professional website for my Notion page using the website generation prompt. 
Focus on my full-stack development skills and startup experience."
```

## Project Structure

Understanding how this project is organized will help you customize it for your needs:

```text
job-finding-assistant/
├── job_finding_assistant.system.prompt.md    # Main AI assistant system prompt
├── inputs/                          # Your personal data and examples
│   ├── knowledge-bases/            # Your career information (YAML format)
│   ├── document-library/           # Your resume, portfolio, certificates
│   └── example-websites/           # Sample websites for inspiration
├── prompts/                        # AI instructions and templates
│   ├── notion_website_content_generation.user.prompt.md
│   ├── develop_personal_brand.user.prompt.md
│   └── set_career_objectives.user.prompt.md
├── outputs/                        # Generated content
│   ├── cover_letters/             # AI-generated cover letters
│   └── websites/                  # Generated website content
└── README.md                      # This documentation
```

### Key Files Explained

**Knowledge Base** (`inputs/knowledge-bases/job_search_knowledge_base.yaml`)

- Your personal "database" of career information
- Contains your skills, preferences, goals, and personal brand
- **Template provided** - customize with your information
- Required for the AI to create personalized content

**Document Library** (`inputs/document-library/`)

- Upload your resume, portfolio projects, and certificates
- The AI references these for accurate, detailed content
- Supports PDF, CSV, HTML, and text formats
- More recent documents take priority over older ones

**User Prompts** (`prompts/`)

- Detailed instructions that teach the AI how to personalize your career coaching
- Each prompt specializes in different aspects: goal setting, branding, content development, website development, networking, and more
- Copy and paste these into your AI platform

**Generated Outputs** (`outputs/`)

- Examples of AI-generated content
- Cover letters, website content, and networking messages
- Use these as templates and inspiration

## Practical Examples

### Example 1: LinkedIn Networking Message

**Your Input:**

```text
"Create a LinkedIn connection request for a Senior AI Engineer role at OpenAI. 
I have 3 years of Python experience and worked on a chatbot project. Keep it under 200 characters."
```

**AI Output:**

```text
Hi [Name], I'm a Python developer with 3 years experience building AI systems, including a production chatbot. 
I'd love to connect and learn about OpenAI's engineering culture. Thanks!
```

### Example 2: Cover Letter Generation

**Your Input:**

```text
Job Description: "We're seeking a Full Stack Developer with React and Node.js experience..."
Focus on: My 2 years at a startup, React projects, and team leadership experience.
```

**AI Output:**

```text
Dear Hiring Manager,

I'm excited to apply for the Full Stack Developer position. In my 2 years at [Startup], 
I led a team of 3 developers building React applications that served 10,000+ users...
[Continues with personalized content based on your knowledge base]
```

### Example 3: Personal Website Content

**Your Input:**

```text
"Generate a professional website for my portfolio. Focus on my machine learning projects, 
Python skills, and interest in healthcare AI. Target audience: hiring managers at health tech companies."
```

**AI Output:**

```markdown
# [Your Name] | ML Engineer Transforming Healthcare

## About
Passionate ML engineer with 4+ years building AI solutions for healthcare challenges...

## Projects
### Healthcare Prediction Model
Built a machine learning model that improved patient diagnosis accuracy by 23%...
[Continues with detailed, personalized content]
```

## Job Search Strategy Guide

### Why This AI-Powered Approach Works

**Traditional Job Search Problems:**

- Generic applications get ignored
- Hard to personalize at scale
- Inconsistent personal branding
- Time-consuming research and writing

**AI-Powered Solutions:**

- **Personalization at Scale**: Generate dozens of tailored messages quickly
- **Consistent Branding**: Every message reflects your authentic professional identity
- **Data-Driven Content**: Based on your actual skills and experience
- **Professional Quality**: Matches industry standards and best practices

### Modern Networking Strategy

1. **Research First**: Use LinkedIn to identify hiring managers and team leads
2. **Personalized Outreach**: Reference specific company projects or challenges
3. **Value-First Approach**: Offer insights or ask thoughtful questions
4. **Follow-Up System**: Maintain relationships beyond initial contact
5. **Content Creation**: Share relevant articles and insights to build credibility

### Best Practices for Tech Professionals

**LinkedIn Optimization:**

- Compelling headline
- Detailed experience with quantified achievements
- Regular posting about industry trends and projects
- Active engagement with your network's content

**Application Strategy:**

- Apply within 24-48 hours of job posting
- Customize resume keywords for each application
- Include a personalized cover letter
- Follow up after 1 week if no response

**Interview Preparation:**

- Research the company's tech stack and challenges
- Prepare specific examples using the STAR method (Situation, Task, Action, Result)
- Prepare thoughtful questions about team culture and growth opportunities

## Why I chose the MIT License

This license aligns with Modular Earth's mission to support social good through open-source AI-driven applications and our commitment to accessibility, privacy, trust, and minimizing costs.

**Permissive Use**: The MIT License is one of the most permissive licenses, allowing for the software to be used, modified, and distributed freely, even for commercial purposes. This aligns well with Modular Earth's goal of making wealth accessible and supporting a wide range of uses without restrictive conditions.

**Simplicity and Clarity**: The MIT License is short and straightforward, making it easy for users to understand their rights and obligations. This simplicity can help ensure broader adoption and use of the AI assistant.

**Compatibility**: The MIT License is compatible with many other licenses, which can be beneficial if the financial assistant needs to be integrated with other software or libraries that have different licensing terms.

**Community Trust**: The MIT License is widely recognized and trusted in the open-source community. Using a well-known and respected license can help build trust with users and contributors.

**Minimal Restrictions**: The only significant requirement of the MIT License is that the original copyright and permission notice be included in all copies or substantial portions of the software. This minimal restriction supports Modular Earth's principles of minimizing costs and maximizing accessibility.

The MIT License effectively supports Modular Earth's mission and principles. It allows this AI assistant to be accessible to all.

## Troubleshooting

### Common Issues and Solutions

#### "The prompt is too long"

**Problem**: Your AI platform has character limits for system prompts

**Solutions**:

1. **Use a shorter version**: Ask the AI to summarize the main prompt to fit your platform's limits
2. **Split into multiple messages**: Break the system prompt into 2-3 parts and send them sequentially
3. **Upgrade your plan**: Many AI platforms offer higher limits with paid subscriptions

#### "The AI doesn't understand my knowledge base"

**Problem**: Generated content doesn't reflect your actual experience

**Solutions**:

1. **Check file format**: Ensure your YAML file is properly formatted (use a YAML validator)
2. **Upload correctly**: Make sure you're attaching the file to your conversation
3. **Be specific**: Include more detailed information in your knowledge base
4. **Test with simple requests**: Start with basic questions to verify the AI can access your data

#### "Generated content is too generic"

**Problem**: Messages and cover letters lack personalization

**Solutions**:

1. **Provide more context**: Include specific job descriptions and company information
2. **Update your knowledge base**: Add more detailed achievements and quantified results
3. **Be explicit**: Tell the AI exactly what aspects to emphasize
4. **Iterate**: Ask for revisions focusing on specific improvements

#### "I don't know what to put in my knowledge base"

**Problem**: Unsure how to structure your career information

**Solutions**:

1. **Start with the template**: Use the provided example as a guide
2. **Review your resume**: Extract key achievements, skills, and experiences
3. **Think about goals**: Define what roles and companies you're targeting
4. **Ask for help**: The AI can help you identify what information to include

#### "The AI generates outdated or incorrect information"

**Problem**: Content references old roles or incorrect details

**Solutions**:

1. **Update your knowledge base**: Ensure all information is current
2. **Specify timeframes**: Clearly indicate current vs. past roles and skills
3. **Provide corrections**: When you notice errors, correct them and update your files
4. **Regular maintenance**: Review and update your knowledge base monthly

#### "I'm not getting responses to my outreach"

**Problem**: Low response rates on LinkedIn messages or emails

**Solutions**:

1. **Personalize more**: Research the specific person and company before messaging
2. **Shorten messages**: Keep initial outreach under 150 words
3. **Lead with value**: Mention something specific about their work or company
4. **Follow up appropriately**: Wait 1-2 weeks, then send a brief, polite follow-up
5. **A/B test**: Try different message styles and track what works

### Getting Help

**Community Resources**:

- GitHub Issues: Report bugs or request features
- LinkedIn: Connect with [the repository owner](https://www.linkedin.com/in/paulprae/) and other users for tips and networking
- AI Platform Communities: Platform-specific help (ChatGPT, Claude, etc.)

**Self-Help Tips**:

1. **Start simple**: Begin with basic requests before trying complex scenarios
2. **Iterate gradually**: Make small improvements rather than complete rewrites
3. **Save what works**: Keep successful prompts and messages as templates
4. **Track results**: Monitor response rates and adjust your approach accordingly

**When to Seek Professional Help**:

- Consistently low response rates after trying multiple approaches
