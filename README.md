# FactHarborDSS

**[Read the documentation](https://robertschaub.github.io/FactHarborDSS/)**

FactHarborDSS is a planned Decision Support System for factual-claim assessment and comparison of options against evidence and human-confirmed goals.

**Status — 28 October 2026:** requirements and architecture work in progress; the first development milestone has not started. The DSS application is not yet implemented or evaluated.

## Documentation source files

- [Start here](docs/index.md)
- [Association and projects](docs/Background.md)
- [From FactHarbor to DSS](docs/FactHarbor.md)
- [Our AI Charter and EGA](docs/Charter-and-EGA.md)
- [Purpose and approach](docs/Concept.md)
- [Analysis pipeline and agent debate](docs/Pipeline.md)
- [Why a fresh implementation](docs/Rationale.md)
- [Planned architecture](docs/Architecture.md)
- [Partnerships and funded development](docs/Cooperation.md)
- [Contribution guide](CONTRIBUTING.md) and [contact routes](docs/Links.md)

The MkDocs site organizes these pages into Overview, Product and Cooperation. It preserves the distinction between the existing Alpha, the Charter/EGA concepts and planned DSS capabilities.

## Preview locally

With Python 3.12:

```powershell
python -m venv .venv
.venv\Scripts\python -m pip install -r requirements-docs.txt
.venv\Scripts\python -m mkdocs serve --dev-addr 127.0.0.1:8000
```

Open the local address printed by MkDocs. Use `.venv\Scripts\python -m mkdocs build --strict` for a checked static build. On macOS/Linux, use `.venv/bin/python` in the same commands. Edit pages in `docs/` and navigation in `mkdocs.yml`; generated files go to the ignored `site/` directory. The agent workflow is excluded from the site.

## Repository work

[CONTRIBUTING.md](CONTRIBUTING.md) explains how to propose and check changes. Agents start with [AGENTS.md](AGENTS.md) and the [agent workflow](docs/agents/Workflow.md). Contributions and future builds must remain self-contained without private planning material.

Implementation, live evidence acquisition, provider spending and application deployment require an explicitly agreed task. This repository and its documentation are public; repository-wide licensing remains pending.

Pull requests to `main` run a strict documentation build without deploying. The MkDocs site is published through GitHub Pages. Documentation changes pushed to `main` are built and published automatically by the [documentation workflow](.github/workflows/deploy-docs.yml).
