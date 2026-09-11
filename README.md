# InterviewFlowAI MCP

Connect InterviewFlowAI to Claude, ChatGPT, Codex, and other MCP-compatible AI assistants. Ask about your candidates and interviews in plain language, and perform supported recruiting actions without leaving your AI workflow.

```text
"Show me the candidates who completed the interview."

"Show me the top 10 candidates by interview score."

"Show me candidates with an interview score of 70 or above."
```

Ask a question like that in Claude or Codex, and the answer comes back from your own InterviewFlowAI workspace — not from a spreadsheet you pasted in ten minutes ago.

> **InterviewFlowAI MCP is a hosted remote MCP server.** You do not need to run anything locally, install a package, or manage a server. You connect your AI assistant to `https://api.interviewflowai.com/mcp` and sign in with your InterviewFlowAI account.

- **MCP endpoint** — `https://api.interviewflowai.com/mcp`
- **Documentation** — https://docs.interviewflowai.com/platform/mcp
- **Product page** — https://interviewflowai.com/features/mcp

---

## Why this exists

Recruiting teams already use AI assistants to write outreach, summarize notes, and prep for debriefs. The gap is data: the assistant does not know who applied, who finished an interview, or how anyone scored. So you copy and paste, and the assistant reasons about a stale fragment of your pipeline.

