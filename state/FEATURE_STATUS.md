# Feature Status
<!-- Updated by weekly analysis. AUTO-tier state file. -->
<!-- Last updated: 2026-04-11T12:15Z (week 29 analysis) -->

## In Progress
| Feature | Issue | PR | Status | Blocked Since | Blocker |
|---------|-------|-----|--------|---------------|---------|
| Root index.html (landing page) | #2 | #4 | needs-human | 2026-03-14 | Merge conflicts, ~1080h (45+ days). Human must rebase and merge. |
| Awesome-list submission | #24 | — | needs-human | 2026-03-27 | Human must submit to awesome-claude-code lists |
| Agent log archival | — | #39 | needs-human | 2026-04-01 | Reviewer approved but merge-blocked by conflicts |
| Research log rotation | — | #42 | needs-human | 2026-04-02 | Reviewer approved via comment but merge-blocked by conflicts |
| Log archival in analyze | — | #48 | needs-human | 2026-04-04 | Reviewer approved via comment but merge-blocked by conflicts |
| Aggressive log truncation | — | #51 | needs-human | 2026-04-04 | 2 formal reviews, merge-blocked by conflicts |
| Auto-rebase capability | — | #50 | needs-human | 2026-04-04 | Comment-only review, merge-blocked by conflicts |
| tokenman v0.5.0 upgrade | — | — | pending | 2026-04-07 | v0.5.0 detected 10:25Z 04-07 (jumped from v0.4.0). Upgrade issue pending. 4+ days unacted. |
| Recurring log truncation | — | — | proposed | 2026-04-10 | One-time truncation done W28. Logs regrowing at ~32KB/day. Need issue→coder pathway for recurring mechanism. |

## Stalled (no automated path forward)
| Item | Weeks Stalled | Attempts | Blocker |
|------|--------------|----------|---------|
| Cron frequency reduction | 26 | 10+ PRs | Circular deadlock: hourly cron → state commits → merge conflicts → PR failure. Human must edit evolve.yml + watcher.yml directly. |
| Repo topics | 17 | 1 API call | GITHUB_TOKEN lacks admin scope. Human must set manually. |
| Redundant PR cleanup (#5, #11, #16) | 15-17 | 0 | Human must close. |
| Phantom PR pattern | 4 | 7 phantom PRs (#54, #55, #56, #59, #60 + prior) | Circular: proposals to fix the pattern also phantom-merge. Only coder direct edits via issues work. |

## Completed
| Feature | Issue | PR | Completed |
|---------|-------|-----|-----------|
| Log truncation (direct state commit) | — | — | 2026-04-10 (W28 analysis: agent_log 616→140KB, research_log 276→28KB. First successful truncation in 9+ weeks.) |
| Bypass phantom PR proposal (phantom) | — | #60 | 2026-04-10 (merged but proposal NOT implemented — phantom PR pattern) |
| Direct log truncation (phantom PR) | — | #59 | 2026-04-10 (merged but logs NOT truncated — phantom PR pattern) |
| evolve_config stale source fix (direct edit) | #57 | #58 | 2026-04-10 (directly edited evolve_config.md: agentfolio→tokenman. Closes #57.) |
| evolve-config-direct-fix (incomplete) | — | #55 | 2026-04-09 (merged 19:56Z, phantom PR — config NOT updated) |
| Watcher silent-clear mode | — | #53 | 2026-04-09 (merged 08:05Z, expected ~80% watcher noise reduction) |
| Emergency log truncation (proposed change) | — | #52 | 2026-04-09 (merged, execution of truncation pending) |
| Inline log truncation in analyze | — | #49 | 2026-04-04 (merged 07:51Z, insufficient — logs still growing but plateaued) |
| Weekly Analysis dual failure fix | #46 | #47 | 2026-04-03 (merged, full pipeline chain ~5 min) |
| Direct log archival in analyze | — | #45 | 2026-04-03 (merged, analyze→watcher→reviewer→merge chain) |
| Weekly Analysis push rejection fix | #43 | #44 | 2026-04-02 (merged, full pipeline chain ~3 min) |
| Evolve no-action run compaction | — | #41 | 2026-04-01 (merged, ~30-40% evolve log reduction) |
| Research log quiet-run aggregation | — | #40 | 2026-04-01 (merged, aggregated format for no-action research entries) |
| Watcher abbreviated health check format | — | #38 | 2026-04-01 (merged, ~75% health check log reduction) |
| evolve_config.md update (tokenman v0.3.0) | — | #37 | 2026-03-31 (merged by reviewer, tokenman rename + v0.3.0 version) |
| Agent log compaction | — | #35 | 2026-03-30 (merged by reviewer, ~80% watcher log reduction) |
| FEATURE_STATUS.md creation | — | — | 2026-03-30 (direct commit, 9 weeks / 7+ PR attempts failed) |
| README cleanup (garbled content) | #20 | #21 | 2026-03-27 |
| OpenAI blog removal from config | — | #14 | 2026-03-26 |
| Cron frequency PR (ineffective) | — | #15 | 2026-03-26 |
| Weekly Analysis branch collision fix | #12 | #13 | 2026-03-25 |
| Weekly Analysis rm bug fix | #8 | #9 | 2026-03-24 |
| Growth Strategist adopters.md fix | #6 | #7 | 2026-03-23 |
| Deploy workflow package-lock fix | #1 | — | 2026-03-22 |

## Growth Prerequisites
- [x] Clean README (PR #21 merged 2026-03-27)
- [x] First release (v0.1.0 released 2026-03-26)
- [ ] Repo topics (needs admin scope)
- [ ] Landing page (PR #4 blocked ~1080h)
