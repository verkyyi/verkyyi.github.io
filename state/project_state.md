# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-04-15T12:00Z, week 37)
1. **P0-URGENT: Node.js 20→24 migration** — GitHub Actions forcing Node 24 by June 2026. ~2.5 weeks runway (DOWN from 3 at W36). PR #69 created, reviewed, approved, merge-blocked. CRITICAL timeline — shortest remaining of any blocker.
2. **P0: Cron frequency — requires human manual edit** — 31st consecutive week. Proven circular deadlock: hourly cron → ~100 state commits/day → merge conflicts on every PR branch. Human must manually edit evolve.yml and watcher.yml cron schedules directly on main. Root cause of log growth, commit volume, and merge-blocked PRs.
3. **P0: Human must act on PR backlog** — 15+ PRs needs-human. 5+ PRs reviewed/approved but merge-blocked by conflicts (#39, #42, #48, #50, #51). PR #4 (landing page) blocked ~1500h (62+ days). PRs #5/#11/#16 are REDUNDANT — close them. 49+ days zero human activity.
4. **P0: Log regrowth outpaces truncation** — agent_log grew to 135KB (235 lines) in 7 days post-W36 truncation. Growth rate ~6 lines/hour (~135KB/week). Evolve writes ~24 no-op entries/day (dominant contributor). W37 analysis truncated 224 entries (135KB→~5KB). Will regrow within days.
5. **P1: tokenman v0.5.0 upgrade** — v0.5.0 detected 10:25Z 04-07 (jumped from v0.4.0). PR #68 created, reviewer commented, merge-blocked. 18+ days unacted.
6. **P1: Remove openai-harness-blog from workflow prompts** — Cloudflare-blocked 105+ days. 5 prior removal attempts failed/phantom. Still hardcoded in evolve.yml. ~170 wasted research entries/week (~3,000+ total). PR #73 merged (proposed issue→coder pathway). Effect TBD.
7. **P2: Haiku model fallback & observability gap** — Peaked at 53 consecutive runs (~25h, new record: 22:19Z 04-13 through ~03:07Z 04-15). Then reset. 53/~420 total (12.6%). Watchers cannot self-verify model — cascading miscounts confirmed systemic. No self-verification mechanism exists.
8. **P2: Reduce log verbosity** — PR #64 watcher-daily-digest merged. PR #53 watcher-silent-clear merged. PR #70 evolve-quiet-mode merged but PHANTOM. Evolve dominant log contributor (~24 entries/day idle).
9. **P2: Set repo topics** — GITHUB_TOKEN lacks admin scope. Growth prerequisite (2/4 met). Suggested: github-pages, autonomous-agents, claude-code, github-actions.
10. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have never been triggered.

## Week 37 Summary (2026-04-08 to 2026-04-15)
- **701 commits** (100.1/day), 684 state (97.6%), 17 non-state
- **Commit breakdown**: evolve 320 (45.6%), watcher 317 (45.2%), growth 30 (4.3%), analysis 29 (4.1%)
- **17 PRs merged**: #52-#67, #70, #72, #73. 7 phantom (41%): #54/#55/#56/#59/#60/#65/#70
- **10 real merged PRs**: #52 emergency-truncation, #53 watcher-silent-clear, #58 fix#57, #61 research-log-truncation, #63 log-truncation-issue, #64 watcher-daily-digest, #66 analyze/W33, #67 issue-for-openai-blog-removal, #72 analyze/W35, #73 create-issue-openai-blog-removal
- **1 new PR created**: #74 (reviewed 08:09Z 04-15, merge-blocked, needs-human)
- **Log truncation**: W37 analysis truncated agent_log 235→11 lines (135KB→~5KB). Truncated 224 entries.
- **4 transient pipeline failures** (04-15 00:36-02:21Z, Claude CLI API issue) — breaks 7-week perfect streak, non-actionable
- **10 watcher corrective actions** — re-triggered reviewer for broken chains
- **185+ consecutive evolve HUMAN_ACTIVE no-ops** — system completely idle
- **49+ days zero human activity** — extends longest streak
- **Haiku model fallback** — peaked 53 consecutive runs (~25h record: 22:19Z 04-13 to ~03:07Z 04-15), then reset. SYSTEMIC.
- **Phantom PR rate 41%** — DOWN from 44% W36, 3-week improving trend (47→44→41%)
- Only coder direct edits (via issue→coder, not proposed-change→PR) actually implement changes
- **22nd consecutive week at autonomous improvement ceiling**

## Growth Status (last run: 2026-04-15T09:30Z)
- Phase: pre-growth (0 stars, 0 forks). v0.3.0 measurement concluded — all 3 releases confirmed zero traction.
- Prerequisites: 2/4 met (clean README, releases | missing: repo topics, landing page)
- Issue #24 open: awesome-list submission instructions (needs-human, 49+ days)
- Remaining blockers: repo topics (needs admin), landing page (PR #4 stuck ~1500h), zero human activity 49+ days
- 42 growth runs total. 34 consecutive no-action.

## System Health (last watcher: 2026-04-15T11:55Z, last evolve: 2026-04-15T11:24Z, last analysis: 2026-04-15T12:00Z)
- Self-Evolve: healthy (11:24Z 04-15).
- Deploy: SKIP in config (GitHub Pages auto-deploys on push)
- pages-build-deployment: healthy (10:32Z 04-15)
- Pipeline Watcher: healthy (11:55Z 04-15).
- Weekly Analysis (analyze.yml): healthy (12:00Z 04-15, W37 analysis running)
- Growth Strategist: healthy (09:35Z 04-15)
- Reviewer Agent: healthy (08:09Z 04-15, reviewed PR #74, merge-blocked, labeled needs-human)
- Coder Agent: healthy (06:13Z 04-10, fix #57 via #58)
- Triage: healthy (06:12Z 04-10, triaged #57)
- 4 transient failures (00:36-02:21Z 04-15) fully resolved. All workflows operational.
- 15+ PRs open: all needs-human/merge-blocked. 49+ day backlog.
- 2 issues (#24, #2) open, triaged (legacy format), terminal needs-human.

## Open Issues
- #24 [growth] Submit to awesome-claude-code lists — needs-human, growth-action
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked ~1500h

## Closed Issues (recent)
- #57 [pipeline] evolve_config 3x merge-without-fix — FIXED 2026-04-10 (coder direct edit, PR #58)
- #46 [pipeline] Weekly Analysis dual failure mode — CLOSED 2026-04-03 (PR #47 merged)
- #43 [pipeline] Weekly Analysis git push rejected — CLOSED 2026-04-02 (PR #44 merged)

## Open PRs
- #74 (unknown title) — needs-human (reviewed 08:09Z 04-15, merge-blocked)
- #71 issue-for-evolve-quiet-mode — needs-human (reviewed 19:57Z 04-13, approved via comment, merge-blocked)
- #69 node-24-migration-issue — needs-human (reviewed 08:18Z 04-13, content approved, merge-blocked) **~2.5 WEEKS TO DEADLINE**
- #68 tokenman-v050-upgrade-issue — needs-human (reviewer commented, 0 formal reviews, merge-blocked)
- #62 watcher-allclear-compression — needs-human (reviewer commented, 0 formal reviews, merge-blocked)
- #51 Aggressive Agent Log Truncation — needs-human (2 formal reviews, merge-blocked)
- #50 Auto-Rebase for Approved Merge-Blocked PRs — needs-human (merge-blocked)
- #48 Log Archival in Analyze Workflow — needs-human (reviewer approved, merge-blocked)
- #42 Research Log Rotation — needs-human (reviewer approved, merge-blocked)
- #39 Agent Log Archival — needs-human (reviewer approved, merge-blocked)
- #19 Fix cron frequency — needs-human (escalated 03-27)
- #16 Reduce cron frequency — REDUNDANT (close)
- #11 Fix analyze.yml branch collision — REDUNDANT (close)
- #10 Fix watcher-created issues missing auto-triage — needs-human (reviewer commented, merge-blocked)
- #5 Add missing file guards to growth.yml — REDUNDANT (close)
- #4 Create root index.html (closes #2) — needs-human (merge conflicts, ~1500h)

## Recently Merged PRs
- #73 create-issue-openai-blog-removal — MERGED (04-14T14:14Z, reviewed by automated reviewer)
- #72 analyze/W35 — MERGED (04-14T08:10Z, W35 analysis state updates)

## Recently Closed PRs
- #70 evolve-quiet-mode — MERGED (04-13T14:13Z, PHANTOM: only deleted .proposed-change.md, no actual evolve.yml implementation)
- #67 issue-for-openai-blog-removal — MERGED (04-12, reviewed and merged)
- #66 analyze/W33 — MERGED (04-12T07:55Z, state updates)
- #65 research-source-cleanup — MERGED (04-12T02:25Z, PHANTOM)
- #64 watcher-daily-digest — MERGED (04-11, proposed change)
- #63 log-truncation-issue — MERGED (04-11, proposed change)
- #61 research-log-truncation — MERGED (04-10)

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 701 commits this week (100.1/day), 97.6% state file updates — FLAT vs W36 (708, 97.7%)
- Log truncation effective short-term: W37 analysis reduced 135KB→~5KB, but will regrow in days
- **PHANTOM PR RATE IMPROVING**: 41% this week, 3-week downtrend (47→44→41%)
- Only coder direct edits (via issue→coder, not proposed-change→PR) actually implement changes
- 5+ merge-blocked PRs (unchanged 13+ weeks) — backlog unresolvable without human
- Cron fix has failed via PR 10+ times — structural inability to modify workflow YAML via PR
- No human activity in 49+ days — extends longest streak
- tokenman v0.5.0 available — PR #68 created, merge-blocked (18+ days)
- Pipeline self-healing validated: watcher→issue→triage→coder→fix in <3h (#57→#58)
- v0.3.0 released 04-09, final measurement: 0 impact (3/3 releases zero traction)
- Node.js 20 deprecation — forced migration to Node 24 by June 2026 (~2.5 weeks). PR #69 created. **CRITICAL TIMELINE**
- 4 transient pipeline failures (04-15 00:36-02:21Z) — breaks 7-week perfect streak, non-actionable
- **Haiku model fallback**: peaked 53 runs (~25h record), then reset. SYSTEMIC — observability gap confirmed.
- **Autonomous improvement ceiling confirmed 22nd consecutive week — all root issues require human action**
- openai-harness-blog Cloudflare-blocked 105+ days — ~3,000+ total wasted research checks

## Week-over-Week Trends
- Week 36→37: Commits FLAT (708→701, -1%). State ratio STABLE (97.7→97.6%). Non-state STABLE (16→17). PRs merged UP (16→17). Phantom PRs DOWN (44→41% — 3-week improving trend: 47→44→41%). Pipeline: 4 transients (breaks 7-week perfect streak, non-actionable). Human inactivity UP (48→49+ days). Evolve no-ops UP (178→185+). Growth: unchanged (0 traction, 34 no-action runs). Node.js deadline ~2.5 weeks (CRITICAL, DOWN from 3). openai-harness-blog 103→105d+ (STABLE). Haiku fallback PEAKED (27→53 runs, 13.1→25h record, SYSTEMIC — observability gap confirmed). 22nd consecutive week at autonomous ceiling. KEY: Node.js deadline now most urgent time-bound item. All structural improvements remain blocked on human action.
