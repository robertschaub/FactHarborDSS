# Principles

<a id="how-the-parts-fit-together"></a>

These principles set out what the planned DSS must and must not do. They are design commitments, not delivered functionality. Which of them Stage 1 covers, and in what form, is set when it is scoped; reports say what was not assessed. The records they refer to are shown in the [core data model](Architecture.md#core-data-model).

Unless a section says otherwise, its principles apply to all of DSS. A few apply only to fact-checking, that is, to a request that only asks whether claims are true; they are marked <span class="dss-scope">Fact-checking only</span> and say what applies in decision support instead.

## Core principles

1. **Support, not decision-making.** FactHarborDSS is a decision support system, not a decision-making system. It collects evidence and provides a sound information basis to assist people in making decisions; the decisions stay with them.
2. **An assessment is not a fact.** DSS assesses claims, but every verdict is labelled as a model judgment. It establishes no fact and carries no authority.
3. **Only a check establishes.** A statement counts as established only when trusted code or a person has checked it, and a model never gives its own output that status. What is established, what lacks essential evidence and what remains a model judgment are always shown separately.
4. **Agreement is not a check.** When a model reviews another model's work, or several models or runs agree, the result is still a model judgment.
5. **An authentic source can be about something else.** Whether a cited passage concerns the right person or institution, matter, time and relation remains a model judgment until a person checks it. Search can confuse similar records, so a search hit is only a candidate until it has been assessed.
6. **Method quality is not proof in the single case.** Measured agreement with independent reviewers describes the method, not an individual verdict. DSS is meant to make human checking faster and more complete, not to replace it, and that benefit must be measured.
7. **Every result shows its basis and its limits.** It states how well the evidence supports it, what would change it and what is missing; gaps are named, not hidden.
8. **A result never grants permission.** Permission to share or act is given separately and needs its own justification. Urgency never turns uncertainty into knowledge or waives a required check.

The sections below set out how DSS applies these principles.

## How each result was established

- **Each result says how it was established:** captured, checked by trusted code (fixed, tested software rules), judged by a model, or reviewed or adopted by a person. Only checks by trusted code or people are called checked, validated or verified, and a model's conclusion is labelled as a model judgment. A person's check is recorded with their role and covers only what they examined.
- **Recorded basis.** Each assessment records the reading of the question or claim, the context of the statement where known (speaker, date and venue), the key details considered, the evidence capture dates, and the versions of the assessment schema and scale.

## Claim assessment

Applies to every factual claim DSS assesses: in fact-checking and as a factual premise of a decision.

### Results and their meaning

- **Atomic claims first.** A claim is split into atomic claims; a simple claim is one atomic claim, whose verdict is then also the overall verdict. Each atomic claim gets its own verdict, confidence, reasoning and cited evidence. The overall verdict is a separate judgment built on the atomic claims decisive for it; it never averages their verdicts or counts how many are supported. Where no overall verdict is justified, the report says so and the atomic-claim verdicts stand.
- **Verdict and confidence.** A factual verdict is set by model judgment on a scale from 0 (false) to 100 (true), and fixed rules assign its readable label. A separate confidence is explained by the evidence and the completeness of the search. Neither is a calibrated probability, and no formula derives them from weight levels, reliability labels or item counts.
- **Separate states.** Mixed is a supported middle result: the evidence shows the claim to be about as much true as false. Unverified means that no adequately supported judgment was reached, for a stated reason: insufficient evidence or an unresolved conflict. A claim that could not be assessed, or an assessment that failed or did not run, is a separate state. Finding no evidence never produces False or a midpoint score.
- **Reading and scope.** The original wording is kept, and a claim's own qualifiers are neither strengthened nor weakened. Atomic claims that were not assessed are named. Opinions and value judgments get no verdict and are named as not assessable. A literally accurate but misleading claim keeps its factual verdict, and the misleading framing is explained separately.
- **Ambiguous claims** <span class="dss-scope">Fact-checking only</span>: an ambiguous claim is assessed in its most plausible reading, and the other material readings are named. In decision support, the person clarifies a material ambiguity.
- **Basis and overturn conditions.** Each verdict states how well the evidence supports it and names the evidence or finding that would change it. A true, mostly true, false or mostly false verdict on an atomic claim cites at least one considered evidence item in its direction, or a recorded inference or calculation.
- **Decisive atomic claims.** A true or mostly true overall verdict requires each atomic claim decisive for it to point the same way: true or mostly true if it supports the claim, false or mostly false if it contradicts it; the reverse holds for false or mostly false overall verdicts. Which atomic claims are decisive is itself a model judgment and is shown in the report.
- **Contradiction notice** <span class="dss-scope">Fact-checking only</span>: if a verdict still breaks the rule on decisive atomic claims after a correction attempt, it keeps its label but carries a prominent notice naming the atomic claim that is not established. In decision support, such a result is held until the contradiction is resolved.

### Evidence

- **Right subject and context.** For the atomic claims a verdict rests on, the report shows whether each cited passage concerns the same subject, matter, time and relation, and names open questions.
- **Search in both directions.** For each atomic claim, the search also looks for contradicting evidence. Every search query is recorded with its purpose, and the report says whether a search for contradicting evidence ran. A retrieved document is a candidate; it counts as evidence only after it has been assessed.
- **Evidence assessed before it counts.** The model first assesses whether each cited document substantiates the statement it is cited for, for example with data, method or checkable sources, and whether it is the original source; a record of what someone said shows that it was said, not that it is true. Material that does not substantiate its statement is not counted as evidence and is named in the report; baseless claims such as fabrications are never considered. For evidence a verdict rests on, the original source is sought within the run's search allowance; if it is not found or not sought, the report says so.
- **Weighed, not counted.** Each evidence item gets a reasoned weight level, from very strong to very weak, based on its documentation, origin, independence and the reliability of its source; very weak items are not considered and are named in the report. Items that share an origin count as one basis, not as independent confirmation. The same rules apply to supporting and contradicting evidence. No numeric evidence weights, evidence or source scores, or formulas apply.
- **Scope and claim assessment boundaries.** Each evidence item records the scope of its data, such as method, period and region. Evidence with compatible scopes can be grouped into claim assessment boundaries. Where boundaries lead to different conclusions, the assessment shows a finding for each and explains the difference; each atomic claim keeps one verdict.
- **Source reliability.** Ratings rest on retrieved, cited third-party material, such as fact-checks, correction records and ownership; without such material the result is insufficient data, not a low rating. Where no evaluation is available, reliability is shown as not assessed. These assessments are shown to readers.

## Consistency of judgments

- **Repeated runs:** if runs are repeated on the same captured evidence, a result is never set by picking a favourable run, rerunning until runs agree, or voting or averaging. A single run means stability is not measured. Whether and how run variation is shown is decided after reader testing.
- **Separate measures:** evidence sufficiency and any observed run variation stay separate and are never merged into one score. Run variation is also kept apart from the result and its confidence. A model's stated confidence always comes with its evidence-based reasons, is not a calibrated probability and never establishes correctness on its own.

<a id="gaps-and-limits"></a>

## Gaps, limits and corrections

- **Missing steps:** a required task or check that cannot run is named as missing, never silently skipped.
- **Named limits instead of stops** <span class="dss-scope">Fact-checking only</span>: uncertainty, missing or conflicting evidence, missing steps and atomic claims that could not be assessed are named in the report, and the analysis continues; access, disclosure and release checks still apply. In decision support, such findings can hold the work or limit the result until the person clarifies them.
- **Corrections:** an issued report edition is never changed silently. A correction or reassessment creates a new dated edition linked to the earlier one, stating what changed and why; the earlier edition keeps its content and shows that it was superseded.

## Decisions (later stage)

Applies to comparing options for a decision.

- **People set the basis:** goals, constraints and priorities are confirmed by the responsible person.
- **Open points:** the report names open decisive points as questions for the person deciding; possible consequences of an error are stated only where evidence supports them.

## People and software

- **Same functions through an API:** technical users, such as other software and AI agents acting for a responsible person, get the same functions as people, with their own identity and never more rights. Confirming goals and approving actions stay with people.

## Evaluation

- **Before routine use:** methods must pass independent evaluation against reference judgments by competent reviewers, with pass criteria set before testing. Until then, results are labelled as coming from a method not yet independently evaluated.
- **Independent reference judgments:** reviewers record their judgments before seeing DSS results, and disagreements are reported, not forced into consensus. For claims, evaluation covers the reading, the atomic claims and the verdicts, and compares English and German versions of the same claims.

See the [analysis pipeline](Pipeline.md) for how these principles fit into the planned workflow.
