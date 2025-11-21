---
id: MT-001
title: Knowledge Ingestion Latency
category: metric
version: 0.1.0
tags: [metrics, ingestion, ops]
created_at: 2024-05-05
updated_at: 2024-05-05
author: Ops Analytics
source_repo: sans-serif-sentiments/knowledge-repo
confidence: medium
---

# Summary
Defines the SLA for turning merged KB pull requests into indexed chunks available to downstream assistants.

# Details
## Definition
Time between merge timestamp in this repo and confirmation from `/health` that `last_indexed_at` reflects the new commit.

## Targets
- P50: < 5 minutes
- P90: < 15 minutes
- Error budget: 2 ingest failures per quarter

## Measurement
- GitHub Actions emit webhooks to the ingestion service.
- Observability pipeline records ingest start/end in the metrics warehouse.

# References
- Ingestion pipeline doc (app/kb/ingestion.py)
- Ops dashboard (Looker link)
