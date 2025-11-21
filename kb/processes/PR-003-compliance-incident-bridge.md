---
id: PR-003
title: Compliance Incident Bridge Workflow
category: process
tags: [compliance, incidents, escalation]
version: 1.0.0
created_at: 2025-02-20
updated_at: 2025-02-20
author: Risk & Compliance Office
confidence: medium
contacts:
  - name: Anita Singh
    title: Chief Compliance Officer
    email: compliance@company.com
    slack: "@anita-singh"
    notes: Final approver for regulatory disclosures.
    priority: 1
  - name: DevOps On-Call
    title: DevOps
    email: devops@company.com
    slack: "#incident-ai"
    notes: Executes technical mitigations.
    priority: 2
related_units:
  - SEC-002
  - IT-002
systems:
  - PagerDuty
  - Jira
---

# Summary
End-to-end bridge for handling incidents that may trigger regulatory reporting or affect compliance posture. Aligns DevOps, Legal, HR, and Sales to share facts with a single source of truth.

# Details
## Trigger Criteria
- SEV0/SEV1 events (see SEC-002) with customer data exposure.
- Any policy breach under IT-002 or CO-LG-001.
- HR or Sales escalations flagged as “regulatory risk”.

## Workflow
1. **Activation:** Incident commander opens `COMPLIANCE-BRIDGE` Jira and tags Compliance + HR.
2. **Evidence Lock:** DevOps snapshots logs + access controls; attach to Jira.
3. **Assessment:** Compliance runs impact template; HR reviews employee implications; Sales/CS prepares customer statements.
4. **Decision:** Anita Singh (or delegate) decides on regulatory notification and approves messaging.
5. **Closeout:** Postmortem filed under PR-002 with compliance appendix.

## Communication Guidelines
- Use CO-003 tone when drafting customer updates.
- Internal Slack updates go to `#compliance-incident` with timestamped summaries.

# References
- SEC-002 Security Incident Response Playbook
- IT-002 Access Control Standards
