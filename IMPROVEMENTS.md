# Improvement plan

This workflow is a demo. Today it works as a radar for discovery: a fast way to scan public requests with links to check each one. It is not yet a tool to defend enterprise roadmap decisions. This plan lists what would close that gap, based on two independent reviews of the 16 November report.

## 1. Fix before sharing more widely

**Align the report and the backlog.** The sheet marks any flagged request as `Review`, but the report's top 10 picks by score only. The two concurrency requests show up both as roadmap candidates and as needing a human look. Use one rule in both places and show the review status in the top 10 table.

**Name things for what they measure.**
- "Distinct demand" counts votes plus replies. Replies can come from the same person, and nothing identifies distinct companies. Call it *forum demand*.
- "Enterprise impact" is a model estimate from the request text. It does not say which companies need it, what they pay or which deal it blocks. Present the output as *public signals of possible enterprise needs*.
- "Probably not roadmap" is too strong. A niche request can unblock a strategic account, and DocuSign with 26 votes needs more than a one-off probability to be dropped. Rename it *Partner or community node first?* and say that commercial context and effort are missing.

## 2. Better synthesis

**Separate breadth from intensity.** Summing priorities favors large areas: integrations leads with 61 requests while observability has 5 with roughly four times the priority per request. Show total priority (breadth) and average priority per request (intensity) side by side.

**Group requests into problems.** Several threads describe the same need (dynamic credential selection, concurrency limits). Group them into problems with a shared outcome and variants, and stop adding their votes as if they were distinct users. Jev can assign each request to a problem from a list defined in code, since that is a choice, not generated text.

**Open with findings, written by a person.** The most useful read of the current top 10 is buried: running workflows in production (observability, token usage, retries, dynamic credentials, concurrency) stands out more than "integrations leads". The report should open with three hypotheses, the evidence behind each and what to validate. For example: *investigate whether dynamic credential selection reduces workflow duplication in multi-client or multi-environment setups.*

Options for who writes them:

| Option | Pros | Cons |
|---|---|---|
| Code templates | Deterministic, free, never invents | Reads as boilerplate; cannot reach a real hypothesis |
| An LLM node | Fresh synthesis every week | Another key and cost; can claim more than the data supports, on a public page |
| A product manager, with evidence filled in by the workflow | The judgment the report exists for | Does not scale; automated runs show the last note |

The third option fits best: the workflow keeps the evidence fresh, and a dated analyst note sits on top.

## 3. Make it weekly for real

**Show what changed.** Today the report ranks cumulative totals, so each Monday reads almost the same. Store a snapshot per run and report new requests, vote growth, rank movements and requests that were closed.

**Check whether a need is already covered.** Some requests are solved by features that already ship. Mark them so they do not compete with open gaps.

## 4. Better inputs

The public forum underrepresents enterprise buyers. The next sources would be CRM deal notes and support tickets, weighted by account size, so impact comes from real accounts and not only from request text.
