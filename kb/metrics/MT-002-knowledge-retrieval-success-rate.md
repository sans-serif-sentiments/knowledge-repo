---
id: MT-002
title: Knowledge Retrieval Success Rate
category: metric
tags: [metrics, retrieval, rag]
version: 0.1.0
created_at: 2025-02-18
updated_at: 2025-02-18
author: Ops Analytics
source_repo: sans-serif-sentiments/knowledge-repo
confidence: medium
related_units:
  - KG-002
  - PR-002
systems:
  - SQLite
  - Looker
---

# Summary
Measures how often the hybrid retriever surfaces at least one chunk above the min-score threshold for production traffic.

# Details
## Definition
`successful_queries / total_queries` where *success* means `selected_chunks >= 1` and response confidence != `low`.

## Targets
- Weekly minimum: 92%
- Stretch: 95%+ after every ingestion batch
- Alert if drop >3 points within 24 hours

## Data Sources
- `/query` debug payloads logged to the warehouse
- Chroma + SQLite metadata joined by `knowledge_unit_id`
- Evaluation harness outputs stored under `app/eval`

# References
- KG-002 Context Packaging Framework
- PR-002 Incident Postmortem Lifecycle
