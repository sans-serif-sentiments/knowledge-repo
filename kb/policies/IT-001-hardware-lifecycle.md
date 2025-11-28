---
id: IT-001
title: Hardware Lifecycle & Asset Management
category: policy
tags:
- it
- hardware
- asset-management
version: 1.0.5
created_at: 2024-07-15
updated_at: 2025-02-12
author: Carlos Jimenez
source_repo: sans-serif-sentiments/knowledge-repo
confidence: medium
contacts:
- name: IT Helpdesk
  email: it-help@company.com
last_reviewed: '2025-11-27'

---

# Summary
Standards for provisioning, maintaining, and decommissioning laptops, phones, and peripherals.

# Details
## Lifecycle Stages
1. **Provisioning**: IT prepares device with MDM + baseline security controls within 5 business days of request.
2. **Maintenance**: automatic OS updates enforced weekly; critical patches within 48 hours.
3. **Decommission**: devices wiped using NIST 800-88 method, logged in asset registry, and recycled via approved vendors.

## Ownership
- **Asset Owner**: assigned employee; responsible for reporting loss within 1 hour.
- **IT Ops Manager**: Carlos Jimenez `employee_id: 8740` `it-ops@company.com`
- **Security Reviewer**: Divya Aggarwal `employee_id: 1117` ensures wipe logs retained 3 years.

# References
- Asset registry: `it/assets/devices.csv`
- Lost device SOP
