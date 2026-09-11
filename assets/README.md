# Assets

Images and recordings used by the repository README.

This directory is currently a **specification, not a library**. The files below do not exist yet — they need to be captured from the real product. No placeholder or mocked-up screenshots are committed here, because a fabricated product screenshot in a public repository is a claim about a product that does not match what users will see.

Once a real asset is supplied, drop it in this directory and embed it in the [main README](../README.md).

## What we need

### Demo 1 — Completed candidates

**Prompt to capture**

```text
Show me the candidates who completed the interview.
```

**Filename** — `completed-candidates.gif`

Show the prompt being typed and the list of completed candidates coming back. This is the first thing a new user tries, so it is the most valuable asset on the list.

### Demo 2 — Top candidates

**Prompt to capture**

```text
Show me the top 10 candidates by interview score.
```

**Filename** — `top-candidates.gif`

Show the ranked list. This is the clearest single demonstration of why connecting real pipeline data matters.

### Demo 3 — Score filter

**Prompt to capture**

```text
Show me candidates with an interview score of 70 or above.
```

**Filename** — `score-filter.gif`

Show a large pool being narrowed by a threshold.

### Demo 4 — Connection setup

**Filename** — `mcp-setup.png`

A screenshot of InterviewFlowAI connected in an MCP client — the Claude Desktop connector screen or the Claude Code `/mcp` panel showing InterviewFlowAI as connected. This is the "it actually works" proof that belongs next to the setup instructions.

## Capture guidelines

**Use real data from a demo workspace, never a customer workspace.** Every candidate name, email address, score, and role visible in a recording is published permanently the moment the repository is public, and a GIF cannot be partially redacted after the fact.

- **Use fictional candidates** in a dedicated demo workspace. Do not blur real names — set up fake ones.
- **Check the whole frame**, not just the conversation: browser tabs, bookmarks, notification banners, the window title, and anything in the sidebar.
- **Check for tokens.** Never record a screen that shows an OAuth token, an API key, or a configuration file containing credentials.

**Format**

- GIFs: 12–18 seconds, silent, looping. Show the prompt and the answer — nothing else.
- Width: 1200–1600px, so the text stays readable on GitHub without a click.
- Keep files under a few MB. A README that takes ten seconds to load is a README people leave.
- PNGs: crop tightly to the relevant UI.

**Accessibility**

Every asset needs descriptive alt text when it is embedded. `![Claude returning a list of candidates who completed their interview, ranked by score](assets/top-candidates.gif)` — not `![demo](assets/top-candidates.gif)`.
