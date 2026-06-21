# /last30days — Social Research Skill v3.8.0

Source: `mvanhorn/last30days-skill`

Research any topic across Reddit (with upvoted comments), X/Twitter, YouTube (full transcripts), TikTok, Instagram Reels, Hacker News, Polymarket (prediction markets), GitHub, Threads, Bluesky, and web search via Brave/Perplexity.

## What this skill does

- Resolves relevant handles, subreddits, and hashtags before searching
- Runs parallel queries across all configured sources
- Merges identical stories from multiple platforms into single clusters
- Ranks results by actual engagement: Reddit upvotes, view counts, market odds
- Synthesizes findings with inline citations and "Best Takes" from the community

## Execution flow

1. Parse user intent (topic, query type, target sources)
2. Detect keyword traps / disambiguation before research
3. Resolve X handles, GitHub users/repos, subreddits, TikTok/Instagram creators
4. Generate JSON query plan across sources
5. Run searches with resolved targeting flags
6. Supplement with 2–3 web search queries
7. Synthesize into prose paragraphs with inline markdown citations — never raw clusters

## Output contract

- Use `What I learned:` as the prose label (no invented title lines)
- Weave at least 2 verbatim community comments into synthesis
- Every citation is an inline markdown link `[name](url)`
- No trailing Sources blocks — emoji-tree footer is the only citation block
- Use single hyphens with spaces ( - ) not em-dashes
- No `##` section headers in body for non-comparison queries
- Include engine footer verbatim in synthesis
