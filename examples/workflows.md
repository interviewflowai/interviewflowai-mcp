# Recruiting workflows

Practical, end-to-end ways recruiting teams use InterviewFlowAI MCP. Each workflow gives you a goal, a prompt to start from, what InterviewFlowAI MCP actually does, and the human step that follows.

Every workflow ends with a person. InterviewFlowAI MCP finds, surfaces, and organizes candidate information, and it carries out the actions you approve — it does not decide who advances.

Workflows marked **Owner** change data or email candidates. They need a workspace Owner role, and each change runs only after you confirm its preview.

---

## 1. Morning candidate review

**Goal**
Start the day knowing exactly who is ready to be looked at, without filtering a dashboard.

**Example prompt**

```text
Show me the candidates who completed the interview for Senior Engineer this week, with their scores.
```

**What InterviewFlowAI MCP does**
Lists the AI Interviewer's candidates sorted by most recent completion, with interview, resume, and assessment scores, plus whole-pipeline counts by status.

**Human review / next step**
Skim the list and pick the handful worth real attention. Follow up with `Summarize this candidate's interview.` on anyone you are unsure about. You decide who gets your time.

---

## 2. High-score review

**Goal**
Cut a large pool down to the group that clears a bar you set.

**Example prompt**

```text
Show me candidates for Product Designer with an interview score of 70 or above.
```

**What InterviewFlowAI MCP does**
Filters the candidates by score range on the server, so the assistant gets only the ones that clear the bar instead of reading every page.

**Human review / next step**
A score threshold is a triage tool, not a verdict. Read the interviews behind the top results before you treat the number as meaningful, and check what a cut-off at your threshold excluded — the boundary is where a score is least reliable.

---

## 3. Explaining a score

**Goal**
Understand why a candidate scored the way they did before you trust or overrule the number.

**Example prompt**

```text
Why did this candidate get a low resume score? Show me their timeline too.
```

**What InterviewFlowAI MCP does**
Reads the resume screening analysis — score, strengths, gaps, and how the resume matched the job's requirements — and the candidate's timeline of invitations, reminders, stage changes, and interview events.

**Human review / next step**
Decide whether the gaps matter for this role. A resume that misses a keyword is not the same as a candidate who lacks the skill; the interview is often the better evidence.

---

## 4. Shortlist preparation

**Goal**
Hand a hiring manager a ranked shortlist with the evidence attached.

**Owner** for the starring step.

**Example prompt**

```text
Show me the top 10 candidates for Senior PM by interview score and summarize each in two sentences.
Then star the ones I pick and export the starred candidates as a CSV.
```

**What InterviewFlowAI MCP does**
Retrieves the ranked candidates and their interviews so the summaries come from the real interview rather than the score alone. After you pick, it previews the star ratings, applies them once you confirm, and exports the starred candidates to a CSV with a download link.

**Human review / next step**
Read each summary against the interview before it goes out, and add your own read on fit. The export link works for 15 minutes for anyone who has it, so download the file and send that, not the link, to the hiring manager.

---

## 5. Candidate interview review before a call

**Goal**
Walk into a screening call or debrief with the substance of the interview, not just a number.

**Example prompt**

```text
Summarize this candidate's interview, then suggest three follow-up questions for a live call.
```

**What InterviewFlowAI MCP does**
Retrieves the candidate's interview, evaluation, and details, giving the assistant the context to summarize and to suggest follow-ups grounded in what the candidate actually said.

**Human review / next step**
Use the summary as preparation, not as a substitute for the interview. Open the full record in InterviewFlowAI for anything that will affect a decision.

---

## 6. Comparing two finalists

**Goal**
Make a side-by-side comparison from evidence rather than from memory of two calls last week.

**Example prompt**

```text
Compare these two candidates on their interview and role play results. Where does each one look stronger?
```

**What InterviewFlowAI MCP does**
Retrieves both candidates' interviews and graded role play results, so your assistant can put them side by side on the same criteria.

**Human review / next step**
A comparison is an input to a hiring conversation, not the outcome of one. Take it into the debrief and let the panel weigh it against everything the interview did not capture.

---

## 7. Moving candidates through your stages

**Goal**
Keep the pipeline in step with decisions made in a debrief, without clicking through each candidate.

**Owner**

**Example prompt**

```text
Move the starred candidates for Product Designer to the Onsite stage.
```

