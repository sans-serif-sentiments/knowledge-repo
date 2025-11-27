---
id: AI-PR-001
title: AI Change Request & Rollback Process
category: process
tags:
  - ai
  - change-management
  - rollback
version: 1.0.0
status: active
owners:
  - name: AI Platform Lead
    email: ai-platform@company.com
contacts:
  - name: AI Platform Lead
    email: ai-platform@company.com
  - name: DevOps On-Call
    email: devops@company.com
last_reviewed: 2025-11-26
---

## When to use
- Adding/updating/removing an AI model/tool (local or SaaS).
- Changing prompt templates, retrieval thresholds, reranker, or embeddings.

## Steps
1) **Request:** File a change ticket with: model/tool, data class, owner, test plan, rollback plan.
2) **Review:** AI Platform + Security/Compliance approve or reject; confirm logging/retention requirements.
3) **Test:** Run in staging with sample prompts; verify citations and guardrails.
4) **Deploy:** Schedule window; announce to stakeholders; capture versions/configs.
5) **Validate:** Run smoke tests; monitor errors/latency and guardrail hits.
6) **Rollback:** If issues, revert to prior model/config; notify stakeholders; log incident if needed.

## Artifacts to keep
- Ticket ID, model/version, embeddings/reranker versions, prompts, test results, rollback steps.

## Contacts
- AI Platform Lead — ai-platform@company.com
- DevOps On-Call — devops@company.com
