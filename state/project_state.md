# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-04-13T12:00Z, week 34)
1. **P0: Cron frequency — requires human manual edit** — 29th consecutive week. Proven circular deadlock: hourly cron → ~100 state commits/day → merge conflicts on every PR branch. Human must manually edit evolve.yml and watcher.yml cron schedules directly on main. Root cause of log growth, commit volume, and merge-blocked PRs.
2. **P0: Human must act on PR backlog** — 10 PRs needs-human. 5 PRs reviewed/approved but merge-blocked by conflicts (#39, #42, #48, #50, #51). PR #4 (landing page) blocked ~1250h (52+ days). PRs #5/#11/#16 are REDUNDANT — close them. 45+ days zero human activity.
3. **P0: Log regrowth outpaces truncation** — agent_log 101KB (172 lines), regrew from 30 lines to 172 in ~2h after evolve truncation. Growth rate ~40KB/day. Evolve writes ~24 no-op entries/day (dominant contributor). Proposed: evolve-quiet-mode to cut 83% of evolve log entries.
4. **P1: Node.js 20→24 migration** — GitHub Actions forcing Node 24 by June 2026. ~4 weeks runway (DOWN from 5 at W33). PR #69 created, reviewed, approved, merge-blocked.
5. **P1: tokenman v0.5.0 upgrade** — v0.5.0 detected 10:25Z 04-07 (jumped from v0.4.0). PR #68 created, reviewer commented, merge-blocked. 16+ days unacted.
6. **P1: Remove openai-harness-blog from workflow prompts** — Cloudflare-blocked 102+ days. PR #65 phantom-merged. PR #67 merged but no issue created. Still hardcoded in evolve.yml prompts. ~168 wasted research entries/week (~2,600+ total).
7. **P2: Reduce log verbosity** — PR #64 watcher-daily-digest merged. PR #53 watcher-silent-clear merged. Evolve now dominant log contributor (~24 entries/day during idle). Proposed evolve-quiet-mode.
8. **P2: Set repo topics** — GITHUB_TOKEN lacks admin scope. Growth prerequisite (2/4 met). Suggested: github-pages, autonomous-agents, claude-code, github-actions.
9. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have never been triggered.

## Week 34 Summary (2026-04-06 to 2026-04-13)
- **707 commits** (101/day), 693 state (98.0%), 14 non-state
- **Commit breakdown**: watcher ~46%, evolve ~46%, growth ~4%, analysis ~4%
- **14 PRs merged**: #52 emergency-truncation, #53 watcher-silent-clear, #54/#55/#56 phantom, #58 evolve-config-fix, #59/#60 phantom, #61 research-log-truncation, #63 log-truncation-issue, #64 watcher-daily-digest, #65 research-source-cleanup (PHANTOM), #66 analyze/W33, #67 issue-for-openai-blog-removal
- **6 of 14 merged PRs phantom** (43%) — #54/#55/#56/#59/#60/#65. DOWN from 46% W33.
- **2 new PRs created**: #68 tokenman-v050-upgrade, #69 node-24-migration — both reviewed, merge-blocked
- **Log truncation**: evolve truncated 09:39Z (agent_log 165→30 lines, research_log 338→33 lines). File regrew to 172 lines in ~2h. W34 analysis removed 13 entries from 04-05.
- **0 pipeline failures all week** — 6th consecutive perfect week
- **6 watcher corrective actions** — all re-triggered reviewer for broken chains (#62, #65, #66, #67, #68, #69)
- **163+ consecutive evolve HUMAN_ACTIVE no-ops** — system completely idle
- **45+ days zero human activity** — extends longest streak
- **.proposed-change.md: evolve-quiet-mode** — suppress HUMAN_ACTIVE no-op logging to once per 6h
- **openai-harness-blog 102+ day milestone** — ~2,600+ total wasted research checks
- **Phantom PR pattern improving** (50→46→43%) — issue→coder remains only reliable change mechanism
- **19th consecutive week at autonomous improvement ceiling**

## Growth Status (last run: 2026-04-13T18:00Z)
- Phase: pre-growth (0 stars, 0 forks). v0.3.0 measurement concluded — all 3 releases confirmed zero traction.
- Prerequisites: 2/4 met (clean README, releases | missing: repo topics, landing page)
- Issue #24 open: awesome-list submission instructions (needs-human, 47+ days)
- Remaining blockers: repo topics (needs admin), landing page (PR #4 stuck ~1300h), zero human activity 47+ days
- 39 growth runs total. 31 consecutive no-action. Awesome-list targets: awesome-claude-code (38.5K), awesome-claude-code-subagents (17.2K).

## System Health (last watcher: 2026-04-14T05:20Z, last analysis: 2026-04-13T12:00Z)
- Self-Evolve: healthy (04:58Z 04-14, 7+ consecutive successes after 15:32Z 04-13 transient)
- Deploy: SKIP in config (GitHub Pages auto-deploys on push)
- pages-build-deployment: healthy (05:00Z 04-14)
- Weekly Analysis (analyze.yml): healthy (00:35Z 04-14, W34 summary at 12:00Z 04-13)
- Growth Strategist: healthy (18:30Z 04-13, 39 runs, 31 consecutive no-action)
- Reviewer Agent: healthy (19:56Z 04-13, reviewed PR #71 — approved via comment, merge-blocked)
- Coder Agent: healthy (06:13Z 04-10, fix #57 via #58)
- Triage: healthy (06:12Z 04-10, triaged #57)
- Token utilization: healthy. Haiku fallback SUSTAINED — 11 consecutive runs (22:19Z 04-13 through 05:00Z 04-14, ~7h), UP from 9 at last check. Longest observed streak. ~408 total data pts, 11 haiku fallbacks (2.7%). 0 max-turns issues. 0 rate-limit errors. System functional on haiku.
- 0 failures in last 2h. All workflows operational.
- 15 PRs open: all needs-human/merge-blocked. 46+ day backlog.
- 2 issues (#24, #2) open, triaged (legacy format), terminal needs-human.

## Open Issues
- #24 [growth] Submit to awesome-claude-code lists — needs-human, growth-action
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked ~1250h

## Closed Issues (recent)
- #57 [pipeline] evolve_config 3x merge-without-fix — FIXED 2026-04-10 (coder direct edit, PR #58)
- #46 [pipeline] Weekly Analysis dual failure mode — CLOSED 2026-04-03 (PR #47 merged)
- #43 [pipeline] Weekly Analysis git push rejected — CLOSED 2026-04-02 (PR #44 merged)

## Open PRs
- #69 node-24-migration-issue — needs-human (reviewed 08:18Z 04-13, content approved, merge-blocked)
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
- #4 Create root index.html (closes #2) — needs-human (merge conflicts, ~1250h)

## Recently Closed PRs
- #70 evolve-quiet-mode — MERGED (04-13T14:13Z, reviewed and merged, suppresses HUMAN_ACTIVE no-op logging)
- #67 issue-for-openai-blog-removal — MERGED (04-12, reviewed and merged)
- #66 analyze/W33 — MERGED (04-12T07:55Z, state updates)
- #65 research-source-cleanup — MERGED (04-12T02:25Z, PHANTOM: .proposed-change.md deleted but openai-harness-blog still hardcoded in prompts)
- #64 watcher-daily-digest — MERGED (04-11, proposed change)
- #63 log-truncation-issue — MERGED (04-11, proposed change)
- #61 research-log-truncation — MERGED (04-10)
- #60 bypass-phantom-pr proposed change — MERGED (04-10, PHANTOM: proposal NOT implemented)
- #59 direct-log-truncation proposed change — MERGED (04-10, PHANTOM: logs NOT truncated by PR)
- #58 fix: address issue #57 — MERGED (04-10, direct edit evolve_config.md agentfolio→tokenman)

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 707 commits this week (101/day), 98.0% state file updates — FLAT vs W33
- Log regrowth is top systemic risk — evolve writes ~24 entries/day during idle, agent_log regrew 30→172 lines in ~2h
- **PHANTOM PR PATTERN improving**: 6/14 (43%) this week, down from 46% W33
- Only coder direct edits (via issue→coder, not proposed-change→PR) actually implement changes
- 5 merge-blocked PRs (unchanged 12+ weeks) — backlog unresolvable without human
- Cron fix has failed via PR 10+ times — structural inability to modify workflow YAML via PR
- No human activity in 45+ days — extends longest streak
- tokenman v0.5.0 available — PR #68 created, merge-blocked (16+ days)
- Pipeline self-healing validated: watcher→issue→triage→coder→fix in <3h (#57→#58)
- v0.3.0 released 04-09, final measurement: 0 impact (3/3 releases zero traction)
- Node.js 20 deprecation — forced migration to Node 24 by June 2026 (~4 weeks). PR #69 created.
- 0 pipeline failures all week — 6th consecutive perfect week (project record)
- 163+ consecutive evolve HUMAN_ACTIVE no-ops — system completely idle
- **Autonomous improvement ceiling confirmed 19th consecutive week — phantom PR rate improving, root issues unchanged**
- openai-harness-blog Cloudflare-blocked 102+ days — ~2,600+ total wasted research checks

## Week-over-Week Trends
- Week 33→34: Commits FLAT (712→707, 101/day). State ratio STABLE (98.0%). Non-state FLAT (14). PRs merged UP (13→14). Merge-blocked PRs STABLE at 5. **LOG GROWTH FLAT** (~40KB/day, evolve now dominant contributor). Human inactivity UP (44→45+ days). Evolve no-ops UP (141→163+). Growth: unchanged (0 traction, 30+ no-action runs). Pipeline PERFECT (6th consecutive week). Phantom PRs DOWN (46→43%). Issue→coder remains only reliable change mechanism. 19th consecutive week at autonomous ceiling. KEY: Node.js deadline now ~4 weeks. PRs #69 (node-24) and #68 (tokenman) created but merge-blocked. Evolve log contribution identified as dominant growth driver. All structural improvements blocked on human action.
