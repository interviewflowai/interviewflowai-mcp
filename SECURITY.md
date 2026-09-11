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
2. **Disconnect the affected MCP connection** in your AI client and re-authenticate to obtain a fresh session.
3. **Tell us**, through the private channels above, so we can help check for misuse.
4. **Rotate anything related.** If one credential was exposed through a given path, assume others on the same path were too.

## Scope

This repository contains documentation, examples, and configuration resources.

- **Issues in this repository** — incorrect or unsafe setup instructions, documentation that would lead someone to expose a credential, or problems with the files published here. Report them as described above.
- **Issues in the hosted InterviewFlowAI MCP service or the InterviewFlowAI platform** — report them through the private channels above as well. The service implementation is not published in this repository, but the report reaches the same team.

## Good practice for users

- Connect with read-only access (`mcp:read`) unless you need to write.
- Authenticate through the browser sign-in flow rather than pasting credentials into a client configuration file.
- Never commit a client configuration file containing tokens to a repository.
- Review every write action before approving it.
- Remove the connection from any device you no longer control.
