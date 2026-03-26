# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-03-26, week 5)
1. **P0: Human PR queue cleanup** — 5 open PRs, 3 redundant (#5, #11, #16), 2 blocked on merge conflicts (#4, #10). Zero can progress without human action. PR #4 (landing page) blocked ~153h. Close redundant PRs, rebase #4 and #10.
2. **P0: Validate cron reduction impact** — PR #15 deployed 07:56Z 03-26, reducing evolve+watcher from hourly to every 3h. First full day shows ~16 state commits/day (down from ~48). Monitor for one full week to confirm merge conflict reduction on PR branches.
3. **P1: Update evolve_config** — agentfolio renamed to tokenman (v0.3.0 "Lean Operations" released 03-26). Config still references stale repo name, no Version field. Proposed change written.
4. **P1: Add auto-rebase capability** — Even with reduced cron, state commits still cause conflicts on long-lived PR branches. Auto-rebase would eliminate human dependency for conflict resolution.
5. **P2: Create FEATURE_STATUS.md** — 5th consecutive weekly recommendation, still missing. Should track: landing page, README fix, awesome-list submissions, workflow activation.
6. **P2: Fix README.md** — Garbled content (repeated analyze.yml rows). Prerequisite for awesome-list submissions and general discoverability.
7. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have never been triggered (0 runs across 429 commits).

## Recent Changes (since last analysis 2026-03-26T06:30Z)
- Cron reduction validated: ~16 state commits/day observed (target met)
- PR #16 reviewed by reviewer agent — recommends closing (redundant, PR #15 already merged)
- Watcher escalated PR #16 to needs-human
- tokenman v0.3.0 release detected (Lean Operations — 69% cost reduction via cron optimization, aligns with our PR #15)
- Growth strategy: 4th run, created v0.1.0 release earlier today
- All 10 historical pipeline failures remain ALREADY-FIXED
- Model fallback rate stable at 1% (2/210, isolated haiku bursts during concurrent merges)

## Growth Status (last run: 2026-03-26T09:00Z)
- Phase: pre-growth (0 stars, 0 forks) but v0.1.0 release created
- v0.1.0 "The Self-Healing Scaffold" released 2026-03-26 — 6 merged PRs, 11 workflows, proven autonomous pipeline
- Remaining blockers: broken README (garbled content), no landing page (PR #4 stuck ~153h), no human activity in 14+ days
- Growth targets: awesome-claude-code (32K), awesome-ai-agents (27K), awesome-claude-code-subagents (15K), awesome-claude-code-toolkit (906), awesome-claude-code-plugins (646)
- Next action: fix README (prerequisite for awesome-list submissions)

## System Health (last watcher: 2026-03-26T17:50Z)
- Self-Evolve: healthy (last success 17:25Z 03-26, running on 3h cadence)
- Deploy: SKIP in config (workflow_dispatch-only)
- pages-build-deployment: healthy (last success 17:27Z 03-26)
- Growth Strategist: healthy (last success 09:24Z 03-26, created v0.1.0 release)
- Weekly Analysis: healthy (last success 12:21Z 03-26)
- Reviewer: completed PR #16 review (14:05Z) — passed but recommends closing (redundant, conflicts)
- Token utilization: 210 data points, 2 model fallbacks (1% rate, isolated, not actionable), 0 max-turns hits, 0 rate-limit errors

## Open Issues
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked on merge conflicts ~153h

## Closed Issues (recent)
- #12 [pipeline] Weekly Analysis branch collision — CLOSED 2026-03-25T21:53Z (PR #13)
- #8 [pipeline] Weekly Analysis rm bug — CLOSED 2026-03-24T03:33Z (PR #9)
- #6 [pipeline] Growth Strategist adopters.md — CLOSED 2026-03-23T21:54Z (PR #7)
- #1 [pipeline] Deploy workflow package-lock.json — CLOSED 2026-03-22T16:50Z (PR #3)

## Open PRs
- #16 Reduce evolve.yml and watcher.yml cron frequency — needs-human (reviewer passed 14:06Z, recommends closing — redundant, PR #15 already merged the fix). Human should close.
- #11 Fix analyze.yml branch collision — REDUNDANT (PR #13 already merged). Human should close.
- #10 Fix watcher-created issues missing auto-triage — needs-human (1 review, merge conflicts). Human rebase required.
- #5 Add missing file guards to growth.yml — REDUNDANT (PR #7 already merged). Human should close.
- #4 Create root index.html (closes #2) — needs-human (merge conflicts, ~153h). Human rebase required.

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 429 commits this week, 96.3% state file updates — cron reduction now deployed, monitoring impact
- Merge conflicts remain the #1 systemic issue (5th consecutive week) but root cause partially addressed
- No human activity in 14+ days — all issues/PRs created by automation
- agentfolio upstream repo renamed to tokenman (v0.3.0) — evolve_config stale
- No skills directory, no FEATURE_STATUS.md

## Week-over-Week Trends
- Week 4→5: Cron frequency reduction DEPLOYED (PR #15 merged, P0 resolved). OpenAI blog source REMOVED (PR #14). Branch collision RESOLVED (PR #13 validated). v0.1.0 release CREATED (growth milestone). Human activity UNCHANGED (none, 14+ days). PR #4 blockage WORSENED (136h→153h). Redundant PRs GREW (2→3, #16 added). Pipeline chain PROVEN 3x total. Token utilization STABLE (210 pts, 1% fallback rate). State commit rate REDUCED (~48→~16/day, monitoring).
