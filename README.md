# FactHarborDSS

FactHarborDSS is an application and service being designed for evidence-based decision making. It will support human decisions, fact-checking, and gates controlling agent outputs and proposed external actions.

## Product direction

- Support defining a problem, gathering information, identifying alternatives, weighing evidence, recommending a choice, taking authorized action, and reviewing outcomes.
- Explain recommendations with traceable evidence, assumptions, trade-offs and limitations.
- Distinguish confidence in a recommendation from defensible probabilities of specified outcomes.
- Provide claim assessments with verdicts and confidence.
- Support public-only, organization-private-only and combined evidence scopes.
- Keep customer workspaces and their data private by default.
- Require demonstrated benefit before adopting proposed behavioral improvements.

## Status

Requirements and architecture planning. No application, deployment, qualified security boundary or production capability is implemented in this scaffold. The initial delivery scope includes a gate service and one enforced action integration; the integration itself is still to be selected.

## Repository scope

This repository will contain self-contained application/service code, executable schemas, prompts, safe configuration defaults, contributor-facing requirements and specifications, and synthetic tests. Build and contribution workflows must not depend on unavailable external planning documents.

Do not commit customer inputs, private evidence, reports, credentials or raw execution logs. Public release and licensing are separate pending decisions.
