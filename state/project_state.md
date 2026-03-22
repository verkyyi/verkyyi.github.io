# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2).

## Recent Changes
- Fixed deploy.yml: removed push trigger and npm cache, made workflow_dispatch-only (closes #1)
- Added agentfolio autonomous pipeline workflows
- 6 evolve runs completed (2026-03-22, 3 under HUMAN_ACTIVE, 3 normal)
- Created issue #1: Deploy workflow fails due to missing package-lock.json
- Created issue #2: Create root index.html as portfolio landing page
- Self-Evolve pipeline stabilized after initial failures

## System Health (last watcher: 2026-03-22T16:46:07Z)
- Self-Evolve: healthy (last success 16:07)
- Deploy workflow: SKIP in config (fixed — workflow_dispatch-only, issue #1 resolved)
- pages-build-deployment: healthy
- Triage: ran for issue #1 (15:43); re-triggered for issue #2 (16:46)
- Coder: ran for issue #1, created PR #3 (run reported failure due to duplicate PR step, but PR exists)
- Reviewer: re-triggered for PR #3 (auto-triggered runs were skipped, 0 reviews)
- No agentfolio release exists yet for version tracking
- OpenAI harness blog persistently blocked by Cloudflare

## Open Issues
- #1 [pipeline] Deploy workflow fails: missing package-lock.json — PR #3 open, being merged
- #2 [evolve] Create root index.html as portfolio landing page — triage re-triggered

## Open PRs
- #3 fix(workflow): disable deploy.yml push trigger (closes #1) — approved, merging

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- Research sources quiet: agentfolio only has state commits, quarto-cli stable at v1.9
- No human-created issues in past 7 days
