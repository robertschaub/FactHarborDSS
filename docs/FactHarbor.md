# From FactHarbor to DSS

<a id="factharbor-application"></a>
<a id="read-the-result"></a>
<a id="inspect-the-evidence"></a>

The existing **FactHarbor application (Alpha)** provides experience to build on. [See the FactHarbor report walkthrough](https://robertschaub.github.io/FactHarbor/#read-a-report), including sources, evidence and separate assessment and confidence labels.

## What DSS would carry forward

DSS would retain inspectable claims, evidence, sources and limitations, keeping the assessment of a claim distinct from confidence in it. It would add a more explicit basis for preserving and replaying the evidence used, and later compare options against human-confirmed goals and constraints.

These are design intentions, not delivered capabilities or inherited proof of quality. DSS must demonstrate its own usefulness. The **FactHarbor association** remains the organization behind both applications.

## How the Alpha assesses evidence today

In the Alpha, a model extracts evidence, judges its direction and probative value, and assesses each claim. Fixed code combines the claim verdicts into the overall verdict, using fixed weighting rules that also take probative value and the share of derivative evidence into account; where claims point in different directions, a model decides within fixed bounds. Code checks minimum conditions: with too little or too uniform evidence, a claim is unverified. A plausibility check tests whether the cited evidence exists, belongs to the claim and does not entirely contradict the verdict. It measures consistency with the model's own evidence directions, not truth. Derivative items are flagged, but their originals are not retrieved.

A model rates each source's reliability from a search about it, and a second model may correct the rating. Code caps the rating for some source types, such as sources classified as propaganda or state-controlled. The rating reaches verdicts only as guidance to the models; an earlier fixed weighting formula was switched off.

The planned DSS is designed to change this: model judgments are labelled, and the way each result was established is recorded. Evidence is assessed before it counts and weighed through reasoned levels instead of numeric weights. Source reliability comes from cited third-party material without caps or formulas, and the originals of the evidence a verdict rests on are sought within the run's search allowance. See the [key requirements](Requirements.md).

See the [purpose and approach](Concept.md), [reasons for a fresh implementation](Rationale.md) and [planned architecture](Architecture.md).
