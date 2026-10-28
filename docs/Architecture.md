# Planned architecture

FactHarborDSS is in planning. The diagram shows the selected design, not an implemented or validated system.

[![Planned architecture: TypeScript browser, modular .NET application and worker, PostgreSQL evidence store, separate Source Reliability service, and checked external calls](assets/system-architecture.svg)](assets/system-architecture.svg)

*Open the diagram for a larger view. Components show responsibilities, not security isolation. Original diagram; repository-wide licensing remains undecided.*

## Core design

- **One application:** a TypeScript interface served by C#/.NET 10, with a worker initially running in the same process.
- **Traceable evidence:** PostgreSQL stores captured web content, source versions, assessments, reports and durable jobs. Full-text search provides the retrieval baseline.
- **Repeatable evidence basis:** reassessment uses the saved version without hidden fetching. Refreshes create new versions; model outputs may still differ.
- **Separate source evaluation:** Source Reliability has its own service interface and database. Its role in the first milestone remains undecided.
- **Permissions enforced in code:** access, report release and external actions are checked separately. Retrieved documents and AI assessments cannot grant authority; source restrictions also apply to derived reports.

The first milestone focuses on web evidence and minimal claim assessment. Broader decision workflows, working-agent access and controlled external actions come later. The [pipeline](Pipeline.md) explains the broader assessment and agent-debate design.

## Planning documents

Detailed requirements, specifications and architecture documents currently reside in the related private **FactHarborDSS-internal** repository. Public contributions must receive the relevant contracts and acceptance criteria without requiring private access.
