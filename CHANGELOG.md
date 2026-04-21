# Changelog

All notable changes to this project will be documented in this file.

This project adheres to [Semantic Versioning](https://semver.org/) and [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) conventions.

---

## [Unreleased]

### Planned
- `prompts/analysis/` — process decomposition prompt templates
- `prompts/generation/` — report & document generation prompts
- `architectures/n8n/` — workflow diagrams for HBM data pipeline
- `scripts/validators/` — LLM output validation framework
- `docs/kpi-framework.md` — full KPI measurement methodology
- `docs/pilot-guide.md` — MVP deployment step-by-step guide

---

## [0.1.0] — 2026-04-21

### Added
- `README.md` — full project overview, repository structure, tech stack, quick start, KPI targets, and contributing guide
- `CHANGELOG.md` — initialized changelog following Keep a Changelog format
- Defined 7-phase AI automation design methodology
- Documented core technology stack: n8n, GitHub Actions, OpenAI, LangChain, Notion API, Python
- Established standardized prompt template structure (Role / Context / Input / Instructions / Output Format / Quality Gates)
- Set baseline KPI targets: ≥60% time saved, ≤5% error rate, ≥75% automation coverage, −40% cost per document

### Repository
- Initialized public repository: `GilbertKwak/ai-automation-hub`
- Default branch: `main`

---

## Version Conventions

| Version Segment | When to Increment |
|----------------|------------------|
| `MAJOR` (X.0.0) | Breaking changes to prompt schemas or architecture blueprints |
| `MINOR` (0.X.0) | New automation modules, prompt categories, or architecture patterns added |
| `PATCH` (0.0.X) | Bug fixes, prompt refinements, documentation corrections |

---

## Change Categories

- **Added** — new features, files, prompts, or scripts
- **Changed** — updates to existing functionality or documentation
- **Deprecated** — features scheduled for removal in a future version
- **Removed** — features or files deleted in this release
- **Fixed** — bug fixes or prompt correction
- **Security** — vulnerability patches or access control changes
