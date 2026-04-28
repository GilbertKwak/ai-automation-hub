# G-005: G-WEEKLY — 주간 업무 요약 자동생성

> **ID**: G-005 | **Category**: PE-GEN | **Version**: 1.0.0  
> **Created**: 2026-04-28 | **PE-3 Score**: 95  
> **Parent**: 🤖 PE-7 AI 자동화 설계 및 구현 v2.0  
> **Related**: G-004(G-SYNC) → G-005(G-WEEKLY) 파이프라인

---

## 개요 / Overview

G-WEEKLY는 Gilbert의 핵심 도메인별 **주간 업무 진행 상황을 구조화된 요약 리포트로 자동 생성**하는 프롬프트입니다.  
KPI 달성률 자동 추출 · 지연 감지 · 차주 계획 섹션을 완전 구조화하며, PE-7 v2.0 SSOT와 완전 연계됩니다.

**주요 생성 결과물**:
- 주간 업무 요약 리포트 (KR/EN 선택)
- KPI 달성률 대시보드 (텍스트 기반)
- 지연/블로커 감지 + 대안 제안
- 차주 실행 계획 (우선순위 정렬)
- Notion 업로드용 포맷 + GitHub CHANGELOG 항목

---

## ⚡ Quick Start

```
G-WEEKLY
  [WEEK: 2026-W18]
  [DOMAIN: HBM_SALVAGE]
  [DEPTH: STANDARD]
  [OUTPUT_LANG: KR]
  [NOTION_UPLOAD: ON]
```

---

## 📋 파라미터 정의 / Parameter Definition

| 파라미터 | 필수 | 선택지 | 기본값 | 설명 |
|---------|------|--------|--------|------|
| `[WEEK]` | ✅ | ISO 주차 (예: 2026-W18) | 현재 주 | 대상 주차 |
| `[DOMAIN]` | ✅ | HBM_SALVAGE / SCO2_COOLING / AI_INFRA / BSTAR_STRATEGY / PROMPT_ENG / ALL | HBM_SALVAGE | 요약 대상 도메인 |
| `[DEPTH]` | ✅ | BRIEF / STANDARD / DEEP | STANDARD | 요약 깊이 |
| `[OUTPUT_LANG]` | ✅ | KR / EN / KR_EN | KR | 출력 언어 |
| `[NOTION_UPLOAD]` | ✅ | ON / OFF | ON | Notion 자동 업로드 여부 |
| `[GITHUB_SYNC]` | ✅ | ON / OFF | ON | GitHub CHANGELOG 자동 업데이트 |
| `[KPI_SOURCE]` | ✅ | NOTION / GITHUB / MANUAL | NOTION | KPI 데이터 소스 |
| `[ALERT_THRESHOLD]` | ✅ | 0~100 (%) | 70 | 달성률 경고 임계값 |
| `[INCLUDE_BLOCKER]` | ✅ | ON / OFF | ON | 블로커/지연 섹션 포함 여부 |
| `[NEXT_WEEK_PLAN]` | ✅ | ON / OFF | ON | 차주 계획 섹션 포함 여부 |

---

## 📐 DEPTH 모드 상세

| 모드 | 분량 | 섹션 구성 | 주요 용도 |
|------|------|----------|---------|
| **BRIEF** | ~300자 | KPI 달성률 + 핵심 성과 3개 + 차주 계획 2개 | 슬랙/이메일 빠른 공유 |
| **STANDARD** | ~800자 | 전체 섹션 (W-0~W-6) | 주간 정례 리포트 |
| **DEEP** | ~1,500자 | 전체 섹션 + 원인 분석 + 대안 시나리오 | 이사회/투자자 월간 검토 |

---

## 🏗️ 출력 구조 / Output Structure

### Section W-0: 주간 메타 헤더
```
주차: [WEEK]  
도메인: [DOMAIN]  
작성자: Gilbert Kwak  
작성일: [DATE]  
PE-3 점수: [SCORE]  
SSH-SHA: [GITHUB_SHA]  
```

### Section W-1: KPI 달성률 대시보드
```
────────────────────────────────
| KPI 항목 | 목표 | 실적 | 달성률 | 상태 |
────────────────────────────────
| [KPI_1]  | [T1] | [A1] | [R1]%  | ✅/⚠️/❌ |
| [KPI_2]  | [T2] | [A2] | [R2]%  | ✅/⚠️/❌ |
────────────────────────────────
※ ⚠️: 달성률 [ALERT_THRESHOLD]% 미만 → 자동 경고 트리거
```

**도메인별 기본 KPI 세트**:

