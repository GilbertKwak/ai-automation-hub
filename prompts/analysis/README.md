# PE-ANA — Analysis Prompt Library Index

> **Category**: Prompt Engineering / Analysis (PE-ANA)  
> **Version**: 1.0.0 | **Last Updated**: 2026-04-28 | **Phase**: H  
> **Maintainer**: Gilbert Kwak | **Repo**: `GilbertKwak/ai-automation-hub`

---

## 개요 / Overview

PE-ANA는 **프로세스 분해 · 시장 분석 · 기술 성숙도 · 리스크 평가** 4대 분석 프레임을  
Gilbert의 핵심 도메인(HBM Salvage · AI 인프라 · B-Star sCO2)에 직접 적용하기 위한  
프롬프트 라이브러리입니다.

> PE-ANA is a prompt library applying four core analysis frameworks —  
> Process Decomposition, Market Analysis, Technology Readiness, and Risk Assessment —  
> directly to Gilbert's domains: HBM recycling, AI infrastructure, and B-Star sCO2.

---

## 📁 Directory Structure

```
prompts/analysis/
├── README.md                    ← 현재 파일 (마스터 인덱스)
├── A-DECOMP_v1.0.md             (A-001) 프로세스 분해
├── A-MARKET_v1.0.md             (A-002) 시장·경쟁 분석
├── A-TECH_v1.0.md               (A-003) 기술 성숙도 분석
└── A-RISK_v1.0.md               (A-004) 리스크 평가
```

---

## 📋 전체 프롬프트 인덱스 / Full Prompt Index

| ID | 파일 | 프레임워크 | 핵심 방법론 | PE-3 | 주요 용도 |
|----|------|-----------|-----------|------|----------|
| **A-001** | [A-DECOMP_v1.0.md](./A-DECOMP_v1.0.md) | Process Decomposition | MECE · Lean 7대 낭비 · Automation Matrix | **94** | 워크플로우 분해, 병목 식별, 자동화 후보 도출 |
| **A-002** | [A-MARKET_v1.0.md](./A-MARKET_v1.0.md) | Market & Competitive Analysis | TAM/SAM/SOM · Porter 5 Forces · Entry Timing | **95** | 시장 규모 추정, 경쟁 구도 분석, 진입 시기 결정 |
| **A-003** | [A-TECH_v1.0.md](./A-TECH_v1.0.md) | Technology Maturity & Readiness | TRL · CRL · IRL · IP Moat | **95** | 기술 성숙도 평가, 상업화 준비도 진단, 투자 준비도 |
| **A-004** | [A-RISK_v1.0.md](./A-RISK_v1.0.md) | Risk Assessment & Mitigation | FMEA · RCA(5-Why) · Monte Carlo Thinking | **94** | 리스크 등록부 작성, 근본 원인 분석, 시나리오 플래닝 |

---

## ⚡ Quick-Reference Usage

### 언제 어떤 프롬프트를 쓰는가?

| 상황 | 권장 프롬프트 | 호출 예시 |
|------|-------------|----------|
| HBM Salvage 소싱→분류 프로세스 개선 | **A-001** | `A-DECOMP [DOMAIN: HBM_SALVAGE] [DEPTH: L2]` |
| AI 데이터센터 냉각 시장 TAM 분석 | **A-002** | `A-MARKET [DOMAIN: AI_INFRA] [FOCUS: TAM_SIZING]` |
| B-Star sCO2 시장 진입 타이밍 | **A-002** | `A-MARKET [DOMAIN: BSTAR_SCO2] [FOCUS: ENTRY_TIMING]` |
| sCO2 기술 TRL·CRL 현황 진단 | **A-003** | `A-TECH [TECHNOLOGY: B-Star sCO2] [EVAL_TYPE: FULL]` |
| HBM4 열관리 기술 성숙도 평가 | **A-003** | `A-TECH [DOMAIN: HBM_THERMAL] [EVAL_TYPE: TRL_ONLY]` |
| B-Star Series A 전 리스크 점검 | **A-004** | `A-RISK [DOMAIN: BSTAR_SCO2] [OUTPUT: ALL]` |
| HBM Salvage 운영 리스크 등록부 | **A-004** | `A-RISK [DOMAIN: HBM_SALVAGE] [OUTPUT: RISK_REGISTER]` |

---

## 🔗 PE-ANA × PE-CON 연계 사용법

```
분석 흐름 (권장 순서):

[1] A-MARKET (시장 분석)
        ↓ 시장 기회 확인
[2] A-TECH (기술 성숙도)
        ↓ TRL/CRL/IRL 현황
[3] A-RISK (리스크 평가)
        ↓ Top 3 리스크 + 미티게이션
[4] A-DECOMP (프로세스 분해)
        ↓ 실행 워크플로우 최적화
        ↓
[5] PE-CON 전략 의사결정
    ├── C-007-AI (AI 인프라 McKinsey 포지셔닝)
    ├── C-008-BS (B-Star sCO2 CEO 자문)
    └── C-006-HBM (HBM 포트폴리오 BCG)
```

---

## 📊 PE-3 Score Summary

| 프롬프트 | 명확성 | 구조성 | 특이성 | 실행가능성 | 적용가능성 | **종합** |
|---------|--------|--------|--------|-----------|-----------|--------|
| A-001 (DECOMP) | 95 | 96 | 92 | 95 | 94 | **94** |
| A-002 (MARKET) | 96 | 96 | 94 | 95 | 96 | **95** |
| A-003 (TECH) | 96 | 96 | 94 | 95 | 96 | **95** |
| A-004 (RISK) | 95 | 95 | 93 | 95 | 95 | **95** |
| **평균** | **95.5** | **95.8** | **93.3** | **95.0** | **95.3** | **94.8** |

---

## 🔖 Naming Convention

```
A-[FUNCTION]_v[MAJOR].[MINOR].md

예시:
A-DECOMP_v1.0.md    → 프로세스 분해 v1.0
A-MARKET_v1.1.md    → 시장 분석 v1.1 (업데이트)

ID 체계:
A-001 ~ A-004  = PE-ANA 핵심 4종
A-005+         = 향후 추가 분석 템플릿
```

---

## 🔗 Cross-Library Links

- [PE-CON 인덱스 →](../consulting/README.md) — BCG · McKinsey · CEO Advisor 전략 프롬프트
- [전체 CHANGELOG →](../../CHANGELOG.md) — 버전 이력
- [루트 README →](../../README.md) — 전체 저장소 개요

---

## 📅 Changelog (PE-ANA)

| 버전 | 날짜 | 내용 |
|------|------|------|
| **v1.0.0** | 2026-04-28 | PE-ANA 초기 릴리즈 — A-001 · A-002 · A-003 · A-004 |

---

## 🚀 Next Steps (Planned)

- [ ] `A-DATA_v1.0.md` (A-005) — 데이터 분석 · KPI 대시보드 템플릿
- [ ] `A-BENCH_v1.0.md` (A-006) — 벤치마킹 · Best Practice 분석
- [ ] `A-FIN_v1.0.md` (A-007) — 재무 모델링 · Unit Economics 분석
- [ ] PE-ANA × Notion 연동 자동화 스크립트
