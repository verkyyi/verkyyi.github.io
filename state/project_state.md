# Project State

## Current Focus
Portfolio landing page — site needs a root index.html (issue #2). Deploy workflow fix pending (issue #1).

## Recent Changes
- Added agentfolio autonomous pipeline workflows
- 5 evolve runs completed (2026-03-22, 3 under HUMAN_ACTIVE, 2 normal)
- Created issue #1: Deploy workflow fails due to missing package-lock.json
- Created issue #2: Create root index.html as portfolio landing page
- Self-Evolve pipeline stabilized after initial failures

## System Health (last evolve: 2026-03-22T14:10:31Z)
- Self-Evolve: healthy (3 consecutive successes)
- Deploy workflow: SKIP in config (failures expected, covered by issue #1)
- pages-build-deployment: healthy
- Config re-check: passed (no structural changes detected)
- No agentfolio release exists yet for version tracking

## Open Issues
- #1 [pipeline] Deploy workflow fails: missing package-lock.json for npm cache
- #2 [evolve] Create root index.html as portfolio landing page

## Key Observations
- No apps/ directory — flat static site, not using Astro
- Site has 2 project subdirs (6150/ survival analysis, Presentation/ chatbot) but no landing page
- OpenAI harness engineering blog consistently blocked by Cloudflare
- Quarto CLI at v1.9 — no actionable changes for this repo
- No human-created issues in past 7 days
