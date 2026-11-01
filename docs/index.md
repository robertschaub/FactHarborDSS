# FactHarborDSS

<div class="dss-intro" markdown="1">

<span class="dss-eyebrow">Decision Support System · In planning</span>

## Evidence for better-informed decisions

FactHarborDSS is a planned AI-assisted tool for **checking factual claims** and, later, **comparing courses of action**. It would use AI models to assess evidence, and every conclusion would show its sources, reasons and uncertainty, including which steps were AI judgments rather than checks.

It would serve people directly and, through an API with the same functions, software and AI agents acting for a person.

[How it would work](Concept.md){ .md-button .md-button--primary }
[Principles](Requirements.md){ .md-button }
[Cooperate with us](Cooperation.md){ .md-button }

</div>

## The problem

AI-assisted analysis can sound convincing without showing what is actually established. A reader needs to see what supports a conclusion, what contradicts it, what is missing and which steps were model judgments.

<a id="the-approach"></a>

## How DSS is designed to work

These are design commitments, not delivered functionality.

- **AI judgments stay labelled.** Verdicts and evidence ratings are model judgments and are shown as such. Only checks by people, or by fixed software rules such as confirming that a quote appears in the saved source, count as checked; agreement between models never does.
- **Each atomic claim gets its own verdict.** As in the FactHarbor Alpha, a claim is split into atomic claims, statements that can each be checked on their own. The overall verdict builds on the decisive ones, without averaging or counting.
- **Evidence is weighed, not counted.** Searches also look for contradicting evidence. Each item is first assessed for whether it substantiates what it says and whether it is the original, then given a reasoned weight from very strong to very weak, with no numeric formula.
- **Every verdict shows its basis.** It names the evidence and atomic claims it rests on, how well the evidence supports it and what would change it.
- **Gaps are named, not hidden.** Missing or conflicting evidence and atomic claims that could not be assessed are listed in the report; fact-checking continues and names them instead of stopping.
- **People decide.** DSS would provide an inspectable basis, not authority. Confirming goals and approving actions stay with people; any external action needs separate authorization.

The [principles](Requirements.md) set out these commitments in more detail.

## Planned stages

1. **Claim checking:** factual claims assessed with public web sources, with the evidence examined saved for reassessment.
2. **Comparative evaluation** of assessment quality against independent reviewers.
3. **Decision support** for one selected type of decision, using permitted files and human-confirmed goals and constraints.
4. **Controlled actions by AI agents**, checked under [Evidence-Gated Agents](Charter-and-EGA.md).

Each stage is scoped and authorized separately after the previous one is reviewed; DSS must demonstrate its benefit before routine use.

## Building on existing work

DSS builds on the FactHarbor application (Alpha): it keeps the Alpha's structure of atomic claims, evidence items and claim assessment boundaries and changes how verdicts are combined—see the Alpha's [report walkthrough](https://robertschaub.github.io/FactHarbor/#read-a-report) and [what DSS keeps and changes](FactHarbor.md). It also builds on [Evidence-Gated Agents](Charter-and-EGA.md): examine what supports a conclusion, and keep permission to share or act separate.

DSS is a project of the [FactHarbor association](Background.md), a Swiss non-profit.

## Where we are now

**Planning stage — 1 November 2026.** Stage 1 would check factual claims with public web sources and save the evidence examined. Implementation has not started; DSS benefits have yet to be demonstrated.

Explore the [analysis pipeline](Pipeline.md), the [planned architecture](Architecture.md), [why a fresh implementation](Rationale.md), or [partnership and funding opportunities](Cooperation.md).
