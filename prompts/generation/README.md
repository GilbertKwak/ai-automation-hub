# PE-GEN — Report Auto-Generation Prompt Library Index

> **Category**: Prompt Engineering / Generation (PE-GEN)  
> **Version**: 1.2.0 | **Last Updated**: 2026-04-28 | **Phase**: I  
> **Maintainer**: Gilbert Kwak | **Repo**: `GilbertKwak/ai-automation-hub`  
> **Parent System**: 🤖 PE-7 AI 자동화 설계 및 구현 v2.0

---

## 개요 / Overview

PE-GEN은 Gilbert의 핵심 도메인(HBM Salvage · AI 인프라 · B-Star sCO2)에 특화된  
**보고서 자동생성 · Executive Summary · 슬라이드 스크립트 · SSOT 동기화 · 주간 업무 요약 · Knowledge Graph**  
6종 프롬프트 라이브러리입니다.

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
├── G-WEEKLY_v1.0.md             (G-005) 주간 업무 요약 자동생성
└── G-KG_v1.0.md                 (G-006) Knowledge Graph 자동생성
```

---

## 📋 전체 프롬프트 인덱스 / Full Prompt Index

| ID | 파일 | 생성 결과물 | 핵심 프레임워크 | PE-3 | 주요 용도 |
|----|------|-----------|--------------|------|----------|
| **G-001** | [G-REPORT_v1.0.md](./G-REPORT_v1.0.md) | FU-Series 기술 보고서 | Section 0~6 표준 + E-0N 내장 | **96** | FU-026+ 보고서 초안, 기술 실사 |
| **G-002** | [G-EXEC_v1.0.md](./G-EXEC_v1.0.md) | Executive Summary (1p) | Pyramid Principle + CTA 필수 | **95** | 투자자 브리핑, 이사회 보고 |
| **G-003** | [G-SLIDE_v1.0.md](./G-SLIDE_v1.0.md) | 슬라이드 스크립트 | 10-Slide Standard + Action Title | **94** | Pitch Deck, 컨퍼런스 발표 |
| **G-004** | [G-SYNC_v1.0.md](./G-SYNC_v1.0.md) | SSOT 동기화 리포트 | PE-7 5단계 파이프라인 + E-0N | **95** | 주간 동기화 감사, E-0N 수정 |
| **G-005** | [G-WEEKLY_v1.0.md](./G-WEEKLY_v1.0.md) | 주간 업무 요약 | KPI 대시보드 + 블로커 감지 | **95** | 주간 정례 보고, 이사회 검토 |
| **G-006** | [G-KG_v1.0.md](./G-KG_v1.0.md) | Knowledge Graph (3포맷) | build_kg 5단계 + 엔티티/관계 AUTO | **96** | KG 시각화, Neo4j 임포트, FU-Series 연계 |

---

## ⚡ Quick-Reference Usage

| 상황 | 권장 | 호출 예시 |
|------|------|----------|
| FU-026 보고서 초안 | **G-001** | `G-REPORT [FU_NUMBER: FU-026] [DOMAIN: HBM_SALVAGE] [DEPTH: STANDARD]` |
| 투자자용 1p 요약 | **G-002** | `G-EXEC [PURPOSE: 투자 유치] [READER: INVESTOR]` |
| Pitch Deck 스크립트 | **G-003** | `G-SLIDE [TOPIC: B-Star Pre-Series A] [SLIDES: 10]` |
| Notion-GitHub 동기화 점검 | **G-004** | `G-SYNC [SCAN_SCOPE: ALL] [AUTO_FIX: ON]` |
| 이번 주 업무 요약 | **G-005** | `G-WEEKLY [WEEK: 2026-W18] [DOMAIN: HBM_SALVAGE] [DEPTH: STANDARD]` |
| 전체 도메인 주간 요약 | **G-005** | `G-WEEKLY [WEEK: 2026-W18] [DOMAIN: ALL] [DEPTH: DEEP]` |
| HBM KG 생성 (Mermaid) | **G-006** | `G-KG [DOMAIN: HBM_SALVAGE] [OUTPUT_FORMAT: MERMAID] [DEPTH: STANDARD]` |
| 전체 KG Neo4j 임포트 | **G-006** | `G-KG [DOMAIN: ALL] [OUTPUT_FORMAT: CYPHER] [DEPTH: DEEP]` |
| FU-Series 빠른 KG 시각화 | **G-006** | `G-KG [SOURCE: FU_SERIES] [OUTPUT_FORMAT: MERMAID] [DEPTH: SHALLOW]` |
| HBM 투자 패키지 | **G-001+G-002** | G-001 생성 → G-002 [SOURCE: G-001] 순서실행 |

---

## 🔗 PE-7 v2.0 통합 실행 흐름

```
[PE-7 v2.0 세션 시작]
      │
      ├─ [PRE]  G-004(G-SYNC) → SSOT 스캔 + E-0N 자동 분류
      │
      ├─ [MON]  G-005(G-WEEKLY) → 주간 업무 요약 자동 생성
      │
      ├─ [WED]  G-006(G-KG) → Knowledge Graph 자동 생성·업데이트
      │
      ├─ [EXEC-A] 보고서 생성 파이프라인
      │   G-001 → G-002 → G-003
      │
      ├─ [EXEC-B] PE-ANA 분석 파이프라인
      │
      ├─ [EXEC-C] PE-CON 전략 의사결정
      │
      └─ [POST] G-004 동기화 리포트 → Notion + GitHub 업로드
