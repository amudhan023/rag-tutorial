# notebooks

📖 **[Read the full visual documentation](docs/index.html)** — plain-English, diagram-heavy walkthroughs of every notebook, plus a concepts/deep-dive reference. No ML background needed.

RAG-from-scratch, built for the SRE Copilot project's runbook search assistant.
Four planned notebooks, each replacing one piece of the previous one's stack with
a more production-grade version — no LangChain until the mechanics are understood.

| Notebook | Covers | Status |
|---|---|---|
| `rag_from_scratch_notebook_1.ipynb` | Chunking, TF-IDF, cosine similarity, prompt building — all by hand | Done |
| `rag_semantic_notebook_2.ipynb` | Sentence-transformer embeddings, FAISS, cross-encoder re-ranking, hybrid BM25, metadata filtering | Done |
| `rag_production_notebook_3.ipynb` | PostgreSQL + pgvector, HNSW recall/latency trade-off, from-scratch IR metrics, observability | Done |
| Notebook 4 — Agentic RAG | LangGraph, retrieval as a tool, multi-step reasoning, memory, human-in-the-loop | Not started |

## Running locally

Notebook 3 needs PostgreSQL + pgvector. `docker/pgvector/docker-compose.yml` runs it
in a container that matches the Milestone 13 setup for the main SRE Copilot project:

```bash
cd docker/pgvector
docker compose up -d
```

Then set `USE_DOCKER = True` in the notebook's config cell to skip the Colab-internal
Postgres install path.

## Context

Companion notebooks to the SRE Copilot learning project — a 40-milestone curriculum
building an AI-powered incident investigation platform (Kafka -> Flink -> LangGraph ->
pgvector -> OpenSearch -> Kubernetes).
