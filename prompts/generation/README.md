# PE-GEN — Report Auto-Generation Prompt Library Index

> **Category**: Prompt Engineering / Generation (PE-GEN)  
> **Version**: 1.1.0 | **Last Updated**: 2026-04-28 | **Phase**: I  
> **Maintainer**: Gilbert Kwak | **Repo**: `GilbertKwak/ai-automation-hub`  
> **Parent System**: 🤖 PE-7 AI 자동화 설계 및 구현 v2.0

---

## 개요 / Overview

PE-GEN은 Gilbert의 핵심 도메인(HBM Salvage · AI 인프라 · B-Star sCO2)에 특화된  
**보고서 자동생성 · Executive Summary · 슬라이드 스크립트 · SSOT 동기화 · 주간 업무 요약**  
5종 프롬프트 라이브러리입니다.

> **PE-7 v2.0 완전 통합**: 세션 자동 실행 프로토콜 + E-0N 오류 예측 시스템 + 3-Engine(PE-1/PE-2/PE-3) 연계

---

## 📁 Directory Structure

```
prompts/generation/
├── README.md                    ← 현재 파일 (마스터 인덱스)
├── G-REPORT_v1.0.md             (G-001) FU-Series 기술 보고서 자동생성
├── G-EXEC_v1.0.md               (G-002) Executive Summary 자동생성
├── G-SLIDE_v1.0.md              (G-003) 슬라이드 스크립트 자동생성
├── G-SYNC_v1.0.md               (G-004) Notion-GitHub SSOT 동기화 리포트
└── G-WEEKLY_v1.0.md             (G-005) 주간 업무 요약 자동생성
```

---

## 📋 전체 프롬프트 인덱스 / Full Prompt Index

| ID | 파일 | 생성 결과물 | 핵심 프레임워크 | PE-3 | 주요 용도 |
|----|------|-----------|--------------|------|----------|
| **G-001** | [G-REPORT_v1.0.md](./G-REPORT_v1.0.md) | FU-Series 기술 보고서 | Section 0~6 표준 + E-0N 내장 | **96** | FU-026+ 보고서 초안, 기술 실사 보고서 |
| **G-002** | [G-EXEC_v1.0.md](./G-EXEC_v1.0.md) | Executive Summary (1p) | Pyramid Principle + CTA 필수 | **95** | 투자자 브리핑, 이사회 보고, 파트너 제안 |
| **G-003** | [G-SLIDE_v1.0.md](./G-SLIDE_v1.0.md) | 슬라이드 스크립트 | 10-Slide Standard + Action Title | **94** | Pitch Deck, 이사회 업데이트, 컨퍼런스 발표 |
| **G-004** | [G-SYNC_v1.0.md](./G-SYNC_v1.0.md) | SSOT 동기화 리포트 | PE-7 5단계 파이프라인 + E-0N 전체 | **95** | 주간 동기화 감사, E-0N 자동 수정 리포트 |
| **G-005** | [G-WEEKLY_v1.0.md](./G-WEEKLY_v1.0.md) | 주간 업무 요약 리포트 | KPI 대시보드 + 블로커 감지 + 차주 계획 | **95** | 주간 정례 보고, 이사회 월간 검토, 슬랙 공유 |

---

## ⚡ Quick-Reference Usage

### 언제 어떤 프롬프트를 쓰는가?

| 상황 | 권장 프롬프트 | 호출 예시 |
|------|-------------|----------|
| FU-026 기술 보고서 초안 작성 | **G-001** | `G-REPORT [FU_NUMBER: FU-026] [DOMAIN: HBM_SALVAGE] [DEPTH: STANDARD]` |
| 투자자용 1페이지 요약 | **G-002** | `G-EXEC [PURPOSE: 투자 유치] [READER: INVESTOR] [DOMAIN: BSTAR_SCO2]` |
| B-Star sCO2 Pitch Deck 스크립트 | **G-003** | `G-SLIDE [TOPIC: B-Star Pre-Series A] [AUDIENCE: INVESTOR] [SLIDES: 10]` |
| 이사회 전략 보고 슬라이드 | **G-003** | `G-SLIDE [AUDIENCE: BOARD] [DOMAIN: HBM_SALVAGE] [SLIDES: 8]` |
| Notion-GitHub 동기화 점검 | **G-004** | `G-SYNC [SCAN_SCOPE: ALL] [AUTO_FIX: ON] [REPORT_FORMAT: STANDARD]` |
| 빠른 SHA 불일치 체크 | **G-004** | `G-SYNC [SCAN_SCOPE: SHA_ONLY] [REPORT_FORMAT: BRIEF]` |
| 이번 주 업무 요약 생성 | **G-005** | `G-WEEKLY [WEEK: 2026-W18] [DOMAIN: HBM_SALVAGE] [DEPTH: STANDARD]` |
| 전체 도메인 주간 요약 | **G-005** | `G-WEEKLY [WEEK: 2026-W18] [DOMAIN: ALL] [DEPTH: DEEP]` |
| 슬랙 공유용 빠른 요약 | **G-005** | `G-WEEKLY [WEEK: 2026-W18] [DOMAIN: BSTAR_STRATEGY] [DEPTH: BRIEF]` |
| HBM 기술 이사회 보고 패키지 | **G-001 + G-002** | G-001 생성 → G-002 [SOURCE: G-001 결과물] 순서 실행 |

