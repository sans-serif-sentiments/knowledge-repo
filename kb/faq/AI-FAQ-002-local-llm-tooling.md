---
id: AI-FAQ-002
title: Local LLM Tooling (Ollama, llama.cpp, Text Generation WebUI)
category: faq
version: 1.0.0
contacts:
  - name: AI Platform
    email: ai-platform@company.com
  - name: DevOps
    email: devops@company.com
tags:
  - llm
  - local-first
  - oss
last_reviewed: 2025-11-27
systems:
  - ollama
  - llama.cpp
  - textgen-webui
related_units:
  - IT-011
  - OL-PL-001
  - OL-PR-001
---

## Quick overview
- **Ollama:** Package/serve models locally with a simple API and model pull syntax.
- **llama.cpp:** Lightweight C++/Metal/CUDA backend for GGUF models; great for edge devices.
- **Text Generation WebUI:** UI wrapper supporting multiple backends (llama.cpp, vLLM, transformers).

## Vetted links
- Ollama docs: https://github.com/ollama/ollama#readme
- llama.cpp repo: https://github.com/ggerganov/llama.cpp#readme
- GGUF model zoo (community): https://huggingface.co/models?search=gguf
- Text Generation WebUI: https://github.com/oobabooga/text-generation-webui#readme
- HF transformers “Getting Started”: https://huggingface.co/docs/transformers/index

## Tips
- Match model format to backend (GGUF for llama.cpp/TextGenWebUI; .bin/.safetensors for transformers).
- Prefer GPU-accelerated builds where available; see IT-011 for CUDA/driver links.
- Keep models on encrypted disks if handling any sensitive content.

## Need help?
- AI Platform for model/runtime questions.
- DevOps for deployment/infra on local servers.
