# FactHarborDSS roadmap

As of 28 October 2026, the delivery sequence below is selected and the first milestone is not started. These are development and evaluation stages, not release dates or demonstrated capabilities. Implementation and live operations still require agreed scope, permissions and resource limits.

## 1. Capture and replay web evidence

The first milestone is a small human-facing development path: use one configured search route and an explicitly agreed public source set, capture bounded content in PostgreSQL, inspect the exact stored text and passages, and run a minimal claim assessment against that evidence. Public-wiki handling is planned within this boundary; authenticated or private wiki acquisition remains excluded. The implementation task must fix the exact source selection, formats, languages and adapters before dependent work; this overview approves no connector or source set.

Completion needs an actual permitted acquisition and model assessment, not only a synthetic demonstration. The evidence basis must retain source versions, extraction details, coverage and citations. Reassessment must use the pinned stored evidence without hidden searches or fetches; an explicit refresh must create a new result. Empty, partial, missing, corrupt and denied inputs must remain distinguishable. Model calls during reassessment must still be permitted and accounted for.

Someone other than the project owner must also try the path unaided and explain whether they understood the conclusion and uncertainty, where it was wrong, what they would do next and what would make them return. This reader check and structural tests do not establish analytical correctness or readiness for ordinary use.

Before work starts, the implementation task needs defined limits, operator identity and access, an assessment method and output states, acceptance checks and a reader arrangement. Live operation additionally needs approved providers, data use, total resource limits, retention and recovery rules. There is no committed start date.

## 2. Evaluate claim assessment

After the first milestone's closeout and reader check, the next candidate is a separately scoped comparison using fixed database evidence. It should compare DSS with a competently configured assistant or checking baseline under comparable evidence and criteria.

The evaluation must define reference judgments, acceptance criteria, protected cases, revision limits and independent review before testing. Relevant outcomes include justified conclusions, unsupported conclusions, uncertainty handling, unnecessary refusals and the reader's preparation and correction effort. Storing citations or passing implementation tests is insufficient evidence of benefit.

Three questions need separate answers: did acquisition find suitable evidence; did assessment use a given evidence set well; and did the complete reviewer workflow help? A comparison on fixed evidence addresses the second question, not all three. No superiority result or qualification is claimed. If an existing approach meets the need with less effort, narrowing or reconsidering DSS remains a valid outcome.

## 3. Pilot file-based claim and decision support

The later pilot would search a real, representative, versioned file collection and support both descriptive claims and one bounded decision-comparison workflow across multiple cases. The recurring decision family, intended reader and evaluation scope remain to be selected.

Files would be manually supplied in an authorized read-only collection accessible to the service. FileEvidenceService is the planned search boundary, not a file-management or upload product. The pilot would retrieve relevant material and counterevidence, preserve the versions used and explain collection coverage and limitations.

For a decision, the authorized human must confirm objectives, alternatives, constraints and priorities, or adopt an approved reusable template. Historical or controlled shadow evaluation and independent review must precede qualification for ordinary use. The pilot needs evidence of useful justified recommendations as well as appropriate uncertainty and holds. A synthetic example is not a successful pilot.

## Broader product direction

Beyond these milestones, scope includes combined public/private acquisition, multi-customer operation, authenticated working-agent access and governed retrieval, broader decision workflows, adaptive analysis, additional report formats and controlled external actions. The full first release, which these staged milestones do not complete, includes public-only, private-only and combined evidence scopes, a gate service and an enforced HTTP/webhook action integration with idempotency and status lookup; its detailed contract and permitted effects remain to be specified. Causal or predictive assessment and high-stakes uses require separate qualification.

Source Reliability has a selected separate service and database boundary. Whether the first milestone includes a bounded lookup or explicitly records reliability as not assessed remains undecided. Full service delivery and live reliability evaluation are not automatically included in the first milestone.

See the [concept](Concept.md), [planned architecture](Architecture.md) and [cooperation options](Cooperation.md).
