# From FactHarbor to DSS

<a id="factharbor-application"></a>
<a id="read-the-result"></a>
<a id="inspect-the-evidence"></a>

The existing **FactHarbor application (Alpha)** provides experience to build on. [See the FactHarbor report walkthrough](https://robertschaub.github.io/FactHarbor/#read-a-report), including sources, evidence and separate verdict and confidence labels.

<a id="what-dss-would-carry-forward"></a>

## What DSS keeps from the Alpha

DSS is designed to keep the Alpha's analysis structure:

- **Atomic claims, each with its own verdict:** a verdict from 0 (false) to 100 (true) with seven labels and a separate confidence.
- **Evidence items** with the extracted statement, the quoted passage, the source type, whether the item derives from another source, and the scope of its data, such as method, period and region.
- **Claim assessment boundaries** that group evidence with a compatible scope, with a finding per boundary where they lead to different conclusions.
- **Search for contradicting evidence**, not only for support.
- **Source reliability** evaluated by a model, separately from the claim.
- **Challenges by model roles**, where only evidence-backed objections change a verdict, and misleading framing explained separately from truth.

DSS would also add a more explicit basis for preserving and replaying the evidence used, and later compare options against human-confirmed goals and constraints. These are design intentions, not delivered capabilities or inherited proof of quality; DSS must demonstrate its own usefulness. The **FactHarbor association** remains the organization behind both applications.

<a id="how-the-alpha-assesses-evidence-today"></a>

## What DSS changes

The Alpha column describes its source code and default configuration as of late October 2026.

| | Alpha | Planned DSS |
|---|---|---|
| Overall verdict | Fixed code combines the claim verdicts, weighting each by centrality, potential harm, confidence, agreement across claim assessment boundaries, whether it carries the input's key truth condition, probative value and share of derivative evidence; where claims point in different directions, a model decides within fixed bounds | A labelled model judgment built on the decisive atomic claims, without averaging or counting |
| Evidence before it counts | Models rate probative value; code filters out items rated low and items from opinion sources | The documentation and origin of each cited item are assessed and shown |
| Evidence weight | Probative value and derivative share enter the weighting rules | Reasoned weight levels from very strong to very weak, without a formula |
| Minimum evidence | With too few items, no directional item, or too little diversity of source types and websites, code sets a claim to unverified | A true, mostly true, false or mostly false verdict cites at least one considered item in its direction, or a recorded inference or calculation; no minimum count |
| Repeated runs | Code lowers confidence when repeated runs disagree | Run variation is kept separate from the verdict and its confidence |
| Source reliability | A model rates each source from a search about it, a second model may correct the rating, and code caps it for some source types; its weighting of verdicts is switched off by default | Rated from cited third-party material, with insufficient data shown separately and no caps or formulas |
| Derivative evidence | Flagged and down-weighted; originals are not fetched, though a claim lacking primary sources may get one extra search | Originals of the evidence a verdict rests on are sought within the search allowance |

See [how it would work](Concept.md), the [principles](Requirements.md), [reasons for a fresh implementation](Rationale.md) and the [planned architecture](Architecture.md).
