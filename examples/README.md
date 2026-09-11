# Examples

Copy-and-paste material for using InterviewFlowAI with your AI assistant.

| File | What's in it |
|---|---|
| **[recruiting-prompts.md](recruiting-prompts.md)** | A categorized prompt library: candidate discovery, interview completion, scoring, review, summaries, AI Interviewers, operations, and notes. |
| **[workflows.md](workflows.md)** | Seven end-to-end recruiting workflows, each with a goal, a prompt, what MCP does, and the human review step. |

## How to use these

1. **Connect InterviewFlowAI to your assistant first.** Follow the setup steps in the [main README](../README.md#connect-interviewflowai-to-your-ai-assistant). You need a working connection before any of these prompts will do anything.
2. **Copy a prompt and paste it into your assistant.** Claude, ChatGPT, Codex — anything with the connection configured.
3. **Adjust the wording freely.** These are not commands with a fixed syntax. The assistant interprets intent, so rephrase to match how you actually talk about your pipeline, and substitute your own roles, scores, and thresholds.
4. **Start with a read-only prompt.** `Show me the candidates who completed the interview.` is the fastest way to confirm the connection works. If candidates come back, you are connected.

## Before you use a write prompt

Prompts marked **Owner only** change candidate records. They need the `mcp:write` scope and a workspace Owner role.

- Add **"show me the change first"** to any write prompt, and read what comes back before approving.
- Be most careful with prompts that touch several candidates at once.
- Hiring decisions stay with your team. These examples help you find and review candidates, not decide who advances.

## Need something that isn't here?

If there is a recruiting task you want to do through MCP and no prompt here covers it, open an issue describing what you're trying to accomplish.

**Do not include candidate names, customer data, or any other personal data in a public issue.** Describe the task in general terms.
