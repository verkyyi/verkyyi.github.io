# verkyyi.github.io

Personal portfolio and project showcase, hosted on GitHub Pages. Powered by an autonomous self-evolving harness that triages issues, writes fixes, reviews PRs, and monitors pipeline health — all through GitHub Actions and Claude Code.

[![GitHub Pages](https://img.shields.io/website?url=https%3A%2F%2Fverkyyi.github.io&label=GitHub%20Pages)](https://verkyyi.github.io)

## Workflows

| Workflow | Trigger | Description |
|----------|---------|-------------|
| `analyze.yml` | Schedule, manual | Weekly codebase analysis |
| `claude-task.yml` | Manual dispatch | Run ad-hoc Claude tasks |
| `coder.yml` | Issue labeled, manual | Implement fixes from issues |
| `deploy.yml` | Manual dispatch | Deploy to GitHub Pages |
| `discover.yml` | Manual dispatch | Discover and onboard new projects |
| `evolve.yml` | Schedule, manual | Self-evolution orchestrator |
| `feedback-learner.yml` | PR/issue events | Learn from merged PRs and closed issues |
| `growth.yml` | Schedule, manual | Growth and traction strategy |
| `reviewer.yml` | PR opened/updated, manual | Automated PR review |
| `triage.yml` | Issue opened/reopened, manual | Classify and elaborate new issues |
| `watcher.yml` | Schedule, manual | Pipeline health monitoring |

## Features

- **Autonomous pipeline** — issues are triaged, coded, reviewed, and merged without human intervention
- **Self-healing** — the watcher detects failures and opens fix issues automatically
- **State tracking** — all agent activity is logged in `state/` for cross-session continuity
- **Growth strategy** — automated outreach and traction monitoring

## Project Structure

```
.
├── .github/workflows/   # 11 GitHub Actions workflows
├── 6150/                # Survival analysis project (Quarto-generated)
├── Presentation/        # Chatbot presentation project
├── skills/              # Agent skill definitions
├── state/               # Agent state and logs
├── CLAUDE.md            # Scaffold constitution and harness rules
└── README.md
```

## Getting Started

The site deploys automatically to GitHub Pages on push to `main`. No build step is required — the content is static HTML, CSS, and JavaScript.

To run a workflow manually, go to **Actions** and trigger any `workflow_dispatch`-enabled workflow.

## License

This project is open source. See the repository for details.
