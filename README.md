# Simple Multi-Agent Chat System

A minimal prototype of a multi-agent chat system built in **Python**.  
This system demonstrates **role separation, inter-agent coordination, structured memory, and adaptive fallback to an LLM (Groq)**.

---

## Features

- **Coordinator (Manager Agent)**  
  Orchestrates other agents, logs conversation + trace, manages fallback to LLM.

- **ResearchAgent**  
  Retrieves facts from the structured memory (vector search).

- **AnalysisAgent**  
  Provides heuristic comparisons (e.g., optimizers in machine learning).

- **MemoryAgent**  
  Stores facts with provenance (`source`, `time`) and retrieves by vector similarity.

- **Router**  
  Lightweight keyword-based intent classifier (with fallback to LLM).

- **SummarizerAgent (stub)**  
  Optional summarization of long outputs (can be extended with T5/DistilBART).

- **Groq LLM Integration**  
  If a local match cannot be found, queries are sent to Groq’s `llama-3.1-8b-instant` model.  
  Responses are logged back into local memory with provenance = `Groq`.

---

## Requirements

Install dependencies:

```bash
pip install sentence-transformers numpy groq
