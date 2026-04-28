# PE-CON — Consulting Prompt Library Index

> **Category**: Prompt Engineering / Consulting (PE-CON)  
> **Version**: 1.1.0 | **Last Updated**: 2026-04-28 | **Phase**: G-3  
> **Maintainer**: Gilbert Kwak | **Repo**: `GilbertKwak/ai-automation-hub`

---

## 개요 / Overview

PE-CON은 **BCG · McKinsey · CEO Strategic Advisor** 수준의 컨설팅 프레임워크를  
Gilbert의 핵심 도메인(HBM Salvage · AI 인프라 · B-Star sCO2)에 직접 적용하기 위한  
프롬프트 라이브러리입니다.

> PE-CON is a prompt library applying BCG · McKinsey · CEO Advisor frameworks  
> directly to Gilbert's domains: HBM recycling, AI infrastructure, and B-Star sCO2 commercialization.

---

## 📁 Directory Structure

```
prompts/consulting/
├── README.md                        ← 현재 파일 (마스터 인덱스)
│
├── C-BCG-MASTER_v1.0.md            (C-006) BCG 통합 마스터
├── C-MCK-MASTER_v1.0.md            (C-007) McKinsey 통합 마스터
├── C-ADV-MASTER_v1.0.md            (C-008) Strategic Advisor 통합 마스터
│
└── variants/
    ├── C-BCG-HBM_v1.0.md           (C-006-HBM) BCG × HBM 재활용 시장
    ├── C-MCK-AI_INFRA_v1.0.md      (C-007-AI)  McKinsey × AI 데이터센터
    └── C-ADV-BSTAR_v1.0.md         (C-008-BS)  CEO Advisor × B-Star sCO2
```

---

## 📋 전체 프롬프트 인덱스 / Full Prompt Index

### 🔷 Masters (부모 프롬프트)

| ID | 파일 | 프레임워크 | 레벨 셀렉터 | PE-3 | 주요 용도 |
|----|------|-----------|------------|------|----------|
| **C-006** | [C-BCG-MASTER_v1.0.md](./C-BCG-MASTER_v1.0.md) | BCG Growth–Share Matrix · Experience Curve · GenAI | `[LEVEL: JUNIOR/EXECUTIVE/BOARD]` | **93** | 사업 포트폴리오 전략, 원가경쟁력 분석 |
| **C-007** | [C-MCK-MASTER_v1.0.md](./C-MCK-MASTER_v1.0.md) | McKinsey 7S · Issue Tree · SGI · MECE | `[LEVEL: SENIOR/PARTNER/DIRECTOR]` | **95** | 복잡 문제해결, Partner급 전략 보고서 |
| **C-008** | [C-ADV-MASTER_v1.0.md](./C-ADV-MASTER_v1.0.md) | CEO Advisor · BATNA · Assumption Attack | `[PERSONA: MBA_PROF/ADVISOR/CEO_ADVISOR/BOARD]` | **96** | 고위험 의사결정, 투자자 설득, 협상 |

---

### 🔶 Domain Variants (도메인 특화 변형체)

| ID | 파일 | 부모 | 도메인 | PE-3 | 핵심 차별점 |
|----|------|------|--------|------|------------|
| **C-006-HBM** | [variants/C-BCG-HBM_v1.0.md](./variants/C-BCG-HBM_v1.0.md) | C-006 | HBM 반도체 재활용 시장 | **95** | 4포지션(Star·Cash Cow·QM·Dog) HBM 직접 매핑, Portfolio Decision Logic 내장 |
| **C-007-AI** | [variants/C-MCK-AI_INFRA_v1.0.md](./variants/C-MCK-AI_INFRA_v1.0.md) | C-007 | AI 데이터센터 열관리 | **96** | Decision Question(sCO2 vs 액침냉각 vs 하이브리드) + Value Leakage Tree + SGI |
| **C-008-BS** | [variants/C-ADV-BSTAR_v1.0.md](./variants/C-ADV-BSTAR_v1.0.md) | C-008 | B-Star sCO2 상업화 | **97** | 4상황별 Response Protocol + Mandatory Diagnostic 3종 + IR 논리 Framework |

---

## ⚡ Quick-Reference Usage

### 언제 어떤 프롬프트를 쓰는가?

