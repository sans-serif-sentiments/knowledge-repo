---
id: SEC-003
title: Data Classification & Handling
category: policy
tags:
  - security
  - data
  - classification
version: 1.0.0
status: active
owners:
  - name: Security Architect
    email: security@company.com
contacts:
  - name: Security Architect
    email: security@company.com
  - name: Compliance Officer
    email: compliance@company.com
last_reviewed: 2025-11-26
---

## Classes
- Public, Internal, Confidential, Restricted (PII/PCI/PHI).

## Rules
- Restricted data only in approved systems; no prompts/uploads to SaaS AI without approval.
- Encrypt in transit/at rest; log access to Restricted data; least privilege.
- Use redaction/minimization before sending to tools; follow retention (CP-004).

## Contacts
- Security Architect — security@company.com
- Compliance Officer — compliance@company.com
