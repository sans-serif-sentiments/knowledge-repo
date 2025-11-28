---
id: CO-003
title: Product Communication Bridge Policy
category: policy
tags:
- product
- communications
- launch-readiness
version: 1.0.0
created_at: 2025-02-20
updated_at: 2025-02-20
author: Product Communications Council
confidence: medium
contacts:
- name: Priya Kapoor
  title: Director, Product Marketing
  email: priyakapoor@company.com
  slack: '@priya.pmm'
  notes: Approves messaging matrices and controls launch readiness gates.
  priority: 1
- name: Simon Park
  title: Principal PM
  email: simon.park@company.com
  slack: '@simonpm'
  notes: Coordinates roadmap disclosures and press briefings.
  priority: 2
related_units:
- PT-001
- EN-FAQ-002
systems:
- Launch Tracker
- Salesforce
last_reviewed: '2025-11-27'

---

# Summary
Defines how Product and Communications teams share intel before, during, and after customer-facing launches to keep messaging aligned with compliance, sales, and support teams.

# Details
## Handshake Moments
1. **Discovery sync:** PM shares narrative brief + risk register at least 30 days before GA.
2. **Messaging lock:** Communications publishes tone + data guardrails (CO-001) 10 days prior to GA; PM signs off.
3. **Post-launch loop:** PMM circulates KPI snapshot, support insights, and compliance notes within 7 days.

## Required Artifacts
- Launch summary slide referencing PT-001 checklist.
- Enabling FAQ entry linked to EN-FAQ-002.
- Salesforce campaign notes for sales enablement.

## Enforcement
Non-compliance triggers a `product-communications-bridge` Jira issue assigned to the owning PM/P MM. Repeated misses escalate to the Product Communications Council.

# References
- CO-001 Communications Tone and Messaging Guardrails
- PT-001 Launch Communications Pattern
