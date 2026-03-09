<div align="center">
	<img src="https://raw.githubusercontent.com/snehachels/snehachels/master/header.svg" width="800" height="400">
	<br>
</div>

# AI Engineer Portfolio Projects (2026)

A collection of five production-grade AI engineering projects designed to build a standout portfolio for AI engineering roles in 2026. Based on guidance from an experienced AI engineer with backgrounds at Google, Microsoft, and IBM.

---

## Projects Overview

### 1. Production-Grade RAG System
A domain-specific document Q&A system with proper citations and evaluation.

**Key features:**
- Document ingestion (PDF, markdown, web pages) with 500–800 token chunks and ~100 token overlap
- Vector store (ChromaDB or Weaviate) + hybrid retrieval (BM25 + semantic search)
- Cross-encoder re-ranker for improved precision
- Citation enforcement — refuses to answer if retrieved chunks don't support the response
- Golden evaluation dataset (50–200 QA pairs) with faithfulness metrics via RAGAS
- CI pipeline that fails if quality drops below threshold

**Tech stack:** LangChain/LangGraph, ChromaDB/Weaviate, Cohere Reranker or Sentence Transformers, RAGAS

---

### 2. Local AI Assistant (Offline)
A fully offline AI assistant benchmarking small open-source language models.

**Key features:**
- Models run locally via Ollama (Llama 3.2, Phi-4, Mistral 7B)
- Structured JSON output with Pydantic validation and retry logic
- Temperature analysis (0 vs 0.7) documenting output variance
- Comparative benchmark report across 3 models: memory usage, tokens/sec, output quality
- Quantization experiments (GGUF Q4/Q5) with quality vs. speed trade-off analysis

**Tech stack:** Ollama, FastAPI, Pydantic

---

### 3. AI Observability & Monitoring Layer
An operational observability layer added on top of the RAG system from Project 1.

**Key features:**
- Full request tracing: retrieved chunks, reranker order, prompt sent, tokens consumed
- Latency tracking at P50 and P95 percentiles
- Cost-per-request tracking in dollar terms
- Citation coverage and failure rate dashboards
- Prompt versioning alongside code
- CI regression gating tied to the evaluation dataset

**Tech stack:** Langfuse (self-hosted), LangSmith, or Braintrust

---

### 4. Fine-Tuning Project
Supervised fine-tuning + preference optimization for a specific, measurable task.

**Key features:**
- Task: structured JSON extraction or tool-call accuracy
- Supervised fine-tuning (SFT) using LoRA/QLoRA on 2,000–10,000 clean examples
- Base model: Qwen 3 8B (runs on single A100 or T4 with QLoRA)
- Evaluation metrics: JSON validity rate, exact match accuracy, refusal correctness
- DPO-style preference tuning with before/after comparison
- Training curves and honest write-up of failures and iterations

**Tech stack:** Hugging Face TRL, Axolotl, Fireworks AI (compute)

---

### 5. Real-Time Multimodal Application
A low-latency streaming pipeline with resilience and latency budgeting.

**Tracks (pick one):**
- **Voice Assistant** — ASR → LLM → TTS
- **Computer Vision Pipeline** — Webcam feed → Object detection → LLM reasoning
- **Streaming Log Analyzer** — Real-time log ingestion → Anomaly detection → LLM explanation

**Key features:**
- End-to-end streaming pipeline via WebSockets
- Per-component latency breakdown (ASR, LLM TTFT, TTS, overhead)
- Graceful degradation on service failure (timeouts, fallbacks)
- Replay mode for debugging with recorded inputs

**Tech stack (voice track):** Deepgram/Whisper (ASR), any capable LLM, ElevenLabs/Cartesia (TTS), WebSockets

---

## Skills Demonstrated

| Project | Skill |
|---|---|
| Production RAG | Retrieval systems, evaluation, CI/CD for AI |
| Local AI Assistant | Edge deployment, model benchmarking, inference optimization |
| Observability Layer | Systems thinking, monitoring, operational discipline |
| Fine-Tuning | Model training, alignment techniques, data quality |
| Multimodal App | Streaming systems, latency engineering, resilience |

---

## Resources

- [RAGAS](https://github.com/explodinggradients/ragas) — RAG evaluation framework
- [Langfuse](https://langfuse.com/) — Open-source LLM observability
- [Ollama](https://ollama.com/) — Local model inference
- [Hugging Face TRL](https://github.com/huggingface/trl) — SFT and DPO training
- [Axolotl](https://github.com/OpenAccess-AI-Collective/axolotl) — Fine-tuning framework
- [Deepgram](https://deepgram.com/) — Speech recognition API
