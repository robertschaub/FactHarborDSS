# FactHarborDSS

<div class="dss-intro" markdown="1">

<span class="dss-eyebrow">Decision Support System · In planning</span>

## Evidence for better-informed decisions

FactHarborDSS is a planned tool for **checking factual claims** and, later, **comparing courses of action**. It aims to make conclusions easier to inspect and challenge—with clear evidence, reasons and uncertainty.

Designed for people and for technical users, such as other software and working AI agents acting for a responsible person, with the same functions through an API.

[How it would work](Concept.md){ .md-button .md-button--primary }
[Key requirements](Requirements.md){ .md-button }
[Cooperate with us](Cooperation.md){ .md-button }

</div>

## The problem

AI-assisted analysis can sound convincing without showing what is actually established. A reader needs to see what supports a conclusion, what contradicts it, what is missing and which steps were model judgments.

## The approach

- **Model judgment stays labelled.** A verdict is a model judgment and is shown as one. Only checks by trusted code or by people count as checked; agreement among models never does.
- **Evidence is assessed before it counts.** Unfounded material is not evidence. Each cited item gets a reasoned weight level based on its documentation, origin, independence and source reliability, without numeric formulas.
- **Every verdict shows its basis.** It names the parts it rests on, how well the evidence supports it and what would change it.
- **Gaps are named, not hidden.** Missing evidence, open parts and contradictions are reported explicitly. In fact-checking, the analysis continues and names them instead of stopping.
- **People decide.** DSS provides an inspectable basis, not authority. Confirming goals and approving actions stay with people; any action needs its own approval.

The [key requirements](Requirements.md) set out these commitments in more detail.

## Planned stages

1. **Claim checking:** public-web claims, with the evidence examined preserved for reassessment.
2. **Comparative evaluation** of assessment quality against independent reviewers.
3. **Decision support** for one selected type of decision, using permitted files and human-confirmed goals and constraints.
4. **Controlled actions by working agents**, checked under [Evidence-Gated Agents](Charter-and-EGA.md).

Each stage is scoped and authorized separately after the previous one is reviewed; DSS must demonstrate its benefit before ordinary use.

## Building on existing work

The project builds on lessons from the FactHarbor application (Alpha)—see its [report walkthrough](https://robertschaub.github.io/FactHarbor/#read-a-report) and [what DSS changes](FactHarbor.md)—and on [Evidence-Gated Agents](Charter-and-EGA.md): examine what supports a conclusion, and keep permission to share or act separate.

It is developed within the [FactHarbor association](Background.md), a Swiss non-profit.

## Where we are now

**Planning stage — 1 November 2026.** The first development phase would check public-web claims and preserve the evidence examined. Implementation has not started; DSS benefits have yet to be demonstrated.

Explore the [analysis pipeline](Pipeline.md), the [planned architecture](Architecture.md), [why a fresh implementation](Rationale.md), or [partnership and funding opportunities](Cooperation.md).
