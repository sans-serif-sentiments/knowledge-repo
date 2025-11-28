---
id: LG-OWN-001
title: LangGraph Ownership and Escalation
category: overview
version: 1.0.0
contacts:
  - name: LangGraph Steward
    email: langgraph-steward@company.com
  - name: Reliability On-Call
    email: ai-oncall@company.com
tags:
  - langgraph
  - ownership
  - escalation
related_units:
  - LG-PR-001
  - LG-FAQ-001
last_reviewed: 2025-11-27
systems:
  - langgraph-orchestrator
---

## What this covers
- Ownership and escalation paths for LangGraph orchestration, agent flows, and incidents.
- How to request changes to LangGraph graphs, prompts, or tool wiring.
- Where to find runbooks and FAQs.

## Primary contacts
- **LangGraph Steward:** langgraph-steward@company.com (design/roadmap decisions, graph changes)
- **Reliability On-Call:** ai-oncall@company.com (incidents, degraded routing, model/tool failures)
- **KB Updates:** knowledge@company.com (metadata/frontmatter fixes)

## Scope
- Orchestration graph definitions, agent routing, and tutor mode behavior.
- Integration with LLM backends, retrievers, and tool adapters.
- Incident handling for LangGraph-specific outages or misroutes.

## How to request changes
- File a change ticket with:
  - Proposed graph/node change and expected intent coverage.
  - Impacted KB IDs (e.g., LG-PR-001, LG-FAQ-001) and rollout date.
  - Test plan and rollback trigger.
- Change approval SLA: **1 business day** (Steward). Rollback SLA: **30 minutes** (On-Call).

## Key documents
- **Runbook:** LG-PR-001 (LangGraph orchestration runbook)
- **FAQ:** LG-FAQ-001 (LangGraph & local LLM FAQ)
- **Agentic concepts:** LG-AGENTIC-CONCEPTS

## Escalation
1) Page **Reliability On-Call** for incidents (ai-oncall@company.com).
2) Notify **LangGraph Steward** for structural or design issues.
3) If KB metadata is wrong or missing, email **knowledge@company.com** to re-run indexing.

## Success signals
- Intent coverage: LangGraph intents respond with owners and links.
- Zero “ownership missing” responses for LangGraph queries.
- Updated KB citations resolve to GitHub links.
