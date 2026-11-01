# Planned architecture

FactHarborDSS is in planning. The diagrams show the selected design, not an implemented or validated system.

[![Planned architecture: TypeScript browser, modular .NET application and worker, PostgreSQL evidence store, separate Source Reliability service, and checked external calls](assets/system-architecture.svg)](assets/system-architecture.svg)

*Open the diagram for a larger view. Components show responsibilities, not security isolation. Technical users would call the same application API; the diagram shows the browser path only. Original diagram; repository-wide licensing remains undecided.*

## Core design

- **One application:** a TypeScript interface served by C#/.NET 10, with a worker initially running in the same process.
- **Traceable evidence:** PostgreSQL stores captured web content, source versions, assessments, reports and durable jobs. Full-text search provides the retrieval baseline.
- **Repeatable evidence basis:** reassessment uses the saved version without hidden fetching. Refreshes create new versions; model outputs may still differ.
- **Separate source evaluation:** Source Reliability has its own service interface and database. Its role in Stage 1 remains undecided.
- **Permissions enforced in code:** access, report release and external actions are checked separately. Retrieved documents and AI assessments cannot grant authority; source restrictions also apply to derived reports.

Stage 1 focuses on claim checking with public web sources and saved evidence. From Stage 1 on, technical users such as AI agents acting for a responsible person would get the same functions as people through the same API as the browser interface; confirmations, permissions and approvals stay with people. Broader decision workflows and controlled external actions come later. The [pipeline](Pipeline.md) explains the broader assessment and agent-debate design.

## Core data model

Like the FactHarbor Alpha, DSS splits a claim into atomic claims, statements that can each be checked on their own, and gives each one its own assessment. The overall assessment builds on these. Assessments cite evidence items that quote exact passages in captured documents, and evidence with a compatible scope can be grouped into claim assessment boundaries. Every judgment records how it was established, and the report names gaps as limitations. The [principles](Requirements.md) set out the rules these records serve.

```mermaid
erDiagram
  Claim ||--|{ AtomicClaim : "split into"
  Claim ||--o{ OverallAssessment : "assessed in"
  OverallAssessment ||--|{ AtomicClaimAssessment : "built on"
  AtomicClaim ||--o{ AtomicClaimAssessment : "assessed in"
  AtomicClaim |o--o{ SearchQuery : "searched with"
  SearchQuery }o--o{ Document : finds
  AtomicClaimAssessment ||--o{ Citation : cites
  Citation }o--|| EvidenceItem : "refers to"
  AtomicClaimAssessment ||--o{ BoundaryFinding : "finds per boundary"
  BoundaryFinding }o--|| ClaimAssessmentBoundary : for
  ClaimAssessmentBoundary }o--o{ EvidenceItem : groups
  EvidenceItem }o--|| Document : "extracted from"
  Document }o--o{ Document : "derived from"
  Document }o--|{ Source : "published by"
  Source ||--o{ ReliabilityEvaluation : "rated in"
  EvidenceItem }o--o| ReliabilityEvaluation : "weighed using"
  ReportEdition }o--o{ OverallAssessment : presents
  ReportEdition }o--o{ Limitation : names
  AtomicClaimAssessment |o--o{ Limitation : "limited by"
  OverallAssessment |o--o{ Limitation : "limited by"
  Claim {
    text wording "exact, as submitted"
    text context "speaker, date, venue"
  }
  AtomicClaim["Atomic claim"] {
    text statement
    label role "supports, contradicts or context"
    text expected_evidence
    label harm_potential "for scrutiny, never weight"
    text necessary_assignments "subject, matter, time, relation"
  }
  AtomicClaimAssessment["Atomic claim assessment"] {
    int truth_score "0-100, with a verdict only"
    label verdict "seven labels, unverified or not assessed"
    label confidence
    text overturn_conditions
    label established_by
  }
  OverallAssessment["Overall assessment"] {
    text reading "other readings named"
    int truth_score "with a verdict only"
    label verdict "or not synthesized, with reason"
    label confidence
    text decisive_atomic_claims "per direction"
    label established_by
  }
  SearchQuery["Search query"] {
    text query
    label purpose "supporting, contradicting, origin or follow-up"
  }
  Citation {
    label direction "supports, contradicts or qualifies"
    label assignment "for decisive atomic claims"
    label established_by
  }
  BoundaryFinding["Boundary finding"] {
    label direction "supports, contradicts or mixed"
    text reasoning
  }
  ClaimAssessmentBoundary["Claim assessment boundary"] {
    text scope "compatible method, period, region"
  }
  EvidenceItem["Evidence item"] {
    text statement_and_quote
    label foundedness
    label origin_status
    text scope "method, period, region"
    label weight_level "very strong to very weak"
    label established_by
  }
  Document["Captured document"] {
    time captured_at
    label authenticity "for decisive evidence"
  }
  Source {
    text publisher_or_author
  }
  ReliabilityEvaluation["Reliability evaluation"] {
    label rating "seven labels or insufficient data"
    text cited_material
    date evaluated_on
  }
  ReportEdition["Report edition"] {
    time issued_at
    text supersedes "earlier edition, if corrected"
  }
  Limitation {
    label type
    text reason
  }
```

*Simplified conceptual model of the planned design, not a database schema. Read each line as a sentence, for example "a claim is split into one or more atomic claims". At a line end, a bar means one, a crow's foot many and a circle zero.*

## Planning documents

[How it would work](Concept.md), the [principles](Requirements.md) and the [analysis pipeline](Pipeline.md) complement this architecture overview. We supply detailed requirements and acceptance criteria with each agreed piece of work.
