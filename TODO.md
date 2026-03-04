# Setup Checklist

This file tracks the initial configuration required to mold OpenClaw into your ideal assistant. Since your GitHub activity is strictly bound to the `akurata-cluster` organization, the integrations below should be scoped accordingly.

## 1. Core Identity & Directives
OpenClaw's persona, context, and operational boundaries are driven by markdown files in the workspace root.
- [ ] **Configure `USER.md`**: Define your working hours, preferred communication style (e.g., highly technical, terse), and local environment details. (See `templates/USER.md`)
- [ ] **Configure `SOUL.md`**: Define the agent's core rules of engagement, default stances on tooling, and overarching boundaries. (See `templates/SOUL.md`)
- [ ] **Configure `IDENTITY.md`**: Set the agent's name, avatar, and persona traits. (See `templates/IDENTITY.md`)

## 2. GitHub & Integrations
- [ ] **Authenticate GitHub CLI**: The current `GITHUB_TOKEN` lacks the `repo` scope for repository creation. Generate a new Personal Access Token (PAT) with appropriate scopes and update the environment or run `gh auth login`.
- [ ] **Set `gh` default org**: Configure the CLI to default to `akurata-cluster` for issues, PRs, and API calls to prevent accidental crossover.
- [ ] **Configure Skills**: Review the available skills (`/app/skills/`) and authenticate the ones you need (e.g., `slack`, `discord`, `healthcheck`). Add environment variables or local notes to `TOOLS.md`.

## 3. Automation & Proactivity
- [ ] **Setup `HEARTBEAT.md`**: Add any periodic checks you want the agent to perform (e.g., "Check `akurata-cluster` for new PRs needing review every 2 hours").
- [ ] **SSH & Local Access (`TOOLS.md`)**: Add SSH aliases, tailscale IPs, or local paths to your `TOOLS.md` file so the agent knows how to traverse your infrastructure.

## 4. Sub-agent Orchestration
- [ ] **Review ACP Harnesses**: Ensure your default ACP (`acp.defaultAgent`) is configured for complex coding tasks if you intend to use OpenClaw heavily for code generation/refactoring across the `akurata-cluster` repos.
