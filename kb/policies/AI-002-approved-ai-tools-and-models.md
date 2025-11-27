---
id: AI-002
title: Approved AI Tools & Models
category: policy
tags:
  - ai
  - tooling
  - governance
version: 1.0.0
status: active
owners:
  - name: AI Platform Lead
    email: ai-platform@company.com
contacts:
  - name: AI Platform Lead
    email: ai-platform@company.com
  - name: Security Architect
    email: security@company.com
last_reviewed: 2025-11-26
---

## Scope
Defines the approved AI tools/models and the conditions under which they may be used.

## Approved Stack (examples)
- Local: Ollama-hosted models (llama3.2:3b, bge-small-en embeddings, bge-reranker-base), LangGraph orchestrator.
- SaaS: Anthropic Claude (enterprise tenant) for non-PII knowledge tasks.
- Utilities: Internal KB ingestion tools (app/kb/*), Chroma/SQLite storage.

## Data Handling Rules
- Follow SEC-003 classification; do not paste regulated PII/PCI/PHI into SaaS models without explicit approval.
- Use redaction/minimization for prompts; store outputs per CP-004 retention rules.
- Log AI interactions when handling customer or compliance-relevant data.

## Change & Rollback
- New models/tools require AI-PR-001 (change) approval.
- Rollback plans must exist for any model or config update (see OL-PR-001 and CL-PR-001).

## Exceptions
- Require AI Platform + Security approval, documented with ticket ID and expiry.

## Contacts
- AI Platform Lead — ai-platform@company.com
- Security Architect — security@company.com
