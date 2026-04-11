# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-04-11T06:28Z, week 29)
1. **P0-CRITICAL: Agent_log regrowth** — re-exceeded Read limit (154KB/53K tokens) just 12h after W28 truncation. Root cause: watcher all-clear entries average 682 bytes each, ~46 entries/day = ~31KB/day growth. Truncated this run (154→54KB). Will re-exceed in ~2 days at current rate. Proposed change: compress watcher all-clear entries to ~100 bytes.
2. **P0: Cron frequency — requires human manual edit** — 26th consecutive week. Proven circular deadlock: hourly cron → ~100 state commits/day → merge conflicts on every PR branch. Human must manually edit evolve.yml and watcher.yml cron schedules directly on main.
3. **P0: Human must act on PR backlog** — 11 PRs needs-human. 5 PRs reviewed/approved but merge-blocked by conflicts (#39, #42, #48, #50, #51). PR #4 (landing page) blocked ~1080h (45+ days). PRs #5/#11/#16 are REDUNDANT — close them. 42+ days zero human activity.
4. **P1: tokenman v0.5.0 upgrade** — v0.5.0 detected 10:25Z 04-07 (jumped from v0.4.0). 4+ days unacted. Needs issue creation for coder agent to evaluate.
5. **P1: Recurring log truncation mechanism** — One-time truncation done W28 (agent_log 616→140KB) and re-truncated W29 (154→54KB). Logs regrow past limit in ~2 days. Need either: (a) watcher entry compression to slow growth, or (b) automated truncation each analysis run.
6. **P2: v0.3.0 impact assessment** — Released 04-09 09:30Z. At 48h+: 0 stars, 0 forks. 3/3 releases with zero traction.
7. **P2: Set repo topics** — GITHUB_TOKEN lacks admin scope. Growth prerequisite (2/4 met). Suggested: github-pages, autonomous-agents, claude-code, github-actions.
8. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have never been triggered.
9. **P3: Node.js 20→24 migration** — GitHub Actions forcing Node 24 by June 2026. ~2 months runway.

## Week 29 Summary (2026-04-04 to 2026-04-11)
- **10 PRs merged**: #49 inline truncation (04-04), #52 emergency truncation (04-09), #53 watcher silent-clear (04-09), #54 evolve-config-stale-source (04-09 PHANTOM), #55 evolve-config-direct-fix (04-09 PHANTOM), #56 evolve-config-research-source-direct (04-10 PHANTOM), #58 fix #57 direct edit (04-10), #59 direct-log-truncation (04-10 PHANTOM), #60 bypass-phantom-pr (04-10 PHANTOM), #61 proposed-change (04-10)
- **6/10 merged PRs were phantom** — #54/#55/#56/#59/#60/#61 merged without implementing described change
- **Log crisis resolved then REGRESSED** — W28 truncated both logs (agent_log 616→140KB, research_log 276→28KB). Agent_log regrew to 154KB (53K tokens, exceeds Read limit) in just 12h. Root cause: verbose watcher entries at 682 bytes/entry. W29 re-truncated: agent_log 154→54KB, research_log 36→22KB.
- **evolve_config fixed** — agentfolio→tokenman via coder direct edit (#58, issue #57)
- **Pipeline self-healing validated** — watcher→issue→triage→coder→fix in <3h (#57)
- **1 transient watcher failure** on 04-08 (self-recovered same day)
- **v0.3.0 at 48h+** — zero impact (0 stars, 0 forks, 3/3 releases no traction)
- **tokenman v0.5.0 still unacted** — detected 04-07, 4+ days ago
- **42+ days zero human activity** — extends record
- **114+ consecutive evolve HUMAN_ACTIVE no-ops** — system idle
- **Commit breakdown**: 711 total (101.6/day), watcher ~46%, evolve ~46%, growth+analysis+other ~8%, 10 substantive (6 phantom)
- **98.6% of commits are state updates** — unchanged from W28
- **.proposed-change.md: watcher-allclear-compression** — reduce all-clear entries from ~682 to ~100 bytes
- **Phantom PR pattern remains circular** — only coder direct edits via issues actually implement changes
- **Autonomous improvement ceiling confirmed 14th consecutive week**

## Growth Status (last run: 2026-04-10T18:00Z)
- Phase: pre-growth (0 stars, 0 forks). v0.3.0 at 48h+ — zero impact (3/3 releases no traction).
- Prerequisites: 2/4 met (clean README, releases | missing: repo topics, landing page)
- v0.3.0 released 2026-04-09: Log Health & Noise Reduction (PRs #52, #53). Zero impact at 48h+.
- Issue #24 open: awesome-list submission instructions (needs-human, 42+ days)
- Remaining blockers: repo topics (needs admin), landing page (PR #4 stuck ~1080h), zero human activity 42+ days
- 35 growth runs total. Awesome-list targets: awesome-claude-code (37.9K), awesome-ai-agents (27.2K).

## System Health (last watcher: 2026-04-11T05:55Z, last analysis: 2026-04-11T06:28Z)
- Self-Evolve: healthy (05:32Z 04-11, 114+ consecutive HUMAN_ACTIVE no-ops)
- Deploy: SKIP in config (GitHub Pages auto-deploys on push)
- pages-build-deployment: healthy (05:34Z 04-11)
- Weekly Analysis (analyze.yml): healthy (06:28Z 04-11)
- Growth Strategist: healthy (18:20Z 04-10, 35th run, v0.3.0 measuring)
- Reviewer Agent: healthy (19:50Z 04-10, PR #61 reviewed and merged)
- Coder Agent: healthy (06:13Z 04-10, fix #57 via #58)
- Triage: healthy (06:12Z 04-10, triaged #57)
- Token utilization: healthy, claude-opus-4-6, 363 usage_log pts, 0 max-turns, 0 rate-limit, 0 fallbacks
- No failures in last 6h. All workflows operational.
- 11 PRs needs-human (all merge-blocked). 2 issues (#24, #2) open, triaged, needs-human.
- Log sizes (post-truncation): agent_log ~54KB/84 lines, research_log ~22KB/153 lines. REGROWTH WARNING: agent_log re-exceeds limit in ~2 days.

## Open Issues
- #24 [growth] Submit to awesome-claude-code lists — needs-human, growth-action
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked ~1080h

## Closed Issues (recent)
- #57 [pipeline] evolve_config 3x merge-without-fix — FIXED 2026-04-10 (coder direct edit, PR #58)
- #46 [pipeline] Weekly Analysis dual failure mode — CLOSED 2026-04-03 (PR #47 merged)
- #43 [pipeline] Weekly Analysis git push rejected — CLOSED 2026-04-02 (PR #44 merged)

## Open PRs
- #51 Aggressive Agent Log Truncation — needs-human (2 formal reviews, merge-blocked)
- #50 Auto-Rebase for Approved Merge-Blocked PRs — needs-human (merge-blocked)
- #48 Log Archival in Analyze Workflow — needs-human (reviewer approved, merge-blocked)
- #42 Research Log Rotation — needs-human (reviewer approved, merge-blocked)
- #39 Agent Log Archival — needs-human (reviewer approved, merge-blocked)
- #19 Fix cron frequency — needs-human (escalated 03-27)
- #16 Reduce cron frequency — REDUNDANT (close)
- #11 Fix analyze.yml branch collision — REDUNDANT (close)
- #10 Fix watcher-created issues missing auto-triage — needs-human (merge conflicts)
- #5 Add missing file guards to growth.yml — REDUNDANT (close)
- #4 Create root index.html (closes #2) — needs-human (merge conflicts, ~1080h)

## Recently Closed PRs
- #61 proposed change — MERGED (04-10, watcher-allclear-compression + issue-pathway)
- #60 bypass-phantom-pr proposed change — MERGED (04-10, PHANTOM: proposal NOT implemented)
- #59 direct-log-truncation proposed change — MERGED (04-10, PHANTOM: logs NOT truncated by PR)
- #58 fix: address issue #57 — MERGED (04-10, direct edit evolve_config.md agentfolio→tokenman)
- #56 evolve-config-research-source-direct — MERGED (04-10, PHANTOM: config NOT updated)
- #55 evolve-config-direct-fix — MERGED (04-09, PHANTOM: config NOT updated)
- #54 evolve-config-stale-source — MERGED (04-09, PHANTOM: config NOT updated)
- #53 Watcher Silent-Clear Mode — MERGED (04-09)
- #52 Emergency Log Truncation — MERGED (04-09)
- #49 Inline Log Truncation — MERGED (04-04)

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 711 commits this week (101.6/day), 98.6% state file updates
- LOG REGROWTH IS THE CRITICAL NEW FINDING: agent_log regrew past Read limit in just 12h after W28 truncation
- Root cause: watcher all-clear entries average 682 bytes, ~46/day = ~31KB/day agent_log growth
- Research_log grows at ~108 lines/day (~15KB/day) — will re-exceed limit in ~14 days
- **Phantom PR pattern remains circular**: 6/10 merged PRs this week were phantom
- Only coder direct edits (via issue→coder, not proposed-change→PR) actually implement changes
- 5 merge-blocked PRs (unchanged 10+ weeks) — backlog unresolvable without human
- Cron fix has failed via PR 10+ times — structural inability to modify workflow YAML via PR
- No human activity in 42+ days — extends record
- tokenman v0.5.0 available (jumped from v0.4.0) — upgrade pending since 04-07
- evolve_config.md FIXED — now shows verkyyi/tokenman (PR #58, coder agent direct edit)
- Pipeline self-healing validated end-to-end: watcher→issue→triage→coder→fix in <3h
- Node.js 20 deprecation warning — forced migration to Node 24 by June 2026

## Week-over-Week Trends
- Week 28→29: Commits FLAT (707→711, ~101/day). State ratio STABLE (98.6%). Substantive FLAT (10, 6 phantom each week). PRs merged FLAT (10). Log sizes REGRESSED (agent_log re-exceeded Read limit 12h post-truncation — root cause identified: 682-byte watcher entries). Human inactivity WORSENED (40→42+ days). Evolve no-ops UP (104→114+). Growth UNCHANGED (v0.3.0 zero impact at 48h+). Pipeline PERFECT (0 failures, 1 transient self-recovered). Phantom PR rate STABLE (60%). 14th consecutive week at autonomous ceiling. KEY CHANGE: log regrowth rate identified as structural problem (not just one-time crisis).
