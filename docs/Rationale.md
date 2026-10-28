# Why a fresh implementation

The proposed fresh implementation is intended to carry forward the experience and useful work from developing the FactHarbor application while creating a simpler foundation for claim assessment, later decision support and EGA. It starts with a small implementation whose benefits must be verified before the scope expands.

**These are development motivations and intended improvements, not measured DSS results.** A rewrite alone would establish neither better assessments nor market demand.

## Maintainability

The maintainer's experience is that the Alpha has accumulated considerable code and complexity, making changes harder to manage. A fresh modular structure is intended to make responsibilities clearer, reduce unnecessary coupling and make changes easier to review.

This does not imply discarding everything learned or automatically copying existing code. Useful designs and selected implementation candidates need deliberate reuse decisions.

## Speed and running costs

The intention is to simplify the analysis workflow and avoid unnecessary processing while protecting quality. More steps, agents or model calls are not a measure of better reasoning.

Any improvement must be demonstrated against a suitable baseline, considering assessment quality alongside time, cost and the reader's correction effort. No DSS speedup or cost saving has been established.

## Quality and testing

Preserving the exact evidence used by each assessment should make comparisons more systematic and regressions easier to detect. The design separates acquisition quality, assessment quality on fixed evidence and the usefulness of the complete reviewer workflow.

Repeatable inputs support investigation; they do not guarantee identical model output or correct conclusions. Independently judged cases, protected evaluation material and explicit acceptance criteria remain necessary.

## A common foundation for broader capabilities

Fact-checking asks what the evidence supports. Decision support adds human-confirmed goals, alternatives and constraints. EGA also asks whether a proposed step is supported and permitted to proceed.

These uses can share evidence and reporting while keeping their methods and authority boundaries distinct. See the [concept](Concept.md) for their purpose and the [architecture](Architecture.md) for the selected foundations.

## Production readiness

The planned architecture is intended to improve the foundation for database storage, background processing, recovery and access controls, with a path toward more users and workloads. Durable work and explicit permissions should be designed into the application rather than assumed from an AI response.

This is a design direction, not production readiness already achieved. Capacity, recovery, access controls and hosting must be implemented and qualified for their intended use. See the [architecture overview](Architecture.md).

## Development with coding agents

Clear requirements, smaller modules, explicit interfaces and focused tests should make delegated changes easier to review and integrate. An accountable integrator, independent review where required and evidence-based acceptance remain necessary.

A better structure may help both human contributors and coding agents. It does not prove faster development, reliable autonomous operation or installed technical enforcement. The [contribution guide](https://github.com/robertschaub/FactHarborDSS/blob/main/CONTRIBUTING.md) explains how to propose scoped work.

## Start small and test the reasons

The first development target is bounded web evidence capture and replay with minimal claim assessment. Comparative evaluation follows separately. Continue, narrow or reconsider the work based on demonstrated benefit, not the fact that a rewrite has begun.

The initial work must therefore produce evidence about quality, usefulness and effort as well as functioning software. The [cooperation options](Cooperation.md) explain how cases, reviewers, engineering capacity and funding could support that process.
