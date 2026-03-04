# Use Case: Automated Code Review

With OpenClaw deeply integrated into the `akurata-cluster` organization, you can offload routine and preliminary code reviews to a sub-agent.

## Setup

1. **GitHub Skill:** Ensure the `github` skill is installed and authenticated (completed).
2. **Heartbeat:** Configure a periodic check in `HEARTBEAT.md` to look for new pull requests.
3. **SOUL Directives:** Set strict review boundaries (e.g., "Always prioritize performance and scalability over readability").

## Execution Flow

1. **Trigger:** `HEARTBEAT.md` polls the `akurata-cluster` repositories for open PRs requiring review every few hours.
2. **Analysis:** When a PR is found, the main agent spawns a background session (`runtime="acp"`) to analyze the diffs and commit messages.
3. **Action:** The sub-agent uses the `gh` CLI to leave structured, technical feedback inline on the PR, or simply summarizes the architectural impact in a single comment.
4. **Notification:** If critical issues are found, the agent uses the `slack` or `discord` skill to alert you directly.
