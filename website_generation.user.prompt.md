# Single-Page Notion Website Generator — User Prompt Template

This is a reusable, YAML-inspired Markdown prompt you can fill in and paste into your AI agent to generate a single-page, professional personal website in advanced Markdown. The result will be easy to copy-paste into a single Notion page and act as your business website at your custom domain.

—

## How to use
1) Fill in the “Fill me in” section below completely (keep keys, replace values).
2) Paste the entire prompt into your AI agent (Claude, ChatGPT, etc.).
3) The agent must output a single Markdown document only, following the Output Spec.
4) Copy the result and paste into a new Notion page; Notion will auto-convert.

—

## Fill me in (User Inputs)

site:
	# Treat me as a services + product startup. Keep brand and message simple.
	brand_name: "Paul Prae"
	primary_message: "I help [TARGET CUSTOMER] achieve [OUTCOME] with [CORE CAPABILITY]."
	# One core idea that everything aligns to; keep it short and sticky.
	core_narrative: "[ONE-LINER VALUE PROP]"
	# Who should hire me and why (must align to GTM strategy and career objectives).
	target_audiences:
		- name: "[Title/Segment: e.g., Founders at seed/Series A]"
			pain_points: ["[pain 1]", "[pain 2]"]
			desired_outcomes: ["[outcome 1]", "[outcome 2]"]
	career_objectives:
		- "[Objective 1]"
		- "[Objective 2]"
	gtm_strategy_alignment:
		offer_positioning: "[Positioning statement]"
		pricing_or_engagement_model: "[e.g., Fractional, Advisory, Fixed-scope, Day rate]"
		proof_strategy: "[Case studies, metrics, references, open-source, talks]"
	services:
		- name: "[Service Name]"
			description: "[What it is, who it’s for, outcome]"
			deliverables: ["[Deliverable 1]", "[Deliverable 2]"]
			time_to_value: "[e.g., 2 weeks to initial results]"
		- name: "[Service Name]"
			description: "[...]"
			deliverables: ["..."]
			time_to_value: "[...]"
	products:
		- name: "[Product/Asset Name]"
			type: "[Template / Toolkit / Micro-SaaS / Course]"
			description: "[Short what/why]"
			link: "[URL or coming-soon]"
	key_skills:
		categories:
			- name: "[e.g., AI/ML Engineering]"
				skills: ["[Skill]", "[Skill]"]
			- name: "[e.g., Product & GTM]"
				skills: ["[Skill]"]
	selected_projects_gallery:
		# Provide 4–12 high-signal items; these will appear in a minimal gallery/table.
		- title: "[Project Name]"
			role: "[Your role]"
			context: "[Company/Stage/Industry]"
			stack: ["[Tech]", "[Tech]"]
			problem: "[What was broken]"
			approach: "[What you did]"
			impact: "[Metric or concrete outcome]"
			link: "[URL]"
			image: "[Optional image URL]"
		- title: "[...]"
			role: "[...]"
			context: "[...]"
			stack: ["..."]
			problem: "[...]"
			approach: "[...]"
			impact: "[...]"
			link: "[...]"
			image: "[...]"
	testimonials:
		- quote: "[Short punchy quote]"
			author: "[Name, Title, Company]"
			link: "[LinkedIn or site]"
	references_and_inspiration:
		# Use these to guide style/tone/structure (the agent should pattern-match, not copy).
		- url: "[reference-site-1]"
			notes: "[what you like]"
		- url: "[reference-site-2]"
			notes: "[...]"
	contact:
		primary_cta_label: "Email Paul"
		primary_cta_link: "mailto:paul@paulprae.com"
		secondary_links:
			- label: "LinkedIn"
				url: "[LinkedIn URL]"
			- label: "GitHub"
				url: "[GitHub URL]"
			- label: "Twitter/X"
				url: "[Profile URL]"
	visual_style:
		# Minimal, resume-like. Emphasis on clarity and whitespace. No heavy art.
		tone: "confident, direct, senior operator energy"
		typography: "[Sans only / Sans + Mono for code]"
		color_notes: "[monochrome or 1-accent]"
		icon_style: "[Simple emoji or none]"
	notional_sections: # Toggle any off by removing it; agent will omit.
		- hero
		- services
		- products
		- projects_gallery
		- skills
		- testimonials
		- process
		- about
		- contact

