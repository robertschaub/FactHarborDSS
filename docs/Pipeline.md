# Analysis pipeline and agent debate

The planned pipeline connects an exact question to permitted evidence, an assessment people can challenge, and a report released to its intended reader. Claim assessment and decision comparison share evidence and reporting, while using distinct analytical methods.

**This is the broader proposed design, not an implemented workflow.** The first milestone remains web evidence capture/replay and minimal claim assessment. Decision comparison and the additional-agent debate route are later scope, subject to evaluation. More agents are not themselves evidence of better results.

[![Simplified planned pipeline: frame the request, capture or replay evidence, assess a claim or decision, select bounded debate tasks, reconcile objections, validate, finalize and check recipient release; a direct route retains mandatory checks](assets/analysis-pipeline.svg)](assets/analysis-pipeline.svg)

*Open the diagram for a larger view. The “Conditional agent debate” panel contains possible debate tasks; it does not prescribe all roles, parallel dispatch or a fixed number of model calls. The Validator role is represented in step 4 alongside trusted code checks; required validation applies on both routes.*

*Simplified adaptation of the FactHarbor/DSS design. Attribution: FactHarbor contributors · [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) · [Public visual lineage](https://robertschaub.github.io/FactHarbor/diagrams/homepage-method.svg).*

## What the agents would contribute

The controller selects only required or justified tasks, their dependencies and their permitted inputs. Each task works against the exact evidence and assessment versions it was assigned.

| Task | Contribution |
|---|---|
| Advocate | Explain the evidence-backed case, including assumptions and limitations; do not defend a preferred answer regardless of evidence. |
| Challenger / specialist | Examine counterevidence, alternative explanations, citation or scope defects, or a specific expert question. |
| Self-consistency | Examine instability or contradictions on comparable inputs. Repetition and agreement add no independent evidence. |
| Reconciler | Accept, reject or retain each material objection as unresolved, with reasons; revise affected findings where justified. |
| Validator | Apply the required qualified semantic checks, including whether citations support the claim. Trusted code separately checks reference existence, exact quotations, evidence dates, versions, arithmetic and current authority. It applies no source weights or evidence-count formulas. Validation grants no release or action permission. |

These are task roles, not necessarily five permanent agents or five different models. Different role names do not establish independence. The controller joins only the dependencies it admitted, rejects stale or incompatible results, and retains an explicit outcome for failed or cancelled tasks.

## Challenge without voting or endless retries

Baseline assessment already examines counterevidence. When no extra agent is needed, the direct path still undergoes mandatory checks. A required challenge cannot be skipped because another agent agrees or the budget has run out.

Reconciliation follows the substance of an objection, not the number of agents supporting it. A demonstrated reasoning or quotation defect can justify correction without a new source; unsupported disagreement does not automatically reduce a score. Material unresolved issues constrain the conclusion and its intended use.

The controller can admit useful refinement or request human input within the same remaining resource allowance, or record a limited result, hold or stop. Further rounds do not reset limits. Deliberate scope narrowing or changed decision priorities require the applicable human adoption; a claim-only request needs no irrelevant preference approval.

## Judgment reliability

In the planned design, assessments rely on guided model judgment rather than hand-set weights. Reliability comes from recording, separating and measuring judgments:

- **Recorded basis:** each assessment records the interpretation of the question or claim, the key details considered, the evidence capture dates, and the versions of the assessment schema and scale.
- **Separate states:** conflicting evidence, insufficient evidence and no assessment are distinct outcomes.
- **Repeated runs:** if runs are repeated on the same captured evidence, their disagreement is never voted or averaged into a verdict. A single run means stability was not measured. Whether and how observed variation is shown is decided after reader testing.
- **Separate measures:** evidence sufficiency and any observed run variation stay separate and are never merged into one score. A model's self-reported confidence is never used alone.
- **Source information, not source weights:** source type, ownership, independence and track record inform the assessment and are shown to readers. They are never applied as a weight or gate. Publisher ratings recalled by a model are not used.

## From candidate to permitted report

Reports retain material objections, dispositions, changes, reasons, uncertainty and stopping conditions—not raw debate transcripts. Only a valid candidate becomes a fixed report edition. Recipient-specific access, disclosure, quality and any required human review still govern release; a misleading redaction must be withheld.

A report is evidence, not permission to act. External actions have a separate authorization and execution path and are outside this simplified diagram.

See the [system architecture](Architecture.md) and [purpose and approach](Concept.md).
