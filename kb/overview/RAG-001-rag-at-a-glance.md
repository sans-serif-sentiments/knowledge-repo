---
id: RAG-001
title: RAG at a Glance
category: overview
version: 1.0.0
contacts:
  - name: AI Platform
    email: ai-platform@company.com
tags:
  - rag
  - retrieval
  - architecture
last_reviewed: 2025-11-27
systems:
  - ai-kms
related_units:
  - EN-FAQ-004
  - assets/rag_ingest_flow.md
  - assets/query_flow.md
---

## How it works
- **Ingest:** Parse KB markdown, validate frontmatter, chunk, store metadata in SQLite, embeddings in Chroma.
- **Retrieve:** Hybrid search (BM25 + vectors + graph) with allowed_prefixes per intent; rerank top candidates.
- **Generate:** LLM answers strictly from selected chunks; shows sources and confidence.
- **Guardrails:** If no good chunks, say so and suggest KB IDs; external mode only when user allows it.

## Diagrams
- RAG/Ingest flow: assets/rag_ingest_flow.md
- Query flow: assets/query_flow.md
- AI change/rollback: assets/ai_change_rollback_flow.md

## What to cite
- Internal KB IDs (HR, IT, SEC, AI, LG, FIN, SALES, etc.) and relevant sections.
- Avoid external links unless approved per AI-003.
