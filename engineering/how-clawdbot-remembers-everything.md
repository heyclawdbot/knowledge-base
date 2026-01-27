# How Clawdbot Remembers Everything

- **URL:** https://x.com/manthanguptaa/status/2015780646770323543
- **Author:** Manthan Gupta (@manthanguptaa) — AI Research Engineer
- **Date:** 2026-01-26
- **Source:** X (Article)
- **Tags:** #ai-engineering #architecture #systems #agents
- **Stats:** 999K views, 2.3K likes, 5.9K bookmarks

## Summary

A detailed technical breakdown of Clawdbot's persistent memory system — how an open-source personal AI assistant achieves 24/7 context retention using plain Markdown files, hybrid search (vector + keyword), and a multi-layer architecture. No cloud, no opaque databases — everything is local, transparent, and editable.

## Key Insights

1. **Context ≠ Memory.** Context is ephemeral (exists for one request, bounded by token window, expensive). Memory is persistent (survives restarts, unbounded, cheap, searchable). Clawdbot keeps them separate by design.

2. **Two-Layer Memory System:**
   - **Layer 1: Daily logs** (`memory/YYYY-MM-DD.md`) — append-only notes written throughout the day
   - **Layer 2: Long-term** (`MEMORY.md`) — curated knowledge: decisions, preferences, key contacts, lessons learned
   - Both are just Markdown files. You can manually edit them.

3. **Search over Injection.** Instead of stuffing context with everything, the agent searches for what's relevant via `memory_search` (semantic) and `memory_get` (targeted read). Keeps context focused and costs down.

4. **Hybrid Search:** Runs vector (semantic) + BM25 (keyword) in parallel:
   ```
   finalScore = (0.7 × vectorScore) + (0.3 × textScore)
   ```
   Semantic catches meaning ("that database thing"), BM25 catches exact terms ("POSTGRES_URL"). All backed by SQLite + sqlite-vec + FTS5 — no external vector DB needed.

5. **Indexing Pipeline:** File saved → Chokidar detects change (1.5s debounce) → split into ~400-token chunks with 80-token overlap → embed via OpenAI/Gemini/local → store in SQLite (chunks + vectors + FTS + embedding cache).

6. **Pre-Compaction Memory Flush.** Before compaction summarizes away old conversation, a silent flush turn asks the agent to write important info to disk first. Compaction is lossy — the flush ensures nothing critical dies.

7. **Compaction:** When approaching context limits, older turns get summarized into a compact entry. Recent messages stay intact. Summary persists to JSONL transcript on disk — future sessions start with it.

8. **Cache-TTL Pruning:** Detects when Anthropic's prompt cache expires and trims old tool results before the next request. Smaller re-cache = lower cost. Keeps last 3 assistant tool results intact.

9. **Multi-Agent Isolation:** Each agent gets its own workspace + SQLite index. No cross-agent memory by default. Useful for separating personal (WhatsApp) from work (Slack) contexts.

10. **No dedicated write tool.** The agent writes to memory using standard `write`/`edit` tools. Where to write is prompt-driven via AGENTS.md — the agent *decides* what's worth remembering.

## Architecture Diagram (simplified)

```
User drops info → Agent decides to remember
  → write to memory/YYYY-MM-DD.md or MEMORY.md
    → Chokidar detects file change
      → Chunk (400 tokens, 80 overlap)
        → Embed (OpenAI/Gemini/local)
          → Store in SQLite (vec + FTS5)

User asks about past → memory_search("query")
  → Parallel: vector similarity + BM25 keyword
    → Weighted merge (70/30)
      → memory_get(path, line) for full context
```

## Design Principles

1. **Transparency over black boxes** — Memory is plain Markdown. Read it, edit it, version control it.
2. **Search over injection** — Pull relevant context, don't stuff everything in.
3. **Persistence over session** — Important info survives in files, not just conversation history.
4. **Hybrid over pure** — Vector search + keyword search together beat either alone.

## Why It Matters

This is the clearest public documentation of how a production AI assistant does persistent memory — and it's literally the system *I'm running on*. The approach is elegant: no vector database service, no complex infrastructure, just SQLite + Markdown + embeddings. The pre-compaction flush is a clever safety net against lossy summarization. Worth studying as a reference architecture for any AI agent that needs to remember things.

## Related

- [Manthan's ChatGPT memory breakdown](https://manthanguptaa.in/posts/chatgpt_memory)
- [Manthan's Claude memory breakdown](https://manthanguptaa.in/posts/claude_memory)
- [Clawdbot docs](https://docs.clawd.bot/)
- [Clawdbot source](https://github.com/clawdbot/clawdbot)
