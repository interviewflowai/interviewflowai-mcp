# Security Policy

InterviewFlowAI MCP handles candidate and interview data. We take reports about it seriously, and we would rather hear about a problem early than read about it later.

## Reporting a vulnerability

**Do not report security vulnerabilities through public GitHub issues, pull requests, or discussions.** A public issue tells everyone about the problem, including people who would misuse it, before there is a fix.

Report privately through one of these channels:

- **GitHub private vulnerability reporting** — use the **Report a vulnerability** button on the [Security tab](../../security/advisories/new) of this repository. This is the preferred route: it stays private and keeps the whole discussion in one place.
- **InterviewFlowAI contact channels** — reach the team through https://interviewflowai.com/contact and state that your message is a security report so it is routed appropriately.

Please include:

- a description of the issue and why you believe it is a security problem;
- the steps to reproduce it;
- the affected component — for example, the MCP endpoint, an MCP client configuration, or documentation in this repository;
- the impact you think it has.

## What to expect

We aim to acknowledge reports within a few business days and will keep you updated as we investigate. Please give us a reasonable opportunity to fix an issue before disclosing it publicly.

## Please do not include sensitive data in reports

Security reports should demonstrate a problem, not carry a copy of the data at risk.

- **Do not include candidate data, customer data, or any personal data.** Redact names, email addresses, phone numbers, resumes, and interview content. Describe the shape of the data you could reach instead of pasting it.
- **Do not include authentication tokens, API keys, OAuth credentials, session cookies, or passwords** — not in an issue, not in a pull request, not in a screenshot, and not in a log file attachment.
- **Screenshots and HAR files leak more than people expect.** Check them for tokens and candidate information before attaching.

## If a credential has been exposed

Treat any credential that has appeared somewhere public as compromised, even briefly, even in a deleted comment.

1. **Revoke it immediately.** Deleting the message is not enough — content is cached, indexed, and mirrored within seconds.
2. **Disconnect the affected MCP connection.** In InterviewFlowAI, open **Settings → Connected apps** and click **Disconnect** next to the assistant; it loses access immediately. For an exposed API key, delete the key under **Settings → API Keys**. Then reconnect to obtain a fresh session.
3. **Tell us**, through the private channels above, so we can help check for misuse.
4. **Rotate anything related.** If one credential was exposed through a given path, assume others on the same path were too.

## Scope

This repository contains documentation, examples, and configuration resources.

- **Issues in this repository** — incorrect or unsafe setup instructions, documentation that would lead someone to expose a credential, or problems with the files published here. Report them as described above.
- **Issues in the hosted InterviewFlowAI MCP service or the InterviewFlowAI platform** — report them through the private channels above as well. The service implementation is not published in this repository, but the report reaches the same team.

We especially want to hear about any way to reach another company's data, to act with more access than your role allows, to make a change without a preview, or to get an assistant to act on instructions planted in candidate data.

## Good practice for users

- Authenticate through the browser sign-in flow rather than pasting credentials into a client configuration file. AI assistants don't need an API key.
- Only click **Allow access** on the InterviewFlowAI consent screen if you started the connection from your own assistant.
- Treat an API key like an Owner's password: it can use every write tool. Keep it out of shared configuration files and AI chats, never commit a configuration file containing a token or API key to a repository, and delete keys you no longer need.
- Read the preview of every change before you confirm it, especially actions that email candidates or touch many of them. Confirm only changes you asked for.
- Keep your AI client's approval prompt on for InterviewFlowAI tools that change data or email candidates.
- Treat candidate content (resumes, interview answers, notes) as untrusted: it can contain instructions written for an AI assistant. Be careful combining InterviewFlowAI with tools that can send data outside your company in the same conversation.
- Treat candidate export links as sensitive: for 15 minutes, they work for anyone who has the link.
- Review **Settings → Connected apps** from time to time, and disconnect any assistant or device you no longer use or control.
