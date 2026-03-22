# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2). Deploy workflow fix pending (issue #1).

## Recent Changes
- Added agentfolio autonomous pipeline workflows
- 6 evolve runs completed (2026-03-22, 3 under HUMAN_ACTIVE, 3 normal)
- Created issue #1: Deploy workflow fails due to missing package-lock.json
- Created issue #2: Create root index.html as portfolio landing page
- Self-Evolve pipeline stabilized after initial failures

## System Health (last evolve: 2026-03-22T15:08:28Z)
- Self-Evolve: healthy (6 consecutive successes since initial failures)
- Deploy workflow: SKIP in config (failures expected, covered by issue #1)
- pages-build-deployment: healthy
- Triage: 0 runs ever — issues #1/#2 still untriaged
- Coder: 0 runs (no agent-ready issues yet)
- No agentfolio release exists yet for version tracking
- OpenAI harness blog persistently blocked by Cloudflare

## Open Issues
- #1 [pipeline] Deploy workflow fails: missing package-lock.json for npm cache
- #2 [evolve] Create root index.html as portfolio landing page

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- Research sources quiet: agentfolio only has state commits, quarto-cli stable at v1.9
- No human-created issues in past 7 days
