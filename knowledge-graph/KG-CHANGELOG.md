# Knowledge Graph Changelog

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

### 누적 통계

```
v4.4  : 133n / 201e  (C-33 신설)
v4.7  : 142n / 217e  (STRAT v5.2 3종 등록)
```

---

## v4.6 — 2026-05-03 17:22 KST
> AUTOPLUS-v1.0-OPT/KR/GLOBAL + GIPA-v2.0-OPT + PHFA-v2.0-OPT 등록
> 139n / 212e
