# Agentfolio

A self-evolving web project harness powered by Claude Code. The scaffold IS the system — it improves its own workflows, fixes its own bugs, and manages its own development lifecycle autonomously.

[![GitHub Pages](https://img.shields.io/badge/deploy-GitHub%20Pages-blue)](https://verkyyi.github.io)
[![Release](https://img.shields.io/github/v/release/verkyyi/verkyyi.github.io)](https://github.com/verkyyi/verkyyi.github.io/releases)

## How it works

Every agent action is a commit. State lives in `state/`. Events flow through GitHub Issues. Eleven workflows orchestrate the full development lifecycle — from discovering improvements to implementing, reviewing, and deploying them.

| Workflow | Trigger | Role |
|----------|---------|------|
| `evolve.yml` | Scheduled | Self-evolution engine: research, planning, improvement |
| `triage.yml` | Issue event | Categorize and prioritize incoming issues |
| `coder.yml` | Issue event | Implement changes from triaged issues |
| `reviewer.yml` | PR event | Automated code review |
| `watcher.yml` | Scheduled | Pipeline health monitoring and self-healing |
| `analyze.yml` | Scheduled | Weekly codebase analysis |
| `growth.yml` | Scheduled | Growth strategy and distribution |
| `feedback-learner.yml` | PR merge | Learn from merged PRs to improve future work |
| `discover.yml` | Manual | Research upstream changes and new projects |
| `claude-task.yml` | Manual | Ad-hoc task execution |
| `deploy.yml` | Manual | Deploy to GitHub Pages |

## What makes it interesting

- **Self-healing pipeline**: When a workflow fails, the watcher detects it, opens an issue, the coder fixes it, and the reviewer merges — all autonomously
- **State as code**: All agent state is committed to `state/`, making the system's "memory" fully auditable via git history
- **Scaffold-first**: The first project is itself — the harness improves its own rules, workflows, and capabilities over time

## Project structure

```
.github/workflows/   # 11 autonomous workflows
state/               # Agent state (committed every run)
skills/              # Reusable skill definitions
CLAUDE.md            # Scaffold constitution and autonomy rules
```

## Getting started

1. Fork this repo
2. Add `CLAUDE_CODE_OAUTH_TOKEN` to your repo secrets
3. The workflows will begin their autonomous cycle

## License

MIT
