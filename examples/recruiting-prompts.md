# Recruiting prompt library

Prompts you can copy into Claude, ChatGPT, Codex, or any other MCP-compatible assistant once InterviewFlowAI MCP is connected.

Every prompt here maps to a documented InterviewFlowAI MCP capability. Prompts marked **Owner only** need the `mcp:write` scope and a workspace Owner role — see [Permissions](../README.md#permissions).

Write prompts in your own words. These are starting points, not commands with a fixed syntax; the assistant interprets intent, so "who finished their interview?" works as well as the phrasing below.

> New to this? Start with [Candidate discovery](#candidate-discovery) and [Interview completion](#interview-completion). They are read-only, they answer immediately, and they tell you straight away whether the connection is working.

---

## Candidate discovery

Find the people in your pipeline without filtering a dashboard first.

```text
Show me the candidates in my workspace.
```

```text
Which candidates have applied for the Customer Support Lead role?
```

```text
Show me the candidates who have not completed their interview yet.
```

```text
How many candidates do we have in total right now?
```

---

## Interview completion

Separate the pipeline into "ready to review" and "still waiting."

```text
Show me the candidates who completed the interview.
```

```text
Which candidates completed an interview this week?
```

```text
Show me everyone who started an interview but did not finish it.
```

---

## Candidate scoring

Turn a large pool into a short list worth your attention.

```text
Show me the top 10 candidates by interview score.
```

```text
Show me candidates with an interview score of 70 or above.
```

```text
Rank the candidates who completed the interview by score, highest first.
```

```text
What is the score distribution across candidates who completed the interview?
```

---

## Candidate review

Get the detail on one person before you spend time on them.

```text
Show me everything you have on this candidate.
```

```text
What was this candidate's interview score, and what drove it?
```

```text
Compare these two candidates on their interview performance.
```

```text
Which of the top-scoring candidates should I look at first, and why?
```

---

## Interview summaries

Read the substance of an interview in seconds rather than scanning a transcript.

```text
Summarize this candidate's interview.
```

```text
Summarize the interviews for the top 5 candidates, one short paragraph each.
```

```text
What are the main strengths and gaps in this candidate's interview?
```

```text
What follow-up questions should I ask this candidate in a live call?
```

---

## AI Interviewers

Check what is actually configured in your workspace.

```text
List the AI Interviewers in my workspace.
```

```text
Show me the details of the AI Interviewer used for the Support Lead role.
```

```text
Which AI Interviewer did this candidate go through?
```

---

## Recruiting operations

**Owner only.** These change candidate records. Ask the assistant to show you the change before it applies it.

```text
Add a note to this candidate: strong on stakeholder examples, needs a technical follow-up.
```

```text
Update this candidate's custom field "Stage" to "Hiring manager review".
```

```text
Archive the candidates who did not complete their interview — show me the list first.
```

```text
Change this candidate's visibility so the hiring manager can see them.
```

---

## Candidate notes

**Owner only.** Notes are the lightest-weight way to keep a record current from inside your assistant.

```text
Add a note to this candidate summarizing what we discussed on today's call.
```

```text
Based on this candidate's interview summary, draft a note for the hiring manager — show it to me before you save it.
```

```text
Add a note to each of the top 3 candidates saying they have been shortlisted for a hiring manager review. List the changes before making them.
```

---

## Working safely

- **Confirm every write.** Add "show me the change first" to any prompt that updates a record.
- **Watch out for bulk changes.** A prompt that touches many candidates at once is the one worth reviewing most carefully.
- **Verify what matters.** Open the candidate in InterviewFlowAI before you act on a summary in a high-stakes decision.
- **Keep the decision human.** Use these prompts to find and review candidates. Deciding who advances is your team's job — see [InterviewFlowAI MCP](https://interviewflowai.com/features/mcp) for more on where the line sits.

---

## Next

- **[workflows.md](workflows.md)** — these prompts assembled into end-to-end recruiting workflows.
- **[Official MCP documentation](https://docs.interviewflowai.com/platform/mcp)** — the authoritative capability list.
