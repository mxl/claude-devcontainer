# Claude Devcontainer

A sandboxed development container for running [Claude Code](https://code.claude.com) with network isolation via firewall rules.

## Requirements

- [Docker](https://www.docker.com/)
- [Dev Container CLI](https://github.com/devcontainers/cli): `npm install -g @devcontainers/cli`

## Usage

Source the included shell script to get a `claude` command that starts the devcontainer and launches Claude in one step:

```bash
# Add to your ~/.zshrc or ~/.bashrc
source /path/to/claude.sh

# Run from any project directory
cd ~/my-project
claude

# Pass additional Claude flags
claude --dangerously-skip-permissions
```

The workspace is automatically inferred from your current directory.

## What's inside

- **Node 20** base image with zsh, git, fzf, gh, and common dev tools
- **Claude** installed via the native installer (`curl -fsSL https://claude.ai/install.sh | bash`)
- **Firewall** (`init-firewall.sh`) that restricts outbound traffic to an allowlist:
  - GitHub
  - npm registry
  - Anthropic API
  - Sentry, Statsig, VS Code marketplace
