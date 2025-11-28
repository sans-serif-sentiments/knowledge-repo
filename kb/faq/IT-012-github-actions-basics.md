---
id: IT-012
title: GitHub Actions Basics (CI/CD)
category: faq
version: 1.0.0
contacts:
  - name: DevOps
    email: devops@company.com
tags:
  - github
  - ci
  - cd
last_reviewed: 2025-11-27
systems:
  - github-actions
related_units:
  - SEC-011
  - FIN-002
---

## Quick steps
- Workflows live in `.github/workflows/*.yml`.
- Triggers: `push`, `pull_request`, `schedule`, or manual `workflow_dispatch`.
- Use repository/environment secrets for credentials; never hardcode keys.

## Vetted links
- Actions docs: https://docs.github.com/actions
- Workflow syntax: https://docs.github.com/actions/writing-workflows/workflow-syntax-for-github-actions
- Secrets and security hardening: https://docs.github.com/actions/security-guides/security-hardening-for-github-actions
- Official actions marketplace: https://github.com/marketplace?type=actions

## Security tips
- Pin action versions (use SHA or tagged release).
- Least-privilege PATs; prefer OIDC to cloud providers where possible.
- For third-party vendors, run through procurement/security if they process data (see FIN-002, SEC-011).

## Common patterns
- Lint/test matrix: Node/Python examples from GH docs.
- Build-and-upload artifacts with retention.
- Deploy steps gated by branch/environment protections.
