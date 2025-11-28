---
id: IT-002
title: Access Control Standards
category: policy
tags:
- it
- access
- security
version: 1.2.0
created_at: 2024-08-12
updated_at: 2025-02-18
author: IT Security
source_repo: sans-serif-sentiments/knowledge-repo
confidence: high
contacts:
- name: Riya Menon
  title: Identity & Access Manager
  email: iam@company.com
  slack: '@riya.menon'
  phone: +1-415-555-0301
  notes: Approves privileged access and quarterly reviews.
  priority: 1
- name: Mateo Alvarez
  title: SOC Lead
  email: secops@company.com
  slack: '@mateo.alvarez'
  notes: Coordinates emergency revocations tied to SEC-002.
  priority: 2
related_units:
- SEC-002
- PR-001
systems:
- Okta
- Jamf
last_reviewed: '2025-11-27'

---

# Summary
Defines provisioning, least-privilege, and review requirements for SaaS tools, infrastructure credentials, and local admin rights.

# Details
## Provisioning
- Requests originate in Workday or the Access Portal catalog.
- Managers must document business justification; IAM verifies compliance with role matrices.
- High-risk tools (prod DB, customer data lake) require VP and SOC sign-off.

## Reviews
- Quarterly: IAM exports entitlement reports, managers attest via audit workflow.
- Immediate: revoke access during offboarding or SEV1 incidents as outlined in SEC-002.

## Tooling
- Okta manages SSO, with SCIM syncing to SaaS apps.
- Jamf + Intune enforce device security baselines before granting local admin.
- Access ledger entries mirror PR-001 audit requirements.

# References
- SEC-002 Security Incident Response Playbook
- PR-001 User Data Access Request Flow
