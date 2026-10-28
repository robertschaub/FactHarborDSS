# FactHarborDSS

FactHarborDSS is a planned Decision Support System for factual-claim assessment and comparison of options against evidence and human-confirmed goals.

**Status — 28 October 2026:** requirements and architecture work in progress; the first development milestone has not started. The documentation site is buildable. The DSS application is not yet implemented or evaluated.

## Read the documentation

- [Start here](docs/index.md)
- [Association and projects](docs/Background.md)
- [FactHarbor application (Alpha) in practice](docs/FactHarbor.md)
- [Our AI Charter and EGA](docs/Charter-and-EGA.md)
- [Purpose and approach](docs/Concept.md)
- [Analysis pipeline and agent debate](docs/Pipeline.md)
- [Why a fresh implementation](docs/Rationale.md)
- [Roadmap](docs/Roadmap.md) and [planned architecture](docs/Architecture.md)
- [Partnerships and funded development](docs/Cooperation.md)
- [Development guide](docs/Development.md) and [contact routes](docs/Links.md)

The MkDocs site organizes these pages into Overview, Product, Development and Cooperation. It preserves the distinction between the existing Alpha, the Charter/EGA concepts and planned DSS capabilities.

Detailed requirements, specifications and architecture documents currently live in the related private repository; see [Planning documents](docs/Architecture.md#planning-documents).

## Preview locally

With Python 3.12:

```powershell
python -m venv .venv
.venv\Scripts\python -m pip install -r requirements-docs.txt
.venv\Scripts\python -m mkdocs serve --dev-addr 127.0.0.1:8000
```

Open the local address printed by MkDocs. Use `.venv\Scripts\python -m mkdocs build --strict` for a checked static build. See the [development guide](docs/Development.md#build-and-preview-the-documentation) for details and the macOS/Linux command path.

## Repository work

[CONTRIBUTING.md](CONTRIBUTING.md) routes to the cooperation and development pages. Agents start with [AGENTS.md](AGENTS.md) and the [agent workflow](docs/agents/Workflow.md). Contributions and future builds must remain self-contained without private planning material.

Implementation, live evidence acquisition, provider spending and deployment require an explicitly agreed task. This repository and its documentation are public; repository-wide licensing remains pending. No GitHub Pages deployment is enabled by the local documentation setup.
