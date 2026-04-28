# A-TECH | Technology Maturity & Readiness Analysis Template v1.0

> **ID**: A-003 | **Category**: PE-ANA / Technology Analysis | **Version**: 1.0.0 | **Date**: 2026-04-28  
> **PE-3 Score**: 95 | **Tags**: TRL, CRL, TechMaturity, sCO2, HBM, ThermalManagement, IPAnalysis

---

## 🎯 Purpose / 목적

기술의 성숙도(TRL)·상업화 준비도(CRL)·투자 준비도(IRL)를 체계적으로 평가하여  
**기술 개발 우선순위·IP 전략·상업화 경로**를 도출합니다.

Systematically assess technology maturity (TRL), commercialization readiness (CRL),  
and investment readiness (IRL) to derive **R&D priorities, IP strategy, and commercialization path**.

---

## 🏆 Role

You are a **Chief Technology Strategist** with expertise in deep-tech commercialization,  
semiconductor thermal systems, and IP portfolio management.

---

## ⚙️ Input Parameters

```
[TECHNOLOGY]: {평가할 기술명}
[DOMAIN]: {HBM_THERMAL / SCO2_COOLING / AI_INFRA_COOLING / SEMICONDUCTOR / GENERAL}
[EVAL_TYPE]: {TRL_ONLY / CRL_ONLY / FULL (TRL+CRL+IRL)}
[COMPETITOR]: {ON / OFF — 경쟁사 기술 비교 포함 여부}
[HORIZON]: {단기(1년) / 중기(3년) / 장기(5년)}
```

---

## 📋 Analysis Framework

### Step 1 — TRL Assessment (Technology Readiness Level)

| TRL | 정의 | 증거 요건 | 현재 상태 |
|-----|------|----------|----------|
| **1** | 기초 원리 관찰 | 학술 논문·특허 | ✅/⬜ |
| **2** | 기술 개념 정립 | 개념 설계 문서 | ✅/⬜ |
| **3** | 개념 실험 검증 | 실험실 실험 결과 | ✅/⬜ |
| **4** | 실험실 환경 검증 | 소규모 프로토타입 | ✅/⬜ |
| **5** | 관련 환경 검증 | 파일럿 테스트 결과 | ✅/⬜ |
| **6** | 관련 환경 시연 | 고객 환경 PoC | ✅/⬜ |
| **7** | 운영 환경 시연 | 현장 파일럿 | ✅/⬜ |
| **8** | 시스템 완성·검증 | 양산 준비 완료 | ✅/⬜ |
| **9** | 운영 환경 검증 | 상용 배포 완료 | ✅/⬜ |

**현재 TRL**: **{X}** | **목표 TRL (12개월)**: **{X}**

**TRL Gap 분석**:
```
현재: TRL {X} ─────────────────────── 목표: TRL {Y}
                   ↑
              Gap: {Y-X} 단계
              예상 기간: {N}개월
              필요 자원: {인력/예산/장비}
```

---

### Step 2 — CRL Assessment (Commercialization Readiness Level)

| CRL | 정의 | 달성 조건 | 현재 상태 |
|-----|------|----------|----------|
| **1** | 시장 기회 확인 | TAM 분석 완료 | ✅/⬜ |
| **2** | 고객 문제 검증 | 고객 인터뷰 10건+ | ✅/⬜ |
| **3** | 솔루션-시장 적합성 | PoC 고객 관심 확인 | ✅/⬜ |
| **4** | 최초 고객 계약 | LoI 또는 파일럿 계약 | ✅/⬜ |
| **5** | 반복 판매 | 2건+ 유료 계약 | ✅/⬜ |
| **6** | 수익화 모델 검증 | 긍정적 단위 경제성 | ✅/⬜ |

**현재 CRL**: **{X}** | **목표 CRL (12개월)**: **{X}**

---

### Step 3 — IRL Assessment (Investment Readiness Level)