---

## 🔗 PE-7 v2.0 통합 실행 흐름

```
[PE-7 v2.0 세션 시작]
      │
      ├─ [PRE] G-004(G-SYNC) → SSOT 스캔 + E-0N 자동 분류
      │
      ├─ [MON] G-005(G-WEEKLY) → 주간 업무 요약 자동 생성
      │   ├─ KPI 달성률 대시보드
      │   ├─ 블로커 감지 + 대안 제안
      │   └─ 차주 실행 계획 우선순위 정렬
      │
      ├─ [EXEC-A] 보고서 생성 파이프라인
      │   G-001 (기술 보고서) → G-002 (Executive Summary) → G-003 (Pitch Deck)
      │
      ├─ [EXEC-B] 분석 파이프라인 (PE-ANA 연계)
      │   A-MARKET → A-TECH → A-RISK → A-DECOMP
      │
      ├─ [EXEC-C] 전략 의사결정 (PE-CON 연계)
      │   C-BCG / C-MCK / C-ADV → 도메인 Variants
      │
      └─ [POST] G-004 동기화 리포트 자동 생성 → Notion + GitHub 업로드
```

---

## 🔄 PE-GEN × PE-ANA × PE-CON 연계 매트릭스

| 상황 | PE-ANA (분석) | PE-CON (전략) | PE-GEN (생성) |
|------|-------------|-------------|-------------|
| HBM 투자 패키지 | A-MARKET + A-RISK | C-BCG-HBM | G-001 + G-002 + G-003 |
| B-Star sCO2 Series A | A-TECH + A-MARKET | C-ADV-BSTAR | G-002 + G-003 |
| AI 인프라 파트너 제안 | A-DECOMP + A-TECH | C-MCK-AI_INFRA | G-003 + G-002 |
| 주간 SSOT 감사 | — | — | G-004 |
| 주간 업무 요약 | — | — | **G-005** |
| 월간 이사회 패키지 | A-MARKET + A-RISK | C-BCG | G-005(DEEP) + G-002 + G-003 |

---

## 📊 PE-3 Score Summary

| 프롬프트 | 명확성 | 구조성 | 특이성 | 실행가능성 | 적용가능성 | **종합** |
|---------|--------|--------|--------|-----------|-----------|--------|
| G-001 (REPORT) | 97 | 97 | 95 | 96 | 97 | **96** |
| G-002 (EXEC) | 96 | 95 | 94 | 96 | 96 | **95** |
| G-003 (SLIDE) | 95 | 95 | 93 | 94 | 94 | **94** |
| G-004 (SYNC) | 96 | 96 | 95 | 95 | 95 | **95** |
| G-005 (WEEKLY) | 96 | 96 | 94 | 95 | 96 | **95** |
| **평균** | **96.0** | **95.8** | **94.2** | **95.2** | **95.6** | **95.0** |

---

## 🏷️ Naming Convention

```
G-[FUNCTION]_v[MAJOR].[MINOR].md

예시:
G-REPORT_v1.0.md    → FU-Series 보고서 자동생성 v1.0
G-WEEKLY_v1.0.md    → 주간 업무 요약 자동생성 v1.0

ID 체계:
G-001 ~ G-005  = PE-GEN 핵심 5종
G-006+         = 향후 추가 생성 템플릿
```

---

## 🔗 Cross-Library Links

- [PE-CON 인덱스 →](../consulting/README.md) — BCG · McKinsey · CEO Advisor 전략 프롬프트
- [PE-ANA 인덱스 →](../analysis/README.md) — 프로세스 분해 · 시장 분석 · 기술 성숙도 · 리스크
- [PE-7 원본 →](https://www.notion.so/34955ed436f081149dd6de25dba027d7) — AI 자동화 심층 프롬프트 v2.0
- [SSOT Hub →](https://www.notion.so/f392046f06ff491698ca249849f03a40) — Workspace Master Directory
- [전체 CHANGELOG →](../../CHANGELOG.md)

---

## 📅 Changelog (PE-GEN)

| 버전 | 날짜 | 내용 |
|------|------|------|
| **v1.1.0** | 2026-04-28 | G-005 (G-WEEKLY) 추가 — 주간 업무 요약 자동생성 |
| **v1.0.0** | 2026-04-28 | PE-GEN 초기 릴리즈 — G-001 · G-002 · G-003 · G-004 |

---

## 🚀 Next Steps (Planned)

- [ ] `G-KG_v1.0.md` (G-006) — Knowledge Graph 자동생성 (build_kg 연동)
- [ ] `G-PR_v1.0.md` (G-007) — GitHub Pull Request 본문 자동생성
- [ ] G-005 GitHub Actions 스케줄 등록 (매주 월요일 08:00 KST)
- [ ] PE-GEN × GitHub Actions 완전 자동화 파이프라인
- [ ] G-SYNC 일일 자동 실행 스케줄 등록