| 상황 | 권장 프롬프트 | 호출 예시 |
|------|-------------|----------|
| HBM Salvage 포트폴리오 포지셔닝 | **C-006-HBM** | `C-BCG-HBM 분석 실행` |
| HBM Salvage 임원 보고서 작성 | **C-006** `[LEVEL: EXECUTIVE]` | `C-BCG-MASTER [LEVEL: EXECUTIVE]` |
| AI 데이터센터 열관리 시장 진입 결정 | **C-007-AI** | `C-MCK-AI_INFRA 실행` |
| sCO2 vs 액침냉각 포지셔닝 심화 | **C-007-AI** `[HYPOTHESIS: H2]` | `C-MCK-AI_INFRA [HYPOTHESIS: H2]` |
| B-Star Series A IR 논리 점검 | **C-008-BS** | `C-ADV-BSTAR 실행` |
| B-Star GTM 경로 결정 | **C-008-BS** `[SITUATION: GTM]` | `C-ADV-BSTAR [SITUATION: GTM]` |
| B-Star 피벗 판단 | **C-008-BS** `[SITUATION: PIVOT_CHECK]` | `C-ADV-BSTAR [SITUATION: PIVOT_CHECK]` |
| 일반 McKinsey 문제해결 (Partner급) | **C-007** `[LEVEL: PARTNER]` | `C-MCK-MASTER [LEVEL: PARTNER]` |
| CEO/이사회 수준 전략 자문 | **C-008** `[PERSONA: BOARD]` | `C-ADV-MASTER [PERSONA: BOARD]` |

---

## 🔗 Cross-Link Matrix

```
C-006 (BCG MASTER)
  └── C-006-HBM ──── HBM 포트폴리오 포지셔닝
          │
          └──▶ C-007-AI (AI 인프라 열관리 포지셔닝)
                   │
                   └──▶ C-008-BS (B-Star sCO2 상업화 자문)
                             │
                             └──▶ C-007-AI (자원 배분 시퀀싱)

C-007 (MCK MASTER)
  └── C-007-AI ──── AI 데이터센터 McKinsey 문제해결
          │
          └──▶ C-006-HBM (HBM Cash Cow → sCO2 투자 재원)

C-008 (ADV MASTER)
  └── C-008-BS ──── B-Star CEO 자문 4상황
          │
          ├──▶ C-007-AI (GTM 경로 PoC 확보 전략 연계)
          └──▶ C-006-HBM (HBM Salvage Cash Cow화 연계)
```

---

## 📊 PE-3 Score Summary

| 프롬프트 | 명확성 | 구조성 | 특이성 | 실행가능성 | 적용가능성 | **종합** |
|---------|--------|--------|--------|-----------|-----------|--------|
| C-006 (BCG MASTER) | 92 | 94 | 90 | 93 | 94 | **93** |
| C-007 (MCK MASTER) | 95 | 96 | 93 | 95 | 96 | **95** |
| C-008 (ADV MASTER) | 96 | 95 | 95 | 96 | 97 | **96** |
| C-006-HBM | 95 | 96 | 93 | 95 | 97 | **95** |
| C-007-AI | 97 | 96 | 94 | 96 | 97 | **96** |
| C-008-BS | 97 | 96 | 97 | 97 | 98 | **97** |

> **PE-3 기준**: 명확성 · 구조성 · 특이성 · 실행가능성 · 적용가능성 5개 차원, 각 100점 만점

---

## 🔖 Naming Convention

```
C-[FRAMEWORK]-[DOMAIN]_v[MAJOR].[MINOR].md

예시:
C-BCG-MASTER_v1.0.md      → BCG 통합 마스터 v1.0
C-MCK-AI_INFRA_v1.0.md    → McKinsey × AI 인프라 변형체 v1.0
C-ADV-BSTAR_v1.0.md       → Advisor × B-Star 변형체 v1.0

ID 체계:
C-006           = 마스터 프롬프트
C-006-HBM       = 마스터(C-006)의 HBM 도메인 변형체
```

---

## 📅 Changelog (PE-CON)

| 버전 | 날짜 | 내용 |
|------|------|------|
| **v1.1.0** | 2026-04-28 | 도메인 변형체 3종 추가 (C-006-HBM · C-007-AI · C-008-BS) |
| **v1.0.0** | 2026-04-28 | 마스터 3종 초기 릴리즈 (C-006 · C-007 · C-008) |

전체 변경 이력 → [CHANGELOG.md](../../CHANGELOG.md)

---

## 🚀 Next Steps (Planned)

- [ ] `prompts/analysis/` — 프로세스 분해 프롬프트 템플릿
- [ ] `prompts/generation/` — 보고서 자동 생성 프롬프트
- [ ] `docs/kpi-framework.md` — KPI 측정 방법론
- [ ] `docs/pilot-guide.md` — MVP 배포 가이드
- [ ] C-006-HBM v1.1 — 경쟁사 오버레이 옵션 추가
- [ ] C-007-AI v1.1 — Hyperscaler PoC 협상 시나리오 확장
