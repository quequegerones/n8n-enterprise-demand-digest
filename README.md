# Enterprise demand digest (n8n + Jev)

*Independent project, not affiliated with n8n.*

An n8n workflow that reads n8n's public [Feature Requests forum](https://community.n8n.io/c/feature-requests/5) every Monday and answers one product question: **where is enterprise demand concentrating, and what should we say no to?**

**Latest report: [reports/latest.md](reports/latest.md)** · **Run it live: [open the form](https://gmgerones.app.n8n.cloud/form/4e79744c-2183-4242-9083-e705217cf758)** (runs on my n8n instance with my connections; one fresh run per hour, otherwise it shows the cached result and says so)

## How it works

1. **Collect.** Pulls the most voted and the most recently active feature requests (about 90 per run) and dedupes them.
2. **Judge with Jev.** Each request goes to [Jev](https://typesafe.ai) (TypeSafe's System One model) with three typed questions in one call:
   - *Product area* (choice): identity and access, governance and compliance, credentials and secrets, environments and DevOps, observability, AI agents, integrations, editor, other.
   - *Enterprise impact* (score 0 to 3): from "matters to individual builders" to "can block adoption, a security review or a renewal at a large company".
   - *One-off* (yes/no probability): is this tied to one company's setup or a niche tool?
3. **Rank in code.** Priority = distinct demand (log of votes and replies) × enterprise impact above the small-team level × (1 − one-off). Many voices beat one loud request, and the weights live in code, so they can change without re-running the model.
4. **Act.**
   - A Google Sheets **backlog**, upserted by request id, with a recommendation per row: roadmap candidate, monitor, review, or not roadmap.
   - A public **form** that runs the whole pipeline on demand and shows the report on screen, with a one-hour cache so repeated clicks don't re-run the model.
   - A Markdown **report** committed here every week (dated file plus `reports/latest.md`): top areas, top 10 candidates, what is probably not roadmap, what needs a human look, and blind spots.

## Why Jev instead of a chat model

The workflow needs judgments that code can consume: a category, a number and a probability, not paragraphs to parse. Jev returns typed answers with confidence, so low-confidence classifications are routed to "needs a human look" instead of being trusted blindly.

## Known limits

- The public forum shows little demand for identity and governance. Two readings: much of it already ships in n8n's Business and Enterprise plans (SSO, LDAP, environments, Git, audit logging, log streaming, external secrets), and buyers who need more raise it in sales calls and support tickets. The next input would be CRM notes and tickets weighted by account size.
- Integration requests are numerous, so that area tends to lead on volume; the top 10 table ranks individual requests and is the better read.

## Run it yourself

1. Import `workflow.json` into n8n.
2. Create a Header Auth credential for Jev (`Authorization: Bearer <TypeSafe API key>`) on *Classify with Jev*.
3. Connect Google Sheets on *Update backlog sheet* and pick a sheet whose first row has these headers: `id, title, theme, enterprise_impact, one_off, votes, replies, priority, recommendation, flags, url, last_activity, last_seen`.
4. Connect GitHub on *Save dated report* and *Update latest report*, and point them to your repo.
5. Optional: set your sheet and repo URLs in *Cache report page* and publish the workflow to get a public form.

Built by [Gonzalo Geronés](https://gmgerones.com).
