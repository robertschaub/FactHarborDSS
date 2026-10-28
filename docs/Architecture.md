# Planned FactHarborDSS architecture

The selected technical direction, as of 28 October 2026, is a TypeScript browser interface served by a C#/.NET 10 application, a .NET worker sharing backend modules, and PostgreSQL. This is an architecture overview; code, physical schemas, provider integrations and deployment are not yet implemented.

## System at a glance

[![Planned system architecture: TypeScript browser, one modular .NET application and co-hosted worker, application PostgreSQL, a separate Source Reliability interface and database, and checked external calls](assets/system-architecture.svg)](assets/system-architecture.svg)

*Open the diagram for a larger view. Boxes show responsibilities, not independently deployed or security-isolated services. All components and controls shown are planned.*

Trusted application code owns permissions, task admission, accepted state and release. The worker shares evidence, assessment and reporting modules; model-produced findings are candidates, not authority. Durable records remain in PostgreSQL across worker restarts.

The separate Source Reliability store is an adopted boundary; whether to integrate it in the first milestone remains an open scope choice. Later file evidence, working-agent clients and external actions are omitted to keep this view focused. The [analysis pipeline](Pipeline.md) shows how assessment and selective agent debate would work inside these responsibilities.

## Application and worker

The initial shape is one modular application, with the worker hosted in the same process. Durable job state belongs in PostgreSQL so work does not depend on an in-memory queue. Relevant state changes and their job intents should commit together; long-running acquisition and inference should run outside database transactions.

| Responsibility | Planned boundary |
|---|---|
| Browser interface | TypeScript assets served by .NET; permission-checked access to evidence and reports. |
| Application policy and state | Cases, current permissions, job admission, accepted results and report release. |
| Evidence acquisition and retrieval | Bounded capture/extraction, exact source and passage references, coverage and explicit failure states. |
| Analytical module | Typed assessment candidates for validation; no authority to grant access, release reports or approve actions. |
| Application database | Cases, captured evidence, assessments, reports, permissions and durable jobs. |
| Source Reliability service | Its own PostgreSQL database and interface for versioned source/publisher evaluations. |

Shared modules are a responsibility boundary, not process-level security isolation. A separately deployed worker, message broker, vector database or mandatory multi-agent debate chain is not required for the initial milestone. Broader adaptive analysis remains later scope.

## Evidence storage and replay

The selected storage design keeps captured web bytes, extracted text, passage references and acquisition metadata in PostgreSQL. Database full-text search is the retrieval baseline. Captured representations and extracted views have distinct identities; partial capture must remain labelled as partial.

An assessment binds to an exact evidence result, including its source versions, passages and coverage. A new acquisition or changed extraction creates a new version rather than rewriting the basis of an earlier assessment. Replay uses retained versions without acquisition calls. Separately permitted model calls may still occur, and identical outputs are not guaranteed.

Retention and current rights govern every replay. Missing, deleted, corrupt or unauthorized inputs must produce explicit states without a hidden refetch or replacement with the latest version. Captured scripts and linked resources must not execute during replay. Historical evidence must retain its time basis rather than appear freshly verified.

For later FileEvidence use, manually supplied original files stay in authorized read-only locations outside the database. The application database holds permitted extracted views, indexes and version references. Reassessment from retained text and re-extraction from an original file are different operations with different availability requirements.

## Source Reliability

Source Reliability has a separate database and service interface; case evidence and reports stay together in the application database. Both databases may share a PostgreSQL server, and the service may initially run in the same deployment. Database separation alone does not establish tenant isolation.

The application would consume a permitted, exact evaluation version through the interface rather than access its tables directly. Source reliability is an input to assessment, not proof that a particular claim is true. Updating a source evaluation must not rewrite a previous report's input basis.

Lookup and evaluation/refresh are separate operations. A missing or expired evaluation must not silently become a trusted default score or trigger paid calls. Private case context must not enter reusable public evaluations. Integration in the first milestone remains an explicit scope choice, including the alternative of recording reliability as not assessed under the declared development method.

## Trust boundaries

The planned implementation must enforce case/source access, state transitions, arithmetic and structural validation in trusted deterministic code. Case access requires explicit sharing; source-use and recipient permissions are separate. An administrator or operator role does not by itself grant content access. Source restrictions also apply to derived conclusions and reports.

Semantic judgments such as relevance, equivalence and assessment use explicit model contracts with evaluated limitations. Lexical retrieval may select candidates, but keyword rules must not substitute for those judgments. Model output and retrieved documents cannot grant permissions.

For initial web acquisition, generated queries must use an explicitly authorized public input view. Trusted code must check exact outbound arguments, destination, purpose and current authorization before each call. A model cannot declare private context public. Caller-authored queries retain a separate exact-disclosure requirement. Human evidence inspection also needs current recipient and release checks.

Fetched text must be treated as untrusted evidence, never as instructions. Acquisition must reject private/local destinations and unsafe redirects, limit time, requests and content size, and prevent arbitrary page execution. These controls require offline verification before live use.

Synthetic identities belong only in offline tests. The planned live development path requires an actual identified, entitled operator. Identity/bootstrap details, supported formats and languages, provider choices, resource limits, retention/recovery policy and hosting remain unresolved for execution. Service roles and cross-database authorization, version retention and recovery also require detailed contracts and checks before use.

## Verification direction

The selected test direction is xUnit for backend and fixture checks, isolated PostgreSQL integration databases for database behavior, and browser-level checks of the assembled application. No test runner or application tests are installed here yet. Synthetic checks should cover both permitted paths and missing, partial, changed and denied inputs.

Passing these checks would establish only their covered behavior. Analytical usefulness requires the separate comparisons and reader evaluation described in the [roadmap](Roadmap.md). Contributor tasks must supply the public contracts and acceptance material needed for their scope; this overview is not a complete implementation specification.

## Planning documents

The detailed **requirements, specifications and architecture documents currently live in the related private FactHarborDSS-internal repository**. They remain work in progress and require review and refinement before implementation. These public pages summarize the direction; access to the private repository is restricted.

Public builds and contributions must remain self-contained. An agreed contribution needs the relevant public contracts and acceptance material supplied here before dependent work; it must not require access to private planning documents.
