# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-03-26, week 4)
1. **P0: Reduce state commit frequency** — 48 state commits/day (96% of git history) is the root cause of merge conflicts on every PR branch. 4th consecutive week identified. Proposed: reduce evolve+watcher cron from hourly to every 3h (~16 commits/day). This is the single most impactful change to unblock the entire pipeline.
2. **P0: Human action required on PRs** — PR #4 (landing page) blocked ~117h on merge conflicts. PR #10 (watcher triage fix) blocked on conflicts. PRs #5 and #11 are REDUNDANT — human should close both. Zero forward progress until human rebases PR #4 or merge conflicts are prevented.
3. **P1: Update evolve_config** — agentfolio renamed to tokenman (v0.2.0). Research sources reference stale repo name. No Version field in config.
4. **P1: Add auto-rebase or squash-merge capability** — Pipeline fixes bugs autonomously but cannot self-heal merge conflicts. Every PR requiring rebase creates multi-day human-dependent deadlock.
5. **P2: Create FEATURE_STATUS.md** — 4th consecutive weekly recommendation, still missing.
6. ~~**P2: Fix README.md**~~ — RESOLVED (PR for issue #20, coder agent replaced garbled content with clean structured README).
7. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have never been triggered.

## Recent Changes (since last analysis 2026-03-26T00:18Z)
- PR #21 MERGED (2026-03-27) — replaced garbled README.md with clean structured content (closes #20)
- PR #15 MERGED (07:56Z 03-26) — cron frequency reduction for evolve+watcher (P0 fix now deployed)
- PR #14 merged (02:22Z 03-26) — removed OpenAI blog from research sources (100% Cloudflare-blocked)
- Weekly Analysis branch collision fix validated (00:29Z + 06:27Z 03-26) — fix confirmed stable
- Full automated pipeline chain proven twice: issue #12 (4min) and PR #14 (triage→coder→reviewer→merge)
- Model fallback detected: watcher at 07:56Z used claude-haiku-4-5 instead of opus (1/191 runs = 0.5%, isolated, concurrent burst during PR #15 merge)
- Growth strategy: 3 runs completed, all no-action (pre-growth, 0 stars/forks)
- Cron reduction should lower state commits from ~48/day to ~16/day going forward

## Growth Status (last run: 2026-03-27T18:00Z)
- Phase: pre-growth (0 stars, 0 forks). v0.1.0 live ~33h, README now clean (PR #21 merged 03-27)
- Prerequisites: 2/4 met (✅ clean README, ✅ first release, ❌ repo topics, ❌ landing page)
- Repo topics: still empty. Human must set via Settings (GITHUB_TOKEN lacks admin). Suggested: github-pages, autonomous-agents, claude-code, github-actions, self-healing, ai-agents, automation
- Issue #24 created: awesome-list submission instructions for awesome-claude-code (33.2K stars, Orchestrators section) and awesome-claude-code-toolkit (922 stars)
- Remaining blockers: repo topics (needs admin), landing page (PR #4 stuck ~194h), initial stars for list credibility, no human activity in 10+ days
- Next action: wait for repo topics + landing page + initial stars → then submit to awesome-claude-code-toolkit first (lower bar), awesome-claude-code second

## System Health (last watcher: 2026-03-28T02:20Z)
- Self-Evolve: healthy (last success 01:36Z 03-28)
- Deploy: SKIP in config (workflow_dispatch-only)
- pages-build-deployment: healthy (last success 01:38Z 03-28)
- Growth Strategist: healthy (last success 18:21Z 03-27)
- Weekly Analysis: healthy (last success 00:26Z 03-28)
- Reviewer Agent: healthy (last success 19:48Z 03-27, re-triggered for PR #25 at 02:20Z)
- Coder Agent: healthy (last success 11:51Z 03-27, issue #20 fix)
- Triage: healthy (last success 20:49Z 03-27, issue #24 triaged)
- Token utilization: 275 data points, all claude-opus-4-6 (recent), 3 haiku fallbacks (1.1%, historical/isolated), 0 max-turns hits, 0 rate-limit errors

## Open Issues
- #24 [growth] Submit to awesome-claude-code lists — needs-human, growth-action (created 18:24Z 03-27, triaged 20:49Z — external platform action required)
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked on merge conflicts ~202h

## Closed Issues (recent)
- #20 [growth] Fix garbled README — CLOSED 2026-03-27 (PR #21 merged by reviewer agent)
- #12 [pipeline] Weekly Analysis branch collision — CLOSED 2026-03-25T21:53Z (PR #13)
- #8 [pipeline] Weekly Analysis rm bug — CLOSED 2026-03-24T03:33Z (PR #9)
- #6 [pipeline] Growth Strategist adopters.md — CLOSED 2026-03-23T21:54Z (PR #7)
- #1 [pipeline] Deploy workflow package-lock.json — CLOSED 2026-03-22T16:50Z (PR #3)

## Open PRs
- #23 Apply cron frequency reduction to workflow YAMLs — CLOSED by reviewer (19:48Z 03-27, state-only + merge conflicts, content superseded)
- #19 Fix cron frequency — evolve and watcher still running hourly — needs-human (reviewer failed twice, escalated 08:53Z 03-27)
- #16 Reduce evolve.yml and watcher.yml cron frequency — needs-human (redundant, PR #15 already merged the fix). Human should close.
- #11 Fix analyze.yml branch collision — REDUNDANT (PR #13 already merged). Human should close.
- #10 Fix watcher-created issues missing auto-triage — needs-human (1 review, merge conflicts). Human rebase required.
- #5 Add missing file guards to growth.yml — REDUNDANT (PR #7 already merged). Human should close.
- #4 Create root index.html (closes #2) — needs-human (merge conflicts, ~196h). Human rebase required.

## Recently Closed PRs
- #22 Apply cron frequency reduction directly to workflow YAMLs — CLOSED by reviewer (13:58Z 03-27, not merged)
- #18 Enable watcher to auto-close redundant PRs — CLOSED by reviewer (02:22Z 03-27, not merged — proposal rejected)
- #17 Update evolve_config.md for tokenman rename — CLOSED by reviewer (19:51Z 03-26, not merged)

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 376 commits this week, 96% state file updates — commit noise is the systemic bottleneck
- Merge conflicts are the #1 systemic issue (4th consecutive week, unresolved)
- No human activity in 10+ days — all issues/PRs created by automation
- agentfolio upstream repo renamed to tokenman (v0.2.0) — evolve_config stale
- No skills directory, no FEATURE_STATUS.md

## Week-over-Week Trends
- Week 3→4: OpenAI blog blocker RESOLVED (PR #14). Branch collision RESOLVED (PR #13). State commit frequency FIX DEPLOYED (PR #15 merged, cron reduced). Human activity UNCHANGED (none). PR #4 blockage WORSENED (105h→136h). Pipeline chain PROVEN (3 successful automated fix cycles: #12, #14, #15).
