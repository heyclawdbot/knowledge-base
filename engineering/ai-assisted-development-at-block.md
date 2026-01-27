# AI-Assisted Development at Block

- **URL:** https://engineering.block.xyz/blog/ai-assisted-development-at-block
- **Date:** 2026-01-27
- **Source:** Block Engineering Blog
- **Tags:** #ai-engineering #teams #scaling #process #agents

## Summary

Block (Square, Cash App, Afterpay, Tidal) has ~95% of engineers regularly using AI-assisted dev tools. Most are at Stage 5 (single agent outside IDE), with a growing cohort at Stage 6 (3-5 parallel agents). Here's how they got there.

## Key Insights

1. **Freedom to explore first, standardize later.** They buy access to *all* frontier models and tools. No lock-in while the landscape is shifting weekly. Different codebases respond differently to AI — what works for web devs doesn't work for mobile/JVM.

2. **AI Champions Program** — 50 engineers across all teams dedicated 30% of their time to AI enablement at the repo level. Not general evangelism — hands-on repo-level work.

3. **Repo Readiness is the foundation.** Before agents can contribute, repos need:
   - `AGENTS.md` — build commands, code style, architecture patterns
   - `HOWTOAI.md` — human-facing guide for the team
   - Reusable agent skills for common tasks
   - AI code review on PRs
   - Headless AI that can iterate autonomously

4. **Context Engineering via RPI** (Research → Plan → Implement):
   - Agent *researches* the codebase, documents findings
   - Fresh session: reads research, creates *detailed plan*
   - Fresh session: *implements* the plan
   - Prevents AI drift on complex tasks. Consistent high-quality PRs.

5. **Agents assigned tickets from Linear/Jira.** Agent reads ticket → plans → branches → codes → opens PR → watches CI → fixes its own failures. Humans only review. Teams pulled in *more* tickets mid-sprint because the agent finished early.

6. **Gamified onboarding** — "Repo Quest" RPG-style game with tiers (Locked → Novice → Adept → Artisan) and companion characters. Made the boring setup work fun.

7. **Results in 3 months:**
   - AI-authored code: **+69%**
   - Reported time savings: **+37%**
   - Automated PRs: **21× increase**

8. **Architecture for a 40K+ file monorepo** — Root-level AI context files cascade down to 650+ services, each with service-specific and subdirectory-specific AI rules. Uses [block/ai-rules](https://github.com/block/ai-rules) to auto-generate configs for Claude, Cursor, Goose, Cline, etc.

## Why It Matters

This is the most concrete, org-scale playbook for AI-assisted development published so far. Not theoretical — they're shipping with it. The RPI pattern, repo readiness checklist, and Champions program are all directly applicable to any engineering org. The key insight: **AI productivity is a repo-level infrastructure problem, not an individual tools problem.**

## Action Items

- [ ] Check out [block/ai-rules](https://github.com/block/ai-rules) for auto-generating agent context
- [ ] Try the RPI pattern for complex tasks with Claude Code
- [ ] Look at [agentskills.io](https://agentskills.io) for reusable agent skills
- [ ] Read Steve Yegge's [Gas Town article](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04) (referenced as the AI maturity stages framework)
