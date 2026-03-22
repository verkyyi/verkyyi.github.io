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

## System Health (last watcher: 2026-03-22T15:41:48Z)
- Self-Evolve: healthy (consecutive successes)
- Deploy workflow: SKIP in config (fixed — workflow_dispatch-only, issue #1 resolved)
- pages-build-deployment: healthy
- Triage: first run triggered for issue #1 (was 0 runs ever); issue #2 next
- Coder: 0 runs (awaiting triage to label issues agent-ready)
- No agentfolio release exists yet for version tracking
- OpenAI harness blog persistently blocked by Cloudflare

## Open Issues
- #1 [pipeline] Deploy workflow fails: missing package-lock.json for npm cache — PR opened
- #2 [evolve] Create root index.html as portfolio landing page

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- Research sources quiet: agentfolio only has state commits, quarto-cli stable at v1.9
- No human-created issues in past 7 days
