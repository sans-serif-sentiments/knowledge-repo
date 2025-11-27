---
id: SEC-004
title: MFA, Password, and Secrets Policy
category: policy
tags:
  - security
  - mfa
  - passwords
  - secrets
version: 1.0.0
status: active
owners:
  - name: Security Architect
    email: security@company.com
contacts:
  - name: Security Architect
    email: security@company.com
  - name: IT Access Manager
    email: it-access@company.com
last_reviewed: 2025-11-26
---

## Requirements
- MFA required for all corporate apps; hardware token where available for admins.
- Strong passwords; rotate secrets in vaults; no secrets in code/repos/prompts.
- Shared credentials forbidden; use SSO and per-user accounts.

## Contacts
- Security Architect — security@company.com
- IT Access Manager — it-access@company.com
