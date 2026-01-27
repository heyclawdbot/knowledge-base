# LLMs Eat Scaffolding for Breakfast

- **URL:** https://x.com/nicbstme/status/2015795605524901957
- **Author:** Nicolas Bustamante (@nicbstme) — CEO of Fintool (AI Portfolio Manager)
- **Date:** 2026-01-26
- **Source:** X (Article)
- **Tags:** #ai-engineering #architecture #scaling #process

## Summary

Every line of scaffolding code is a confession that the model wasn't good enough. As LLMs improve, the infrastructure we built to compensate for their limitations becomes technical debt. The best AI teams build for fast obsolescence and celebrate deleting code.

## Key Insights

1. **The Scaffolding Cycle:** We build complex systems to compensate for model limitations (PDF parsers, RAG pipelines, JSON validators, chain-of-thought logic). Then a new model drops and natively handles what we built. The scaffolding becomes debt.

2. **Real example — Codex system prompts:**
   - GPT-o3 prompt: **310 lines** (hand-holding on how to plan, validate, behave)
   - GPT-5 prompt: **104 lines** (just Codex-specific technical requirements)
   - **66% reduction.** The model already knows how to be a coding agent.

3. **Four LLM Constants** (things that keep improving):
   - **Context windows:** 4K → 128K → 200K → 1M → 2M+ (heading to 100M+)
   - **Generation speed:** 30-40 → 300+ tokens/sec (Cerebras hits 2,000)
   - **Intelligence:** No wall in sight. New frontier = tool use + long-horizon tasks
   - **Cost:** ~10× cheaper every 12 months for the same capability level

4. **Scaffolding on the decline:**
   - Vector databases (just put docs in the prompt now)
   - LLM frameworks like LangChain (use the API directly)
   - Prompt engineering teams (models just need clear instructions)
   - Model fine-tuning (next-gen base models outperform your fine-tune)
   - Custom caching layers (prompt caching is built into APIs)

5. **Critical skills for AI teams:**
   - Deep model awareness — know exactly what today's models can/can't do
   - Strategic foresight — distinguish surviving infra from dead-on-arrival infra
   - Frontier vigilance — treat model releases like breaking news
   - Ruthless iteration — celebrate deleting code, pivot in days not months

6. **The Counter-Intuitive Truth:** Software engineering has always been about adding layers of abstraction. AI is inverting this — the best AI code is simple and close to the model. Experienced engineers see a modern AI codebase and think "where's the architecture?" The answer: the model ate it.

7. **Forces fighting against simplification:**
   - Sunk cost fallacy ("We spent 3 years on this RAG pipeline!")
   - Resume-driven development ("RAG + vector DB + reranking" looks good on LinkedIn)
   - Organizational inertia (deleting infrastructure needs approval; building it doesn't)
   - Fear of regression on edge cases

## Why It Matters

This is the clearest articulation of why building in AI feels like running on a treadmill. The mental model — **every scaffolding line is a bet against future model capability** — is a powerful decision framework. Before building any AI infrastructure, ask: "Will the next model make this unnecessary?"

## Quotable

> "The worst AI codebases are the ones that were best practices 12 months ago."

> "Experienced engineers look at modern AI codebases and think: 'This can't be right. Where's the architecture?' The answer: The model ate it bro, get over it."
