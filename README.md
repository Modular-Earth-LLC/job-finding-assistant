# How To Use the Job Finding Assistant

This guide shows job seekers how to pair their own career story with modern AI tools (such as ChatGPT Custom GPTs, Claude, or Mistral) to create polished job-search materials on demand.

## Introduction

The Job Finding Assistant is a comprehensive workflow that treats your job search like a project: gather requirements, develop your personal brand, position yourself in the market, and generate outreach content that wins interviews. Everything you need to run these stages lives in this repository. Follow the steps below to personalize the toolkit and start producing high-quality messages, cover letters, and website copy in minutes.

## Prerequisites

- An AI assistant that supports custom instructions and file uploads (e.g., ChatGPT Plus with Custom GPTs, Claude Pro, or Mistral Le Chat Pro)
- A copy of this repository (download the ZIP from GitHub or clone it)
- A text editor to update the knowledge base files (`inputs/knowledge-bases/`)
- Your recent resume, project list, and any information relevant to your job search you want the AI to reference

## Step-by-Step Instructions

1. **Get the project files**  
   Download or clone `job-finding-assistant` to a convenient folder. Keep the structure intact so the paths in this guide stay accurate.

2. **Review the knowledge base**  
   Open `inputs/knowledge-bases/job_search_knowledge_base.json` to familiarize yourself with the sections. The assistants in each stage will generate structured updates for you. Only make manual changes if you spot inaccurate or outdated information that needs a quick correction.

3. **Run Stage 1 – Career Requirements Gathering**  
   Load `career_coach_assistant.system.prompt.md` as a system prompt in your AI tool. This assistant conducts an initial consultation to:
   - Understand your current situation and constraints
   - Define clear career, financial, and life objectives
   - Document timeline requirements and preferences
   - Create or update the knowledge base with foundational information
   
   The assistant will provide a summary and update only the `user_profile.basic_info` and `career_objectives` sections.

4. **Run Stage 2 – Personal Brand Development**  
   Load `personal_brand_development_assistant.system.prompt.md` as a system prompt. This assistant will:
   - Discover your mission, vision, and values
   - Capture your authentic personality traits
   - Create brand narratives that resonate
   - Update the `personal_brand` section of the knowledge base

5. **Run Stage 3 – Go-To-Market Strategy**  
   Load `job_market_positioning.system.prompt.md` as a system prompt. This strategic assistant:
   - Maps target roles and industries based on your objectives
   - Develops positioning statements and value propositions
   - Creates actionable go-to-market plans
   - Updates the `go_to_market_strategy` section

6. **Run Stage 4 – Professional Networking Outreach**  
   After Stages 1–3 are complete, load `professional_networking_outreach_assistant.system.prompt.md` as a system prompt. Upload the latest knowledge base file each session. This execution assistant:
   - Creates targeted outreach content based on your established strategy
   - Conducts focused company research (10 minutes max)
   - Generates platform-optimized messages (LinkedIn, email, cover letters)
   - Executes your positioning through compelling, personalized content

7. **Generate job-search materials**  
   Ask for exactly what you need—networking outreach, application follow-ups, cover letters, or website copy. Reference the role, company, and constraints (word counts, tone). Examples:

```text
   Generate a LinkedIn connection request for a Principal AI Engineer opening at [Company]. Keep it under 275 characters and reference my healthcare AI background.
```

```text
   Create a two-paragraph email to a recruiter for the attached job description. Emphasize my AI governance experience and ask for a 15-minute screening call.
   ```

## Expected Results

- Your knowledge base becomes a single source of truth that all assistants can reference
- Each stage builds on the previous one, creating a coherent job search strategy
- The outreach assistant produces consistent, on-brand messages aligned with your objectives
- You can rapidly generate tailored content without starting from scratch each time

## Troubleshooting

- **AI says the prompt is too long**: Split the system prompt into smaller chunks when pasting, or upgrade to a plan with higher limits
- **Content sounds generic**: Ensure you've completed all stages to populate the knowledge base with specific details
- **Wrong or outdated details**: Update the knowledge base and re-upload it before generating new content
- **Assistant skips to later stages**: Remind it of its specific role and boundaries (each assistant stays in its lane)
- **Attachment issues**: Most platforms accept JSON, PDF, and CSV files. Convert unsupported formats to PDF or plain text

## Knowledge Base Management

The first three assistants build your knowledge base incrementally:

- **Stage 1 - Career Coach**: Creates objectives and basic profile information
- **Stage 2 - Brand Assistant**: Adds mission, vision, values, and personality
- **Stage 3 - Positioning Assistant**: Completes strategy with target markets and positioning

The Stage 4 Outreach Assistant reads from but does not modify the knowledge base, ensuring consistent execution of your established strategy.

## Additional Information

- **Stage overview**:

| Stage | Purpose | System Prompt File |
| --- | --- | --- |
| 1. Requirements Gathering | Understand objectives, constraints, timeline | `career_coach_assistant.system.prompt.md` |
| 2. Personal Brand | Develop mission, vision, values, voice | `personal_brand_development_assistant.system.prompt.md` |
| 3. Go-To-Market Strategy | Map target roles, industries, positioning | `job_market_positioning.system.prompt.md` |
| 4. Content Execution | Generate outreach, cover letters, follow-ups | `professional_networking_outreach_assistant.system.prompt.md` |

- **Knowledge assets**: `inputs/document-library/` stores resumes, transcripts, and other references the assistants can cite. Keep this folder updated so the AI always has fresh proof points.

- **Roadmap**: See `TODO.md` for planned improvements and integration ideas. Contributions and suggestions are welcome via GitHub issues.

- **License**: This project uses the MIT License, allowing you to adapt the workflow for personal or commercial use. Just include the original copyright and permission notice.

