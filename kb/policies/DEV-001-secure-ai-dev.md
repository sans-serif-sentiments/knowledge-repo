---
id: DEV-001
title: Secure AI Development Policy
category: policy
tags:
- dev
- security
- ai
version: 1.0.0
created_at: 2025-02-20
updated_at: 2025-02-20
author: Platform Security
confidence: medium
contacts:
- name: Mateo Alvarez
  title: SOC Lead
  email: secops@company.com
  slack: '@mateo.alvarez'
  notes: Handles AI code review escalations.
  priority: 1
- name: Jia Patel
  title: Lead ML Engineer
  email: jia.patel@company.com
  slack: '@jia-patel'
  notes: Maintains LangGraph templates and threat models.
  priority: 2
related_units:
- IT-002
- CO-LG-001
systems:
- GitHub
- LangGraph Platform
last_reviewed: '2025-11-27'

---

# Summary
Mandates secure coding practices for AI-assisted development, covering source control, dependency scanning, and LangGraph graph reviews.

# Details
## Code Requirements
- Use approved LangGraph templates; custom nodes require security review.
- All PRs must run `make secure` (static analysis + dependency audit) before merge.
- Sensitive secrets never live in graphs; use vault references.

## Operational Controls
- LangGraph deployments must reference CO-LG-001 guardrails.
- Devs must log AI-generated code segments in PR descriptions (“AI diff” block).
- SOC monitors runtime logs for unusual tool calls.

# References
- IT-002 Access Control Standards
- CO-LG-001 LangGraph Usage & Governance
