<div align="center">
  <img src="https://raw.githubusercontent.com/opengraviton/graviton/main/assets/logo.svg" alt="OpenGraviton" width="200" />
  <h1>OpenGraviton</h1>
  <p><strong>500B+ parameter LLMs. Locally. On a Mac Mini.</strong></p>
  <p>The most powerful AI shouldn't belong to corporations. We're making it accessible to everyone.</p>
</div>

<br />

## The Mission

AI is being monopolized. The most capable models are locked behind cloud APIs and corporate gatekeepers.

**Graviton breaks that barrier.** Open-source engine that takes the models corporations run on server farms and makes them run on your desk. A 72B model compressed to **36 GB**, streamed layer by layer onto a Mac Mini.

## What It Does

| Feature | What You Get |
|---|---|
| **Run 500B+ models locally** | Stream, compress, and run models never meant for consumer hardware |
| **Shrink models up to 10x** | 16-bit to 4-bit or 1.58-bit — 4–10x smaller |
| **Stream what doesn't fit** | Loads one layer at a time, compresses each — never needs full model in memory |
| **2–3x faster generation** | Speculative decoding + dynamic sparsity |
| **Private and free** | Runs locally. No cloud. No API keys. No monthly bill |
| **Built for AI agents** | Headless REST API for programmatic access |
| **Graviton-Native** | Train BitNet & MoE from scratch — 350M in 66 MB, 500B on 32 GB RAM |

## First Inference — It Works!

<p align="center">
  <img src="https://raw.githubusercontent.com/opengraviton/graviton/main/assets/first-inference.png" alt="Graviton running TinyLlama-1.1B inference on Apple Silicon" width="100%" />
</p>

<p align="center"><em>TinyLlama-1.1B running locally via Graviton on Apple M1 Max — 65 tokens in 2.99s (21.8 tok/s)</em></p>

## The Numbers

| Scenario | Without Graviton | With Graviton |
|---|---|---|
| **Qwen2.5-72B** | 144 GB — locked in data centers | **36 GB** — runs on your Mac |
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
[![Graviton-Native](https://opengraph.githubassets.com/1/opengraviton/graviton-native)](https://github.com/opengraviton/graviton-native)

> For gated models (LLaMA, Mixtral), see the [HuggingFace setup guide](https://github.com/opengraviton/graviton#huggingface-setup-for-downloading-models).

## Community

- **Website**: [opengraviton.github.io](https://opengraviton.github.io)
- **Contributing**: PRs welcome.
- **License**: Apache 2.0.

---

<p align="center">
  <em>"The age of AI starts when it reaches everyone's desk — not just the data center."</em>
</p>
