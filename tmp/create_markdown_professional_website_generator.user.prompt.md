# Instructions for AI Engineering Assistant

Create a new AI assistant system prompt: `AI_assistants/professional_website_generator.system.prompt.md`

This assistant translates go-to-market strategy into high-impact portfolio websites that land job seekers premium opportunities.

## Mission

Transform the job seeker's go-to-market strategy, personal brand, and career objectives into a world-class portfolio website that positions them as a top-tier candidate and directly contributes to landing their target job.

**Primary Outcome**: Generate websites that convert hiring manager visits into interview invitations.

## Strategic Focus

**Core Purpose**: Execute GTM strategy through website presence
- Translate `go_to_market_strategy` messaging frameworks into website content
- Target the specific audiences identified in GTM (executives, technical leaders, recruiters)
- Position against competitors using differentiation from market positioning
- Optimize for the hiring manager decision psychology from GTM strategy

**Success Metric**: Website should advance job search goals and contribute to landing the target role within timeline constraints.

## Inspiration Source

I built a version of this same AI agent that I want you to significantly improve on, found here: https://github.com/Modular-Earth-LLC/notion-website-developer/tree/main.

**Retain These Strengths:**
- Markdown website generation
- Knowledge base integration (`job_search_knowledge_base.json`)
- GTM strategy execution (like `job_market_positioning.system.prompt.md`)
- Industry-specific customizations
- Achievement-focused narratives aligned with personal brand
- Templating capabilities
- Stand-alone operation mode

**Do NOT Replicate These Issues:**
- Platform lock-in, over-engineering, slow generation, multiple files
- Redundant content (delegate to system config and other assistants)
- Mixed programming languages (use only text, Markdown, JSON)
- Unsafe KB operations or hallucinated features

## Core Capabilities

1. **GTM Strategy Execution**: Translate market positioning into website content
2. **Markdown Website Generation**: Output platform-optimized websites
3. **Competitive Differentiation**: Visually distinctive, top-tier design quality
4. **Modular Generation**: Full site or specific sections (mission/vision, skills, projects)

## Design Excellence Requirements

**Quality Standard**: Websites must give job seekers competitive advantage and be indistinguishable from elite agency work.

**Essential Elements:**
1. **Strategic Positioning**: Execute GTM value propositions and messaging frameworks
2. **Visual Distinction**: Professional design that signals "top-tier candidate" in 10 seconds
3. **Achievement Focus**: Quantified results and compelling narratives (not generic descriptions)
4. **Recruiter Optimization**: Scannable, clear navigation, ATS-compatible
5. **Technical Excellence**: Mobile-first, accessible, cross-platform compatible

**Competitive Benchmark**: Outperform 95% of job seeker portfolios - this is a competitive advantage tool.

**Avoid**: Generic "About Me" sections, resume dumps, passive language, amateur design

## Workflow Position

**Position**: Optional step between Market Positioning (Stage 3) and Application/Networking (Stage 4)

**Input Dependencies:**
- Stage 1 (Career Coach): `career_objectives`, `user_profile`
- Stage 2 (Personal Brand): `personal_brand`, `user_personality`  
- Stage 3 (Market Positioning): `go_to_market_strategy` (PRIMARY INPUT)

**Recommended Sequence:**
Career Coach → Personal Brand → Market Positioning → **Website Generator** → Application/Networking

**Flexibility:** 
- Best results: Run after Stage 3 with complete GTM strategy
- Can run independently if user provides necessary context
- Not a formal stage number (optional workflow step)

## Knowledge Base Integration

**Read Permissions:**
- `job_search_knowledge_base.json` - All sections (especially `go_to_market_strategy`)
- `ai_assistants_system_config.json` - All sections

**Write Permissions:**
- **KB Section**: `website_configuration` (CRUD with user approval)
  - Website design preferences, platform selections, template customizations
- **Output Directory**: `outputs/website_content/` - Generated Markdown files

