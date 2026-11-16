# Enterprise demand digest, week of 2026-11-16

88 feature requests from the [n8n community forum](https://community.n8n.io/c/feature-requests/5), classified with Jev (TypeSafe) and ranked by distinct demand × enterprise impact.

## Where enterprise demand concentrates

| # | Area | Priority | Requests | Votes | Top request |
|---|---|---|---|---|---|
| 1 | **integrations nodes** | 31.9 | 61 | 1824 | [Support for Stream in HTTP Request node and OpenAI node](https://community.n8n.io/t/support-for-stream-in-http-request-node-and-openai-node/23771) |
| 2 | **observability reliability** | 11.3 | 4 | 523 | [Capturing n8n flows with Observability & Evaluations platforms like Langfuse, Comet Opik, etc](https://community.n8n.io/t/capturing-n8n-flows-with-observability-evaluations-platforms-like-langfuse-comet-opik-etc/75764) |
| 3 | **credentials secrets** | 10.5 | 4 | 475 | [Select credentials via expression](https://community.n8n.io/t/select-credentials-via-expression/5150) |
| 4 | **environments devops** | 5 | 3 | 86 | [Option for blocking parallel workflow execution](https://community.n8n.io/t/option-for-blocking-parallel-workflow-execution/2842) |
| 5 | **ai agents** | 4.5 | 8 | 123 | [Enable Reasoning Parameters Across All Compatible Models in AI Agent Node](https://community.n8n.io/t/enable-reasoning-parameters-across-all-compatible-models-in-ai-agent-node/164505) |
| 6 | **editor experience** | 2.4 | 6 | 122 | [How to set default “Error Workflow” for new workflows](https://community.n8n.io/t/how-to-set-default-error-workflow-for-new-workflows/7598) |

## Top 10 roadmap candidates

| Request | Area | Impact (0 to 3) | Votes | Priority |
|---|---|---|---|---|
| [Capturing n8n flows with Observability & Evaluations platforms like Langfuse, Comet Opik, etc](https://community.n8n.io/t/capturing-n8n-flows-with-observability-evaluations-platforms-like-langfuse-comet-opik-etc/75764) | observability reliability | 2.14 | 254 | 3.54 |
| [Retrieve LLM Token Usage in AI Agents](https://community.n8n.io/t/retrieve-llm-token-usage-in-ai-agents/68714) | observability reliability | 2.04 | 143 | 3.2 |
| [Select credentials via expression](https://community.n8n.io/t/select-credentials-via-expression/5150) | credentials secrets | 1.99 | 309 | 3.14 |
| [Automatic Retry of Workflows](https://community.n8n.io/t/automatic-retry-of-workflows/5310) | observability reliability | 2.07 | 79 | 2.96 |
| [Access saved credentials from "expressions"](https://community.n8n.io/t/access-saved-credentials-from-expressions/857) | credentials secrets | 2.32 | 89 | 2.88 |
| [Support for Stream in HTTP Request node and OpenAI node](https://community.n8n.io/t/support-for-stream-in-http-request-node-and-openai-node/23771) | integrations nodes | 1.81 | 179 | 2.55 |
| [Dynamically select credentials in nodes](https://community.n8n.io/t/dynamically-select-credentials-in-nodes/68113) | credentials secrets | 2.28 | 29 | 2.46 |
| [Option for blocking parallel workflow execution](https://community.n8n.io/t/option-for-blocking-parallel-workflow-execution/2842) | environments devops | 2.08 | 41 | 2.25 |
| [Add concurrency in workflow settings](https://community.n8n.io/t/add-concurrency-in-workflow-settings/44103) | environments devops | 2.03 | 44 | 2.24 |
| [Feature Request: Custom Nodes for Microsoft Office (Word, Excel, PowerPoint, Access, OneNote, etc.)](https://community.n8n.io/t/feature-request-custom-nodes-for-microsoft-office-word-excel-powerpoint-access-onenote-etc/78210) | integrations nodes | 2 | 31 | 2.18 |

## Probably not roadmap

Needs tied to one setup or a niche tool: answer with a workaround, a template or a community node.

- [Support Jotform Enterprise API domain (subdomain.jotform.com/API) in the JotForm node](https://community.n8n.io/t/support-jotform-enterprise-api-domain-subdomain-jotform-com-api-in-the-jotform-node/328901) (0 votes)
- [Agents: setting the OpenAI service tier (Flex) in the agent config and the advanced panel](https://community.n8n.io/t/agents-setting-the-openai-service-tier-flex-in-the-agent-config-and-the-advanced-panel/328474) (0 votes)
- [Add Official Liferay DXP Nodes and Triggers to n8n](https://community.n8n.io/t/add-official-liferay-dxp-nodes-and-triggers-to-n8n/328059) (0 votes)

## Needs a human look

- [Add concurrency in workflow settings](https://community.n8n.io/t/add-concurrency-in-workflow-settings/44103): area unclear: human review
- [Option for blocking parallel workflow execution](https://community.n8n.io/t/option-for-blocking-parallel-workflow-execution/2842): area unclear: human review
- [Kafka: support AWS MSK IAM authentication (SASL/OAUTHBEARER)](https://community.n8n.io/t/kafka-support-aws-msk-iam-authentication-sasl-oauthbearer/328951): high impact, little demand yet: validate with customers
- [Include Workflow and Project Metadata in Execution Data Reveal Audit Events](https://community.n8n.io/t/include-workflow-and-project-metadata-in-execution-data-reveal-audit-events/327536): high impact, little demand yet: validate with customers
- [Allow editing Data Tables in Protected Environments (for environment-specific configurations)](https://community.n8n.io/t/allow-editing-data-tables-in-protected-environments-for-environment-specific-configurations/319693): high impact, little demand yet: validate with customers
- [MCP Server - include options for Annotations](https://community.n8n.io/t/mcp-server-include-options-for-annotations/298669): area unclear: human review

## Blind spot

Almost no forum demand for identity access and governance compliance. That doesn't mean enterprises don't need it: buyers who need SSO, audit logs or data residency raise it with sales and support, not on a public forum. Next input for this workflow: CRM deal notes and support tickets, weighted by account size.

---

*Method: votes and replies from community.n8n.io. Jev answers three typed questions per request: product area (choice), enterprise impact (score 0 to 3) and one-off probability (yes/no). Priority = log2(1 + votes + replies/2) × max(0, impact − 1)/2 × (1 − 0.7 × one-off). Weights live in code and can change without re-running the model.*