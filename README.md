# my-coding-tools

A curated collection of coding tools for AI-assisted development workflows.
Each tool lives under `tools/` as a self-contained directory.

## Tools

### [treehouse](./tools/treehouse)

**Git worktree manager** — a CLI that automates the creation, management, and cleanup
of git worktrees. Useful for running multiple parallel tasks on the same repo
without conflicts. Integrates directly with firstmate for per-task isolation.

- **Repo:** https://github.com/kunchenguid/treehouse
- **Language:** Go

### [firstmate](./tools/firstmate)

**Multi-agent orchestrator** — talks to a single AI agent (the "first mate") and
uses it to spawn and supervise a fleet of autonomous crewmate agents in isolated
tmux windows and git worktrees. Each crewmate handles one task independently;
firstmate coordinates them and surfaces only decisions that need your attention.

- **Repo:** https://github.com/kunchenguid/firstmate
- **Language:** Bash + AGENTS.md prompt

### [no-mistakes](./tools/no-mistakes)

**AI-powered delivery pipeline** — a `git push` hook that runs a structured
review/test/lint pipeline via an AI agent before opening a PR. Enforces a
consistent gate so every PR is properly validated before it reaches the team.

- **Repo:** https://github.com/kunchenguid/no-mistakes
- **Language:** Bash

## Structure

```
my-coding-tools/
├── tools/
│   ├── treehouse/     # git worktree manager
│   ├── firstmate/     # multi-agent orchestrator
│   └── no-mistakes/   # AI delivery pipeline
├── .gitignore
└── README.md
```

## How the tools fit together

These three tools form a coherent AI development workflow:

1. **no-mistakes** gates your PRs so nothing ships without passing review + tests.
2. **treehouse** gives each in-flight task its own isolated git worktree.
3. **firstmate** orchestrates the whole fleet — spawning agents in treehouse
   worktrees, running them through the no-mistakes pipeline, and surfacing
   finished PRs for your review.

## Source

All tools were originally developed by [@kunchenguid](https://github.com/kunchenguid).
This repo consolidates them for personal reference and ease of navigation.
