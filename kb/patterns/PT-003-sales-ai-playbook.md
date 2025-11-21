---
id: PT-003
title: Sales AI Assist Playbook
category: pattern
tags: [sales, ai, langgraph, playbook]
version: 0.1.0
created_at: 2025-02-20
updated_at: 2025-02-20
author: Revenue Enablement
confidence: medium
contacts:
  - name: Lila Moreno
    title: VP Revenue Enablement
    email: lila.moreno@company.com
    slack: "@lila-moreno"
    notes: Owns playbook updates + training.
    priority: 1
systems:
  - Salesforce
  - Gong
related_units:
  - CO-003
  - EN-FAQ-002
---

# Summary
Reusable pattern for sales teams using LangGraph-powered copilots during discovery calls, RFPs, and renewals while staying compliant with tone and data guardrails.

# Details
## Stages
1. **Preparation:** Query AI-KMS for account intel, reference CO-003 tone, and log prep notes in Salesforce.
2. **Live Call:** Use LangGraph Assistant to fetch policy clarifications in real time; cite KB IDs when sharing specifics.
3. **Follow-up:** Generate recap email with AI assist, reviewed by rep before sending; attach sources.

## Guardrails
- Never paste raw PII into prompts.
- For pricing/legal questions, auto-route to compliance or finance contact list.
- Tag AI-generated notes with `ai-assist` in Salesforce.

# References
- CO-003 Product Communication Bridge Policy
- EN-FAQ-002 Remote Access & VPN FAQ
