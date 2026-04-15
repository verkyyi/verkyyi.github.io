# Feature Status
<!-- Updated by weekly analysis. AUTO-tier state file. -->
<!-- Last updated: 2026-04-15T12:00Z (week 37 analysis) -->

## In Progress
| Feature | Issue | PR | Status | Blocked Since | Blocker |
|---------|-------|-----|--------|---------------|---------|
| Root index.html (landing page) | #2 | #4 | needs-human | 2026-03-14 | Merge conflicts, ~1500h (62+ days). Human must rebase and merge. |
| Awesome-list submission | #24 | — | needs-human | 2026-03-27 | Human must submit to awesome-claude-code lists |
| Agent log archival | — | #39 | needs-human | 2026-04-01 | Reviewer approved but merge-blocked by conflicts |
| Research log rotation | — | #42 | needs-human | 2026-04-02 | Reviewer approved via comment but merge-blocked by conflicts |
| Log archival in analyze | — | #48 | needs-human | 2026-04-04 | Reviewer approved via comment but merge-blocked by conflicts |
| Aggressive log truncation | — | #51 | needs-human | 2026-04-04 | 2 formal reviews, merge-blocked by conflicts |
| Auto-rebase capability | — | #50 | needs-human | 2026-04-04 | Comment-only review, merge-blocked by conflicts |
| tokenman v0.5.0 upgrade | — | #68 | needs-human | 2026-04-07 | v0.5.0 detected 04-07. PR #68 created, reviewer commented, merge-blocked. 18+ days unacted. |
| Node.js 24 migration | — | #69 | needs-human | 2026-04-13 | PR #69 created by analysis. Reviewed (approved), merge-blocked. ~2.5 weeks to GitHub Actions deadline (DOWN from 3 at W36). **CRITICAL** |
| Issue for evolve-quiet-mode | — | #71 | needs-human | 2026-04-13 | PR #71 created, reviewed (approved via comment), merge-blocked. Intended to create issue for coder to implement quiet-mode since PR #70 was phantom. |
| Recurring log truncation | — | #63 | proposed | 2026-04-10 | PR #63 merged (proposed creating issue for coder). Evolve now truncates directly. Logs regrow at ~6 lines/hr (~135KB/week). |

## Stalled (no automated path forward)
| Item | Weeks Stalled | Attempts | Blocker |
|------|--------------|----------|---------|
| Cron frequency reduction | 31 | 10+ PRs | Circular deadlock: hourly cron → state commits → merge conflicts → PR failure. Human must edit evolve.yml + watcher.yml directly. ROOT CAUSE of log growth, commit volume, and all merge-blocked PRs. 31st week. |
| Repo topics | 21 | 1 API call | GITHUB_TOKEN lacks admin scope. Human must set manually. |
| Redundant PR cleanup (#5, #11, #16) | 19-21 | 0 | Human must close. |
| Phantom PR pattern | 11 | 10+ phantom PRs | Rate IMPROVING (47→44→41% over 3 weeks). 7th consecutive .proposed-change.md→PR phantom (#70). Only coder direct edits via issues work. |
| openai-harness-blog removal | 16+ | PR #65 phantom, PR #67 phantom issue, PR #73 issue pathway, 2 proposed YAML edits | Cloudflare-blocked 105+ days. Still checked hourly by evolve (hardcoded in evolve.yml). ~170 wasted entries/week (~3,000+ total). PR #73 merged (issue→coder pathway) — effect TBD. |

## Completed
| Feature | Issue | PR | Completed |
|---------|-------|-----|-----------|
| Create issue for openai-blog-removal | — | #73 | 2026-04-14 (merged 14:14Z, proposed issue→coder pathway for removing hardcoded openai-harness-blog refs) |
| Evolve-quiet-mode (phantom) | — | #70 | 2026-04-13 (PHANTOM: merged 14:13Z, only deleted .proposed-change.md, no actual evolve.yml implementation) |
| Issue for openai-blog-removal | — | #67 | 2026-04-12 (merged, proposed issue creation for coder to remove hardcoded refs) |
| Research source cleanup (phantom) | — | #65 | 2026-04-12 (PHANTOM: merged but openai-harness-blog still hardcoded in workflow prompts) |
| Watcher daily-digest mode | — | #64 | 2026-04-11 (merged, intended to cut watcher log entries ~60%. Effect TBD — monitoring.) |
| Log truncation issue proposal | — | #63 | 2026-04-11 (merged, proposed creating issue for coder to handle recurring truncation) |
| Log truncation (direct state commit) | — | — | 2026-04-10 (W28 analysis: agent_log 616→140KB, research_log 276→28KB.) |
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
- [ ] Landing page (PR #4 blocked ~1500h)
