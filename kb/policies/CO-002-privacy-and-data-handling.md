---
id: CO-002
title: Privacy & Data Handling Policy
category: policy
tags:
- privacy
- data-handling
- compliance
version: 2.0.0
created_at: 2025-01-04
updated_at: 2025-01-15
author: Priya D'Souza
source_repo: sans-serif-sentiments/knowledge-repo
confidence: high
contacts:
- name: Communications
  email: comms@company.com
last_reviewed: '2025-11-27'

---

# Summary
Defines the mandatory controls for collecting, processing, storing, and deleting customer and employee data across all products.

# Details
## Scope
- Applies to all employees, contractors, and vendors with access to user or employee data.
- Covers production systems, analytics environments, and offline exports.

## Core Requirements
1. **Data Minimization**: collect only fields needed for the stated business purpose.
2. **Access Controls**: access is role-based and reviewed quarterly by Security Ops.
3. **Encryption**: sensitive data encrypted in transit (TLS 1.3) and at rest (AES-256).
4. **Retention**: default retention window is 18 months unless legal/contractual obligations specify longer.
5. **Deletion Requests**: must be fulfilled within 15 business days with audit logs stored in the privacy ledger.

## Roles & POCs
- **Data Protection Officer (DPO)**: Priya D'Souza `employee_id: 1042`, contact `dpo@company.com`.
- **Security Ops Lead**: Mateo Alvarez `employee_id: 1088`, contact `secops@company.com`.
- **HR Privacy Liaison**: Sarah Imbeni `employee_id: 1161`, contact `hr-privacy@company.com`.

# Examples
- When engineering needs a dataset for a new feature, submit the Data Access Request (PR-001) including the specific data fields—DPO approves or rejects.
- For customer deletion requests, Support tags the ticket as "Privacy-Delete" and Security Ops handles the purge workflow.

# References
- ISO 27701 certification docs
- PR-001 Data Access Flow
