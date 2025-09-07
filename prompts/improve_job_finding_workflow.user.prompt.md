Improve this {{set career objectives prompt}} given the context of the overall job-finding strategy and workflow. Take into account the context from all files in this repository, with a focus on complementing the other prompts in this repository's prompt folder. The prompts in the prompts folder are designed to run in a workflow as a single, cohesive system. The job-finding assistant system prompt is what defines the job finding assistant AI agent when it is hosted in an AI chat platform. The rest of the user prompts are sent to the agent to perform the task specified within each prompt. Reduce redundancy.

These prompts are part of a comprehensive job-finding system that consists of multiple stages. This workflow typically follows this order:

1. **Stage 1 - Career Objectives**: Defined the candidate's goals, financial targets, and professional aspirations
2. **Stage 2 - Personal Brand**: Established mission, vision, values, and authentic brand narratives
3. **Stage 3 - Website Template**: Created the structural framework optimized for professional portfolios
4. **Stage 4 - Content Generation**: Populate template with personalized, goal-aligned content

The job finding assistant system prompt has more general capabilities to help the job candidate generate content for a variety of situations. The other prompts are for more strategic and specific multimedia creation tasks.

Improve the {{set career objectives prompt}} so it makes sense to occur **before** the job finding assistant runs the other prompts. Here is the order of the prompts:
1. Set career objectives: this defines the goals and purpose of the job-finding assistant and any content it develops, like for cover letters and the job candidate's website.
2. Develop personal brand: This acts as the cornerstone for all content developed, as it represents the mission, vision, and values of the user. 
3. Notion website template generation: this provides the structure, framework, and boilerplate code for the website that the content needs to be populated into.
4. Notion website content generation prompt: This takes the website template as the input and outputs a website complete with custom content personalized for the user and their goals. Generating a personal professional website for the user (aka a portfolio site and online resume for the job candidate) is often the final step in the workflow.

All prompts should follow the principles and guidelines outlined in the job assistant and incorporate input or attachments, such as the career knowledge base YAML file, the user's resume, the user's portfolio, and any other existing content necessary to populate the website template. 

Make sure this prompt fits into this system of prompts and will function as expected when ran. Ensure any changes follow all best practices for prompt and context engineering. 

Ensure that the overall process and logical flow are clearly understood by the agent who receives this prompt. Part of this task involves ensuring we follow best practices in context engineering, so the agent stays focused on its task and creates a best-in-class, professional, and personalized website to help candidates find a job.

Overall, make the instructions clear and understandable.
