---
description: 'Documentation and content creation standards'
applyTo: '**/*.md'
---

## Markdown Content Rules
The following markdown content rules are enforced in the validators:
1. **Headings**: Use appropriate heading levels (H2, H3, etc.) to structure your content. Do not use an H1 heading, as this will be generated based on the title.
2. **Lists**: Use bullet points or numbered lists for lists. Ensure proper indentation and spacing.
3. **Code Blocks**: Use fenced code blocks for code snippets. Specify the language for syntax highlighting. Use fenced code blocks for YAML/CSV/data. Allow code blocks for data (YAML/CSV), code, and commands; avoid code blocks for prose.
4. **Links**: Use proper markdown syntax for links. Ensure that links are valid and accessible.
5. **Images**: Use proper markdown syntax for images. Include alt text for accessibility.
6. **Tables**: Use markdown tables for tabular data. Ensure proper formatting and alignment.
7. **Whitespace**: Use appropriate whitespace to separate sections and improve readability.
8. **Front Matter**: As necessary, include YAML front matter at the beginning of the file with required metadata fields.

## Markdown Formatting and Structure
Follow these guidelines for formatting and structuring your markdown content:
- **Headings**: Use `##` for H2 and `###` for H3. Ensure that headings are used in a hierarchical manner. Recommend restructuring if content includes H4, and more strongly recommend for H5.
- **Lists**: Use `-` for bullet points and `1.` for numbered lists. Indent nested lists with two spaces. Prefer bullets, numbered steps, and small tables over long paragraphs. Use tables only when necessary for compact tabular data; prefer lists for most content in this repo.
- **Code Blocks**: Use triple backticks (`) to create fenced code blocks. Specify the language after the opening backticks for syntax highlighting (e.g., `csharp).
- **Links**: Use `[link text](URL)` for links. Ensure that the link text is descriptive and the URL is valid.
- **Images**: Use `![alt text](image URL)` for images. Include a brief description of the image in the alt text.
- **Tables**: Use `|` to create tables. Ensure that columns are properly aligned and headers are included.
- **Whitespace**: Use blank lines to separate sections and improve readability. Avoid excessive whitespace.

## Markdown Validation Requirements
Ensure compliance with the following validation requirements:
- **Formatting**: Ensure that the content is properly formatted and structured according to the guidelines.
- **Validation**: Run the validation tools to check for compliance with the rules and guidelines.
 - When not applicable: Blog front matter and publishing validators MUST be skipped for prompt authoring tasks.
