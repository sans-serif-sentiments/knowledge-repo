---
id: CL-PL-001
title: Claude Usage Policy (Enterprise Tenant)
category: policy
tags:
  - ai
  - saas
  - claude
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
Use of Anthropic Claude (enterprise) for internal knowledge and productivity tasks.

## Allowed / Not Allowed
- Allowed: internal KB Q&A, summaries, drafting internal docs without regulated PII.
- Not allowed: regulated PII/PCI/PHI or customer secrets without explicit approval; no copying training data out.

## Controls
- Access via SSO/MFA; provision through CL-PR-001.
- Data handling per SEC-003; redact PII, avoid secrets in prompts.
- Logging: enable prompt/output logging for sensitive workflows; follow CP-004 retention.

## Change & Rollback
- Model updates/config changes follow AI-PR-001; rollback to prior version if issues.

## Contacts
- AI Platform Lead — ai-platform@company.com
- Security Architect — security@company.com
