# Changelog

All notable changes to this project will be documented in this file.

This project adheres to [Semantic Versioning](https://semver.org/) and [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) conventions.

---

## [Unreleased]

### Planned
- `prompts/consulting/variants/` — 도메인 특화 변형체 3종 (C-BCG-HBM / C-MCK-AI_INFRA / C-ADV-BSTAR)
- `prompts/analysis/` — process decomposition prompt templates
- `prompts/generation/` — report & document generation prompts
- `architectures/n8n/` — workflow diagrams for HBM data pipeline
- `scripts/validators/` — LLM output validation framework
- `docs/kpi-framework.md` — full KPI measurement methodology
- `docs/pilot-guide.md` — MVP deployment step-by-step guide

---

## [0.2.0] — 2026-04-28 [Phase G]

### Added — Consulting Prompt Library (PE-CON)
- `prompts/consulting/C-BCG-MASTER_v1.0.md` — BCG Matrix·Experience Curve·GenAI 통합 마스터
  - ID: C-006 | Level Selector: JUNIOR / EXECUTIVE / BOARD
  - Consulting_002.txt의 Basic·Advanced·Executive 3개 프롬프트를 1개로 통합
  - PE-3 종합 점수: 80 → 93 (+13)
- `prompts/consulting/C-MCK-MASTER_v1.0.md` — McKinsey 문제해결 통합 마스터
  - ID: C-007 | Level Selector: SENIOR / PARTNER / DIRECTOR
  - Consulting_002.txt의 Senior·Partner·Director·Global Director 4개 프롬프트를 1개로 통합
  - PE-3 종합 점수: 80 → 95 (+15)
- `prompts/consulting/C-ADV-MASTER_v1.0.md` — 전략 자문 페르소나 통합 마스터
  - ID: C-008 | Persona Selector: MBA_PROF / ADVISOR / CEO_ADVISOR / BOARD
  - Consulting_003-2.txt의 4개 페르소나 프롬프트를 1개로 통합
  - PE-3 종합 점수: 89 → 96 (+7)

### PE-3 Summary
| 프롬프트 | Before | After | Delta |
|---------|--------|-------|-------|
| C-BCG-MASTER | 80 | 93 | +13 |
| C-MCK-MASTER | 80 | 95 | +15 |
| C-ADV-MASTER | 89 | 96 | +7 |

### Source Files
- `Consulting_002.txt` — BCG + McKinsey 원본 (7개 프롬프트 → 2개 마스터)
- `Consulting_003-2.txt` — Strategic Advisory 원본 (4개 프롬프트 → 1개 마스터)

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
