---
id: AI-PR-002
title: AI Incident Response
category: process
tags:
  - ai
  - incident
  - response
version: 1.0.0
status: active
owners:
  - name: AI Governance Lead
    email: ai-governance@company.com
contacts:
  - name: AI Governance Lead
    email: ai-governance@company.com
  - name: SOC Lead
    email: soc@company.com
last_reviewed: 2025-11-26
---

## Triggers
- Harmful/offensive outputs reach users.
- PII/regulated data exposure via prompts/outputs.
- Unauthorized model/tool use or policy violations.

## Steps
1) **Contain:** Disable/rollback the model or feature; block further calls if needed.
2) **Assess:** Identify impacted users/data; classify severity with Security/Compliance.
3) **Notify:** AI Governance + SOC + affected stakeholders; follow CO-005 for comms if customer-facing.
4) **Eradicate/Recover:** Fix prompts/configs/models; re-enable after validation.
5) **Postmortem:** Within 72 hours—root cause, mitigations, tests added, follow-ups tracked.

## Logs & Evidence
- Capture prompts/outputs involved, timestamps, model versions, config deltas, and access logs.

## Contacts
- AI Governance Lead — ai-governance@company.com
- SOC Lead — soc@company.com
