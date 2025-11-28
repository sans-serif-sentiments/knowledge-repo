---
id: IT-011
title: GPU Setup for Local Apps (Vetted Links)
category: faq
version: 1.0.0
contacts:
  - name: DevOps
    email: devops@company.com
  - name: IT Helpdesk
    email: it-help@company.com
tags:
  - gpu
  - local-llm
  - setup
last_reviewed: 2025-11-27
systems:
  - nvidia-driver
  - cuda
  - pytorch
related_units:
  - OL-PL-001
  - OL-PR-001
---

## Quick steps
1) Install the correct GPU driver.
2) Install CUDA toolkit matching your driver.
3) Install your framework (PyTorch/TensorFlow) with the matching CUDA build.
4) Verify with a small GPU test (e.g., `torch.cuda.is_available()`).

## Vetted links
- NVIDIA drivers (official): https://www.nvidia.com/Download/index.aspx
- CUDA toolkit compatibility matrix: https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html
- PyTorch install selector (choose CUDA version): https://pytorch.org/get-started/locally/
- TensorFlow GPU install guide: https://www.tensorflow.org/install/pip

## Tips
- Match driver, CUDA toolkit, and framework CUDA build versions.
- If using local LLMs (e.g., Ollama/llama.cpp), prefer builds with GPU acceleration flags; ensure your GPU has sufficient VRAM.
- For Apple Silicon, use Metal builds (no CUDA); see framework docs for Metal support.

## Need help?
- Open a ticket with DevOps and include GPU model, driver version, OS, and error logs.