```

---

## 🔄 PE-GEN × PE-ANA × PE-CON 연계 매트릭스

| 상황 | PE-ANA | PE-CON | PE-GEN |
|------|--------|--------|--------|
| HBM 투자 패키지 | A-MARKET + A-RISK | C-BCG-HBM | G-001 + G-002 + G-003 |
| B-Star sCO2 Series A | A-TECH + A-MARKET | C-ADV-BSTAR | G-002 + G-003 |
| AI 인프라 파트너 제안 | A-DECOMP + A-TECH | C-MCK-AI_INFRA | G-003 + G-002 |
| 주간 SSOT 감사 | — | — | G-004 |
| 주간 업무 요약 | — | — | G-005 |
| 지식 체계 형성/업데이트 | A-TECH | — | **G-006** |
| 월간 이사회 패키지 | A-MARKET + A-RISK | C-BCG | G-005(DEEP) + G-002 + G-003 + G-006 |

---

## 📊 PE-3 Score Summary

| 프롬프트 | 명확성 | 구조성 | 특이성 | 실행가능성 | 적용가능성 | **종합** |
|---------|--------|--------|--------|-----------|-----------|--------|
| G-001 | 97 | 97 | 95 | 96 | 97 | **96** |
| G-002 | 96 | 95 | 94 | 96 | 96 | **95** |
| G-003 | 95 | 95 | 93 | 94 | 94 | **94** |
| G-004 | 96 | 96 | 95 | 95 | 95 | **95** |
| G-005 | 96 | 96 | 94 | 95 | 96 | **95** |
| **G-006** | **97** | **97** | **95** | **96** | **96** | **96** |
| **평균** | **96.2** | **96.0** | **94.3** | **95.3** | **95.7** | **95.2** |

---

## 🏷️ Naming Convention

```
G-[FUNCTION]_v[MAJOR].[MINOR].md

ID 체계:
G-001 ~ G-006  = PE-GEN 핵심 6종
G-007+         = 향후 추가 생성 템플릿
```

---

## 🔗 Cross-Library Links

- [PE-CON →](../consulting/README.md) — BCG · McKinsey · CEO Advisor
- [PE-ANA →](../analysis/README.md) — 시장분석 · 기술성숙도 · 리스크
- [PE-7 v2.0 →](https://www.notion.so/34955ed436f081149dd6de25dba027d7)
- [SSOT Hub →](https://www.notion.so/f392046f06ff491698ca249849f03a40)
- [CHANGELOG →](../../CHANGELOG.md)

---

## 📅 Changelog (PE-GEN)

| 버전 | 날짜 | 내용 |
|------|------|------|
| **v1.2.0** | 2026-04-28 | G-006 (G-KG) 추가 — Knowledge Graph 자동생성 + build_kg 연동 |
| **v1.1.0** | 2026-04-28 | G-005 (G-WEEKLY) 추가 |
| **v1.0.0** | 2026-04-28 | PE-GEN 초기 릴리즈 — G-001 ~ G-004 |

---

## 🚀 Next Steps (Planned)

- [ ] `G-PR_v1.0.md` (G-007) — GitHub Pull Request 본문 자동생성
- [ ] G-005 GitHub Actions 스케줄 등록 (weekly-report.yml)
- [ ] G-006 GitHub Actions 스케줄 등록 (kg-build.yml)
- [ ] Neo4j 연동 추가 구성 (NEO4J_URI 시크릿 등록)
- [ ] 크로스-도메인 KG 자동 관심사항 분석 파이프라인
