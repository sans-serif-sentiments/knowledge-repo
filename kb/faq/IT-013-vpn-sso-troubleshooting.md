---
id: IT-013
title: VPN and SSO Troubleshooting
category: faq
version: 1.0.0
contacts:
  - name: IT Helpdesk
    email: it-help@company.com
  - name: Security Operations
    email: sec-ops@company.com
last_reviewed: 2025-11-27
tags:
  - vpn
  - sso
  - access
systems:
  - vpn
  - okta
related_units:
  - IT-010
  - SEC-010
---

## Common fixes (VPN)
- Ensure latest VPN client and correct gateway/profile.
- Check time sync and certificate validity.
- Toggle network/wifi; try wired if possible.
- If split-tunnel is blocked, disconnect other VPNs.

## Common fixes (SSO/Okta)
- Clear browser cache or use a new profile.
- Verify MFA is enrolled and not locked out.
- If repeatedly prompted, remove stale device/remembered sessions in Okta.

## When to escalate
- Persistent 2FA/MFA lockouts.
- VPN connects but no internal resources.
- Certificate errors that persist after reinstall.

## What to send to IT
- Error message/screenshot, client version, OS, and logs (if available).
