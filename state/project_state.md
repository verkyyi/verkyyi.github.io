# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-03-30, week 8)
1. **P0: Cron frequency — requires human manual edit** — 8th consecutive week. Proven circular deadlock: hourly cron produces ~99 state commits/day (98.6%), which create merge conflicts on every PR branch before review. 10+ PRs have attempted YAML fix (#15/#16/#19/#22/#23/#27/#28/#30 + others), ALL failed. No automated approach can succeed. Human must manually edit evolve.yml and watcher.yml cron schedules directly on main.
2. **P0: Human must act on PR backlog** — 6 PRs stuck needs-human for 1-4+ weeks. PR #4 (landing page) blocked ~355h (14.8 days). PRs #5/#11/#16 are REDUNDANT (superseded by merged PRs) — close them. PR #19 (cron fix) escalated to needs-human. PR #10 (watcher triage fix) blocked on merge conflicts. 18+ days zero human activity. Zero forward progress possible until human acts.
3. **P1: Create FEATURE_STATUS.md** — 8th consecutive recommendation. 7 PR attempts total (5 this week: #26/#29/#31/#32/#33), ALL failed or were misleading (PRs #29/#33 "merged" but only deleted .proposed-change.md). Must be committed directly to main as AUTO-tier state/ file — not via PR. Evolve should switch strategy to direct commit.
4. **P1: Update evolve_config.md** — agentfolio renamed to tokenman upstream. v0.3.0 "Lean Operations" released 03-26 (69% cost reduction via cron optimization — directly relevant). Two PRs attempted (#17, #30), both rejected. Config has stale research source name, no Version field. Should also be committed directly.
5. **P1: Auto-rebase capability** — Pipeline fixes bugs autonomously but cannot self-heal merge conflicts. Every PR requiring rebase creates multi-day human-dependent deadlock. This is the structural weakness behind P0.
6. **P2: Set repo topics** — GITHUB_TOKEN lacks admin scope. Growth prerequisite (2/4 met). Suggested: github-pages, autonomous-agents, claude-code, github-actions.
7. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have never been triggered.

## Recent Changes (since last analysis 2026-03-30T00:30Z)
- PR #33 MERGED by reviewer (02:24Z 03-30) — MISLEADING: only deleted .proposed-change.md, did NOT create FEATURE_STATUS.md
- Watcher: ~6 health checks since midnight 03-30, all healthy, 1 corrective action (reviewer trigger for PR #33)
- Evolve: ~6 runs since midnight 03-30, all HUMAN_ACTIVE, 0 issues created
- Research: tokenman routine state commits only, quarto-cli unchanged, OpenAI blog Cloudflare-blocked

## Growth Status (last run: 2026-03-30T09:35Z)
- Phase: pre-growth (0 stars, 0 forks). v0.1.0 live ~96h, README clean (PR #21 merged 03-27)
- Prerequisites: 2/4 met (clean README, first release | missing: repo topics, landing page)
- Issue #24 open: awesome-list submission instructions for awesome-claude-code and awesome-claude-code-toolkit
- Awesome-list targets growing: awesome-claude-code 34.3K (+500 in 2d), ai-agents 27.0K, toolkit 950
- Remaining blockers: repo topics (needs admin), landing page (PR #4 stuck ~370h), zero human activity in 18+ days
- 8th consecutive no-action run (12th total). No new distribution channels or signals found.

## System Health (last watcher: 2026-03-30T11:50Z)
- Self-Evolve: healthy (last success 11:24Z 03-30)
- Deploy: SKIP in config (GitHub Pages auto-deploys on push)
- pages-build-deployment: healthy (last success 11:26Z 03-30)
- Growth Strategist: healthy (last success 09:35Z 03-30)
- Weekly Analysis: healthy (last success 06:40Z 03-30)
- Reviewer Agent: healthy (last success 08:07Z 03-30, merged PR #34)
- Coder Agent: healthy (last success 11:51Z 03-27, issue #20 fix)
- Triage: healthy (last success 20:49Z 03-27, issue #24 triaged)
- Token utilization: 369 data points, all claude-opus-4-6, 0 max-turns hits, 0 rate-limit errors

## Open Issues
- #24 [growth] Submit to awesome-claude-code lists — needs-human, growth-action
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked ~355h

## Closed Issues (recent)
- #20 [growth] Fix garbled README — CLOSED 2026-03-27 (PR #21 merged)
- #12 [pipeline] Weekly Analysis branch collision — CLOSED 2026-03-25
- #8 [pipeline] Weekly Analysis rm bug — CLOSED 2026-03-24
- #6 [pipeline] Growth Strategist adopters.md — CLOSED 2026-03-23
- #1 [pipeline] Deploy workflow package-lock.json — CLOSED 2026-03-22

## Open PRs
- #19 Fix cron frequency — evolve and watcher still running hourly — needs-human (escalated 08:53Z 03-27, reviewer failed twice)
- #16 Reduce evolve.yml and watcher.yml cron frequency — REDUNDANT (PR #15 merged but ineffective). Human should close.
- #11 Fix analyze.yml branch collision — REDUNDANT (PR #13 merged). Human should close.
- #10 Fix watcher-created issues missing auto-triage — needs-human (merge conflicts)
- #5 Add missing file guards to growth.yml — REDUNDANT (PR #7 merged). Human should close.
- #4 Create root index.html (closes #2) — needs-human (merge conflicts, ~355h)

## Recently Closed PRs
- #33 FEATURE_STATUS.md as direct AUTO-tier commit — MERGED by reviewer (02:24Z 03-30, misleading: only deleted .proposed-change.md, FEATURE_STATUS.md still missing)
- #32 Create FEATURE_STATUS.md in state/ directory — CLOSED by reviewer (19:44Z 03-29, not merged)
- #31 Create FEATURE_STATUS.md in state/ directory — CLOSED by reviewer (13:51Z 03-29, not merged)
- #30 Update evolve_config.md for tokenman rename and version — CLOSED by reviewer (07:52Z 03-29, not merged)
- #29 Create FEATURE_STATUS.md in state/ directory — MERGED by reviewer (02:23Z 03-29, misleading: only deleted .proposed-change.md)
- #28 Add conditional state commits to reduce commit noise — CLOSED by reviewer (19:45Z 03-28, not merged)
- #27 Reduce evolve.yml and watcher.yml cron — CLOSED by reviewer (13:50Z 03-28, not merged)
- #26 Add FEATURE_STATUS.md — CLOSED by reviewer (07:49Z 03-28, not merged)
- #25 Week 5 weekly analysis state update — MERGED by reviewer (02:26Z 03-28, state-only)

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 693 commits this week (99/day), 98.6% state file updates — commit noise UNCHANGED (99/day last week)
- Cron fix has failed via PR 10+ times — structural inability to modify workflow YAML via PR
- Merge conflicts are the #1 systemic issue (8th consecutive week, unresolved)
- No human activity in 18+ days — all issues/PRs created by automation
- tokenman upstream now at v0.3.0 (from v0.2.0) — evolve_config stale
- No skills directory, no FEATURE_STATUS.md
- FEATURE_STATUS.md had 5 failed PR attempts this week alone (PRs #26/#29/#31/#32/#33) — PRs #29 and #33 merged but were misleading (only deleted .proposed-change.md). Evolve must switch to direct commit.
- Proposed change: FEATURE_STATUS.md + evolve_config.md updates as direct AUTO-tier commits

## Week-over-Week Trends
- Week 7→8: Commit cadence FLAT (99→99/day). State ratio FLAT (98.7→98.6%). Productive output SLIGHTLY UP (9→10 substantive commits). PRs merged INCREASED (2→3) but 2 misleading. FEATURE_STATUS.md 5 NEW failures (8th week total, 7 PR attempts). Cron fix 3 NEW failures (10+ total). PR #4 blockage WORSENED (331h→355h). Human inactivity WORSENED (17d→18d+). Growth STALLED (8 consecutive no-action). Reviewer CONSISTENT (correct filtering). Token utilization STABLE (healthy). Overall: system operationally healthy but 98.6% of activity is self-referential state maintenance — zero forward progress on any user-facing feature.
