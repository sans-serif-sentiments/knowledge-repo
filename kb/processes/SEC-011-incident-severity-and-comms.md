---
id: SEC-011
title: Security Incident Severity and Communications
category: process
version: 1.0.0
contacts:
  - name: Security Operations
    email: sec-ops@company.com
  - name: Incident Comms
    email: incident-comms@company.com
tags:
  - security
  - incident
  - communications
last_reviewed: 2025-11-27
systems:
  - incident-tracker
  - comms-bridge
related_units:
  - CO-005
  - SEC-005
  - AI-PR-002
---

## Severity levels (S1–S4)
- **S1 Critical:** Active data loss/service outage; immediate exec bridge and customer notifications.
- **S2 High:** Contained but material risk; rapid response; targeted stakeholder comms.
- **S3 Medium:** Limited scope/low impact; track and remediate; internal comms only.
- **S4 Low:** Informational; log and monitor.

## Roles
- Incident Commander: runs response, owns timelines and actions.
- Comms Lead: prepares internal/external messaging; coordinates CO-005.
- Tech Lead: drives investigation and remediation.

## Communications
- For S1/S2, Comms Lead drafts templates per CO-005; legal review before external sends.
- Customer notices align with contracts/SLAs; keep single source of truth in incident tracker.

## Handoffs
- If AI/LLM systems involved, follow AI-PR-002 (AI Incident Response) in parallel.
- Third-party/vendor issues must engage SEC-005 (vendor security).
