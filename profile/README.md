<div align="center">
  <img src="https://raw.githubusercontent.com/opengraviton/graviton/main/assets/logo.svg" alt="OpenGraviton" width="200" />
  <h1>OpenGraviton</h1>
  <p><strong>AI belongs to everyone — not just those who can afford a GPU cluster.</strong></p>
  <p>We build the open-source engine that runs powerful AI models on your own computer.</p>
</div>

<br />

## The Problem

Today's best AI models need GPU servers costing $10,000–$100,000. The most powerful AI is locked behind a paywall.

## Our Solution

**Graviton** compresses and streams large AI models so they fit on your hardware. A 72B model that needs 144 GB? Graviton fits it into **36 GB** on a Mac. No GPU cluster. No cloud bill. Just your laptop.

## What It Does

| Feature | What You Get |
|---|---|
| **Run 70B+ models on a laptop** | 72B model compressed from 144 GB to 36 GB — runs on 64 GB Mac |
| **Shrink models up to 10x** | 16-bit to 4-bit or 1.58-bit — 4–10x smaller |
| **Stream models that don't fit** | Loads one layer at a time, compresses each, never needs full model in memory |
| **Fast generation** | 2–3x faster with speculative decoding and dynamic sparsity |
| **Private and free** | Runs locally. No cloud. No API keys. No monthly bill |
| **Built for AI agents** | Headless REST API for programmatic access |

## First Inference — It Works!

<p align="center">
  <img src="https://raw.githubusercontent.com/opengraviton/graviton/main/assets/first-inference.png" alt="Graviton running TinyLlama-1.1B inference on Apple Silicon" width="100%" />
</p>

<p align="center"><em>TinyLlama-1.1B running locally via Graviton on Apple M1 Max — 65 tokens in 2.99s (21.8 tok/s)</em></p>

## The Numbers

| Scenario | Without Graviton | With Graviton |
|---|---|---|
| **Qwen2.5-72B** | 144 GB — needs $10K GPU server | **36 GB** — runs on 64 GB Mac |
| **TinyLlama-1.1B** | 2.05 GB | **0.24 GB** (8.4x smaller) |

## Get Started — One Command

**For you** — install and start chatting:

```bash
pip install graviton-ui && graviton-ui
```

**For AI agents** — headless API, no UI:

```bash
pip install "graviton-ai[api]" && graviton-api
```

REST API on `0.0.0.0:7860` with `/api/models/load`, `/api/models/status`, `/api/chat` (SSE), `/api/models/cancel`, `/api/models/unload`.

[![Graviton Engine](https://opengraph.githubassets.com/1/opengraviton/graviton)](https://github.com/opengraviton/graviton)
[![Graviton UI](https://opengraph.githubassets.com/1/opengraviton/graviton-ui)](https://github.com/opengraviton/graviton-ui)

> For gated models (LLaMA, Mixtral), see the [HuggingFace setup guide](https://github.com/opengraviton/graviton#huggingface-setup-for-downloading-models).

## Community

- **Website**: [opengraviton.github.io](https://opengraviton.github.io)
- **Contributing**: PRs welcome.
- **License**: Apache 2.0.

---

<p align="center">
  <em>"The age of AI starts when it reaches everyone's desk — not just the data center."</em>
</p>
