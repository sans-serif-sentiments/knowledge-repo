# Knowledge Repository

This repo is the source of truth for the AI-KMS knowledge base. Content lives as Markdown files under `kb/` with YAML frontmatter that the ingestion pipeline parses into structured `KnowledgeUnit`s.

## Directory Layout

```
kb/
  concepts/
  processes/
  policies/
  glossary/
```

You can add additional folders as long as they sit under `kb/`. The category is driven by frontmatter, not the directory path.

## Frontmatter Schema

Each Markdown file needs YAML frontmatter like:

```yaml
---
id: PE-001
title: Prompt Engineering Fundamentals
category: concept
version: 1.2.0
tags: [prompting, llms]
created_at: 2025-10-01
updated_at: 2025-11-17
author: Shailesh Rawat
source_repo: sans-serif-sentiments/knowledge-repo
confidence: high
---
```

After the frontmatter, structure your content with headings such as `# Summary`, `# Details`, `# Examples`, `# References`. The parser uses these headings to generate retrieval chunks.

## Authoring Checklist

- Choose a unique `id` (prefix with domain, e.g., `PE-###`).
- Select a category from `[concept, process, policy, glossary, faq, decision, metric, pattern]`.
- Include at least one `tag`; multiple tags improve filtering.
- Update `version`, `created_at`, and `updated_at` every time content changes.
- Use `confidence` to reflect data quality (low/medium/high).
- Keep sections concise—prefer bullet lists for details and examples.

## Contribution Workflow

1. Create or update files under `kb/`.
2. Run spell-check / lint if desired.
3. `git add kb/... && git commit -m "Add {id} {title}" && git push`.
4. Pull changes into the AI-KMS service (`make sync` or POST `/sync`) so the indexes refresh.

## License

See [LICENSE](LICENSE).
