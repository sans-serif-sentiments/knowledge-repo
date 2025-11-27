---
id: OL-PR-001
title: Local LLM Deploy, Update, and Rollback
category: process
tags:
  - ollama
  - deployment
  - rollback
version: 1.0.0
status: active
owners:
  - name: DevOps Lead
    email: devops@company.com
contacts:
  - name: DevOps Lead
    email: devops@company.com
  - name: AI Platform Lead
    email: ai-platform@company.com
last_reviewed: 2025-11-26
---

## Steps
1) **Request & Plan:** Ticket with model/version, test plan, rollback steps.
2) **Stage:** Load model in staging; run smoke tests (latency, retrieval, citations).
3) **Deploy:** Roll out to prod (Ollama) during window; announce to stakeholders.
4) **Validate:** Run test prompts; monitor errors/latency; check logs.
5) **Rollback:** If issues, revert to prior model/config; document and notify.

## Notes
- Keep a version ledger of models/configs.
- For prompt/template/reranker changes, follow AI-PR-001 and keep rollback steps.

## Contacts
- DevOps Lead — devops@company.com
- AI Platform Lead — ai-platform@company.com