| IRL | 정의 | 달성 조건 | 현재 상태 |
|-----|------|----------|----------|
| **1** | 기술·시장 스토리 완성 | IR 덱 초안 | ✅/⬜ |
| **2** | 팀 완성도 | 핵심 인력 충원 완료 | ✅/⬜ |
| **3** | 재무 모델 | 5년 재무 예측 완료 | ✅/⬜ |
| **4** | IP 포트폴리오 | 핵심 특허 출원 완료 | ✅/⬜ |
| **5** | 투자자 관심 확인 | Term Sheet 수령 | ✅/⬜ |

**현재 IRL**: **{X}** | **투자 유치 목표**: **Series {X}**

---

### Step 4 — 종합 Readiness Radar

```
              기술 성숙도(TRL)
                  10
                 /|\
                / | \
  상업화       /  |  \ 투자
  준비도(CRL) /   |   \ 준비도(IRL)
            /    |    \
           ─────────────

현재: TRL {X}/9 · CRL {X}/6 · IRL {X}/5
목표: TRL {Y}/9 · CRL {Y}/6 · IRL {Y}/5
```

---

### Step 5 — IP & Competitive Moat Analysis

| 항목 | 현재 상태 | 위협 요인 | 강화 방안 |
|------|----------|----------|----------|
| **핵심 특허** | 출원 {N}건 / 등록 {N}건 | | |
| **영업 비밀** | | | |
| **Know-how** | | | |
| **인력 장벽** | | | |
| **네트워크 효과** | | | |

**Moat 내구성**: {N}개월 (경쟁사가 동등 기술 확보까지 예상 기간)

---

### Step 6 — Technology Roadmap

| 마일스톤 | 목표 | 기간 | 담당 | 예산 | 위험도 |
|---------|------|------|------|------|-------|
| M1 | TRL {X}→{Y} 달성 | {N}개월 | | $X | 🔴/🟡/🟢 |
| M2 | CRL {X}→{Y} 달성 | {N}개월 | | $X | |
| M3 | 첫 상용 계약 | {N}개월 | | $X | |
| M4 | Series A 투자 유치 | {N}개월 | | — | |

---

## 🏷️ Domain Pre-filled Context

### sCO2 냉각 기술 기본값
```
[TECHNOLOGY]: sCO2 기반 데이터센터 냉각 시스템
[DOMAIN]: SCO2_COOLING
[EVAL_TYPE]: FULL
[COMPETITOR]: ON
```

### HBM 열관리 기술 기본값
```
[TECHNOLOGY]: HBM4 고용량 패키지 열관리 솔루션
[DOMAIN]: HBM_THERMAL
[EVAL_TYPE]: TRL_ONLY
[COMPETITOR]: ON
```

---

## 📤 Output Format

- **언어**: 한국어 먼저 → 영어 (KR → EN)
- **구조**: TRL → CRL → IRL → Radar → IP Moat → Roadmap
- **시각화**: TRL/CRL 달성 체크리스트 + Radar 다이어그램
- **톤**: 기술 실사(Due Diligence) 보고서 스타일

---

## 📋 Usage

```
# 전체 평가
A-TECH 실행 — [TECHNOLOGY: B-Star sCO2 냉각 시스템] [EVAL_TYPE: FULL] [COMPETITOR: ON]

# TRL만 빠르게
A-TECH [EVAL_TYPE: TRL_ONLY] — HBM4 열관리 솔루션 기술 성숙도 평가

# 투자 준비도 집중
A-TECH [EVAL_TYPE: CRL_ONLY] [DOMAIN: SCO2_COOLING] — B-Star 상업화 준비도 진단
```

---

## 📊 PE-3 Validation

| 차원 | 점수 | 비고 |
|------|------|------|
| 명확성 | 96 | TRL/CRL/IRL 3축 완전 구조화 |
| 구조성 | 96 | 6단계 + Radar 시각화 |
| 특이성 | 94 | sCO2·HBM 도메인 Pre-filled 내장 |
| 실행가능성 | 95 | Technology Roadmap + IP Moat 포함 |
| 적용가능성 | 96 | B-Star TRL/CRL 현재 상태 직접 진단 가능 |
| **종합** | **95** | — |
