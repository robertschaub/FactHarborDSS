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

## What DSS would offer

- **Who it is for:** anyone who needs to check a factual claim before relying on it, such as a statement in the news, a figure in a report or a claim in a document; later also people preparing a decision. Software and AI agents acting for a person would use the same functions.
- **What you would do:** submit a factual claim. Later you could also describe a decision, with your goals and constraints and the options you are considering.
- **What you would get:** a report with a verdict for each atomic claim, that is, each part of the claim that can be checked on its own, and for the claim as a whole, each with a separate confidence. It shows the evidence for and against, with exact quotes and their sources, what remains uncertain or missing, what would change the verdict, and which steps were AI judgments rather than checks.
- **What stays with you:** DSS would not decide or act for you. It provides an inspectable basis and saves the evidence it examined, so the assessment can be checked again later.

<a id="the-approach"></a>

[How it would work](Concept.md) describes the process. DSS follows a few core [principles](Requirements.md): an assessment is not a fact, only a check establishes, agreement is not a check, and a result never grants permission to act.

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