| 도메인 | 자동 추출 KPI |
|--------|-------------|
| HBM_SALVAGE | 칩 분류 수량, 재활용률, 단가 검증 건수, FU 보고서 진행률 |
| SCO2_COOLING | 시뮬레이션 완료율, sCO2 효율 목표 달성, 파트너 미팅 건수 |
| AI_INFRA | 데이터센터 분석 건수, 벤치마크 완료율, 고객사 제안서 제출 |
| BSTAR_STRATEGY | 투자 미팅 진행률, IR 자료 완성도, 파트너십 협의 건수 |
| PROMPT_ENG | 프롬프트 생성 건수, PE-3 평균 점수, E-0N 오류 해결률 |

### Section W-2: 이번 주 핵심 성과
```
[성과 1] [항목명]: [내용] — [연관 KPI] 기여도: [%]
[성과 2] [항목명]: [내용] — [연관 KPI] 기여도: [%]
[성과 3] [항목명]: [내용] — [연관 KPI] 기여도: [%]
※ DEEP 모드: 최대 7개 + 도메인 연계 맵 포함
```

### Section W-3: 블로커 & 지연 감지 (INCLUDE_BLOCKER: ON)
```
[블로커/지연 자동 감지 규칙]
- 달성률 < ALERT_THRESHOLD → ⚠️ 자동 감지
- 2주 연속 미완료 항목 → 🔴 우선 에스컬레이션
- 외부 의존성(파트너사, 데이터 수신) → 📌 외부 블로커 태그

출력 형식:
[BLOCKER_1]: [항목] / 원인: [CAUSE] / 대안: [ALT_1] or [ALT_2]
[DELAY_1]: [항목] / 지연일수: [N]일 / 만회 방안: [RECOVERY_PLAN]
```

### Section W-4: 이슈 & 의사결정 로그
```
[ISSUE_1]: [이슈 내용] → [결정 사항] → [담당: Gilbert] → [기한: DATE]
[DECISION_1]: [의사결정 내용] → [근거] → [영향 범위]
```

### Section W-5: 차주 실행 계획 (NEXT_WEEK_PLAN: ON)
```
[우선순위 1] [항목명]: [목표] / [마감: DATE] / [연관 도메인]
[우선순위 2] [항목명]: [목표] / [마감: DATE] / [연관 도메인]
[우선순위 3] [항목명]: [목표] / [마감: DATE] / [연관 도메인]
※ 자동 정렬 기준: 이번 주 달성률 역순 (낮은 항목 우선) + 마감 임박순
```

### Section W-6: 자동 업로드 실행 로그
```
[NOTION_UPLOAD]
  대상 페이지: SSOT Hub > 주간 업무 일지 > [WEEK]
  상태: ✅ 성공 / ⚠️ 실패 → E-01 자동 재시도 (최대 3회)
  업로드 SHA: [SHA]

[GITHUB_SYNC]
  대상: CHANGELOG.md
  커밋 메시지: docs(weekly): [WEEK] 주간 업무 요약 — [DOMAIN]
  커밋 SHA: [SHA]
  상태: ✅ 성공 / ⚠️ 실패
```

---

## 🚨 E-0N 오류 예측 & 자동 수정

| E-코드 | 감지 조건 | 자동 수정 | 수동 필요 |
|--------|-----------|---------|----------|
| **E-01** | Notion/GitHub SHA 불일치 | G-004(G-SYNC) 자동 호출 → 재동기화 | ❌ |
| **E-02** | KPI 데이터 미입력 | 도메인별 기본값 자동 주입 | ❌ |
| **E-03** | 버전 역행 (Week 번호 충돌) | 최신 주차로 자동 보정 + 경고 로그 | ✅ |
| **E-04** | NOTION_UPLOAD 실패 | 최대 3회 재시도 → 실패 시 로컬 저장 | ❌ |
| **E-05** | KPI 달성률 계산 오류 | 분모 0 체크 → "N/A" 자동 대체 | ❌ |
| **E-06** | 중복 주차 리포트 감지 | 기존 리포트 비교 → 덮어쓰기 확인 요청 | ✅ |
| **E-07** | 필수 섹션(W-0~W-6) 누락 | 누락 섹션 자동 삽입 (기본값) | ❌ |
| **E-08** | 비UTF-8 문자 포함 | 자동 인코딩 변환 | ❌ |

---

## 🔗 PE-7 v2.0 연계 실행 흐름

