---
id: OL-PL-001
title: Local LLM Usage Policy (Ollama)
category: policy
tags:
  - ollama
  - local-llm
  - ai
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

## Scope
Use of local models via Ollama for internal workloads.

## Allowed / Not Allowed
- Allowed: internal KB Q&A, prototypes, non-regulated content.
- Not allowed: regulated PII/PCI/PHI, secrets, or customer data unless explicitly approved and controls are enabled.

## Controls
- Approved models: `llama3.2:3b`, embeddings `bge-small-en`, reranker `bge-reranker-base` (per AI-002).
- Data handling per SEC-003; redact PII; avoid secrets in prompts.
- Logging and retention per CP-004 when handling sensitive use cases.

## Change & Rollback
- Model/config updates follow AI-PR-001; rollback to last known-good model if issues.

## Contacts
- AI Platform Lead — ai-platform@company.com
- DevOps Lead — devops@company.com
