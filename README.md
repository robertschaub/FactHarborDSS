# FactHarborDSS

FactHarborDSS (DSS: Decision Support System) is a planned successor to both app.FactHarbor.ch and the EvidenceGatedAgents core, supporting evidence-based decision making and fact-checking for both humans and working AI agents.

## Product direction

- Support defining a problem, gathering information, identifying alternatives, weighing evidence, recommending a choice, taking authorized action, and reviewing outcomes.
- Explain recommendations with traceable evidence, assumptions, trade-offs and limitations.
- Distinguish confidence in a recommendation from defensible probabilities of specified outcomes.
- Provide claim assessments with verdicts and confidence.
- Let humans and authenticated working agents request decision support and fact-checking using shared assessment semantics; keep evidence findings, recommendations and permission to release outputs or execute actions distinct.
- Support public-only, organization-private-only and combined evidence scopes.
- Adapt analysis effort and agent orchestration to complexity and the severity of potential consequences, within explicit limits.
- Support iterative analysis and targeted requests for additional input, including authenticated human participation where required.
- Keep customer workspaces and their data private by default.
- Require demonstrated benefit before adopting proposed behavioral improvements.

## Status

Requirements and architecture planning. No application, deployment, qualified security boundary or production capability is implemented in this scaffold. The next proposed implementation is an offline structural skeleton using synthetic local files. The first useful pilot requires bounded retrieval over a real, versioned local collection and both factual-claim assessment and one simple reversible decision workflow. Synthetic success does not establish pilot usefulness or qualify ordinary use.

The broader first-release scope includes output-release gating, a gate service and one enforced action integration: controlled HTTP/webhook delivery to a cooperating receiver with idempotency and status lookup. External actions are later than the pilot. Their detailed contract, endpoint and permitted effects remain to be specified; no real delivery is authorized by this plan.

## Repository scope

Agents start with [AGENTS.md](AGENTS.md) and the [shared development workflow](docs/agents/Workflow.md). The initial setup uses common guidance; client adapters and skills are added only when demonstrated necessary.

Each authorized task supplies its current bet, applicable contract excerpts, fixtures and evaluation material. These must be sufficient for the contributor's work without access to private planning. Stack selection and explicit implementation authorization remain outstanding.

Start the client in this repository root. If it does not load project instructions automatically, explicitly ask it to read AGENTS.md and follow its workflow pointer before work; do not assume startup loading from the client name. Instructions guide behavior and do not establish a sandbox.

This repository will contain self-contained application/service code, executable schemas, prompts, safe configuration defaults, contributor-facing requirements and specifications, and synthetic tests. Build and contribution workflows must not depend on unavailable external planning documents.

Do not commit customer inputs, private evidence, reports, credentials or raw execution logs. Public release and licensing are separate pending decisions.
