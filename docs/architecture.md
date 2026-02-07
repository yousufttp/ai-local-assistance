# Architecture Notes

This project uses a local-first AI architecture.

## Components
- Ollama: Runs LLMs locally
- Open WebUI: Browser-based chat interface
- Knowledge Base: Local RAG using embedded documents

## Data Flow
User → Open WebUI → Ollama → Retrieved Documents → Answer

## Design Decisions
- CPU-friendly models for low-spec machines
- No external APIs for privacy reasons
