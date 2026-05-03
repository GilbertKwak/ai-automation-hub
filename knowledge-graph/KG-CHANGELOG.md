# Knowledge Graph Changelog

## v4.8 — 2026-05-03 22:30 KST

```
total_nodes : 144  (+2 from v4.7)
total_edges : 222  (+5 from v4.7)
base_version: v4.7 (142n / 217e)
trigger     : SAuRP-v3.1-KR + SAuRP-v3.1-GLOBAL PE-2 등록
command     : pe-graph --rebuild v4.8
author      : Gilbert
```

### 신규 노드 (+2)

| ID | 이름 | 타입 | 설명 |
|---|---|---|---|
| N-143 | `SAuRP-v3.1-OPT-HUB` | HubNode | SAuRP v3.1 계열 허브 노드 (Master+KR+GLOBAL 중계) |
| N-144 | `CONFLICT-MODE-ENGINE` | EngineNode | ESCALATE/CONTAIN/PIVOT 3종 모드 실행 엔진 |

### 신규 엣지 (+5)

| ID | Source | Target | 관계 | 설명 |
|---|---|---|---|---|
| E-218 | `SAuRP-v3.1-OPT-HUB` | `PE-STRAT` | `BELONGS_TO` | C-33 PE-STRAT 라이브러리 귀속 |
| E-219 | `SAuRP-v3.1-OPT-HUB` | `PE-AI` | `ECOSYSTEM_LINK` | EW-AI-01/02 연동 (C-28) |
| E-220 | `SAuRP-v3.1-OPT-HUB` | `PE-JV` | `ECOSYSTEM_LINK` | K-칩스법 정책 생태계 연계 |
| E-221 | `SAuRP-v3.1-OPT-HUB` | `STRAT-v5.2-OPT` | `CROSS_VALIDATES` | StrategicMonitoringAgent v5.2 교차 검증 |
| E-222 | `SAuRP-v3.1-OPT-HUB` | `IC-CLOCK` | `MONITORS` | IC-01~04 기한 카운트다운 연동 |

### v4.8 도메인별 누적 통계

```
PromptNode  : 38종 (SAuRP-v3.1-KR, GLOBAL 포함)
HubNode     : 4종
EngineNode  : 3종
SignalNode  : 12종 (EW 8종 + IC 4종)
EcosystemNode: 9종
기타         : 78종
```

### 누적 버전 이력

```
v4.4  : 133n / 201e  (C-33 신설 · 2026-04-30)
v4.5  : 136n / 207e  (SAR/SDR v3.1 6종)
v4.6  : 139n / 212e  (AUTOPLUS/GIPA/PHFA 고도화)
v4.7  : 142n / 217e  (STRAT-v5.2 3종 · SAuRP-v3.0 3종)
v4.8  : 144n / 222e  (SAuRP-v3.1-KR/GLOBAL PE-2 · CONFLICT-MODE-ENGINE 신설)
```

---

## v4.7 — 2026-05-03 19:51 KST

```
total_nodes : 142  (+3 from v4.6)
total_edges : 217  (+5 from v4.6)
base_version: v4.6 (139n / 212e)
trigger     : STRAT-v5.2-OPT + STRAT-v5.2-KR + STRAT-v5.2-GLOBAL 등록
author      : Gilbert
```

### 신규 노드 (+3)

| ID | 이름 | 타입 | 설명 |
|---|---|---|---|
| N-140 | `STRAT-v5.2-OPT` | PromptNode | StrategicMonitoringAgent Master (PE-3: 97) |
| N-141 | `STRAT-v5.2-KR` | PromptNode | StrategicMonitoringAgent KR 변형 (PE-3: 95) |
| N-142 | `STRAT-v5.2-GLOBAL` | PromptNode | StrategicMonitoringAgent 5개국 비교 변형 (PE-3: 94) |

### 신규 엣지 (+5)

| ID | Source | Target | 관계 | 설명 |
|---|---|---|---|---|
| E-213 | `STRAT-v5.2-OPT` | `STRAT-v5.2-KR` | `DERIVED_KR` | KR 파라미터 고정 변형 |
| E-214 | `STRAT-v5.2-OPT` | `STRAT-v5.2-GLOBAL` | `DERIVED_GLOBAL` | 5개국 비교 변형 |
| E-215 | `STRAT-v5.2-OPT` | `IC-03-KR` | `GATES` | 삼성 PoNR 2027-Q1 게이트 |
| E-216 | `STRAT-v5.2-KR` | `EW-KR-01` | `MONITORS` | HBM≥43% 감시 신호 |
| E-217 | `STRAT-v5.2-GLOBAL` | `AUTOPLUS-v1.0-GLOBAL` | `CROSS_VALIDATES` | 멀티국가 교차 검증 |

---

## v4.6 — 2026-05-03 17:22 KST
> AUTOPLUS-v1.0-OPT/KR/GLOBAL + GIPA-v2.0-OPT + PHFA-v2.0-OPT 등록
> 139n / 212e
