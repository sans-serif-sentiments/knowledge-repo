---
id: AI-FAQ-003
title: vLLM Quickstart (Serving LLMs)
category: faq
version: 1.0.0
contacts:
  - name: AI Platform
    email: ai-platform@company.com
  - name: DevOps
    email: devops@company.com
last_reviewed: 2025-11-27
tags:
  - vllm
  - serving
  - llm
systems:
  - vllm
related_units:
  - IT-011
  - AI-FAQ-002
---

## Vetted links
- vLLM docs: https://docs.vllm.ai
- GitHub: https://github.com/vllm-project/vllm
- OpenAI-compatible API usage: https://docs.vllm.ai/en/latest/getting_started/quickstart.html
- CUDA requirements: https://docs.vllm.ai/en/latest/serving/deploying_with_vllm.html#hardware-requirements

## Quick steps
1) Install vLLM in a GPU-enabled environment (see CUDA requirements).
2) Start server with a model, e.g.: `python -m vllm.entrypoints.openai.api_server --model <model-name> --tensor-parallel-size <n>` (choose TP for multi-GPU).
3) Call via OpenAI-compatible endpoints; set `max_model_len` based on VRAM.

## Tips
- Match model format (HF safetensors) and GPU memory; large models may need tensor parallelism.
- Use PagedAttention defaults; adjust block size only if you know the tradeoffs.
- For local-only, ensure disk encryption and avoid sensitive data in prompts.
