# funnywittywares-story-creator

## Active Plugins

### andrej-karpathy-skills@karpathy-skills
Source: `forrestchang/andrej-karpathy-skills`

<!-- plugin:karpathy-skills:start -->
Behavioral guidelines to reduce common LLM coding mistakes. Merge with project-specific instructions as needed.

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

### 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

### 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

### 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

### 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.
<!-- plugin:karpathy-skills:end -->

### last30days-skill@last30days
Source: `mvanhorn/last30days-skill`

<!-- plugin:last30days:start -->
Use the `/last30days` skill to research any topic across social platforms ranked by real engagement signals, not editors.

**Sources searched:** Reddit (with upvoted comments), X/Twitter, YouTube (full transcripts), TikTok, Instagram Reels, Hacker News, Polymarket (prediction markets with real money), GitHub, Threads, Bluesky, Brave/Perplexity web search.

**How it works:**
- Resolves relevant handles, subreddits, and hashtags before searching
- Merges identical stories from multiple platforms into single clusters
- Ranks by actual engagement: upvotes, view counts, market odds
- Synthesizes with inline citations and community "Best Takes"
- Output: prose paragraphs with `[name](url)` inline links, emoji-tree footer
<!-- plugin:last30days:end -->

### brand-voice@brand-voice
Source: `anthropics/knowledge-work-plugins` → `partner-built/brand-voice`

<!-- plugin:brand-voice:start -->
Enforce FunnyWittyWares brand voice on all generated content. Guidelines live in `.claude/brand-voice-guidelines.md`.

**Commands:**
- `/brand-voice:enforce-voice` — apply brand guidelines to any content task
- `/brand-voice:generate-guidelines` — generate guidelines from existing brand materials
- `/brand-voice:discover-brand` — discover brand signals across connected data sources

**Guideline loading order:**
1. Session context (if guidelines were generated earlier this session)
2. `.claude/brand-voice-guidelines.md` (project file — already populated for FunnyWittyWares)
3. Prompt user if neither source exists

**When enforcing:** apply voice constants (wit, punchy, no corporate-speak), flex tone for US vs UK, explain brand decisions in output, and flag open questions rather than guessing.
<!-- plugin:brand-voice:end -->
