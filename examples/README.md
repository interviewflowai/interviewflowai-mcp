# Examples

Copy-and-paste material for using InterviewFlowAI with your AI assistant.

| File | What's in it |
|---|---|
| **[recruiting-prompts.md](recruiting-prompts.md)** | A categorized prompt library: candidate discovery, interview completion, scoring, review, summaries, multi-step questions, role plays, AI Interviewers, exports, pipeline actions, and notes. |
| **[workflows.md](workflows.md)** | Twelve end-to-end recruiting workflows, each with a goal, a prompt, what MCP does, and the human review step. |

## How to use these

1. **Connect InterviewFlowAI to your assistant first.** Follow the setup steps in the [main README](../README.md#connect-interviewflowai-to-your-ai-assistant). You need a working connection before any of these prompts will do anything.
2. **Copy a prompt and paste it into your assistant.** Claude, ChatGPT, Codex, Cursor, VS Code, OpenCode — anything with the connection configured.
3. **Adjust the wording freely.** These are not commands with a fixed syntax. The assistant interprets intent, so rephrase to match how you actually talk about your pipeline, and substitute your own AI Interviewers, stages, scores, and thresholds.
4. **Start with a read-only prompt.** `List my AI Interviewers.` is the fastest way to confirm the connection works. If your AI Interviewers come back, you are connected.

## Before you use an Owner prompt

Prompts marked **Owner only** change data or email candidates. They need a workspace Owner role; a Viewer's assistant does not have these tools at all.

- Your assistant shows you a preview of every change — who is affected, and who will be skipped and why. Read it before you confirm.
- Be most careful with prompts that touch or email several candidates at once. An email can't be unsent.
- Hiring decisions stay with your team. These examples help you find and review candidates and carry out what you have decided, not decide who advances.

## Need something that isn't here?

If there is a recruiting task you want to do through MCP and no prompt here covers it, open an issue describing what you're trying to accomplish.

**Do not include candidate names, customer data, or any other personal data in a public issue.** Describe the task in general terms.
