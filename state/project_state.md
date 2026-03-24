# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-03-23)
1. **P0: Unblock PRs #4 and #5** — both reviewer-approved, blocked on merge conflicts needing human rebase. PR #4 (landing page) blocked 21+h. PR #5 (growth.yml fix) blocked 6+h.
2. **P1: Merge conflict prevention** — state file churn (~4 commits/hour) causes branch divergence. Need auto-rebase capability or reduced commit frequency.
3. **P1: Fix research sources** — drop openai blog (Cloudflare blocked every check), update agentfolio reference (repo renamed to tokenman).
4. **P2: Growth Strategist stabilization** — at 2/3 failure threshold (missing state/adopters.md). PR #5 has fix but blocked on merge conflicts.
5. **P2: Feature tracking** — no FEATURE_STATUS.md exists. Create one for project progress visibility.
6. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have not been triggered.

## Recent Changes
- Fixed growth.yml: added file existence guards to all cat/tail commands in Collect growth context and Build growth prompt steps (closes #6)
- Fixed deploy.yml: removed push trigger and npm cache, made workflow_dispatch-only (closes #1)
- Added agentfolio autonomous pipeline workflows (11 total)
- Self-Evolve stabilized after 5 initial failures (git add path issues)
- Issue #1 full lifecycle completed in ~3h (create to close)
- Issue #2 pipeline complete to reviewer stage (PR #4 approved, blocked merge conflicts)
- Weekly Analysis recovered from 2/3 failures to 0/3
- First token utilization analysis completed (48 data points, healthy)
- First growth metrics collected (stars:0, forks:0, watchers:1, issues:2)

## System Health (last watcher: 2026-03-24T05:10Z)
- Self-Evolve: healthy (last success 04:38)
- Deploy workflow: SKIP in config (workflow_dispatch-only, issue #1 closed)
- pages-build-deployment: healthy (last success 04:41)
- Growth Strategist: FIXED — PR #7 merged at 21:54 (file existence guards in growth.yml, closes #6). No new run since 18:20 (~11h). Awaiting next scheduled run to validate fix.
- Weekly Analysis: FIXED — issue #8 fix merged at 03:33 (reordered rm before git add, added git diff --cached guard). Last failure 00:24. Next validation run expected ~06:18 UTC.
- Triage/Coder/Reviewer: all healthy — full pipeline for #8 completed in ~5 min (03:28-03:33)
- Token utilization: 84 data points — system healthy, no optimization needed

## Open Issues
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked on merge conflicts

## Closed Issues (recent)
- #8 [pipeline] Weekly Analysis fails: rm .proposed-change.md before git commit — CLOSED 2026-03-24T03:33Z (fixed by PR #9)
- #6 [pipeline] Growth Strategist fails: missing state/adopters.md — CLOSED 2026-03-23T21:54Z (fixed by PR #7)
- #1 [pipeline] Deploy workflow fails: missing package-lock.json — CLOSED 2026-03-22T16:50Z

## Open PRs
- #4 fix: [evolve] Create root index.html (closes #2) — reviewer approved (comment), needs-human (merge conflicts, 30+h)
- #5 fix(workflow): add missing file guards to growth.yml — NOW REDUNDANT (PR #7 already merged same fix). Still open with needs-human. Human should close.

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 105 commits in first 23h of operation — 99% state file updates, creating noisy git history
- Merge conflicts are the #1 systemic bottleneck — caused by high-frequency state commits diverging from PR branches
- No human-created issues in past 7 days
- OpenAI blog research source persistently blocked by Cloudflare (every check)
- agentfolio upstream repo renamed to tokenman — evolve_config research sources stale
- No skills directory exists yet
- No FEATURE_STATUS.md exists
