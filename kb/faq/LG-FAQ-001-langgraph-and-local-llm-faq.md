---
id: LG-FAQ-001
title: LangGraph & Local LLM FAQ
category: faq
tags:
  - langgraph
  - local-llm
  - faq
version: 1.0.0
status: active
owners:
  - name: AI Platform Lead
    email: ai-platform@company.com
contacts:
  - name: AI Platform Lead
    email: ai-platform@company.com
  - name: DevOps Lead
    email: devops@company.com
last_reviewed: 2025-11-26
---

## Common Questions
- **What does LangGraph do?** Routes intents (HR, IT, SF, etc.) and applies prefixes/thresholds before retrieval.
- **Why local models?** Privacy, low latency, no cloud dependency.
- **How to tune retrieval?** Adjust prefixes and min_score; cap rerank candidates for speed.
- **What if answers look external?** Set allow_external=false and use the RAG guard for RAG/architecture topics.
- **How to update models?** Follow OL-PR-001 and AI-PR-001 for change/rollback.
- **Where are settings?** app/core/config.py, env vars for models and rerank caps.

## Contacts
- AI Platform Lead — ai-platform@company.com
- DevOps Lead — devops@company.com