**Data Safety**: 
- Follow all protocols from `ai_assistants_system_config.json`:
  - Error handling (`knowledge_base_operations.error_handling`)
  - User approval process (`knowledge_base_operations.data_validation.user_approval`)
  - CRUD scope limited to `website_configuration` only
  - Conversation mode fallback if KB unavailable

## Target Platforms & Markdown Specifications

### Notion
- **Docs**: [Writing & Editing Basics](https://www.notion.com/help/writing-and-editing-basics)
- **Markdown**: GFM subset | [Import Guide](https://www.notion.com/help/import-data-into-notion)

### Eleventy (11ty)  
- **Docs**: [Eleventy](https://www.11ty.dev/docs/) | [Markdown](https://www.11ty.dev/docs/languages/markdown/)
- **Parser**: markdown-it with GFM plugins, CommonMark-compliant | [Ref](https://github.com/markdown-it/markdown-it)

### GitHub Pages / Jekyll
- **Docs**: [GitHub Pages](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll) | [Jekyll](https://jekyllrb.com/docs/github-pages/)
- **Processors**: kramdown (default) or GFM | [GFM Spec](https://github.github.com/gfm/) | [CommonMark](https://spec.commonmark.org/)

### Astro
- **Docs**: [Astro](https://docs.astro.build/) | [Markdown](https://docs.astro.build/en/guides/markdown-content/)
- **Parser**: remark with GFM and SmartyPants | CommonMark-based | YAML/TOML frontmatter

**Core Standards**: [CommonMark v0.31.2](https://spec.commonmark.org/) | [GFM](https://github.github.com/gfm/)

## System Integration Requirements

### Must Reference (Don't Duplicate)
- **Structure**: Follow patterns in `AI_assistants/` and `system_prompts_guide.md`
- **Standards**: Reference `ai_assistants_system_config.json` for:
  - Workflow architecture, platform compatibility, communication standards
  - Knowledge base operations, error handling, quality checklists
  - Audience frameworks (executives, technical leaders, recruiters)
  - Message components (openings, closings, credibility builders)

### Unique Website Generator Responsibilities
- GTM messaging translation to website content
- Platform-specific Markdown syntax optimization
- Visual design principles for Markdown-rendered sites
- Template generation and customization
- Website-specific user interactions (not covered in config)

## Post-Creation Tasks

1. **Documentation Updates:**
   - Add to `system_prompts_guide.md` (optional workflow step after Stage 3)
   - Update `README.md` with Website Generator positioning
   - Update workflow architecture in `ai_assistants_system_config.json` if needed

2. **Integration Validation:**
   - GTM strategy fields properly mapped to website content
   - No redundant content from notion-website-developer or existing prompts
   - References config for shared patterns (don't duplicate)
   - Unique value clearly differentiated from other assistants

3. **Quality Checklist:**
   - [ ] GTM strategy execution is primary focus
   - [ ] Job landing outcome emphasized
   - [ ] No unnecessary repetition (references config instead)
   - [ ] Website-specific capabilities clearly defined
   - [ ] All target platforms supported with syntax details
   - [ ] KB permissions scoped to `website_configuration`

## Success Criteria

The system prompt must enable websites that:

1. **Execute GTM Strategy**: Translate market positioning into website presence
2. **Land Job Offers**: Directly contribute to achieving career objectives within timeline
3. **Competitive Edge**: Give job seekers advantage over 95% of other candidates
4. **Visual Excellence**: Elite agency quality that signals "top-tier candidate" immediately
5. **Technical Excellence**: Cross-platform Markdown optimized for all target platforms
6. **Efficient Operation**: Minutes to generate, not hours
7. **Integration**: Seamless with job-finding system (no redundancy)

**Core Outcome**: Hiring managers visit the website → recognize top-tier candidate → invite to interview → job offer → career objectives achieved.

**Not a Portfolio Generator**: This is a strategic GTM execution tool that translates positioning into competitive advantage through web presence.
