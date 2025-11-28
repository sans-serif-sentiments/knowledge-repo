---
id: AI-003
title: External Answering and World-Mode Policy
category: policy
version: 1.0.0
contacts:
  - name: AI Platform
    email: ai-platform@company.com
  - name: Security Operations
    email: sec-ops@company.com
tags:
  - external
  - world
  - ai
last_reviewed: 2025-11-27
systems:
  - ai-kms
---

## When to allow external answers
- User explicitly opts into “Internal + World” scope or asks general questions not covered in the KB.
- Do not use external context for proprietary/PII/contractual data.

## Guardrails
- All external answers must be labeled “External context”.
- Do not cite unvetted URLs; prefer official/vendor docs when needed.
- If confidence is low or no source is available, say so and offer to add a KB entry.

## Approved sources
- Official vendor docs (e.g., NVIDIA/CUDA, PyTorch, TensorFlow, GitHub product docs).
- Public standards/specs where relevant.
- No arbitrary web search; no personal data.

## Operator actions
- Default to Internal-only for policy/HR/IT/Finance/Security questions.
- For AI/RAG/architecture questions, keep Internal-only and cite KB diagrams/IDs.
- External scope is optional and user-driven.
