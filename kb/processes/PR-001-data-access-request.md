---
id: PR-001
title: User Data Access Request Flow
category: process
version: 1.1.0
tags: [user-data, compliance, support]
created_at: 2024-02-12
updated_at: 2024-05-03
author: Data Ops Team
source_repo: sans-serif-sentiments/knowledge-repo
confidence: medium
---

# Summary
Standard operating procedure for fulfilling internal user data requests while respecting privacy, audit, and approval requirements.

# Details
## Preconditions
- Requestor has completed privacy training within the last 12 months.
- Ticket is filed in the DataOps queue with business justification.

## Steps
1. **Intake**: triage request, validate scope, confirm data owner approval.
2. **Eligibility Check**: ensure requester role matches data sensitivity tier.
3. **Extraction**: run predefined queries stored in the analytics repo; never use ad-hoc exports.
4. **Review**: second analyst reviews sample output for PII redaction.
5. **Delivery**: provide data via secure workspace; expire access after 7 days.
6. **Logging**: record ticket id, dataset, and requester in the access ledger.

# Examples
- Support escalation requesting cohort churn metrics for enterprise account.

# References
- Privacy policy PO-002
- Access ledger dashboard
