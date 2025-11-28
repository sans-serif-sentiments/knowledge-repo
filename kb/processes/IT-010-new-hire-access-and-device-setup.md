---
id: IT-010
title: New Hire Access and Device Setup
category: process
version: 1.0.0
contacts:
  - name: IT Helpdesk
    email: it-help@company.com
  - name: Endpoint Management
    email: devices@company.com
related_units:
  - HR-010
  - SEC-010
tags:
  - onboarding
  - access
  - devices
last_reviewed: 2025-11-27
systems:
  - okta
  - laptop-provisioning
  - vpn
  - mfa
---

## Scope
Day 0/Day 1 steps to deliver a managed laptop and grant access to core systems.

## Steps (new hire)
1) Accept Okta invite; set MFA (authenticator + backup codes).
2) Power on laptop; confirm disk encryption and device check-in to MDM.
3) Install VPN client; test connectivity to internal resources.
4) Sign into email/chat/calendar; verify SSO to core apps.

## Steps (IT/manager)
- Submit access/laptop request at least 5 business days before start.
- Assign appropriate groups (role/function) in Okta.
- Verify device shows compliant in MDM dashboard on Day 1.

## Troubleshooting
- MFA lockouts: contact it-help@company.com.
- VPN issues: ensure latest client and correct gateway; if still blocked, file ticket with logs.

## Related KB
- HR-010 Onboarding Guide
- SEC-010 Security Training Requirement
