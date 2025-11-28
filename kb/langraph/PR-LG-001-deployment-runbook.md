---
id: PR-LG-001
title: LangGraph Deployment Runbook
category: process
tags:
- langgraph
- deployment
- ops
version: 1.0.0
created_at: 2025-02-20
updated_at: 2025-02-20
author: Agent Platform Team
confidence: medium
contacts:
- name: Sahana Kulkarni
  title: LangGraph Platform PM
  email: langgraph-pm@company.com
  slack: '@sahana'
  notes: Coordinates release readiness reviews.
  priority: 1
- name: Dev Ops On-call
  title: DevOps
  email: devops@company.com
  slack: '#incident-ai'
  notes: Handles build failures and rollbacks.
  priority: 2
systems:
- LangGraph Platform
- LangGraph Studio
- GitHub Actions
related_units:
- CO-LG-001
- LG-APPLICATION-STRUCTURE
last_reviewed: '2025-11-27'

---

# Summary
Step-by-step instructions for promoting a LangGraph workspace from sandbox to production, including code, config, and monitoring actions.

# Details
## Prerequisites
- PR merged into `main` with pipeline tests passing.
- `langgraph.json` contains environment-specific overrides.
- Observability dashboard updated with run IDs.

## Steps
1. **Package** – run `npm run build:langgraph` (see repo) to compile graphs + dependencies.
2. **Scan** – DevSecOps runs policy-as-code checks (CO-LG-001) and attaches results to the release ticket.
3. **Deploy** – use LangGraph CLI `langgraph deploy --target prod` referencing `langgraph.json`.
4. **Validate** – open Studio, replay latest recording, and compare against evaluation metrics (MT-002).
5. **Announce** – notify #ai-platform with release summary and rollback plan.

## Rollback
- `langgraph deploy --target prod --release <prev>` to revert.
- Restore secrets via Vault snapshot if env vars changed.

# References
- CO-LG-001 LangGraph Usage & Governance
- LG-Application Structure
