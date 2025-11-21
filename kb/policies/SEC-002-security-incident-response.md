---
id: SEC-002
title: Security Incident Response Playbook
category: policy
tags: [security, incident-response, soc]
version: 1.4.0
created_at: 2024-09-08
updated_at: 2025-01-29
author: Mateo Alvarez
source_repo: sans-serif-sentiments/knowledge-repo
confidence: high
contacts:
  - name: Mateo Alvarez
    title: SOC Lead
    email: secops@company.com
    slack: "@mateo.alvarez"
    phone: "+1-415-555-0021"
    notes: Shift lead + default incident commander for SEV1s.
    priority: 1
  - name: Divya Aggarwal
    title: Cloud Security Architect
    email: cloudsec@company.com
    slack: "@divya.aggarwal"
    phone: "+1-415-555-0028"
    notes: Consult for containment on infra/infra SaaS scopes.
    priority: 2
  - name: Meena Rao
    title: Legal Incident Contact
    email: legal@company.com
    slack: "@meena.rao"
    phone: "+1-415-555-0039"
    notes: Notifies legal + exec bridge on SEV0 escalations.
    priority: 3
related_units:
  - IT-001
  - HR-001
systems:
  - PagerDuty
  - SIEM
---

# Summary
Defines the detection-to-resolution flow for any suspected security event across infrastructure, applications, or employee endpoints.

# Details
## Severity Bands
- **SEV0**: confirmed breach or customer-impacting compromise. Notify Exec Bridge + Legal within 15 minutes.
- **SEV1**: high-risk vuln exploitation attempt. SOC lead coordinates containment within 1 hour.
- **SEV2**: suspicious behavior requiring investigation; respond within 4 business hours.

## Response Flow
1. **Detection**: alert raised via SIEM, employee report, or third party. Ticket created in `sec-bridge` queue.
2. **Triage**: SOC shift lead (Mateo Alvarez `employee_id: 1088`) validates severity and assigns incident commander.
3. **Containment**: follow runbooks (isolate host, revoke credentials, block indicators).
4. **Eradication & Recovery**: engineering + IT implement patches, restore services, and verify monitoring coverage.
5. **Post-mortem**: draft within 72 hours. Owner: assigned incident commander.

## POCs
- **SOC Lead**: Mateo Alvarez `employee_id:1088` `secops@company.com`
- **Cloud Security Architect**: Divya Aggarwal `employee_id:1117` `cloudsec@company.com`
- **Legal Incident Contact**: Meena Rao `employee_id:9612` `legal@company.com`

# References
- Runbook: `security/runbooks/incident-response.md`
- Tooling: PagerDuty schedule `SOC-Primary`
