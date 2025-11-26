---
id: EN-FAQ-004
title: AI-KMS in Plain Language (ELI12)
category: faq
tags:
  - overview
  - how-it-works
  - non-technical
version: 1.0.0
status: active
owners:
  - name: Knowledge Steward
    email: knowledge@company.com
contacts:
  - name: Knowledge Steward
    email: knowledge@company.com
last_reviewed: 2025-11-26
---

## What this is
- Think of AI-KMS as a smart librarian for our company. It reads our approved documents and answers questions with receipts (citations).
- If it cannot find a good answer, it says so and points you to the right people or docs.
- It separates **internal answers** (from our KB) and **external answers** (world/general), labeling the difference clearly.

## One-glance link map
- **Chat & UI:** `frontend/` → your browser.
- **API & Brain:** `app/api/routes.py`, `app/rag/pipeline.py`.
- **Knowledge Base (docs):** `kb_repo/kb/` (policies, FAQs, playbooks, product info).
- **Indexes & Memory:** `storage/chroma` (vectors), `storage/state.sqlite` (metadata), `app/kb/retrieval.py` (search logic), `app/kb/graph.py` (relationships).
- **Ingestion & Sync:** `scripts/initial_index.py`, `app/kb/ingestion.py`, `/sync` API.
- **Toolstack:** Ollama LLMs (answers), Chroma (vector search), SQLite (metadata), LangGraph (intent routing), FastAPI/Uvicorn (server), Vite/React (UI).

## Toolstack (what and why)
- **FastAPI + Uvicorn:** Simple, fast web server to expose `/query`, `/sync`, `/upload`, and health endpoints.
- **Python + Pydantic:** Clear configs and data validation so bad inputs are caught early.
- **Chroma (vector DB):** Finds text that “sounds similar” to your question, even if words differ.
- **SQLite:** Tracks which docs exist, their sections, owners, and when they were last indexed.
- **BM25 (lexical search):** Finds exact word matches to stay precise.
- **Hybrid retrieval + reranker:** Combines BM25 + vectors + knowledge graph, then reorders results to push the best to the top.
- **LangGraph (orchestration):** Detects intent (HR, Sales, IT, world/general, wellness, LangGraph) and routes queries to the right path.
- **Ollama-hosted LLMs:** Local language models for answers; a separate general model handles world questions when allowed.
- **Vite + React UI:** Fast chat and upload experience with confidence bars, source chips, and quick prompts.

## Mind map (text form)
- AI-KMS (the librarian)
  - Documents: `kb_repo/kb/*` (policies, processes, FAQs, product info, LangGraph docs)
  - Ingestion: `scripts/initial_index.py`, `app/kb/ingestion.py`
    - Frontmatter checks (id, title, category, contacts)
    - Chunking into bite-sized pieces
    - Metadata to SQLite; embeddings to Chroma; graph relations
  - Retrieval: `app/kb/retrieval.py`
    - BM25 (exact words)
    - Vectors (similar meaning)
    - Knowledge graph (typed nodes, relations/owners/tags/systems, related_units)
    - Fusion + reranker
  - Orchestration: `app/rag/intent.py`, `app/agents/langgraph_runner.py`
    - Detect intent (HR, Sales, IT, Product, LangGraph, World, Wellness, Small-talk)
    - Set allowed prefixes and thresholds
  - LLMs: `app/rag/llm_client.py`
    - Internal model (default) via Ollama
    - External/general model for world questions (if allowed)
  - UI/UX: `frontend/`
    - Chat, quick prompts, confidence bars, source chips
    - Upload tab (Markdown/PDF/Excel) with preview and required metadata

## How it works (plain steps)
1) **Ingest:** We pull docs from `kb_repo/kb/` (or via the upload tab). Files must have required labels (ID, title, category, contacts). We cut long docs into bite-sized chunks.
2) **Index:** We store chunk text in Chroma (for similarity) and metadata in SQLite. We also build a graph of relationships (tags, related units, systems, owners).
3) **Route:** When you ask a question, LangGraph-like logic detects intent (HR, Sales, IT, product, world, wellness, LangGraph, or small talk).
4) **Retrieve:** We search three ways—BM25 (exact words), vectors (similar meaning), and the graph (relations). We fuse and rerank results, then drop anything below the confidence threshold.
5) **Answer:** The LLM writes a concise reply using only the selected chunks. It shows sources. If external/world is allowed, it uses the general model and labels the answer as “external context.”
6) **Guardrails:** If no good chunks are found, the assistant lists related KB IDs or says it cannot answer. Sensitive or off-topic questions get a polite deferral.

## Why we chose this setup
- **Local-first:** Keeps data private; no default calls to outside services.
- **Hybrid search:** Exact match + semantic match reduces missed answers.
- **Intent routing:** Helps avoid mixing world trivia with internal policy answers.
- **Citations:** Every answer can point to the doc and section that support it.
- **Graceful failure:** If unsure, it says so and suggests next steps.

## Deep dive: RAG and indexing (ELI12 but detailed)
- **Retrieval-Augmented Generation (RAG):** The LLM does not guess from memory alone. We first **retrieve** the best matching snippets from our KB and then **generate** an answer strictly from those snippets.
- **Chunking:** Long docs are sliced into short “post-it notes” (chunks). This makes matching more precise and keeps the answer within token limits.
- **BM25 (lexical search):** Think keyword search—it scores chunks by how well the words match your question.
- **Vector search (semantic):** Think meaning search—it finds chunks that “sound similar,” even if they use different words.
- **Knowledge graph:** A relationship map that links IDs, tags, related units, systems, and owners, with lightweight typing inferred from prefixes (HR-, IT-, SF-, LG-, etc.). It helps surface the right chunk even when wording is fuzzy and boosts items that match the intent’s allowed prefixes.
- **Fusion + rerank:** We blend BM25 + vectors + graph, then reorder with a reranker model so the best evidence floats to the top. Low-score items are discarded by a threshold.
- **Indexing pipeline:** Ingestion → frontmatter validation → chunking → embeddings to Chroma → metadata to SQLite → graph refresh. If a file is removed, its chunks are pruned.

