# Association and projects

The FactHarbor association is a Swiss non-profit association (Verein), founded in 2026 and based in Dietlikon, Zürich. Its purpose is to help people make well-grounded decisions and use technology responsibly. Public benefit, openness, independence and transparency guide the work. [Public stewardship overview](https://robertschaub.github.io/our-ai-charter/About/#stewardship-and-governance)

The association brings together two complementary initiatives. Its FactHarbor initiative develops applications and services for evidence-based decisions, including the existing FactHarbor application (Alpha) and the planned FactHarborDSS. Our AI Charter proposes a trustworthy AI network for free, fair and resilient societies. FactHarborDSS is planned to succeed both the FactHarbor application and the relevant Evidence-Gated Agents core, for claim assessment and decision support.

## How the pieces fit

These are different projects and maturity levels, not interchangeable names for a delivered system. The overview reflects the project presentation and the DSS planning status as of 28 October 2026.

| Work | What exists | Intended contribution to DSS |
|---|---|---|
| **FactHarbor application (Alpha)** | An existing claim-checking application with evidence, sources, reasoning, truth assessment and separate confidence. | Experience with claim assessment, report structure and the reader's inspection path. |
| **Our AI Charter** | Public framework, commitments, research and articles in draft form; a proposed network. | Accountability, openness, traceability and the public-interest context. |
| **Evidence-Gated Agents** | A defined concept and prototype direction; DSS integration remains development work. | Examine a proposed step's evidence and authority before permitted release or action. |
| **AI Charter Runtime** | A separate runnable but unfinished proof of concept, exercised with simulated scenarios and local effects. | Lessons about controls outside the acting AI. Code reuse remains an explicit choice. |
| **FactHarborDSS** | Published concept, pipeline and architecture overviews; planning continues. | A shared core for human and agent claim assessment and decision support. Not yet implemented or evaluated. |

The Alpha's reports are concrete examples of an existing application. Charter documents describe principles and proposed structures. The Runtime proof of concept does not establish completed EGA integration, operational certification or DSS security.

The [project concept](Concept.md) and [planned architecture](Architecture.md) in this repository describe the DSS direction.

## Continuity without assumed parity

DSS is intended to succeed the FactHarbor application and the relevant EGA core. That does not promise delivered feature parity, a replacement date, migration of all historical data or retirement of either predecessor. The FactHarbor association remains the organization behind this work.

Useful experience, report ideas and carefully selected work should carry forward. Implementation reuse needs case-by-case review. The initial DSS milestone acquires new web evidence; it does not depend on importing the Alpha's evidence or results.

Read [what DSS would carry forward](FactHarbor.md), [Our AI Charter and EGA](Charter-and-EGA.md), and [why a fresh implementation is proposed](Rationale.md).
