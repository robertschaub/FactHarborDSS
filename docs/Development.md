# Working on the project

FactHarborDSS is at the requirements and architecture stage. The [home page](index.md) explains its purpose and the [roadmap](Roadmap.md) identifies the selected sequence. For practical partnerships, funding and advisory support, start with [Cooperation](Cooperation.md). This page covers scoped repository work.

## Propose a useful contribution

Open a [repository issue](https://github.com/robertschaub/FactHarborDSS/issues) describing the problem or contribution, who it helps and the evidence that would show it is useful. For substantial work, agree the scope and acceptance criteria with the maintainer before implementing it. A roadmap item is not an assigned implementation task.

For a public claim example, include the exact claim or question, relevant period and scope, public source links, known counterevidence and what makes the case difficult. Link to sources rather than uploading captured collections. Describe unresolved questions rather than supplying a preferred verdict as an answer key.

For evaluation help, explain the judgment or comparison you can contribute and its limits. Development examples and protected evaluation cases serve different purposes: do not post protected cases or answers in public issues. Describe the evaluation help you can offer without including that material, and agree a suitable exchange route with the maintainer before sharing it.

For cooperation or sponsorship, describe the expertise or bounded work you could support and the outcome you would want to evaluate. Funding terms, commitments and continuation criteria need a separate agreement; this repository does not yet offer a donation programme or funding target.

## Material suitable for this repository

Use public-safe prose, original synthetic examples and source material whose reuse and notices have been checked. Do not submit customer inputs, private evidence or reports, credentials, private paths or raw execution logs. Public source availability alone does not settle reuse or processing permission.

Keep proposed behavior, accepted direction, implemented behavior and measured results distinct. Label authored examples as illustrative. Do not attribute predecessor demonstrations or results to DSS. The repository and its documentation are public. Repository-wide licensing is still pending; do not import a predecessor's licensing terms by assumption.

## Changes and review

Keep each change focused and preserve unrelated work. Describe the intended outcome, affected files and meaningful checks. The existing [agent workflow](https://github.com/robertschaub/FactHarborDSS/blob/main/docs/agents/Workflow.md) owns the detailed development and review procedure; agents must also read [AGENTS.md](https://github.com/robertschaub/FactHarborDSS/blob/main/AGENTS.md). No contribution should require access to private planning files. If a task lacks a required contract or acceptance condition, identify that gap before dependent work.

Start an agent client in the repository root. If it does not load project instructions automatically, explicitly ask it to read AGENTS.md and follow its workflow pointer; the client name alone does not establish that the instructions were loaded.

Documentation changes need correct relative links, a strict MkDocs build and `git diff --check`. The documentation build is available; there is no runnable DSS application or application test suite yet. The selected stack and future test direction are described in [Architecture](Architecture.md).

Within an authorized development task, scoped reversible edits and focused offline checks can proceed without repeated approval. Live acquisition, provider evaluation, deployment and external actions require their own applicable scope and permissions. Use synthetic fixtures for default checks and keep evidence/results outside Git when they are not suitable for publication.

Baseline delivery needs acceptance and quality checks; repairs need relevant invariant and non-regression checks. Changes to analytical behavior additionally need predefined benefit criteria, bounded evaluation and independent efficacy review before adoption. Passing a build alone does not demonstrate usefulness. Follow the workflow's protections for acceptance assertions and held-out cases.

In a pull request, explain what changed, why, what was checked and any remaining limitations. Report actual results rather than anticipated success.

## Build and preview the documentation

Use Python 3.12 and the pinned documentation dependencies from the repository root. A local virtual environment keeps them separate from other projects.

```powershell
python -m venv .venv
.venv\Scripts\python -m pip install -r requirements-docs.txt
.venv\Scripts\python -m mkdocs build --strict
.venv\Scripts\python -m mkdocs serve --dev-addr 127.0.0.1:8000
```

On macOS or Linux, use `.venv/bin/python` for the same commands. Open the local address printed by MkDocs. Built files go into the ignored `site/` directory.

Edit the Markdown pages in `docs/`; `mkdocs.yml` owns site navigation. Root README and CONTRIBUTING are entry points, while the pages own the substantive content. The repository's agent workflow remains under `docs/agents/` and is deliberately excluded from the reader-facing site and search index.

The site uses Material for MkDocs with local styles, system fonts and local image/diagram assets. It has no analytics or remote font dependency. A documentation build neither starts DSS services nor calls assessment providers.

## Publication boundary

The repository and its documentation are public. The MkDocs site can be built and previewed locally; no GitHub Pages deployment workflow is installed. Website hosting and repository-wide licensing remain separate decisions.

Before publishing additional material, review its disclosure scope and reuse terms, including any agent guidance excluded from the site. Preserve source-specific notices while repository-wide licensing remains undecided. Website hosting needs its own configuration and authorization.
