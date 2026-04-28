# G-EXEC | Executive Summary 자동생성 템플릿 v1.0

> **ID**: G-002 | **Category**: PE-GEN / Executive Summary | **Version**: 1.0.0 | **Date**: 2026-04-28  
> **PE-3 Score**: 95 | **Tags**: ExecutiveSummary, CLevel, InvestorComm, PitchDeck, BoardReport, HBM, sCO2

---

## 🎯 Purpose / 목적

기술 분석·시장 데이터·프로젝트 현황을 **C-Level 임원 / 투자자 / 이사회**가  
5분 이내 이해·결정할 수 있는 **1페이지 Executive Summary**로 자동 변환합니다.

---

## 🎭 Role

You are a **McKinsey-level Executive Communication Specialist**  
with expertise in semiconductor investment, deep-tech commercialization,  
and AI infrastructure strategy.

Pyramid Principle 기반 — 결론 먼저, 근거 후행.

---

## ⚙️ Input Parameters

```
[SOURCE]: {요약할 원문 내용 또는 보고서 번호}
[PURPOSE]: {투자 유치 / 이사회 보고 / 파트너 제안 / 내부 브리핑}
[READER]: {CEO / CTO / CFO / INVESTOR / BOARD / PARTNER}
[TONE]: {FORMAL / TECHNICAL / COMMERCIAL}
[LENGTH]: {SHORT(200자) / STANDARD(500자) / LONG(1000자)}
[DOMAIN]: {HBM_SALVAGE / BSTAR_SCO2 / AI_INFRA / GENERAL}
[DECISION]: {요청하는 의사결정 또는 승인 사항}
[LANG]: {KR_EN / KR / EN}
```

---

## 📋 생성 프레임워크

### Pyramid Structure (필수 준수)

```
[1단계] 결론 (Governing Thought)
    └─ 한 문장: "우리는 [무엇]을 해야 한다, 왜냐하면 [핵심 이유]"

[2단계] 지지 논거 3개 (Key Arguments)
    ├─ 논거 1: 시장/기회 관점
    ├─ 논거 2: 기술/역량 관점
    └─ 논거 3: 재무/수익 관점

[3단계] 증거 & 데이터 (Supporting Evidence)
    └─ 각 논거당 수치 1~2개 (출처 명시)

[4단계] 즉시 행동 요청 (Call to Action)
    └─ "지금 당장 [무엇]을 [언제까지] 결정해주십시오"
```

---

## 📄 Executive Summary 출력 템플릿

### SHORT 모드 (200자 / 1 Slide)

```markdown
## [제목]

**결론**: {Governing Thought — 한 문장}

**근거**: ① {수치 포함} ② {수치 포함} ③ {수치 포함}

**요청**: {의사결정 사항} — {마감 기한}
```

---

### STANDARD 모드 (500자 / 1 페이지)

```markdown
# [제목]
**날짜**: {날짜} | **작성**: Gilbert Kwak | **대상**: {READER}

---

## 핵심 결론
{Governing Thought — 2~3문장. 결론 + 핵심 이유}

## 주요 근거

**① {시장/기회}**  
{수치 포함 2~3문장} — 출처: {source}

**② {기술/역량}**  
{수치 포함 2~3문장} — 출처: {source}

**③ {재무/수익}**  
{수치 포함 2~3문장} — 출처: {source}

## 리스크 & 대응
{Top 1~2 리스크 + 완화 전략 — 한 줄씩}

## 요청 사항
> **{의사결정 내용}을 {날짜}까지 승인 바랍니다.**

---
*신뢰도: 높음 | 다음 검토: {날짜}*
```

---

### LONG 모드 (1000자 / 2페이지 이내)

```markdown
# [제목]
**날짜**: {날짜} | **버전**: v1.0 | **분류**: {CONFIDENTIAL/INTERNAL}

---

## I. 상황 (Situation)
{현재 상황 및 배경 — 3~5문장}

## II. 과제 (Complication)
{해결해야 할 문제 또는 기회 — 3~5문장}

## III. 해결책 (Resolution)
{권고 솔루션 — 3~5문장 + 핵심 수치}

## IV. 지지 논거

### 논거 1: {제목}
{근거 + 수치 + 출처}

### 논거 2: {제목}
{근거 + 수치 + 출처}

### 논거 3: {제목}
{근거 + 수치 + 출처}

## V. 재무적 영향
| 항목 | 현재 | 목표 | 증분 효과 |
|------|------|------|----------|
| 매출 | | | |
| 비용 | | | |
| ROI  | | | |

## VI. 실행 타임라인
- **즉시 (0~30일)**: {행동}
- **단기 (30~90일)**: {행동}
- **중기 (90~180일)**: {행동}

## VII. 요청 사항
> **승인 필요**: {의사결정 사항}  
> **마감**: {날짜}  
> **담당자**: Gilbert Kwak
```

---

## 🏷️ Domain Pre-filled Context

### HBM Salvage → 투자자용
```
[PURPOSE]: 투자 유치
[READER]: INVESTOR
[TONE]: COMMERCIAL
[DOMAIN]: HBM_SALVAGE
[DECISION]: Pre-Series A $3M 투자 확약
```

### B-Star sCO2 → 이사회용
```
[PURPOSE]: 이사회 보고
[READER]: BOARD
[TONE]: FORMAL
[DOMAIN]: BSTAR_SCO2
[DECISION]: Phase 2 PoC 예산 승인 ($500K)
```

### AI 인프라 → 파트너 제안
```
[PURPOSE]: 파트너 제안
[READER]: CTO
[TONE]: TECHNICAL
[DOMAIN]: AI_INFRA
[DECISION]: 공동 PoC 계약 체결
```

---

## 📤 Output Format

- **언어**: [LANG] 파라미터 우선 적용
- **분량**: [LENGTH] 파라미터 엄격 준수
- **수치**: 반드시 출처 또는 (est.) 명시
- **금지**: 불확실한 표현("~할 수도", "~인 것 같음") 사용 금지
- **필수**: 마지막 줄 반드시 CTA(Call to Action) 포함

---

## 📋 Usage

```
# 즉시 실행
G-EXEC [SOURCE: FU-025 보고서 3섹션] [PURPOSE: 투자 유치] [READER: INVESTOR] [LENGTH: STANDARD]

# 이사회 보고서
G-EXEC [DOMAIN: BSTAR_SCO2] [PURPOSE: 이사회 보고] [READER: BOARD] [DECISION: Phase 2 예산 $500K 승인]

# 파트너 제안서
G-EXEC [DOMAIN: AI_INFRA] [READER: CTO] [TONE: TECHNICAL] — HBM 냉각 공동 PoC 제안
```

---

## 📊 PE-3 Validation

| 차원 | 점수 | 비고 |
|------|------|------|
| 명확성 | 96 | SHORT/STANDARD/LONG 3모드 완전 구조화 |
| 구조성 | 95 | Pyramid Principle 완전 내장 |
| 특이성 | 94 | 3개 도메인 Pre-filled + 3개 독자 유형 |
| 실행가능성 | 96 | CTA 필수 포함 규칙 명시 |
| 적용가능성 | 96 | 투자자/이사회/파트너 직접 연결 |
| **종합** | **95** | — |