—

## Non‑negotiable guardrails (do not edit)
- Treat the subject as a services + product startup; this is a business website.
- Keep messaging extremely simple; align all content to one single core message.
- Align copy and structure to the GTM strategy and career objectives.
- Minimal design, resume-like. Emphasize a clean projects gallery and concise skills.
- Output must be a single Markdown document that is easy to paste into Notion.

—

## Agent Instructions (Generate the website in Markdown)
You are an expert brand/copy + product/AI engineer website generator. Using the filled “site” object above, produce a single, clean, professional Markdown page suitable for a Notion single-page site. Follow the Output Spec and Content Outline. Keep the entire page oriented around the core_narrative. Do not include commentary or placeholders—output the final website only.

### Output Spec
- Single Markdown document; no HTML, no CSS, no scripts.
- Use a strict heading hierarchy: H1 for the page title (brand), H2 for sections, H3 for items.
- Use minimal emoji sparingly (optional) for scannability; do not overdecorate.
- Projects gallery must render clearly in Notion. Prefer a Markdown table with concise columns.
- Keep paragraphs short and skimmable; use bullets for dense info.
- Include at least two strong CTAs to contact/hire aligned with target_audiences.
- No lorem ipsum. Every sentence should advance the single message.

### Content Outline (in this exact order)
1) H1 — Brand Name and One-Liner
	 - H1: brand_name
	 - Short one-liner: primary_message (bold)
	 - One sentence to frame core_narrative and target_audiences.

2) H2 — Services (Business-first)
	 - For each service: H3 Name; 1–2 sentence description; bullets: deliverables, time_to_value, ideal buyer.
	 - Close with a short proof_strategy tie-in.

3) H2 — Products / Assets (Optional)
	 - Short list of assets that accelerate outcomes; link each.

4) H2 — Selected Projects (Gallery)
	 - Preface: what the selection demonstrates (aligned to GTM + objectives).
	 - Render as a compact Markdown table with these columns:

		 | Project | Role | Context | Stack | Impact | Link |
		 |---|---|---|---|---|---|
		 | [Title] | [Role] | [Company/Stage] | [Tech, Tech] | [Metric/Outcome] | [URL] |

	 - Optionally include 1–2 short bullet call-outs below the table for standout wins.

5) H2 — Skills (Concise Matrix)
	 - Group by categories. One line per category with comma-separated skills.

6) H2 — Testimonials (Social Proof)
	 - 2–5 concise quotes with author, title, and link.

7) H2 — How I Work (Process)
	 - 3–5 steps from discovery to delivery; mention engagement model and speed to value.

8) H2 — About
	 - 2–4 tight paragraphs focused on credibility and relevance to the audience.

9) H2 — Contact / Hire
	 - Primary CTA (button-like as bold link text), plus secondary links (LinkedIn, GitHub, etc.).

10) Footer (Light)
	 - Simple line with brand_name and contact; no legalese.

### Style & Tone
- Confident, concise, operator-level clarity. No fluff, no clichés.
- Use numbers and outcomes where possible. Replace adjectives with metrics.
- Avoid jargon unless the audience expects it; explain once, then use shorthand.

### Notion Compatibility Notes
- Stick to standard Markdown headers, lists, bold/italics, links, and tables.
- Images, if any, should be external URLs on their own lines.
- Use horizontal rules (---) to create visual separation sparingly.

### QA Checklist (self-verify before returning)
- Single idea throughout: Does every section reinforce core_narrative?
- Skimmability: Are headings/bullets crisp and non-redundant?
- Gallery: Are 4–12 items, each with a concrete impact, present in the table?
- CTAs: Are there at least two clear, irresistible hire/contact prompts?
- Notion: Would this paste cleanly as one page with no broken formatting?

—

## Example micro-prompts the agent may internalize (do not output verbatim)
- "Make the first screen answer: What Paul does, for whom, and why now."
- "Lead with outcomes and speed-to-value; back with credible proof."
- "Every bullet starts with a strong verb and ends with a concrete benefit."
- "Prune anything that doesn’t reinforce the single core message."

—

## Deliverable
Return only the final website in Markdown, following the Output Spec and Content Outline, with no extra commentary.