**What InterviewFlowAI MCP does**
Matches the stage to one of your custom hiring stages, then previews the move: who will be moved, and who will be skipped because they are shortlisted and have a live interview link. It moves them once you confirm.

**Human review / next step**
Check the skipped list. Shortlisted candidates can only be moved in InterviewFlowAI, so finish those by hand.

---

## 8. Chasing incomplete interviews

**Goal**
Get candidates who stalled to finish, before their link runs out.

**Owner**

**Example prompt**

```text
Who hasn't finished their interview for Customer Support Lead? Remind them,
and give Priya and Sam 3 more days.
```

**What InterviewFlowAI MCP does**
Lists the incomplete candidates, then previews two actions: the reminder emails, with anyone reminded in the last 24 hours or unsubscribed marked as skipped, and the new link expiry for each candidate getting more time. Each runs only once you confirm it.

**Human review / next step**
Read the list before you approve the emails. An incomplete interview is not always a disengaged candidate — a technical problem or a timing clash looks the same in the data. For anyone who matters, a personal message beats a reminder.

---

## 9. Inviting a new batch of candidates

**Goal**
Get a list of sourced or referred candidates into an AI Interviewer in one step.

**Owner**

**Example prompt**

```text
Invite these candidates to the Data Analyst interview: Jane Doe jane@example.com, Sam Lee sam@example.com, …
```

**What InterviewFlowAI MCP does**
Previews who will be added and which email they will get — an interview link, or an application link if you ask them to apply first. Once you confirm, it adds them and sends the emails, skipping anyone already in that AI Interviewer.

**Human review / next step**
Check names and email addresses in the preview. An invitation can't be unsent.

---

## 10. Role play follow-up

**Goal**
Test your strongest candidates in a realistic scenario and read the results without leaving your assistant.

**Owner** for the invitation step.

**Example prompt**

```text
Invite the shortlisted candidates for Account Executive to the customer-call role play.
Later: show me their role play results, best first, with strengths and red flags.
```

**What InterviewFlowAI MCP does**
Previews the invitations, including whether the role play is published, and emails each candidate the link once you confirm. An unpublished role play can't be sent. When candidates finish, it reads each graded session: overall score, per-criterion reasoning and evidence, strengths, gaps, and red flags.

**Human review / next step**
Read the evidence behind any red flag before acting on it. Each candidate gets one attempt per role play.

---

## 11. Setting up an AI Interviewer from a job description

**Goal**
Go from a job description to a working AI Interviewer without filling in a form.

**Owner**

**Example prompt**

```text
Draft an AI Interviewer from this job description: …
```

**What InterviewFlowAI MCP does**
Drafts the title, role, description, experience range, and suggested interview questions, each with what a strong and a weak answer look like. Nothing is saved. When you are happy, the assistant previews the AI Interviewer and creates it once you confirm — private, English, as a web interview of about 10 minutes. To start from an existing one instead, ask it to clone that AI Interviewer.

**Human review / next step**
Edit the questions before you create it; they decide what the interview measures. Then open the new AI Interviewer in InterviewFlowAI to adjust any other settings before you invite candidates.

---

## 12. Keeping records current

**Goal**
Update candidate records from inside your assistant instead of switching tabs to do data entry.

**Owner**

**Example prompt**

```text
Add to this candidate's notes: strong on stakeholder examples, needs a technical follow-up.
Show me the note before you save it.
```

**What InterviewFlowAI MCP does**
Previews the new notes or custom field values and saves them once you confirm. Saving notes replaces the existing notes, so ask the assistant to keep what is already there.

**Human review / next step**
Read the preview, especially for notes the assistant drafted. A note is something a colleague will act on later.

---

## Where the line sits

These workflows are built on a deliberate split:

- **The assistant does the retrieval, the first pass, and the legwork** — finding, filtering, ranking, summarizing, comparing, and carrying out the actions you approve.
- **You do the judgment** — who is worth your time, who moves forward, and what a score actually means for this role.

InterviewFlowAI MCP is built to support that split. Every change and every email to a candidate starts as a preview for you to confirm, and nothing about a candidate is decided automatically.

---

## Next

- **[recruiting-prompts.md](recruiting-prompts.md)** — the full prompt library.
- **[Official MCP documentation](https://docs.interviewflowai.com/platform/mcp)** — the authoritative capability list.
- **[AI Agent for Recruiting](https://interviewflowai.com/blog/ai-agent-for-recruiting)** — the broader case for AI agents in a recruiting workflow.
