---
id: UD-001
title: Unified User Data Model
category: concept
version: 1.0.0
tags:
- user-data
- analytics
- governance
created_at: 2024-01-05
updated_at: 2024-01-05
author: Knowledge Steward
source_repo: sans-serif-sentiments/knowledge-repo
confidence: high
contacts:
- name: Knowledge Steward
  email: knowledge@company.com
last_reviewed: '2025-11-27'

---

# Summary
Defines the canonical entities and relationships used to describe customers, accounts, and product interactions across the organisation.

# Details
## Entities
- **User**: human or organisation consuming our products.
- **Account**: billing scope that may contain multiple users.
- **Interaction**: time stamped event captured from product telemetry or support systems.

## Principles
1. Every record must have a globally unique identifier (UUID).
2. Personally identifiable information (PII) is stored separately and referenced via secure keys.
3. Derived metrics should reference the raw interaction ids for auditability.

# Examples
- User `USR-2031` belongs to account `ACC-493` and performed interaction `INT-8831`.
- Aggregations such as Daily Active Users reference `interaction_type = session.start`.

# References
- Data Warehouse ERD (internal link)
- Privacy classification policy
