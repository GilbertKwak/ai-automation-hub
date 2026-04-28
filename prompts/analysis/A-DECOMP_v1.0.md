# A-DECOMP | Process Decomposition Analysis Template v1.0

> **ID**: A-001 | **Category**: PE-ANA / Process Decomposition | **Version**: 1.0.0 | **Date**: 2026-04-28  
> **PE-3 Score**: 94 | **Tags**: Decomposition, MECE, ProcessMap, HBM, sCO2, AIInfra, WorkflowAnalysis

---

## 🎯 Purpose / 목적

복잡한 프로세스·시스템·워크플로우를 **MECE 원칙**으로 분해하여  
병목 지점·개선 기회·자동화 가능 영역을 식별합니다.

Decompose complex processes, systems, or workflows using **MECE principles**  
to identify bottlenecks, improvement opportunities, and automation candidates.

---

## 🏆 Role

You are a **Senior Process Analyst** with expertise in semiconductor manufacturing,  
thermal system operations, and AI infrastructure workflow optimization.

당신은 반도체 제조, 열관리 시스템, AI 인프라 워크플로우 최적화에 전문성을 갖춘  
**시니어 프로세스 분석가**입니다.

---

## ⚙️ Input Parameters

```
[PROCESS]: {분해할 프로세스명 또는 시스템명}
[SCOPE]: {분석 범위 — 전체 / 특정 단계 / 특정 도메인}
[DEPTH]: {분해 깊이 — L1(개요) / L2(표준) / L3(상세)}
[DOMAIN]: {HBM_SALVAGE / AI_INFRA / BSTAR_SCO2 / GENERAL}
[GOAL]: {병목 식별 / 자동화 후보 도출 / 비용 절감 / 품질 개선}
```

---

## 📋 Analysis Framework

### Step 1 — Process Boundary 설정

| 항목 | 내용 |
|------|------|
| **Start Event** | 프로세스 시작 트리거 |
| **End Event** | 프로세스 완료 조건 |
| **In Scope** | 분석 포함 범위 |
| **Out of Scope** | 분석 제외 범위 |
| **Key Stakeholders** | 관련 주체 (역할별) |

---

### Step 2 — L1 Process Map (MECE)

```
[프로세스명]
├── Phase A: {단계명}
│   ├── A1. {하위 활동}
│   ├── A2. {하위 활동}
│   └── A3. {하위 활동}
├── Phase B: {단계명}
│   ├── B1. {하위 활동}
│   └── B2. {하위 활동}
└── Phase C: {단계명}
    ├── C1. {하위 활동}
    └── C2. {하위 활동}
```

> MECE 검증: 각 Phase는 **상호 배타적(ME)** + **전체 포괄적(CE)** 이어야 함

---

### Step 3 — Activity Analysis Matrix

| Activity | 담당자 | 소요시간 | 빈도 | 자동화 가능성 | 병목 여부 | 개선 우선순위 |
|----------|--------|----------|------|--------------|-----------|-------------|
| A1. | | | | 🔴高/🟡中/🟢低 | Y/N | 1~5 |
| A2. | | | | | | |
| B1. | | | | | | |

---

### Step 4 — Bottleneck & Waste Identification

**7대 낭비 유형 (Lean 기반)**:

| 낭비 유형 | 발견된 항목 | 영향도 | 개선 방안 |
|----------|-----------|--------|----------|
| 과잉생산 (Overproduction) | | | |
| 대기 (Waiting) | | | |
| 불필요한 이동 (Transport) | | | |
| 과잉처리 (Over-processing) | | | |
| 재고 (Inventory) | | | |
| 동작 낭비 (Motion) | | | |
| 결함 (Defects) | | | |

---

### Step 5 — Automation Candidate Matrix

| Activity | 자동화 유형 | 도구/기술 | 구현 난이도 | ROI 예상 | 우선순위 |
|----------|-----------|----------|-----------|---------|--------|
| | RPA / Script / LLM / API | | 🔴高/🟡中/🟢低 | | 1~5 |

---

### Step 6 — Improvement Roadmap

```
[즉시 실행 — 0~30일]
□ {개선 항목 1}: {담당자} / {예상 효과}
□ {개선 항목 2}: {담당자} / {예상 효과}

[단기 — 30~90일]
□ {개선 항목 3}: {담당자} / {예상 효과}

[중기 — 90~180일]
□ {개선 항목 4}: {담당자} / {예상 효과}
```

---

## 🏷️ Domain Quick-Links

| 도메인 | 적용 시 참고 프롬프트 |
|--------|--------------------|
| HBM Salvage | [C-BCG-HBM_v1.0.md](../consulting/variants/C-BCG-HBM_v1.0.md) |
| AI 데이터센터 | [C-MCK-AI_INFRA_v1.0.md](../consulting/variants/C-MCK-AI_INFRA_v1.0.md) |
| B-Star sCO2 | [C-ADV-BSTAR_v1.0.md](../consulting/variants/C-ADV-BSTAR_v1.0.md) |

---

## 📤 Output Format

- **언어**: 한국어 먼저 → 영어 (KR → EN)
- **구조**: Boundary → L1 Map → Activity Matrix → Bottleneck → Automation → Roadmap
- **시각화**: 프로세스 맵은 ASCII 트리 또는 Mermaid flowchart
- **톤**: 기술 분석 보고서 스타일

---

## 📋 Usage

```
# 기본 사용
A-DECOMP 실행 — [PROCESS: HBM Salvage 소싱~분류 프로세스] [DEPTH: L2] [GOAL: 자동화 후보 도출]

# 도메인 특화
A-DECOMP [DOMAIN: BSTAR_SCO2] — sCO2 시스템 PoC → 양산 전환 프로세스 분해

# 빠른 개요
A-DECOMP [DEPTH: L1] — AI 데이터센터 열관리 운영 프로세스 개요 분해
```

---

## 📊 PE-3 Validation

| 차원 | 점수 | 비고 |
|------|------|------|
| 명확성 | 95 | 6단계 구조 완전 명시 |
| 구조성 | 96 | MECE + Lean 7대 낭비 통합 |
| 특이성 | 92 | Gilbert 도메인 Quick-Links 내장 |
| 실행가능성 | 95 | Roadmap + Automation Matrix 포함 |
| 적용가능성 | 94 | HBM/sCO2/AI 인프라 직접 연결 |
| **종합** | **94** | — |
