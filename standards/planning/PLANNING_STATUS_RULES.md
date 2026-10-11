# PLANNING_STATUS 운영 규칙

## 확인과 갱신 책임

실제 앱의 docs/PLANNING_STATUS.md가 현재 기획의 기준이다. 대화 시작 시 파일 내용·버전·갱신일을 확인한다. 접근할 수 없으면 문서 제공을 요청하거나 확인 가능한 정보만으로 잠정 진행하고 미검증 상태임을 밝힌다. 기존 상태를 추정해 덮어쓰지 않는다.
ChatGPT는 갱신안을 만들고, 파일 접근 권한이 있으면 저장 후 확인한다. 없으면 전체 Markdown 또는 정확한 변경 내용을 제공한다. 사용자가 저장·커밋한 내용을 다음 대화에 제공한다. 대화의 승인 사실과 파일 저장 여부를 따로 기록한다.

## 상태 전환

| 현재 | 다음 | 조건 |
|---|---|---|
| NOT_STARTED | IN_PROGRESS | 시작 정보 확인, 이전 단계 APPROVED(Phase 1 제외) |
| IN_PROGRESS | REVIEW | 산출물·완료 조건 점검 후 사용자 검토 대기 |
| IN_PROGRESS / REVIEW | BLOCKED | 진행을 막는 미결정·Critical, 사유·담당자·해소 조건 기록 |
| BLOCKED | IN_PROGRESS | 차단 해소 근거 기록 후 수정 작업 재개 |
| REVIEW | IN_PROGRESS | 사용자 수정 요청 또는 보완 필요 |
| REVIEW | APPROVED | 해당 문서 버전에 대한 명시적 사용자 승인·날짜·증거 기록 |
| APPROVED | REVIEW | 승인된 변경의 영향으로 기존 승인 기준이 달라짐; 이전 승인 이력 보존 |
| APPROVED | BLOCKED | 완료 조건을 깨는 Critical 또는 차단 문제 발견; 이전 승인 이력 보존 |

상태는 NOT_STARTED / IN_PROGRESS / BLOCKED / REVIEW / APPROVED만 사용한다. APPROVED였어도 변경 버전에 자동 승계하지 않는다. 영향 없는 단계는 승인 유지 이유를 적는다. 이전 단계가 재검토되면 영향을 받는 후속 단계도 REVIEW 또는 BLOCKED로 갱신한다.
현재 단계는 재검토가 필요한 가장 이른 단계 또는 진행 중인 단계다. 전체 상태는 초기 NOT_STARTED, 차단이 있으면 BLOCKED, 활성 검토 대기는 REVIEW, 그 외 작업 중이면 IN_PROGRESS다. 전체 APPROVED는 5단계 모두 최신 버전 승인·미해결 Critical 0건일 때만 가능하다.
Codex 인계 완료는 별도 필드에 일시·기준 커밋·수신 확인을 기록하며 전체 기획 상태와 혼동하지 않는다. Phase 5가 APPROVED여도 아직 전달 전일 수 있다.

## 갱신 시점

| 사건 | 갱신 항목 |
|---|---|
| 1 새 프로젝트 시작 | 프로젝트 정보, Phase 1 IN_PROGRESS, 나머지 NOT_STARTED |
| 2 기획 단계 변경 | 현재 단계, 이전 승인, 현재/다음 작업 |
| 3 주요 요구사항 확정 | PD 결정 요약, 관련 FR/NFR, 승인 증거 |
| 4 중요 미확정 추가 | Q ID, 중요도, 결정 필요 시점, 차단 여부 |
| 5 사용자 승인 완료 | 단계 상태, 승인자·날짜·문서 버전·증거 |
| 6 요구사항 변경 | CHG 요약·상세 이력 경로, 재검토 단계, 현재/다음 작업 |
| 7 검토 문제 발견 | REV ID 참조, 심각도, 차단 또는 재검토 상태 |
| 8 Codex 인계 완료 | 전달 버전/커밋, 수신 확인, 인계 상태·일시 |

매번 마지막 갱신일·문서 버전을 함께 수정한다. 상세 요구사항은 FR/NFR 문서, 상세 변경은 REQUIREMENT_CHANGES, 검토 지적은 PLANNING_REVIEW에 둔다. 상태 문서에는 요약과 ID/경로만 남긴다.
