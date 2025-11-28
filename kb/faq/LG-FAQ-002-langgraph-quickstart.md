---
id: LG-FAQ-002
title: LangGraph Quickstart and Escalation
category: faq
version: 1.0.0
contacts:
  - name: LangGraph Steward
    email: langgraph-steward@company.com
  - name: AI Platform
    email: ai-platform@company.com
tags:
  - langgraph
  - orchestration
  - agents
last_reviewed: 2025-11-27
systems:
  - langgraph-orchestrator
related_units:
  - LG-OWN-001
  - LG-PR-001
  - LG-FAQ-001
  - LG-AGENTIC-CONCEPTS
---

## What LangGraph runs here
- Intent-aware orchestration for internal KB questions, LangGraph FAQs, and tutor/world mode when allowed.
- Hybrid retrieval + rerank remains the source of truth; LangGraph routes and traces the steps.

## How to use
- Keep Internal scope on by default; toggle “Internal + World” only when you need external context.
- For ownership/escalation, see LG-OWN-001 (contacts, runbook links).
- To adjust graphs/prompts/tools, file a change with the steward (include test plan + rollback).

## Key runbooks
- LG-PR-001: Orchestration runbook (nodes, flows, metrics).
- LG-FAQ-001: Common questions.
- LG-AGENTIC-CONCEPTS: Agent patterns and intent signals.

## Escalation
- Pager: langgraph-steward@company.com
- Incidents in production flows: follow AI-PR-002 in parallel.
