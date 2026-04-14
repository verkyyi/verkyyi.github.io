# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Priorities (from weekly analysis 2026-04-14T06:45Z, week 35)
1. **P0: Cron frequency — requires human manual edit** — 30th consecutive week. Proven circular deadlock: hourly cron → ~100 state commits/day → merge conflicts on every PR branch. Human must manually edit evolve.yml and watcher.yml cron schedules directly on main. Root cause of log growth, commit volume, and merge-blocked PRs.
2. **P0: Human must act on PR backlog** — 10+ PRs needs-human. 5+ PRs reviewed/approved but merge-blocked by conflicts (#39, #42, #48, #50, #51). PR #4 (landing page) blocked ~1320h (55+ days). PRs #5/#11/#16 are REDUNDANT — close them. 47+ days zero human activity.
3. **P0: Log regrowth outpaces truncation** — agent_log regrew 30→176 lines in ~21h after evolve truncation (04-13 09:39Z). Growth rate ~40KB/day. Evolve writes ~24 no-op entries/day (dominant contributor). Evolve-quiet-mode PR #70 merged but PHANTOM (no implementation). PR #71 (issue-for-quiet-mode) merge-blocked.
4. **P1: Node.js 20→24 migration** — GitHub Actions forcing Node 24 by June 2026. ~3 weeks runway (DOWN from 4 at W34). PR #69 created, reviewed, approved, merge-blocked.
5. **P1: tokenman v0.5.0 upgrade** — v0.5.0 detected 10:25Z 04-07 (jumped from v0.4.0). PR #68 created, reviewer commented, merge-blocked. 17+ days unacted.
6. **P1: Remove openai-harness-blog from workflow prompts** — Cloudflare-blocked 103+ days. PR #65 phantom-merged. PR #67 merged but no issue created. Still hardcoded in evolve.yml (line 92 curl, line 102 seed data). ~170 wasted research entries/week (~2,800+ total). Proposed change: direct YAML edit.
7. **P2: Reduce log verbosity** — PR #64 watcher-daily-digest merged. PR #53 watcher-silent-clear merged. PR #70 evolve-quiet-mode merged but PHANTOM. Evolve dominant log contributor (~24 entries/day idle).
8. **P2: Set repo topics** — GITHUB_TOKEN lacks admin scope. Growth prerequisite (2/4 met). Suggested: github-pages, autonomous-agents, claude-code, github-actions.
9. **P2: Haiku model fallback monitoring** — 20 consecutive haiku runs (22:19Z 04-13 through 08:38Z 04-14, ~10.3h). Streak ended. 20/~420 total (4.8%). Prior watchers undercounted (13→16) — haiku-running watchers misidentify own model as opus. Observability gap.
10. **P3: Activate unused workflows** — discover, feedback-learner, claude-task have never been triggered.

## Week 35 Summary (2026-04-07 to 2026-04-14)
- **705 commits** (100.7/day), 690 state (97.9%), 15 non-state
- **Commit breakdown**: watcher ~46%, evolve ~46%, growth ~4%, analysis ~4%
- **15 PRs merged**: #52 emergency-truncation, #53 watcher-silent-clear, #54/#55/#56 phantom, #58 fix#57 coder-direct-edit, #59/#60 phantom, #61 research-log-truncation, #63 log-truncation-issue, #64 watcher-daily-digest, #65 research-source-cleanup (PHANTOM), #66 analyze/W33, #67 issue-for-openai-blog-removal, #70 evolve-quiet-mode (PHANTOM)
- **7 of 15 merged PRs phantom** (47%) — #54/#55/#56/#59/#60/#65/#70. UP from 43% W34.
- **4 new PRs created**: #68 tokenman-v050-upgrade, #69 node-24-migration, #70 evolve-quiet-mode, #71 issue-for-evolve-quiet-mode — all reviewed, #70 merged (phantom), others merge-blocked
- **Log truncation**: evolve truncated 09:39Z 04-13 (agent_log 165→30, research_log 338→33). W35 analysis removed 17 entries from 04-06.
- **0 pipeline failures all week** — 7th consecutive perfect week (project record)
- **8 watcher corrective actions** — re-triggered reviewer for broken chains (#62, #65, #66, #67, #68, #69, #70, #71)
- **175+ consecutive evolve HUMAN_ACTIVE no-ops** — system completely idle
- **47+ days zero human activity** — extends longest streak
- **Haiku model fallback** — NEW: 13 consecutive runs (~7.5h), resolved. 3.6% total haiku rate.
- **.proposed-change.md: remove-openai-harness-blog-from-evolve** — direct YAML edit to remove 103-day blocked source
- **openai-harness-blog 103+ day milestone** — ~2,800+ total wasted research checks
- **Phantom PR pattern WORSENING** (43→47%) — 7th consecutive phantom of .proposed-change.md→PR type
- **20th consecutive week at autonomous improvement ceiling**

## Growth Status (last run: 2026-04-14T09:30Z)
- Phase: pre-growth (0 stars, 0 forks). v0.3.0 measurement concluded — all 3 releases confirmed zero traction.
- Prerequisites: 2/4 met (clean README, releases | missing: repo topics, landing page)
- Issue #24 open: awesome-list submission instructions (needs-human, 48+ days)
- Remaining blockers: repo topics (needs admin), landing page (PR #4 stuck ~1370h), zero human activity 48+ days
- 40 growth runs total. 32 consecutive no-action. Awesome-list targets: awesome-claude-code (38.6K), awesome-claude-code-subagents (17.3K).

## System Health (last watcher: 2026-04-14T09:10Z, last analysis: 2026-04-14T06:45Z)
- Self-Evolve: healthy (08:36Z 04-14, 8+ consecutive successes)
- Deploy: SKIP in config (GitHub Pages auto-deploys on push)
- pages-build-deployment: healthy (08:38Z 04-14)
- Weekly Analysis (analyze.yml): healthy (06:53Z 04-14, W35 summary, PR #72 merged 08:10Z)
- Growth Strategist: healthy (18:30Z 04-13, 39 runs, 31 consecutive no-action)
- Reviewer Agent: healthy (08:09Z 04-14, reviewed+merged PR #72)
- Coder Agent: healthy (06:13Z 04-10, fix #57 via #58)
- Triage: healthy (06:12Z 04-10, triaged #57)
- Token utilization: healthy. Haiku streak ENDED at 20 runs (22:19Z 04-13 through 08:38Z 04-14, ~10.3h) — prior watchers undercounted (reported 13→16) because haiku-running watchers misidentified own model. 20/~420 total (4.8%). 0 rate-limit errors. 0 max-turns issues.
- 0 failures in last 2h. All workflows operational.
- PR #72 merged (08:10Z). 15 PRs open: all needs-human/merge-blocked. 47+ day backlog.
- 2 issues (#24, #2) open, triaged (legacy format), terminal needs-human.

## Open Issues
- #24 [growth] Submit to awesome-claude-code lists — needs-human, growth-action
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, blocked ~1320h

## Closed Issues (recent)
- #57 [pipeline] evolve_config 3x merge-without-fix — FIXED 2026-04-10 (coder direct edit, PR #58)
- #46 [pipeline] Weekly Analysis dual failure mode — CLOSED 2026-04-03 (PR #47 merged)
- #43 [pipeline] Weekly Analysis git push rejected — CLOSED 2026-04-02 (PR #44 merged)

## Open PRs
- #71 issue-for-evolve-quiet-mode — needs-human (reviewed 19:57Z 04-13, approved via comment, merge-blocked)
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
- #4 Create root index.html (closes #2) — needs-human (merge conflicts, ~1320h)

## Recently Closed PRs
- #70 evolve-quiet-mode — MERGED (04-13T14:13Z, PHANTOM: only deleted .proposed-change.md, no actual evolve.yml implementation)
- #67 issue-for-openai-blog-removal — MERGED (04-12, reviewed and merged)
- #66 analyze/W33 — MERGED (04-12T07:55Z, state updates)
- #65 research-source-cleanup — MERGED (04-12T02:25Z, PHANTOM: .proposed-change.md deleted but openai-harness-blog still hardcoded)
- #64 watcher-daily-digest — MERGED (04-11, proposed change)
- #63 log-truncation-issue — MERGED (04-11, proposed change)
- #61 research-log-truncation — MERGED (04-10)
- #60 bypass-phantom-pr proposed change — MERGED (04-10, PHANTOM: proposal NOT implemented)
- #59 direct-log-truncation proposed change — MERGED (04-10, PHANTOM: logs NOT truncated by PR)
- #58 fix: address issue #57 — MERGED (04-10, direct edit evolve_config.md agentfolio→tokenman)

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- 705 commits this week (100.7/day), 97.9% state file updates — SLIGHT DIP from W34 (707, 98.0%)
- Log regrowth is top systemic risk — agent_log regrew 30→176 lines in ~21h post-truncation
- **PHANTOM PR PATTERN WORSENING**: 7/15 (47%) this week, UP from 43% W34
- Only coder direct edits (via issue→coder, not proposed-change→PR) actually implement changes
- 5+ merge-blocked PRs (unchanged 12+ weeks) — backlog unresolvable without human
- Cron fix has failed via PR 10+ times — structural inability to modify workflow YAML via PR
- No human activity in 47+ days — extends longest streak
- tokenman v0.5.0 available — PR #68 created, merge-blocked (17+ days)
- Pipeline self-healing validated: watcher→issue→triage→coder→fix in <3h (#57→#58)
- v0.3.0 released 04-09, final measurement: 0 impact (3/3 releases zero traction)
- Node.js 20 deprecation — forced migration to Node 24 by June 2026 (~3 weeks). PR #69 created.
- 0 pipeline failures all week — 7th consecutive perfect week (project record)
- 175+ consecutive evolve HUMAN_ACTIVE no-ops — system completely idle
- **Haiku model fallback**: 20 consecutive runs (~10.3h), 4.8% total rate, streak ended — prior watchers undercounted due to haiku self-misidentification
- **Autonomous improvement ceiling confirmed 20th consecutive week — phantom PR rate worsening, root issues unchanged**
- openai-harness-blog Cloudflare-blocked 103+ days — ~2,800+ total wasted research checks (confirmed: evolve.yml lines 92+102)

## Week-over-Week Trends
- Week 34→35: Commits FLAT (707→705, 100.7/day). State ratio STABLE (97.9%). Non-state FLAT (15). PRs merged UP (14→15). Phantom PRs UP (43→47% — trend reversed, was improving). Merge-blocked PRs STABLE at 5+. Human inactivity UP (45→47+ days). Evolve no-ops UP (163→175+). Growth: unchanged (0 traction, 31+ no-action runs). Pipeline PERFECT (7th consecutive week — project record). Node.js deadline ~3 weeks (DOWN from 4). openai-harness-blog 103d+ (UP from 102d+). Haiku fallback NEW phenomenon (3.6%, resolved). 20th consecutive week at autonomous ceiling. KEY: phantom PR rate trend reversed (was improving 50→46→43, now 47%). Evolve-quiet-mode failed to implement via PR (7th consecutive .proposed-change.md phantom). All structural improvements blocked on human action.
