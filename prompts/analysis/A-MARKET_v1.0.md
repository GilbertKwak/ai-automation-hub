# A-MARKET | Market & Competitive Analysis Template v1.0

> **ID**: A-002 | **Category**: PE-ANA / Market Analysis | **Version**: 1.0.0 | **Date**: 2026-04-28  
> **PE-3 Score**: 95 | **Tags**: MarketAnalysis, TAM_SAM_SOM, Porter5Forces, Competitive, HBM, sCO2, AIInfra

---

## 🎯 Purpose / 목적

목표 시장의 규모·성장성·경쟁 구도를 **TAM→SAM→SOM 프레임**과  
**Porter 5 Forces** 기반으로 정량·정성 분석합니다.

Quantitatively and qualitatively analyze target market size, growth, and competitive dynamics  
using **TAM→SAM→SOM** and **Porter's 5 Forces** frameworks.

---

## 🏆 Role

You are a **Senior Market Intelligence Analyst** with deep expertise in  
semiconductor markets, thermal management, and AI infrastructure supply chains.

---

## ⚙️ Input Parameters

```
[MARKET]: {분석할 시장명}
[YEAR]: {기준 연도 — 기본값: 2026}
[HORIZON]: {전망 기간 — 기본값: 5년 (2026~2031)}
[DOMAIN]: {HBM_SALVAGE / AI_INFRA / BSTAR_SCO2 / GENERAL}
[FOCUS]: {TAM_SIZING / COMPETITIVE / ENTRY_TIMING / ALL}
[GEO]: {Global / Korea / APAC / NA / EU}
```

---

## 📋 Analysis Framework

### Step 1 — Market Definition & Segmentation

| 항목 | 내용 |
|------|------|
| **Market Definition** | 시장 정의 (기술·용도·지역 기준) |
| **Primary Segments** | 핵심 세그먼트 (최대 4개) |
| **Adjacent Markets** | 인접 시장 (기회·위협 관점) |
| **Excluded Segments** | 분석 제외 세그먼트 및 이유 |

---

### Step 2 — TAM → SAM → SOM

| 구분 | 정의 | 규모 추정 | 근거 | CAGR |
|------|------|----------|------|------|
| **TAM** | 전체 목표 시장 | $X B | {데이터 출처} | X% |
| **SAM** | 실제 접근 가능 시장 | $X B | {세그먼트 필터링 기준} | X% |
| **SOM** | 현실적 획득 가능 시장 | $X M | {3년 내 목표 점유율 기준} | — |

> **Bottom-up 검증**: SOM = {목표 고객 수} × {평균 계약 단가} × {전환율}

---

### Step 3 — Porter's 5 Forces

| Force | 강도 | 핵심 요인 | Gilbert/B-Star 포지션 |
|-------|------|----------|---------------------|
| **신규 진입자 위협** | 🔴高/🟡中/🟢低 | | |
| **공급자 교섭력** | | | |
| **구매자 교섭력** | | | |
| **대체재 위협** | | | |
| **기존 경쟁자 경쟁 강도** | | | |

**종합 매력도**: ⬜⬜⬜⬜⬜ (5점 만점)

---

### Step 4 — Competitive Landscape

| 경쟁사 | 포지션 | 강점 | 약점 | 시장점유율 | 차별화 전략 |
|--------|--------|------|------|----------|----------|
| | Leader/Challenger/Niche | | | ~X% | |

**경쟁 포지셔닝 맵** (X축: 기술 성숙도, Y축: 시장 접근성):

```
높음 |
     |  [경쟁사 A]      [목표 포지션]
시장  |                ↗
접근성|  [경쟁사 B]  [Gilbert/B-Star]
     |
낮음  |________________________
      낮음    기술 성숙도    높음
```

---

### Step 5 — Entry Timing Analysis

| 요인 | 현재 상태 | 12개월 후 예측 | 진입 적기 신호 |
|------|----------|--------------|---------------|
| 시장 성숙도 | | | |
| 경쟁 밀도 | | | |
| 기술 준비도 | | | |
| 규제 환경 | | | |
| 고객 수요 확실성 | | | |

**Entry Window**: {개월} 이내 / {연도} {분기}까지

---

### Step 6 — Strategic Implications

| # | Implication | Value at Stake | Priority |
|---|-------------|---------------|----------|
| 1 | | | High/Mid/Low |
| 2 | | | |
| 3 | | | |

---

## 🏷️ Domain Pre-filled Context

### HBM Salvage 시장 기본값
```
[MARKET]: HBM 반도체 재활용·재판매 시장
[DOMAIN]: HBM_SALVAGE
[GEO]: Global (APAC 중심)
[FOCUS]: TAM_SIZING + ENTRY_TIMING
```

### AI 인프라 열관리 시장 기본값
```
[MARKET]: AI 데이터센터 액침냉각·sCO2 냉각 시장
[DOMAIN]: AI_INFRA
[GEO]: Global
[FOCUS]: COMPETITIVE + ENTRY_TIMING
```

### B-Star sCO2 기본값
```
[MARKET]: sCO2 기반 산업용 에너지 시스템 시장
[DOMAIN]: BSTAR_SCO2
[GEO]: Korea + APAC
[FOCUS]: ALL
```

---

## 📤 Output Format

- **언어**: 한국어 먼저 → 영어 (KR → EN)
- **구조**: Market Definition → TAM/SAM/SOM → Porter 5 → Competitive Landscape → Entry Timing → Implications
- **수치**: 모든 시장 규모 추정에 출처 또는 가정 명시
- **톤**: 투자자 보고서 + 전략 컨설팅 스타일

---

## 📋 Usage

```
# 전체 분석
A-MARKET 실행 — [MARKET: AI 데이터센터 sCO2 냉각] [YEAR: 2026] [FOCUS: ALL]

# 경쟁 분석 집중
A-MARKET [FOCUS: COMPETITIVE] — HBM 재활용 시장 경쟁 구도 분석

# 진입 타이밍 집중
A-MARKET [FOCUS: ENTRY_TIMING] [DOMAIN: BSTAR_SCO2] — B-Star 시장 진입 적기 분석
```

---

## 📊 PE-3 Validation

| 차원 | 점수 | 비고 |
|------|------|------|
| 명확성 | 96 | TAM/SAM/SOM + Porter 5 완전 구조화 |
| 구조성 | 96 | 6단계 순차 분석 프레임 |
| 특이성 | 94 | 3개 도메인 Pre-filled Context 내장 |
| 실행가능성 | 95 | Entry Timing + Implications 포함 |
| 적용가능성 | 96 | Gilbert 핵심 시장 직접 연결 |
| **종합** | **95** | — |
