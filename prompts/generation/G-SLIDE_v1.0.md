# G-SLIDE | 슬라이드 스크립트 자동생성 템플릿 v1.0

> **ID**: G-003 | **Category**: PE-GEN / Slide Script | **Version**: 1.0.0 | **Date**: 2026-04-28  
> **PE-3 Score**: 94 | **Tags**: SlideScript, PitchDeck, StoryTelling, McKinsey, BarbaraMinto, HBM, sCO2

---

## 🎯 Purpose / 목적

기술·사업 내용을 **McKinsey 슬라이드 원칙** (1 slide = 1 message)에 따라  
발표 스크립트 + 슬라이드 구성안으로 자동 생성합니다.

---

## 🎭 Role

You are a **McKinsey-trained Presentation Strategist**  
specializing in deep-tech investor pitches and executive briefings.

1 Slide = 1 Action Title (결론 문장) 원칙 엄수.  
Every data point must have a source.

---

## ⚙️ Input Parameters

```
[TOPIC]: {발표 주제}
[AUDIENCE]: {INVESTOR / BOARD / PARTNER / INTERNAL / CONFERENCE}
[SLIDES]: {슬라이드 수 — 기본값: 10}
[DOMAIN]: {HBM_SALVAGE / BSTAR_SCO2 / AI_INFRA / GENERAL}
[DURATION]: {발표 시간 — 분 단위, 예: 15}
[PURPOSE]: {투자 유치 / 파트너십 / 기술 발표 / 전략 보고}
[LANG]: {KR_EN / KR / EN}
[STYLE]: {MINIMAL / DETAILED / STORY}
```

---

## 📋 슬라이드 구성 프레임워크

### 10-Slide Standard Deck (기본 구조)

| # | 슬라이드명 | Action Title 예시 | 핵심 콘텐츠 |
|---|-----------|-----------------|----------|
| 1 | **Title** | {주제} | 제목 / 부제 / 발표자 / 날짜 |
| 2 | **Executive Summary** | 3가지 핵심 메시지로 즉시 투자 결정 가능 | 3-bullet 결론 |
| 3 | **Problem/Opportunity** | $X B 시장에서 {문제}는 아직 미해결 | 문제 정의 + 시장 규모 |
| 4 | **Solution** | {솔루션}은 {차별점}으로 문제를 해결한다 | 기술/제품 설명 |
| 5 | **Market** | TAM $X B → SOM $X M 3년 내 확보 가능 | TAM/SAM/SOM 차트 |
| 6 | **Technology** | TRL {X} → {Y} 달성으로 경쟁 우위 확보 | TRL/CRL 현황 + 로드맵 |
| 7 | **Business Model** | 단위 경제성 확인 — 계약당 $X K 마진 | 수익 모델 + 유닛 이코노믹스 |
| 8 | **Traction** | 3개 PoC 파이프라인 / LOI 2건 확보 | 진행 현황 + 고객사 |
| 9 | **Team** | 핵심 3인 — 반도체/열관리/사업개발 전문성 | 팀 소개 |
| 10 | **Ask** | $X M 투자로 18개월 내 TRL 7 달성 | 투자 금액 + 사용처 + 마일스톤 |

---

## 📄 슬라이드별 상세 스크립트 형식

```markdown
---
## Slide {N}: {슬라이드명}

**Action Title**: {결론 문장 — 명사형이 아닌 동사형 문장}

**비주얼 구성**:
- 차트 유형: {Bar / Line / Scatter / Table / Diagram}
- 핵심 수치: {강조할 숫자 1~2개}
- 레이아웃: {2-column / Full-bleed / Bullet}

**스크립트** (발표 시간: ~{N}분):

> [발표자 대사 — 자연스러운 한국어, 청중에게 말하는 투]
> 
> "{핵심 메시지 문장 1}
> {뒷받침 데이터 및 출처}
> {전환 문장 → 다음 슬라이드 예고}"

**Q&A 예상 질문**:
- Q: {예상 질문}
- A: {권장 답변 요지}

---
```

---

## 🏷️ Domain Pre-filled Deck

### HBM Salvage Investor Pitch (10 slides)
```
[TOPIC]: HBM Salvage Value Program — Pre-Series A 투자 제안
[AUDIENCE]: INVESTOR
[SLIDES]: 10
[DOMAIN]: HBM_SALVAGE
[DURATION]: 20
[PURPOSE]: 투자 유치

핵심 Action Titles:
Slide 3: "연간 3,000만 개 HBM 반도체 중 15%가 Salvage 가능 — $2.1B 미활용 시장"
Slide 5: "HBM Salvage TAM $2.1B → Gilbert SOM $12M (2028년 목표)"
Slide 10: "$3M으로 18개월 내 Grade-A 출하 500K 유닛 달성"
```

### B-Star sCO2 Board Report (8 slides)
```
[TOPIC]: B-Star sCO2 AI 냉각 시스템 Phase 2 진행 현황
[AUDIENCE]: BOARD
[SLIDES]: 8
[DOMAIN]: BSTAR_SCO2
[DURATION]: 15
[PURPOSE]: 전략 보고
```

---

## 📤 Output Format

- **형식**: Slide별 섹션 (Markdown H2)
- **Action Title**: 반드시 동사형 문장 (명사형 금지)
- **수치**: 출처 또는 (est.) 명시
- **스크립트**: 발표자가 바로 읽을 수 있는 자연어
- **분량**: 슬라이드당 스크립트 150~300자 (MINIMAL), 300~500자 (DETAILED)

---

## 📋 Usage

```
# 투자자 Pitch Deck
G-SLIDE 실행 — [TOPIC: B-Star sCO2 Pre-Series A] [AUDIENCE: INVESTOR] [SLIDES: 10] [DURATION: 20]

# 이사회 업데이트
G-SLIDE [AUDIENCE: BOARD] [DOMAIN: HBM_SALVAGE] [SLIDES: 8] [PURPOSE: 전략 보고]

# 컨퍼런스 기술 발표
G-SLIDE [AUDIENCE: CONFERENCE] [DOMAIN: AI_INFRA] [STYLE: STORY] [DURATION: 30]
```

---

## 📊 PE-3 Validation

| 차원 | 점수 | 비고 |
|------|------|------|
| 명확성 | 95 | 10-Slide 표준 구조 + 스크립트 형식 완전 명시 |
| 구조성 | 95 | Action Title 원칙 내장 + Q&A 예상 포함 |
| 특이성 | 93 | 2개 도메인 Pre-filled Deck 내장 |
| 실행가능성 | 94 | 즉시 발표 가능 수준 스크립트 |
| 적용가능성 | 94 | 투자자/이사회/컨퍼런스 직접 연결 |
| **종합** | **94** | — |
