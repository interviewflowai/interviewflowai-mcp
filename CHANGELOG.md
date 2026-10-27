# Changelog

All notable changes to this repository are documented here.

This changelog covers the **documentation, examples, and configuration resources in this repository**. It is not a changelog for the hosted InterviewFlowAI MCP service or the InterviewFlowAI platform — see the [official documentation](https://docs.interviewflowai.com/platform/mcp) for those.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.1.0] - 2026-10-27

Brings this repository in line with version 1.1.0 of the hosted server.

### Added

- Setup instructions for claude.ai, Cursor, VS Code, and OpenCode, and the `codex mcp add` command for Codex.
- The agent setup prompt from **Settings → MCP and AI**, which a coding agent can follow to add the server and start sign-in.
- A tool reference in the README: 12 read tools for every signed-in user, and 12 Owner tools.
- Documentation of the new capabilities: resume feedback, candidate timelines, hiring stages, CSV exports, role plays and their graded results, starring candidates, moving them between stages, reminders, invitations, link extensions, role play invitations, and drafting, creating, and cloning AI Interviewers.
- How changes are confirmed: every change and every email to a candidate returns a preview and a one-time confirmation code first, and why your AI client's approval prompt should stay on as a second check.
- Guidance on untrusted candidate content and prompt injection, a note for AI agents that read this repository, and what to report under `SECURITY.md`.
- Limits and rules for each action, a troubleshooting table, and how to disconnect an assistant from **Settings → Connected apps**.
- How to connect a script with an API key, and that an API key acts as the Owner who created it.
- Prompt library sections for role plays, AI Interviewers, exports, and pipeline actions, and five new workflows.
- More MCP clients in the bug report template.

### Changed

- Access now comes from your InterviewFlowAI role — Owners read and write, Viewers read — instead of OAuth scopes chosen in the client. The scopes table and the advice to connect with `mcp:read` alone are removed.
- Visibility and archived status now apply to AI Interviewers, not candidates.
- `server.json` is version 1.1.0, with a description that covers the new actions.
- Security guidance covers connected apps, API keys, and export links.
- Export links are documented as working for 15 minutes, with the file deleted after an hour.

### Removed

- Prompts and the pipeline cleanup workflow for archiving candidates or changing their visibility, which the server no longer supports.

## [1.0.0] - 2026-09-11

### Added

- Initial public release of the InterviewFlowAI MCP repository.
- README covering capabilities, the hosted MCP endpoint, how it works, authentication, and the permissions model.
- Setup instructions for Claude Code, Claude Desktop, Codex CLI, Codex IDE and desktop, ChatGPT, and other MCP-compatible clients.
- Recruiting prompt library in `examples/recruiting-prompts.md`, organized by task.
- Multi-step prompt examples that combine retrieval, comparison, and drafting in a single question.
- End-to-end recruiting workflows in `examples/workflows.md`.
- MCP Registry metadata in `server.json`, declaring the hosted server as a Streamable HTTP remote.
- Published to the official MCP Registry as `com.interviewflowai/mcp` version 1.0.0, under the domain-verified `com.interviewflowai` namespace.
- Security policy in `SECURITY.md`.
- MIT license covering this repository's documentation and examples.
- Asset requirements in `assets/README.md` for the demo recordings referenced by the README.