## Deep dive: LLM usage
- **Internal model:** Answers internal questions; runs locally via Ollama. It receives only the selected chunks (citations) to keep answers grounded.
- **External/general model:** Used only when “Allow general knowledge answers” is enabled. Answers are labeled “external context.”
- **Prompts and guardrails:** Prompts instruct the model to stay factual, cite sources, and avoid speculation. If no evidence, it should defer or ask for a KB ID.

## If you are an editor (more detail)
- Use frontmatter (id, title, category, contacts, last_reviewed). Follow ID prefixes from the ontology (HR-, IT-, CO-, PT-, MT-, SF-, LG-, etc.).
- Prefer short sections and meaningful headings; avoid giant walls of text.
- Add brief text descriptions for images/diagrams so the system can index them (PDFs are text-only).
- After adding/changing docs, run `make update-kb` or `make index` so ingestion, graph, and vector indexes stay fresh.

## What you see in the UI
- A chat box, quick prompts by domain (Policy, Sales, Wellness, LangGraph, World/General), confidence note, and source chips.
- An upload tab to add Markdown/PDF/Excel with required metadata; preview shows the first portion of extracted text.
- “Allow general knowledge answers” toggle for world questions (external model).
- **Learning mode (world/general):** When enabled, the assistant adopts an AI/ML tutor persona, uses a short primer on our stack (local LLMs, hybrid RAG, LangGraph routing), and still labels answers as external.

## What is safe / not safe
- **Safe:** Asking about our policies, processes, playbooks, HR, IT, Sales, LangGraph docs—all stay internal.
- **External answers:** Only when you toggle “Allow general knowledge answers.” These are labeled “external.”
- **If it cannot answer:** It will say so and may list related KB IDs; it will not make up sources.

## How to use (non-technical)
- Ask a clear question: “What is the PTO policy?” or “How do I get a laptop?”
- Check the sources: they are your receipts. If you do not see sources, treat it as low confidence.
- If low confidence: ask for the KB ID or give more detail (team, product, policy name).
- For world questions: toggle external answers on; expect a label that says “external context.”

## Relatable use cases
- **New hire onboarding (HR):** “What is the PTO policy?” → cites HR-001/HR-002 with leave details and contacts.
- **Device and access (IT):** “How do I get a laptop and SSO?” → cites IT-PR-005/IT-PR-006 with steps and links.
- **Salesforce guardrails (Sales/RevOps):** “Who can edit opp stages?” → cites SF-PL-001 and SF-PR-002 with approvals.
- **LangGraph help (Eng/AI):** “How do I run the LangGraph orchestrator?” → cites LG-* docs and shows intent routing notes.
- **Wellness:** “I’m stressed, what support do we have?” → cites HR-003 and lists EAP contacts.
- **World/general (with external toggle):** “Who was Ada Lovelace?” → uses general model, labels as external, no org tie-ins.

## Mini FAQ
- **Why no answer?** Maybe no doc matches. Try a simpler question or include the policy/KB ID if you know it.
- **Why low confidence?** Results scored below the threshold or too few sources. Review the cited docs or ask an owner.
- **Can it handle images?** PDFs are text-only; diagrams should be described in text.
- **Who maintains this?** Knowledge Steward (knowledge@company.com). They keep metadata clean and run lint/index jobs.

## Contacts
- Knowledge Steward — knowledge@company.com

## Glossary (plain language)
- **AI-KMS:** Our AI-powered knowledge assistant; a smart librarian with receipts.
- **KB (Knowledge Base):** The approved set of company docs in `kb_repo/kb/`.
- **Frontmatter:** The required labels at the top of each doc (id, title, category, contacts) so the system can index it.
- **Chunking:** Cutting long docs into small, searchable pieces.
- **BM25 (lexical search):** A keyword search that scores exact word matches.
- **Vector search:** A “meaning” search that finds similar ideas even if wording differs.
- **Knowledge graph:** A relationship map linking IDs, tags, systems, owners, and related docs.
- **Fusion:** Blending results from BM25, vectors, and the graph.
- **Reranker:** A model that reorders candidates so the best evidence comes first.
- **Threshold:** A minimum score; anything below is dropped.
- **RAG (Retrieval-Augmented Generation):** Retrieve evidence first, then have the LLM answer strictly from that evidence.
- **LLM (Large Language Model):** The text model that writes answers; runs locally via Ollama.
- **Internal vs External answers:** Internal uses our KB; external uses the general model and is labeled “external context.”
- **Intent routing:** Detecting what kind of question (HR, IT, Sales, Product, LangGraph, World, Wellness) and adjusting search rules.
- **Allowed prefixes:** ID prefixes (HR-, IT-, SF-, LG-, etc.) that narrow search to relevant docs for each intent.
- **Ingestion:** The process of reading docs, validating frontmatter, chunking, embedding, and updating indexes.
- **Embedding:** Turning text into numbers (vectors) so we can measure similarity.
- **Chroma:** The vector database where embeddings live.
- **SQLite (state store):** Tracks doc metadata, chunk info, owners, relations, and ingest fingerprints.
- **Ollama:** Local service that hosts the LLMs (internal and general models).
- **LangGraph:** The orchestration layer that helps detect intent and route requests.
- **Confidence note:** The UI label showing how sure the system is (low/medium/high).
