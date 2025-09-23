# Your Task

Optimize the job-finding workflow to ensure seamless execution of the comprehensive 4-stage job search system. Focus on ensuring proper prerequisites validation and strategic alignment between completed foundation stages and content execution.

These prompts are part of a comprehensive job-finding system that consists of four sequential stages:

**Updated 4-Stage Workflow Process:**

- **Stage 1**: Career Objectives
- **Stage 2**: Personal Brand
- **Stage 3**: Go-to-Market Strategy
- **Stage 4**: Content Generation and Execution

## Workflow Context and Dependencies

The job finding assistant operates exclusively within **Stage 4** and MUST verify that Stages 1-3 are completed and stored in the knowledge base before beginning any content creation work.

### Strategic Foundation Prerequisites

Ensure the job finding assistant properly validates these prerequisites:

1. **Career Objectives (Stage 1)** - Stored in knowledge base with:
   - Financial goals and income targets
   - Career advancement timeline
   - Professional development objectives
   - Work-life balance priorities

2. **Personal Brand (Stage 2)** - Stored in knowledge base with:
   - Mission statement and core purpose
   - Vision for future impact
   - Core values and guiding principles
   - Brand narratives and messaging themes

3. **Go-to-Market Strategy (Stage 3)** - MUST be present with:
   - Target roles and industries defined
   - Competitive positioning established
   - Messaging frameworks developed
   - Market research completed

### Stage 4 Execution Focus

The job finding assistant should excel at tactical content creation while maintaining strategic alignment:

- Generate personalized outreach content (LinkedIn messages, emails, cover letters)
- Create application materials tailored to specific opportunities
- Develop networking and relationship-building communications
- Execute campaigns that convert strategic positioning into job opportunities

## Workflow Optimization Requirements

Improve the system to ensure:

1. **Prerequisites Validation**: The assistant automatically checks for and validates the presence of Stages 1-3 strategic foundation before beginning Stage 4 work

2. **Strategic Alignment**: All Stage 4 content seamlessly integrates and reflects the strategic decisions made in Stages 1-3

3. **Knowledge Base Integration**: The assistant efficiently accesses and applies stored strategic context from `inputs/knowledge-bases/job_search_knowledge_base.json`

4. **Workflow Continuity**: Smooth handoff from strategic planning (Stages 1-3) to tactical execution (Stage 4)

5. **Quality Control**: Content maintains consistency with established brand narrative and career objectives

## Instructions for Optimization

Ensure the job finding assistant:

- **Validates Prerequisites**: Automatically confirms Stages 1-3 are complete before starting
- **Integrates Strategic Context**: References stored career objectives, personal brand, and go-to-market strategy in all content
- **Maintains Brand Consistency**: Uses pre-defined value propositions and messaging frameworks
- **Executes Tactically**: Focuses on content creation rather than strategy development
- **Measures Success**: Delivers content that generates responses and advances toward job offers

The assistant should refuse to proceed with Stage 4 content creation if the strategic foundation from Stages 1-3 is incomplete, directing users to complete prerequisite stages first.

Make sure this workflow functions seamlessly when deployed, following all best practices for prompt engineering and ensuring clear task boundaries between strategic planning and tactical execution.
