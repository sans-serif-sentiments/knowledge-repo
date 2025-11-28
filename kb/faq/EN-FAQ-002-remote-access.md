---
id: EN-FAQ-002
title: Remote Access & VPN FAQ
category: faq
tags:
- it
- remote-work
- access
version: 1.0.0
created_at: 2025-02-18
updated_at: 2025-02-18
author: IT Support
source_repo: sans-serif-sentiments/knowledge-repo
confidence: medium
contacts:
- name: IT Service Desk
  title: Tier-1 Support
  email: it-help@company.com
  slack: '#help-it'
  notes: First stop for VPN troubleshooting.
  priority: 1
related_units:
- IT-002
- HR-002
systems:
- Okta
- GlobalProtect
last_reviewed: '2025-11-27'

---

# Summary
Answers the top remote-access questions from employees and contractors, including device requirements, approval steps, and troubleshooting workflows.

# Details
## Common Questions
1. **Who can request VPN access?**  
   Any active employee with a managed device; contractors need a sponsoring manager plus NDA confirmation.
2. **How do I request access?**  
   Submit the "Remote Access" catalog item in the Access Portal (ties into IT-002 policy).
3. **What if I'm traveling?**  
   Update your travel dates in Workday to avoid geo-blocks; Finance guidance in FIN-001 still applies.
4. **Who approves exceptions?**  
   Identity & Access Manager plus your VP for privileged resources.

## Troubleshooting Tips
- Verify device encryption + endpoint agent status before filing tickets.
- Use the `globalprotect --status` command then attach logs to Zendesk case.
- For PTO travel, coordinate with HR-002 contacts if you're out longer than 10 days.

# References
- IT-002 Access Control Standards
- HR-002 Leave & Time-Off Policy
