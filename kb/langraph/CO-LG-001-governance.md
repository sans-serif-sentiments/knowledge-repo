---
id: CO-LG-001
title: LangGraph Usage & Governance
category: policy
tags: [langgraph, governance, ai]
version: 1.0.0
created_at: 2025-02-20
updated_at: 2025-02-20
author: AI Solutions Council
confidence: medium
contacts:
  - name: Meera Balan
    title: Director, AI Solutions Council
    email: ai-governance@company.com
    slack: "@meera.balan"
    notes: Approves new LangGraph-powered assistants.
    priority: 1
  - name: Lucas Brandt
    title: Principal Agent Engineer
    email: lucas.brandt@company.com
    slack: "@lucas"
    notes: Technical owner of our LangGraph templates.
    priority: 2
systems:
  - LangGraph Platform
  - GitHub Actions
related_units:
  - PR-LG-001
  - LG-AGENT-DEVELOPMENT
---

# Summary
Defines how we adopt LangGraph inside the organisation, including approved use cases, contribution standards, and operational guardrails.

# Details
## Approved scenarios
- Tier-1: internal copilots built for Engineering, GTM, or Operations teams.
- Tier-2: customer-facing workflows that require extra human-in-the-loop checkpoints.
- Tier-3: Research/experiment branches that never touch production data.

## Guardrails
1. **Code ownership** – every LangGraph repo must have an on-call maintainer documented in `packages.yml`.
2. **Security** – follow CO-002 privacy handling policies when LangGraph nodes touch user data.
3. **Observability** – emit graph run IDs and tool usage to the AI Ops dashboard.

# References
- PR-LG-001 LangGraph Deployment Runbook
- LG-Agent Development Guide
