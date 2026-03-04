# Use Case: Proactive Technical Research

As an AI engineer with a decade of experience, you're constantly evaluating new frameworks, architectures, and models. OpenClaw can pre-digest new information for you in the background.

## Setup

1. **Web Search & Fetch Skills:** Ensure the `web_search` and `web_fetch` tools are configured (usually enabled by default).
2. **PDF Skill:** Ensure the `pdf` skill is ready for parsing whitepapers and documentation.
3. **Heartbeat:** Configure a periodic check to scour specific domains or RSS feeds for new ML research.

## Execution Flow

1. **Trigger:** You casually mention a new paper, framework, or architecture in the main session.
2. **Action:** The main session spawns a background sub-agent (`runtime="subagent"`) to perform an exhaustive deep-dive without blocking your workflow.
3. **Analysis:** The sub-agent uses `web_search` to find relevant documentation, `web_fetch` to extract the content, and `pdf` to analyze whitepapers.
4. **Deliverable:** It synthesizes a concise, highly technical summary, complete with architectural implications, code snippets, and performance benchmarks, delivering it to the chat or appending it to a dedicated Markdown file.
