# Recruiting workflows

Practical, end-to-end ways recruiting teams use InterviewFlowAI MCP. Each workflow gives you a goal, a prompt to start from, what InterviewFlowAI MCP actually does, and the human step that follows.

Every workflow ends with a person. InterviewFlowAI MCP finds, surfaces, and organizes candidate information — it does not decide who advances.

---

## 1. Morning candidate review

**Goal**
Start the day knowing exactly who is ready to be looked at, without filtering a dashboard.

**Example prompt**

```text
Show me the candidates who completed the interview this week, with their scores.
```

**What InterviewFlowAI MCP does**
Retrieves the candidates in your workspace who have finished an interview, along with supported interview information including score, and returns them as a list your assistant can sort and group.

**Human review / next step**
Skim the list and pick the handful worth real attention. Follow up with `Summarize this candidate's interview.` on anyone you are unsure about. You decide who gets your time.

---

## 2. High-score review

**Goal**
Cut a large pool down to the group that clears a bar you set.

**Example prompt**

```text
Show me candidates with an interview score of 70 or above.
```

**What InterviewFlowAI MCP does**
Returns the candidates meeting the threshold, drawn from supported interview information in your workspace.

**Human review / next step**
A score threshold is a triage tool, not a verdict. Read the interviews behind the top results before you treat the number as meaningful, and check what a cut-off at your threshold excluded — the boundary is where a score is least reliable.

---

## 3. Shortlist preparation

**Goal**
Hand a hiring manager a ranked shortlist with the evidence attached.

**Example prompt**

```text
Show me the top 10 candidates by interview score, then summarize each one's interview in two sentences.
```

**What InterviewFlowAI MCP does**
Retrieves the ranked candidates, then pulls the supported interview information for each so your assistant can write the summaries from the real interview rather than from the score alone.

**Human review / next step**
Read each summary against the interview before it goes out. Add your own read on fit — that is the part the assistant cannot supply. Then share the shortlist with the hiring manager.

---

## 4. Candidate interview review before a call

**Goal**
Walk into a screening call or debrief with the substance of the interview, not just a number.

**Example prompt**

```text
Summarize this candidate's interview, then suggest three follow-up questions for a live call.
```

**What InterviewFlowAI MCP does**
Retrieves the candidate's supported interview information and candidate record, giving the assistant the context to summarize and to suggest follow-ups grounded in what the candidate actually said.

**Human review / next step**
Use the summary as preparation, not as a substitute for the interview. Open the full record in InterviewFlowAI for anything that will affect a decision.

---

## 5. Comparing two finalists

**Goal**
Make a side-by-side comparison from evidence rather than from memory of two calls last week.

**Example prompt**

```text
Compare these two candidates on their interview performance. Where does each one look stronger?
```

**What InterviewFlowAI MCP does**
Retrieves supported candidate and interview information for both, so your assistant can put them side by side on the same dimensions.

**Human review / next step**
A comparison is an input to a hiring conversation, not the outcome of one. Take it into the debrief and let the panel weigh it against everything the interview did not capture.

---

## 6. Recruiting operations — keeping records current

**Goal**
Update candidate records from inside your assistant instead of switching tabs to do data entry.

**Requires** the `mcp:write` scope and a workspace **Owner** role.

**Example prompt**

```text
Add a note to this candidate: strong on stakeholder examples, needs a technical follow-up.
Show me the note before you save it.
```

**What InterviewFlowAI MCP does**
Applies a supported update to the candidate record — notes, custom fields, visibility, or archived status. Nothing outside those four is writable.

**Human review / next step**
Confirm every change before it is applied; "show me the change first" belongs in every write prompt. Be especially careful with anything that touches multiple candidates at once — ask for the list before the change, not after.

---

## 7. End-of-week pipeline cleanup

**Goal**
Close out the week with a pipeline that reflects reality.

**Requires** the `mcp:write` scope and a workspace **Owner** role for the archiving step.

**Example prompt**

```text
List the candidates who never completed their interview. Then archive them — show me the list first.
```

**What InterviewFlowAI MCP does**
Retrieves candidates by completion status, then applies the archived status to the ones you approve.

**Human review / next step**
Review the list properly before approving. An incomplete interview is not always a disengaged candidate — a technical failure or a timing problem looks identical from the data. When in doubt, leave them and follow up.

---

## Where the line sits

These workflows are built on a deliberate split:

- **The assistant does the retrieval and the first pass** — finding, filtering, ranking, summarizing, comparing.
- **You do the judgment** — who is worth your time, who moves forward, and what a score actually means for this role.

InterviewFlowAI MCP is built to support that split. There is no supported capability that rejects, advances, or makes a hiring decision, and the write surface is deliberately narrow.

---

## Next

- **[recruiting-prompts.md](recruiting-prompts.md)** — the full prompt library.
- **[Official MCP documentation](https://docs.interviewflowai.com/platform/mcp)** — the authoritative capability list.
- **[AI Agent for Recruiting](https://interviewflowai.com/blog/ai-agent-for-recruiting)** — the broader case for AI agents in a recruiting workflow.