The [Model Context Protocol](https://modelcontextprotocol.io) (MCP) is an open standard that lets AI assistants connect to external systems through a consistent interface. InterviewFlowAI MCP is an MCP server for recruiting: it gives your assistant a supported, permission-aware path to the candidate and interview data already in your InterviewFlowAI workspace.

The result is an AI agent for recruiting that answers from live data — a recruiting MCP you can point Claude, ChatGPT, or Codex at.

---

## What can you do with InterviewFlowAI MCP?

With read access (`mcp:read`), a connected assistant can:

- **Find candidates** in your workspace, including by interview completion status.
- **Inspect candidate information** — the supported fields on a Candidate record.
- **Retrieve AI Interviewer information** — list the AI Interviewers configured in your workspace and inspect their details.
- **Review interview information**, including interview scores.
- **Summarize candidate and interview context** so you can read the substance of an interview in seconds instead of scanning a full transcript.

With write access (`mcp:write`, workspace Owners only), a connected assistant can:

- **Update supported candidate fields** — notes, custom fields, visibility, and archived status.

That is the supported surface. InterviewFlowAI MCP does not screen, rank, reject, or advance anyone on its own — it finds, surfaces, and organizes information so a recruiter can decide.

> **A note on tool names.** This repository documents capabilities rather than individual tool names, because the exact tool list is defined by the hosted server and can change between releases. Your assistant discovers the current tools automatically when it connects. See the [official documentation](https://docs.interviewflowai.com/platform/mcp) for the authoritative capability list.

---

## Example prompts

### Find completed interviews

```text
Show me the candidates who completed the interview.
```

### Find top candidates

```text
Show me the top 10 candidates by interview score.
```

### Filter by score

```text
Show me candidates with an interview score of 70 or above.
```

### Going further

Those three are deliberately simple. In practice you can ask for the retrieval and the thinking together, and this is where a connected assistant starts to save you real time:

```text
Who are my top candidates for the Senior PM role, and where did each of them shine?
```

```text
Compare our top two finalists on communication and problem-solving, and draft a quick summary for the hiring manager.
```

The assistant finds the candidates, reads the interviews behind them, and answers the question you actually had — rather than handing you a list to go read yourself.

A larger, categorized set lives in **[examples/recruiting-prompts.md](examples/recruiting-prompts.md)**, and end-to-end recruiting workflows in **[examples/workflows.md](examples/workflows.md)**.

---

## How it works

```text
Recruiter
   │
   ▼
Claude / ChatGPT / Codex / MCP client
   │
   ▼
InterviewFlowAI MCP
   │
   ▼
InterviewFlowAI
   │
   ▼
Candidates + Interviews
```

In plain terms:

1. **InterviewFlowAI hosts the remote MCP server.** It runs at `https://api.interviewflowai.com/mcp`. Nothing to install or operate.
2. **Your AI assistant connects to it using MCP.** Any MCP-compatible client can speak to it over the Streamable HTTP transport.
3. **You sign in with your InterviewFlowAI account.** That sign-in is what tells the server which workspace you are in and what you are allowed to do.
4. **The assistant calls supported InterviewFlowAI tools** on your behalf, and answers your question using what comes back.

Your assistant never gets blanket access to InterviewFlowAI. It gets exactly the access your own account has, and only through the supported tools the server exposes.

---

## MCP endpoint

```text
https://api.interviewflowai.com/mcp
```

| | |
|---|---|
| Transport | Streamable HTTP |
| Authentication | OAuth 2.1, using your InterviewFlowAI account |
| Scopes | `mcp:read`, `mcp:write` |
| Hosting | Hosted by InterviewFlowAI — no local install |

The server implements standard MCP OAuth discovery, so most clients need nothing beyond the URL: they find the authorization server themselves and walk you through sign-in in your browser.

---

## Connect InterviewFlowAI to your AI assistant

Pick your client below. In every case the only value you need is the endpoint URL, and authentication happens in your browser.

> Setup steps for MCP clients change frequently. The commands below follow each vendor's current documentation, but if a client has changed its syntax, that vendor's own MCP documentation is the source of truth.

### Claude Code

```bash
claude mcp add --transport http interviewflowai https://api.interviewflowai.com/mcp
```

Then authenticate:

```text
/mcp
```

Select **interviewflowai** and complete the browser sign-in. To make the server available across all your projects rather than just the current one, add `--scope user`.

Reference: [Claude Code MCP documentation](https://code.claude.com/docs/en/mcp)

### Claude Desktop

1. Open **Settings → Connectors**.
2. Choose **Add custom connector**.
3. Enter a name (for example, `InterviewFlowAI`) and the URL `https://api.interviewflowai.com/mcp`.
4. Save, then click **Connect** and sign in with your InterviewFlowAI account.

### Codex CLI

Add the server to `~/.codex/config.toml`:

```toml
[mcp_servers.interviewflowai]
url = "https://api.interviewflowai.com/mcp"
```

Then authenticate:

```bash
codex mcp login interviewflowai
```

Reference: [Codex MCP documentation](https://developers.openai.com/codex/mcp)

### Codex IDE extension and desktop app

Open **Settings → MCP servers → Add server**, choose **Streamable HTTP**, enter `https://api.interviewflowai.com/mcp`, and complete the sign-in. Codex IDE and desktop read the same `~/.codex/config.toml`, so a server added through the CLI shows up there too. Restart the application after adding it.

### ChatGPT

InterviewFlowAI can be added to ChatGPT as a custom connector using the same endpoint URL. Connector availability depends on your ChatGPT plan and workspace settings — see the [InterviewFlowAI MCP documentation](https://docs.interviewflowai.com/platform/mcp) for current setup steps.

### Other MCP-compatible clients

Any client that supports remote MCP servers over Streamable HTTP with OAuth can connect. Point it at:

```text
https://api.interviewflowai.com/mcp
```

Most clients will discover the authorization server automatically and prompt you to sign in.

---

## Authentication

You authenticate with **your own InterviewFlowAI account**, using the same email address you sign in to InterviewFlowAI with. Authentication uses OAuth 2.1 through InterviewFlowAI's identity provider, and the sign-in happens in your browser — you do not paste an API key into your AI client, and your password is never handled by the client.

Your session determines two things:

- **Which workspace** the assistant can see. You get your company's workspace, and nothing else.
- **What the assistant may do** in it, based on your role.

Access is expressed as two OAuth scopes:

| Scope | What it grants |
|---|---|
| `mcp:read` | List and inspect AI Interviewers and Candidates, and review supported interview information. |
| `mcp:write` | Update supported candidate fields. Available to workspace **Owners** only. |

If you only ever want to ask questions, connect with `mcp:read` alone. Read-only is a sound place to start, and you can add write access later.

**Never share credentials with anyone, and never paste tokens into a public GitHub issue, a shared document, or a chat with an untrusted party.** If you believe a token has been exposed, see [SECURITY.md](SECURITY.md).

---

## Permissions

| Capability | Read | Write |
|---|:--:|:--:|
| List and inspect supported Candidates | ✓ | |
| List and inspect supported AI Interviewers | ✓ | |
| Review supported interview information and scores | ✓ | |
| Summarize supported candidate and interview context | ✓ | |
| Update candidate notes | | ✓ |
| Update candidate custom fields | | ✓ |
| Update candidate visibility | | ✓ |
| Update candidate archived status | | ✓ |

### Roles

- **Owner** — full access, including the write capabilities above.
- **Viewer** — read-only. Write tools are not exposed to Viewers at all, so a Viewer's assistant cannot change candidate data even if asked to.

An assistant can never exceed the permissions of the person who signed in. If you cannot do something in InterviewFlowAI, your assistant cannot do it either.

### Working safely with write access

- **Review every write before it happens.** Ask the assistant to show you the change first, then approve it.
- **Start read-only.** Get comfortable with the answers before you let anything change records.
- **Keep decisions with people.** Use MCP to find, review, and organize candidate information — not to decide who advances. Hiring decisions are made by your team.

---

## Examples

| | |
|---|---|
| **[examples/recruiting-prompts.md](examples/recruiting-prompts.md)** | A categorized prompt library — candidate discovery, interview completion, scoring, review, summaries, operations, and notes. |
| **[examples/workflows.md](examples/workflows.md)** | End-to-end recruiting workflows, each with a goal, prompt, what MCP does, and the human review step. |
| **[examples/README.md](examples/README.md)** | How to use these examples once you are connected. |

---

## Frequently asked questions

**Do I need to run or host anything?**
No. InterviewFlowAI MCP is a hosted remote MCP server. You connect your client to the endpoint and sign in.

**Is this an open-source MCP server?**
No. This repository holds documentation, examples, and configuration resources. The InterviewFlowAI MCP service itself is a hosted InterviewFlowAI product and its implementation is not published here.

**Can my assistant see other companies' candidates?**
No. Your session is scoped to your own InterviewFlowAI workspace.

**Can it reject or advance candidates automatically?**
No. The supported write capabilities cover candidate notes, custom fields, visibility, and archived status. Screening and hiring decisions stay with your team.

**Which AI assistants are supported?**
Claude (Code and Desktop), ChatGPT, and Codex (CLI, IDE, and desktop), plus other MCP-compatible clients that support remote servers with OAuth.

**Something is missing or wrong in these docs.**
Open an issue — see [Contributing](#contributing) below.

---

## Get started

**Connect InterviewFlowAI MCP**
→ [Official MCP documentation](https://docs.interviewflowai.com/platform/mcp)

**Learn about InterviewFlowAI MCP**
→ [MCP product page](https://interviewflowai.com/features/mcp)

**Learn how AI agents can be used in recruiting**
→ [AI Agent for Recruiting](https://interviewflowai.com/blog/ai-agent-for-recruiting)

**Learn about InterviewFlowAI**
→ [interviewflowai.com](https://interviewflowai.com)

---

## Contributing

Issues are welcome for documentation corrections, unclear setup steps, and MCP capability requests.

> **Do not include candidate information, customer data, personal data, authentication tokens, or any other credentials in a public issue.** Issues in this repository are visible to everyone on the internet. Describe the problem in general terms and redact identifiers.

For security issues, do **not** open a public issue — follow [SECURITY.md](SECURITY.md) instead.

---

## License

The contents of this repository — documentation, examples, and configuration resources — are released under the [MIT License](LICENSE).

> The InterviewFlowAI MCP service itself is a hosted InterviewFlowAI product. This repository provides documentation, examples, and configuration resources and does not contain the proprietary server implementation.

The MIT license applies to the files in this repository only. It does not apply to the hosted InterviewFlowAI MCP service, the InterviewFlowAI platform, or the InterviewFlowAI name and logo. Use of the hosted service is governed by your agreement with InterviewFlowAI.
