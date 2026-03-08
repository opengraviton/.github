<div align="center">
  <img src="https://raw.githubusercontent.com/opengraviton/graviton/main/assets/logo.svg" alt="OpenGraviton" width="200" />
  <h1>OpenGraviton</h1>
  <p><strong>AI belongs to everyone — not just those who can afford a GPU cluster.</strong></p>
  <p>We build the open-source inference engine that runs 70B+ parameter LLMs on hardware you already own.</p>
</div>

<br />

## The Problem

Today's most capable language models have 70–400 billion parameters. Running them requires GPU servers that cost $10,000–$100,000. That means the most powerful AI is locked behind a paywall.

**We believe this is the single biggest barrier to the next era of AI.**

## Our Solution

**Graviton** is an inference engine built from the ground up to break that barrier. It combines streaming layer-by-layer loading, extreme quantization, speculative decoding, dynamic sparsity, and memory-mapped layer streaming to run massive models on consumer hardware.

**The result:** A 72B-parameter model that normally needs 144 GB of VRAM loads into **36 GB** on a Mac with 64 GB unified memory. No GPU cluster. No cloud bill. Just your laptop.

## Core Technologies

| Technology | What It Does |
|---|---|
| **Streaming Layer-by-Layer Loading** | Streams each transformer layer from disk, quantizes in-flight, frees originals. Peak memory = 1 FP16 layer + quantized rest. |
| **Extreme Quantization** | 1.58-bit Ternary (`{-1, 0, +1}`) for 10x compression. Also INT4, INT8, and mixed-precision. |
| **QuantizedLinear** | Drop-in `nn.Linear` replacement with packed weights. INT8 saves 62% memory. |
| **Speculative Decoding** | Layer-skip draft model + full verification. 2-3x throughput. |
| **Dynamic Sparsity** | Top-K activation + MoE routing. 70%+ compute savings per token. |
| **Layer Streaming via MMAP** | Memory-maps weights from NVMe SSD. A 1 TB model runs on 16 GB RAM. |
| **Graviton UI** | Dark-themed [chat interface](https://github.com/opengraviton/graviton-ui) with real-time streaming and layer-by-layer progress. |
| **88 Tests** | Attention, quantization, speculative decoding, KV cache, streaming, e2e — all passing in ~2s. |

## First Inference — It Works!

<p align="center">
  <img src="https://raw.githubusercontent.com/opengraviton/graviton/main/assets/first-inference.png" alt="Graviton running TinyLlama-1.1B inference on Apple Silicon" width="100%" />
</p>

<p align="center"><em>TinyLlama-1.1B running locally via Graviton on Apple M1 Max — 65 tokens in 2.99s (21.8 tok/s)</em></p>

## Proven Results

| Scenario | Before Graviton | After Graviton |
|---|---|---|
| **72B model (Qwen2.5-72B)** | 144 GB FP16 — needs GPU server | **36 GB** — runs on 64 GB Mac |
| **TinyLlama-1.1B** | 2.05 GB FP16 | **0.78 GB** INT8 (62% smaller) |
| **TinyLlama-1.1B** | 2.05 GB FP16 | **0.24 GB** INT4 (8.4x smaller) |

## Get Started — One Command

**For Humans** — install everything and open the chat UI:

```bash
pip install graviton-ui && graviton-ui
```

**For AI Agents** — no UI, just the engine and a REST API:

```bash
pip install "graviton-ai[api]" && graviton-api
```

Headless API on `0.0.0.0:7860` with `/health`, `/api/models/load`, `/api/models/status`, `/api/chat` (SSE), `/api/models/unload`. An agent on a low-budget machine can load 70B+ models and use them programmatically — no GPU cluster required.

[![Graviton Engine](https://opengraph.githubassets.com/1/opengraviton/graviton)](https://github.com/opengraviton/graviton)
[![Graviton UI](https://opengraph.githubassets.com/1/opengraviton/graviton-ui)](https://github.com/opengraviton/graviton-ui)

> For gated models (LLaMA, Mixtral, etc.), see the [HuggingFace setup guide](https://github.com/opengraviton/graviton#huggingface-setup-for-downloading-models).

## Community

- **Website**: [opengraviton.github.io](https://opengraviton.github.io)
- **Contributing**: PRs welcome. Hack on exactly what you want to optimize next.
- **License**: Apache 2.0.

---

<p align="center">
  <em>"The age of AI starts when it reaches everyone's desk — not just the data center."</em>
</p>
