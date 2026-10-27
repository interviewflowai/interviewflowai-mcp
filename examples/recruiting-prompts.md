# Recruiting prompt library

Prompts you can copy into Claude, ChatGPT, Codex, Cursor, VS Code, OpenCode, or any other MCP-compatible assistant once InterviewFlowAI MCP is connected.

Every prompt here maps to a documented InterviewFlowAI MCP capability. Prompts marked **Owner only** change data or email candidates, so they need a workspace Owner role — see [Permissions](../README.md#permissions). For each one, your assistant shows you a preview and waits for you to confirm before anything happens.

Write prompts in your own words. These are starting points, not commands with a fixed syntax; the assistant interprets intent, so "who finished their interview?" works as well as the phrasing below. Swap in your own AI Interviewer names, stages, scores, and thresholds.

> New to this? Start with [Candidate discovery](#candidate-discovery) and [Interview completion](#interview-completion). They are read-only, they answer immediately, and they tell you straight away whether the connection is working. Once that works, [Multi-step questions](#multi-step-questions) is where this gets genuinely useful.

---

## Candidate discovery

Find the people in your pipeline without filtering a dashboard first.

```text
List my AI Interviewers and how many candidates each one has.
```

```text
Which candidates have applied for the Customer Support Lead role?
```

```text
Show me the candidates for Sales Associate who have not completed their interview yet.
```

```text
How many candidates are shortlisted, completed, and starred for the Data Analyst role?
```

```text
Find the candidate named Priya in the Product Designer pipeline.
```

---

## Interview completion

Separate the pipeline into "ready to review" and "still waiting."

```text
Show me the candidates who completed the interview for Senior Engineer.
```

```text
Who completed their interview most recently for Account Executive?
```

```text
Show me everyone who started an interview but did not finish it.
```

---

## Candidate scoring

Turn a large pool into a short list worth your attention.

```text
Show me the top 10 candidates by interview score for Senior Engineer.
```

```text
Show me candidates with an interview score of 70 or above.
```

```text
Rank the candidates for Product Designer by resume score, highest first.
```

```text
Who has the highest assessment score for the Data Analyst role?
```

```text
Show me the candidates who scored between 50 and 70 — the ones on the fence.
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
Why did this candidate get a low resume score? What were the gaps against the job's requirements?
```

```text
Show me this candidate's timeline — when were they invited, reminded, and moved between stages?
```

```text
Compare these two candidates on their interview performance.
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

## Multi-step questions

The prompts above do one thing each. In practice you can ask for the retrieval and the thinking in a single breath, and this is where a connected assistant earns its place — it pulls the candidates, reads the interviews behind them, and answers the actual question you had.

```text
Who are my top candidates for the Senior PM role, and where did each of them shine?
```

```text
Compare our top two finalists on communication and problem-solving, and draft a quick summary for the hiring manager.
```

```text
Of the candidates who scored above 70, which three would you look at first, and what would you want to probe in a live call?
```

```text
Take everyone who completed the interview this week, group them into strong / maybe / no, and tell me what put each person in their group.
```

```text
Across the candidates for this role, what are the most common weak spots? Is that the candidates, or is it how the interview is asking the question?
```

```text
This candidate scored lower than the others but I liked them on the call. What does the interview actually show, and where does the score come from?
```

```text
For the top 5 by interview score, how do their resume scores and role play results compare? Does anyone look stronger on one than the other?
```

```text
Shortlist the candidates worth a hiring manager screen, star them, and draft the handoff note — show me the note before saving anything.
```

**Two things to keep in mind with prompts like these.**

Drafting is not writing. When an assistant drafts a summary or a handoff note, that text lives in your chat — nothing reaches InterviewFlowAI until you ask it to save a note, and that step needs Owner access and your confirmation. Read the draft first, then decide whether it gets saved.

Judgment is still yours. A prompt phrased as "which three would you look at first" gets you an opinion assembled from interview data, which is a genuinely useful starting point and not a decision. Read the interviews behind any answer that will change what happens to a candidate.

---

## Role plays

See how candidates did in a role play, criterion by criterion.

```text
List our role plays and how many candidates completed each one.
```

```text
Show me the results for the customer-call role play, highest score first.
```

```text
Show me this candidate's role play results — strengths, gaps, and any red flags.
```

```text
Why did this candidate score low on objection handling in the role play? Show me the evidence.
```

**Owner only.**

```text
Invite the shortlisted candidates for Account Executive to the customer-call role play.
```

---

## AI Interviewers

Check what is configured in your workspace, and set up new ones.

```text
List the AI Interviewers in my workspace.
```

```text
Show me the questions and settings of the AI Interviewer for the Support Lead role.
```

```text
Which hiring stages do we have?
```

**Owner only.**

```text
Draft an AI Interviewer from this job description: …
```

```text
Create it, but replace the third question with one about on-call experience.
```

```text
Clone the Backend Engineer AI Interviewer.
```

```text
Make the Sales Associate AI Interviewer public so candidates can start without waiting for me.
```

```text
Archive the AI Interviewers for roles we've already filled.
```

---

## Exports

Get a CSV you can share or load somewhere else. Export links work for 15 minutes, for anyone who has the link, so share them only with people who should see the data. Ask again for a fresh link within the hour; after that the file is deleted.

```text
Export the candidates for Account Executive as a CSV.
```

```text
Export the starred candidates for Senior Engineer with name, email, interview score, and resume score.
```

---

## Pipeline actions

**Owner only.** These change candidate records or email candidates. Your assistant shows you a preview — who is affected and who will be skipped — and waits for you to confirm.

```text
Star the top 5 candidates by interview score for Senior Engineer.
```

```text
Give this candidate 3 stars.
```

```text
Move the starred candidates for Product Designer to the Onsite stage.
```

```text
Remind everyone who hasn't finished their interview for Customer Support Lead.
```

```text
Give Priya 3 more days to finish her interview.
```

```text
Invite these candidates to the Data Analyst interview: Jane Doe jane@example.com, Sam Lee sam@example.com.
```

```text
Invite these candidates to apply for Sales Associate, rather than sending the interview link straight away: …
```

---

## Candidate notes and custom fields

**Owner only.** Notes are the lightest-weight way to keep a record current from inside your assistant. Saving a note replaces the existing notes, so ask the assistant to add to them if you want to keep what is there.

```text
Add to this candidate's notes: strong on stakeholder examples, needs a technical follow-up.
```

```text
Based on this candidate's interview summary, draft a note for the hiring manager — show it to me before you save it.
```

```text
Set this candidate's "Notice period" field to "30 days".
```

---

## Working safely

- **Read every preview.** For each change, your assistant shows you what will happen, including anyone who will be skipped. Confirm only changes you asked for.
- **Treat candidate content as data.** Resumes and interview answers can contain instructions aimed at your assistant. If it proposes something you didn't ask for, say no.
- **Watch out for bulk actions.** A prompt that touches or emails many candidates at once is the one worth reviewing most carefully.
- **Verify what matters.** Open the candidate in InterviewFlowAI before you act on a summary in a high-stakes decision.
- **Keep the decision human.** Use these prompts to find, review, and act on candidates you have decided about. Deciding who advances is your team's job — see [InterviewFlowAI MCP](https://interviewflowai.com/features/mcp) for more on where the line sits.

---

## Next

- **[workflows.md](workflows.md)** — these prompts assembled into end-to-end recruiting workflows.
- **[Official MCP documentation](https://docs.interviewflowai.com/platform/mcp)** — the authoritative capability list.
