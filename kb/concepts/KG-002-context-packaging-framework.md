---
id: KG-002
title: Context Packaging Framework
category: concept
tags:
- rag
- context
- retrieval
version: 1.0.0
created_at: 2025-02-18
updated_at: 2025-02-18
author: RAG Architecture Guild
source_repo: sans-serif-sentiments/knowledge-repo
confidence: medium
related_units:
- MT-002
- PT-002
systems:
- Chroma
- Ollama
contacts:
- name: Knowledge Steward
  email: knowledge@company.com
last_reviewed: '2025-11-27'

---

# Summary
Explains the layered heuristic we use to decide which knowledge chunks enter an LLM prompt so answers stay grounded, deduplicated, and within the configured token budget.

# Details
## Pillars
1. **Signal Strength** – prefer lexical/vector consensus hits above the min-score threshold.
2. **Diversity** – cap at two chunks per knowledge unit unless confidence is low.
3. **Freshness** – break ties with `updated_at` timestamps to reflect the newest policies.

## Implementation Notes
- `app/rag/pipeline.py` trims the final list using `max_context_chars`.
- Graph-sourced contact chunks are appended last so owner info is easy to cite.
- Each packaged chunk carries `knowledge_unit_id`, `section`, and `title` metadata for auditing.

# Examples
- PTO questions pull 2 HR-002 body snippets + 1 contacts chunk (< 7k chars total).
- Incident inquiries mix SEC-002 severity steps with MT-002 SLA reminders when tokens allow.

# References
- Retrieval architecture overview
- MT-002 Knowledge Retrieval Success Rate
