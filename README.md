# verkyyi.github.io

Personal portfolio and project showcase, powered by a self-evolving autonomous scaffold.

[![GitHub Pages](https://img.shields.io/badge/deploy-GitHub%20Pages-blue)](https://verkyyi.github.io)
[![Release](https://img.shields.io/github/v/release/verkyyi/verkyyi.github.io)](https://github.com/verkyyi/verkyyi.github.io/releases)

## What's here

- **Portfolio site** hosted on [GitHub Pages](https://verkyyi.github.io) with Quarto-generated project pages
- **Self-healing CI/CD pipeline** that detects failures, creates fixes, and deploys autonomously
- **11 GitHub Actions workflows** that coordinate via committed state files and GitHub Issues

## How the scaffold works

The site is maintained by an autonomous agent pipeline built on [Claude Code](https://claude.ai/claude-code):

| Workflow | Trigger | Purpose |
|----------|---------|---------|
| `evolve.yml` | Cron | Self-evolution: research, improvements, SEO checks |
| `watcher.yml` | Cron | Health monitoring: detects failures, triggers fixes |
| `triage.yml` | Issue event | Auto-labels and routes new issues |
| `coder.yml` | Issue event | Implements changes from triaged issues |
| `reviewer.yml` | PR event | Reviews pull requests |
| `analyze.yml` | Weekly cron | Codebase health analysis and priority recommendations |
| `growth.yml` | Cron | Growth strategy and release management |
| `discover.yml` | Manual dispatch | Research upstream changes |
| `feedback-learner.yml` | PR merge | Learns from merged PRs |
| `claude-task.yml` | Manual dispatch | Ad-hoc task execution |
| `deploy.yml` | Manual dispatch | Manual deploy to GitHub Pages |

### Proven capabilities

- **Self-healing**: 3 autonomous fix cycles completed (issue detection -> fix PR -> review -> merge)
- **State tracking**: All agent activity committed to `state/` folder for full auditability
- **Research pipeline**: Monitors upstream repos and external sources for relevant changes

## Projects

- [Survival Analysis (6150)](./6150/) — Statistical analysis project
- [Chatbot Presentation](./Presentation/) — Chatbot presentation slides

## Stack

HTML, CSS, JavaScript | GitHub Pages | GitHub Actions | Claude Code

## License

This repository is public. The autonomous scaffold pattern is free to study and adapt.
