# How To Use the Job Finding Assistant

This guide shows job seekers how to pair their own career story with modern AI tools (such as ChatGPT Custom GPTs, Claude, or Mistral) to create polished job-search materials on demand.

## Introduction

The Job Finding Assistant is a four-stage workflow that treats your job search like a project: set clear goals, define your personal brand, position yourself in the market, and finally generate outreach content that wins interviews. Everything you need to run those stages lives in this repository. Follow the steps below to personalize the toolkit and start producing high-quality messages, cover letters, and website copy in minutes.

## Prerequisites

- An AI assistant that supports custom instructions and file uploads (e.g., ChatGPT Plus with Custom GPTs, Claude Pro, or Mistral Le Chat Pro)
- A copy of this repository (download the ZIP from GitHub or clone it)
- A text editor to update the knowledge base files (`inputs/knowledge-bases/`)
- Your recent resume, project list, and any information relevant to your job search you want the AI to reference

## Step-by-Step Instructions

1. **Get the project files**  
   Download or clone `job-finding-assistant` to a convenient folder. Keep the structure intact so the paths in this guide stay accurate.

2. **Review the knowledge base**  
   Open `inputs/knowledge-bases/job_search_knowledge_base.json` to familiarize yourself with the sections. You normally won’t edit this file directly—the prompts in Stages 1–3 generate structured updates for you. Only make manual changes if you spot inaccurate or outdated information that needs a quick correction.

3. **Run Stage 1 – Career Objectives**  
   Launch your AI assistant, upload the knowledge base, and paste the contents of `prompts/set_career_objectives.user.prompt.md`. The prompt guides a conversation and finishes by drafting a "Proposed Knowledge Base Update." Review the summary, then copy the approved JSON block into the file. Manual edits are only needed if the output misses something or you need to correct a detail.

4. **Run Stage 2 – Personal Brand**  
   Use `prompts/develop_personal_brand.user.prompt.md` in the same way. The assistant will capture mission, vision, narratives, and voice guidance, then hand you a JSON knowledge-base update block. Paste the approved content into the `personal_brand` section and only tweak it manually if the AI misunderstood your story.

5. **Run Stage 3 – Go-To-Market Strategy**  
   Open `job_market_positioning.system.prompt.md` inside your AI tool. This system prompt acts as a dedicated strategy agent: it maps target roles and industries, drafts positioning statements, and outputs an update block for `go_to_market_strategy`. Approve the proposal and paste it into the knowledge base.

6. **Run Stage 4 – Job Finding Assistant**  
   After Stages 1–3 are complete, load `job_finding_assistant.system.prompt.md` as a system prompt in your AI tool (or configure it inside a Custom GPT). Upload the latest knowledge base file each session. This execution agent verifies that all earlier stages are populated before creating content and flags any missing sections for you to revisit.

> **Roadmap note:** Stages 1 and 2 will eventually ship as dedicated system prompts, making Career Objectives, Personal Brand, and Go-To-Market Strategy fully independent agents. Once those upgrades land, follow the same workflow: run each agent, approve its knowledge-base update, then move to Stage 4 for content execution.

7. **Generate job-search materials**  
   Ask for exactly what you need—networking outreach, application follow-ups, cover letters, or website copy. Reference the role, company, and constraints (word counts, tone). Examples:

```text
   Generate a LinkedIn connection request for a Principal AI Engineer opening at [Company]. Keep it under 275 characters and reference my healthcare AI background.
```

```text
   Create a two-paragraph email to a recruiter for the attached job description. Emphasize my AI governance experience and ask for a 15-minute screening call.
   ```

## Expected Results

- Your knowledge base becomes a single source of truth the assistant can draw from for every interaction.
- The Stage 4 assistant produces consistent, on-brand messages that align with your goals and target market.
- You can rapidly spin up tailored cover letters, outreach campaigns, and website content without starting from scratch.

## Troubleshooting

- **AI says the prompt is too long**: Split the system prompt into smaller chunks when pasting, or upgrade to a plan with higher limits.
- **Content sounds generic**: Add specific accomplishments and quantified results to the knowledge base, then ask the assistant to focus on them.
- **Wrong or outdated details**: Update the knowledge base and re-upload it before generating new content.
- **Assistant refuses to run Stage 4**: Confirm you captured decisions from Stages 1–3 inside the knowledge base (objectives, personal brand, strategy fields).
- **Attachment issues**: Most platforms accept JSON, PDF, and CSV files. Convert unsupported formats (e.g., DOCX) to PDF or plain text.

## Additional Information

- **Stage overview**:

| Stage | Purpose | Files to Use |
| --- | --- | --- |
| 1. Career Objectives | Define goals, timelines, and constraints | `prompts/set_career_objectives.user.prompt.md` |
| 2. Personal Brand | Craft mission, values, and voice | `prompts/develop_personal_brand.user.prompt.md` |
| 3. Go-To-Market Strategy | Map target roles, industries, and positioning | `job_market_positioning.system.prompt.md` |
| 4. Content Execution | Generate outreach, cover letters, and follow-ups | `job_finding_assistant.system.prompt.md` |

- **Knowledge assets**: `inputs/document-library/` stores resumes, transcripts, and other references the assistant can cite. Keep this folder updated so the AI always has fresh proof points.

- **Roadmap**: See `TODO.md` for planned improvements and integration ideas. Contributions and suggestions are welcome via GitHub issues.

- **License**: This project uses the MIT License, allowing you to adapt the workflow for personal or commercial use. Just include the original copyright and permission notice.

