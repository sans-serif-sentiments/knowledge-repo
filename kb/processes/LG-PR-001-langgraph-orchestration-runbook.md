---
id: LG-PR-001
title: LangGraph Orchestration Runbook
category: process
tags:
  - langgraph
  - orchestration
  - routing
version: 1.0.0
status: active
owners:
  - name: AI Platform Lead
    email: ai-platform@company.com
contacts:
  - name: AI Platform Lead
    email: ai-platform@company.com
  - name: DevOps Lead
    email: devops@company.com
last_reviewed: 2025-11-26
---

## Purpose
Operate and troubleshoot the LangGraph-based intent routing (HR, IT, Sales, Product, LangGraph, Wellness, World).

## Key Settings
- Prefixes per intent (HR-, IT-, SF-, PD-, LG-, etc.); allowed_prefixes can be tuned for noise reduction.
- Thresholds: adjust min_score for low-signal intents; rerank cap per RETRIEVAL__RERANK_MAX_CANDIDATES.
- Toggles: allow_external for world/general answers; set to false for internal-only demos.

## Ops Steps
1) Verify intent map and prefixes before releases.
2) Test sample queries per domain with debug=true; confirm sources and confidence.
3) For misroutes, adjust intent keywords/prefixes and redeploy; keep a small regression set.
4) Log metrics: intent fired, confidence, empty-answer rate; watch for drift.

## Troubleshooting
- If answers are empty: check ingestion/index freshness, thresholds, and prefix filters.
- If external text appears: ensure allow_external=false and RAG guard for RAG/arch topics.
- If latency is high: reduce rerank candidates; verify local models are loaded.

## Contacts
- AI Platform Lead — ai-platform@company.com
- DevOps Lead — devops@company.com
