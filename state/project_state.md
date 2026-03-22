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

## System Health (last watcher: 2026-03-22T17:43:32Z)
- Self-Evolve: healthy (last success 17:07)
- Deploy workflow: SKIP in config (fixed — workflow_dispatch-only, issue #1 closed)
- pages-build-deployment: healthy (last success 17:10)
- Triage: ran for issue #2 (16:47, success)
- Coder: ran for issue #2, created PR #4 (16:48, success)
- Reviewer: ran for PR #4 (16:50, success) — approved via comment, noted merge conflicts
- No agentfolio release exists yet for version tracking
- OpenAI harness blog persistently blocked by Cloudflare

## Open Issues
- #2 [evolve] Create root index.html as portfolio landing page — PR #4 open, reviewed (merge conflicts)

## Open PRs
- #4 fix: [evolve] Create root index.html (closes #2) — reviewer approved, has merge conflicts (needs rebase)

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- Research sources quiet: agentfolio only has state commits, quarto-cli stable at v1.9
- No human-created issues in past 7 days
