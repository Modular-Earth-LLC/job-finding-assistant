# Job Finding Assistant

A career coach and digital marketing assistant designed to help job seekers create personalized go-to-market strategies and outreach content for building professional networks and securing job opportunities. The assistant develops a strategy with you and then helps to craft tailored connection requests and introductory messages by analyzing company needs. It treats you like a business, helping to market and sell yourself.

## How to host this agent

1. Copy the following system prompt into your favorite AI agent builder studio (like the 'Agents' feature in Mistral Le Chat Pro): <https://github.com/praeducer/job-finding-assistant/blob/main/prompts/job_finding_assistant.system.prompt.md>.
2. Follow the instructions on your preferred AI platform to host and chat with your new personal job finding assistant.

## How to use this agent to find jobs

1. Ask the agent to generate outreach content for a specific job description and target audience at a company. Include the marketing channel and content length.
2. Attach a file of, or share a link to, a knowledge base of facts about your job preferences, career objectives, personal brand, and go-to-market strategy, e.g., <inputs\knowledge-bases\job_search_knowledge_base.yaml>.

## How to use this agent to generate a personal website in Notion.

Prompt your personalized job finding assistant with this prompt, while attaching your knowledge base: [prompts/notion_website_generation.user.prompt.md](https://github.com/Modular-Earth-LLC/job-finding-assistant/blob/main/prompts/notion_website_generation.user.prompt.md)

## Repository Information

### Knowledge Base

A knowledge base of facts about my job preferences, career objectives, personal brand, and go-to-market strategy:

- Public web link: <https://github.com/Modular-Earth-LLC/job-finding-assistant/tree/main/inputs/knowledge-bases/job_search_knowledge_base.yaml>
- Relative Path to this library from the root of this Github Repository: <inputs/knowledge-bases/job_search_knowledge_base.yaml>

You can use this as a template. Customize it and then use as input to your job finding assistant. The facts in this knowledge base are required for the agent to personalize content.

### Document Library for Generative AI Retrieval Augmented Generation (RAG)

- Title: Professional Background, Work Experience, and Project Portfolio
- Description: This library contains files related to the user's career, including their resume, personal go-to-market strategy, presentations, project descriptions, portfolio, blog posts, and cover letters.
- Publicly accessible link to the library's location: <https://github.com/praeducer/job-finding-assistant/tree/main/inputs/document-library>
- Relative Path to this library from the root of this Github Repository: </inputs/document-library>
- Usage Instructions:
  - Index and reference these files as needed, such as for retrieval augmented generation (RAG).
  - Documents created more recently are more accurate and essential. Some information in older documents may be outdated and should not be referenced if it conflicts with newer data. Current job preferences, career objectives, personal brand, and go-to-market strategy are most important to consider.

### Programming Languages

- Authoring: Markdown, YAML, CSV. Keep examples language-agnostic unless code is required.

### File Formats

- Markdown (`.md`) for narrative and templates
- YAML code-fences for variable schemas and config
- CSV code-fences for tabular source data

## Synthesizing Best Practice Prompt Engineering: Key Takeaways for Builders

Analyzing these diverse prompts reveals a set of converging best practices for building reliable agentic AI systems:

1. **Define the Agent Clearly:** Start with an explicit role, purpose, and scope. Include contextual grounding like date or environment specifics.
2. **Optimize Context Usage:** Structure information hierarchically, compress without losing meaning, and maintain coherence across interactions.
3. **Structure for Clarity:** Break down complex instructions using headings, lists, or tags. Organize rules logically (e.g., group tool instructions, safety rules).
4. **Be Explicit About Tools:** Detail *what* each tool does, *how* to call it (syntax, parameters, format), and *when* (and when not) to use it. Provide examples. Embed usage policies directly.
5. **Mandate Step-by-Step Execution:** Encourage or enforce planning, iteration, and waiting for results/confirmation. Prevent the AI from attempting too much at once. Consider explicit thinking phases or loops.
6. **Embed Domain Knowledge & Constraints:** Include relevant style guides, library usage rules, file conventions, platform limitations, and best practices for the agent's specific domain.
7. **Integrate Safety and Alignment:** Define unacceptable requests and provide clear refusal protocols. Embed specific policies for sensitive operations (data handling, image generation).
8. **Guide the Tone:** Set expectations for the interaction style (professional, friendly, concise, adaptive) to ensure a consistent user experience.
9. **Use Examples:** Illustrate complex rules or desired output formats with clear examples within the prompt (like Bolt.new and v0 do extensively).

Essentially, an effective agentic prompt acts as a comprehensive, well-structured operational manual that leaves little room for ambiguity while empowering the AI with the knowledge and procedures needed to act effectively and safely using its tools.

## Sources leveraged when writing prompts

- Snippets from GitHub Copilot prompt files from the awesome-copilot repository: <https://github.com/github/awesome-copilot>
- Mistral's guidance on prompt engineering:
  - <https://docs.mistral.ai/guides/prompting_capabilities>
  - <https://blog.promptlayer.com/mistral-system-prompt/>
- This comprehensive guide on prompt engineering: <https://www.lakera.ai/blog/prompt-engineering-guide>
- OpenAI's' perspective: <https://help.openai.com/en/articles>
- These prompts are often ran in chatmode in GitHub Copilot in VS Code. This page has instructions about how to use CoPilot: <https://docs.github.com/en/copilot/how-tos>

## Why I chose the MIT License

This license aligns with Modular Earth's mission to support social good through open-source AI-driven applications and our commitment to accessibility, privacy, trust, and minimizing costs.

**Permissive Use**: The MIT License is one of the most permissive licenses, allowing for the software to be used, modified, and distributed freely, even for commercial purposes. This aligns well with Modular Earth's goal of making wealth accessible and supporting a wide range of uses without restrictive conditions.

**Simplicity and Clarity**: The MIT License is short and straightforward, making it easy for users to understand their rights and obligations. This simplicity can help ensure broader adoption and use of the AI assistant.

**Compatibility**: The MIT License is compatible with many other licenses, which can be beneficial if the financial assistant needs to be integrated with other software or libraries that have different licensing terms.

**Community Trust**: The MIT License is widely recognized and trusted in the open-source community. Using a well-known and respected license can help build trust with users and contributors.

**Minimal Restrictions**: The only significant requirement of the MIT License is that the original copyright and permission notice be included in all copies or substantial portions of the software. This minimal restriction supports Modular Earth's principles of minimizing costs and maximizing accessibility.

The MIT License effectively supports Modular Earth's mission and principles. It allows this AI assistant to be accessible to all.

## Troubleshooting

### The prompt is too long

Reduce the character count according to the specs of your own preferences or the AI platform that you are using. LLMs are great at this task ;D
