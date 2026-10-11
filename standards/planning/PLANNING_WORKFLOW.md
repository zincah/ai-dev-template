# 기획 운영 프로세스

아이디어 발굴 → ChatGPT 서비스 기획 → 요구사항 정의 → UX·화면 명세 → 기획 최종 검증 → Codex 인계 → 아키텍처 설계 → 개발 계획 → 기능별 구현 → 테스트·코드 리뷰 → 앱 출시.
기획의 5단계는 아래와 같다. 개발 규칙은 기존 standards와 AGENTS.md를 유지한다.

| 단계 | 상세 규칙 | 산출물 | 승인 기준 |
|---|---|---|---|
| 1 Idea Discovery | [서비스 개념](phases/01_IDEA_DISCOVERY.md) | IDEA_BRIEF.md | 목적·사용자·문제·가치 명확 |
| 2 Product Planning | [제품 기획](phases/02_PRODUCT_PLANNING.md) | PRD.md | 기능·관계·범위·제약 명확 |
| 3 Requirements Definition | [요구사항](phases/03_REQUIREMENTS.md) | FUNCTIONAL_REQUIREMENTS.md, NON_FUNCTIONAL_REQUIREMENTS.md, MVP_SCOPE.md | 완료 조건·MVP·예외 확정 |
| 4 UX Specification | [UX 명세](phases/04_UX_SPECIFICATION.md) | USER_FLOW.md, SCREEN_SPEC.md | 화면·이동·상태 검증 |
| 5 Final Review & Handoff | [최종 검토](phases/05_FINAL_REVIEW.md) | PLANNING_REVIEW.md, HANDOFF.md | Critical 없음·사용자 승인·인계 준비 |

## 템플릿과 단일 원본

기획 문서 이름은 실제 앱의 docs/ 기준이다. templates/planning의 참조형 템플릿은 안내를 복사하지 말고 연결된 templates/docs 원본을 복사한다. [사용 가이드](https://github.com/zincah/ai-dev-template/blob/main/guides/USAGE.md)의 명령은 이를 처리한다.

| 실제 문서 | 템플릿 | 적용 |
|---|---|---|
| IDEA_BRIEF.md | [아이디어](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/IDEA_BRIEF_TEMPLATE.md) | Phase 1 필수 |
| PRD.md | [제품 방향](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/PRD_TEMPLATE.md) → 기존 원본 확장 | 필수 |
| FUNCTIONAL_REQUIREMENTS.md | [FR](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/FUNCTIONAL_REQUIREMENTS_TEMPLATE.md) | 필수 |
| NON_FUNCTIONAL_REQUIREMENTS.md | [NFR](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/NON_FUNCTIONAL_REQUIREMENTS_TEMPLATE.md) | 필수 |
| MVP_SCOPE.md | [MVP](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/MVP_SCOPE_TEMPLATE.md) → 기존 MVP 원본 확장 | 필수 |
| USER_FLOW.md | [흐름](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/USER_FLOW_TEMPLATE.md) → 기존 원본 확장 | 필수 |
| SCREEN_SPEC.md | [화면](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/SCREEN_SPEC_TEMPLATE.md) → 기존 원본 확장 | 모바일 필수, 서버 단독은 해당 없음·근거 |
| PLANNING_STATUS.md | [상태](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/PLANNING_STATUS_TEMPLATE.md) | 항상 필수 |
| PLANNING_REVIEW.md | [최종 검토](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/PLANNING_REVIEW_TEMPLATE.md) | 인계 전 필수 |
| HANDOFF.md | [인계](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/HANDOFF_TEMPLATE.md) → 기존 원본 확장 | 인계 전 필수 |
| REQUIREMENT_CHANGES.md | [변경](https://github.com/zincah/ai-dev-template/blob/main/templates/planning/REQUIREMENT_CHANGES_TEMPLATE.md) | 확정 요구사항 변경 시 필수, 초기엔 빈 이력 |

필수 문서는 짧은 표와 ID 참조로 작성한다. 시작 시 빈 템플릿을 준비하되 해당 단계에서 필요한 내용만 채운다. 사업 분석·별도 와이어프레임·ERD·상세 API 계약은 필요할 때 추가한다. DATABASE/API 상세 설계는 Codex 단계의 기존 템플릿을 사용한다. Spring Boot 단독도 5단계를 거치되 UI 항목의 해당 없음을 승인받는다.

## ID와 기존 프로젝트 호환

FR-001은 상세 기능, NFR-001은 비기능, SCR-001은 화면, FLOW-001은 흐름이다. REQ-001은 기존 제품 요구사항 ID로 유지할 수 있다. 신규 상세 요구사항은 FR/NFR로 작성한다.
추적: PRD의 제품 REQ → FR/NFR → MVP 포함 FR → FLOW/SCR → 설계/API → TASK → 검증 결과.
이미 있는 REQ ID를 자동 치환하거나 재사용하지 않는다. 기존 앱은 HANDOFF에 기존 ID ↔ 새 ID 대응표를 작성하고 승인된 변경으로만 이관한다. MVP.md와 MVP_SCOPE.md를 동시에 원본으로 관리하지 않는다. 기존 앱은 MVP.md를 원본으로 유지하고 HANDOFF/AGENTS에 경로를 명시할 수 있다. 새 앱은 MVP_SCOPE.md를 사용한다.
기술 결정 ADR은 DECISIONS.md, 기획 결정 요약 PD는 PLANNING_STATUS.md에 둔다. 같은 결정의 자세한 근거는 원문 경로로 참조한다.

## 공통 운영

[마스터 지침](CHATGPT_PLANNING_MASTER.md), [상태 규칙](PLANNING_STATUS_RULES.md), [변경 규칙](REQUIREMENT_CHANGE_RULES.md), [품질 규칙](PLANNING_QUALITY.md)을 따른다. 모든 단계는 해당 버전에 대한 사용자 승인 후 전환한다. 최신 승인 내용은 Git에 저장하고 ChatGPT에 명시적으로 제공한다. 대화·업로드 파일·Git 사이 자동 동기화를 가정하지 않는다.