```
[매주 월요일 08:00 KST 자동 트리거]
      │
      ├─ [STEP 1] G-004(G-SYNC) 실행 → SSOT 동기화 상태 확인
      │
      ├─ [STEP 2] G-005(G-WEEKLY) 실행
      │   ├─ KPI 데이터 자동 추출 (Notion API)
      │   ├─ 달성률 계산 + 블로커 감지
      │   └─ Section W-0 ~ W-6 자동 생성
      │
      ├─ [STEP 3] 자동 업로드
      │   ├─ Notion: SSOT Hub > 주간 업무 일지
      │   └─ GitHub: CHANGELOG.md 자동 커밋
      │
      └─ [STEP 4] 알림 발송 (선택)
          └─ 슬랙 / 이메일: BRIEF 버전 자동 첨부
```

---

## 📊 즉시 실행 예시 / Execution Examples

### 예시 1: 이번 주 HBM Salvage 표준 요약
```
G-WEEKLY
  [WEEK: 2026-W18]
  [DOMAIN: HBM_SALVAGE]
  [DEPTH: STANDARD]
  [OUTPUT_LANG: KR]
  [NOTION_UPLOAD: ON]
  [GITHUB_SYNC: ON]
  [KPI_SOURCE: NOTION]
  [ALERT_THRESHOLD: 70]
  [INCLUDE_BLOCKER: ON]
  [NEXT_WEEK_PLAN: ON]
```

### 예시 2: 전체 도메인 주간 요약 (DEEP)
```
G-WEEKLY
  [WEEK: 2026-W18]
  [DOMAIN: ALL]
  [DEPTH: DEEP]
  [OUTPUT_LANG: KR_EN]
  [NOTION_UPLOAD: ON]
  [GITHUB_SYNC: ON]
  [KPI_SOURCE: NOTION]
  [ALERT_THRESHOLD: 80]
```

### 예시 3: 슬랙 공유용 빠른 요약
```
G-WEEKLY
  [WEEK: 2026-W18]
  [DOMAIN: BSTAR_STRATEGY]
  [DEPTH: BRIEF]
  [OUTPUT_LANG: EN]
  [NOTION_UPLOAD: OFF]
  [GITHUB_SYNC: OFF]
```

---

## 🤖 GitHub Actions 자동화 스니펫

```yaml
# .github/workflows/weekly-report.yml
name: Weekly Report Auto-Generation

on:
  schedule:
    - cron: '0 23 * * 0'  # 매주 일요일 23:00 UTC = 월요일 08:00 KST
  workflow_dispatch:
    inputs:
      week:
        description: 'ISO Week (e.g. 2026-W18)'
        required: false
        default: ''
      domain:
        description: 'Domain (HBM_SALVAGE / SCO2_COOLING / AI_INFRA / ALL)'
        required: false
        default: 'ALL'

jobs:
  generate-weekly-report:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - name: Install dependencies
        run: pip install requests python-dateutil
      - name: Run G-WEEKLY
        env:
          NOTION_TOKEN: ${{ secrets.NOTION_TOKEN }}
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        run: python scripts/g_weekly_report.py
```

---

## 📊 PE-3 점수 / PE-3 Score

| 평가 항목 | 점수 | 근거 |
|----------|------|------|
| 명확성 (Clarity) | **96** | 파라미터 정의 완전 명시, 모드별 분량 기준 명확 |
| 구조성 (Structure) | **96** | W-0~W-6 섹션 완전 구조화, 도메인별 KPI 세트 내장 |
| 특이성 (Specificity) | **94** | Gilbert 도메인 5종 완전 특화, KPI 자동 추출 로직 내장 |
| 실행가능성 (Executability) | **95** | GitHub Actions 스니펫 내장, E-0N 완전 자동화 |
| 적용가능성 (Applicability) | **96** | 주간 루틴 완전 자동화, G-004 파이프라인 연계 |
| **종합 (Total)** | **95** | PE-GEN 표준 수준 충족 |

---

## 🔗 Cross-Library Links

- [G-004 (G-SYNC) →](./G-SYNC_v1.0.md) — SSOT 동기화 (G-005 전제 실행)
- [G-001 (G-REPORT) →](./G-REPORT_v1.0.md) — FU-Series 보고서 연계
- [PE-GEN README →](./README.md) — 전체 인덱스
- [PE-7 v2.0 Notion →](https://www.notion.so/34955ed436f081149dd6de25dba027d7)
- [SSOT Hub →](https://www.notion.so/f392046f06ff491698ca249849f03a40)

---

## 📅 Changelog

| 버전 | 날짜 | 내용 |
|------|------|------|
| **v1.0.0** | 2026-04-28 | G-005 초기 릴리즈 — 주간 업무 요약 자동생성 |
