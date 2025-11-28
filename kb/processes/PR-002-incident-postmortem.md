---
id: PR-002
title: Incident Postmortem Lifecycle
category: process
tags:
- incidents
- learning
- postmortem
version: 1.0.0
created_at: 2025-01-28
updated_at: 2025-02-18
author: Reliability PMO
source_repo: sans-serif-sentiments/knowledge-repo
confidence: medium
contacts:
- name: Jordan Kim
  title: Reliability Lead
  email: reliability@company.com
  slack: '@jordan.kim'
  notes: Facilitates SEV1+ reviews and owns template updates.
  priority: 1
- name: Meena Rao
  title: Legal Incident Contact
  email: legal@company.com
  slack: '@meena.rao'
  notes: Confirms language before sharing externally.
  priority: 2
related_units:
- SEC-002
- MT-002
systems:
- PagerDuty
- Notion
last_reviewed: '2025-11-27'

---

# Summary
Outlines how to capture incident learnings from SEV1 and SEV0 events, from kickoff to action tracking, so stakeholders get consistent remediation plans.

# Details
## Triggers
- SEV0 or SEV1 declared per SEC-002 workflow.
- Customer-comms, legal, or exec staff request a documented summary.

## Steps
1. **Draft** – incident commander completes template within 48 hours; include timeline, impact, mitigations, and open risks.
2. **Review** – Reliability Lead, Legal, and product owner comment asynchronously in Notion.
3. **Publish** – final PDF shared via trust center; internal notes kept in Ops Drive.
4. **Action Tracking** – Jira tickets created for each follow-up item; MT-002 tracks SLA compliance.

## Artifacts
- Meeting notes (attached to pager event).
- Executive summary slide (optional but recommended).
- Jira filter: `project = RELINC AND labels = postmortem`.

# References
- SEC-002 Security Incident Response Playbook
- MT-002 Knowledge Retrieval Success Rate
