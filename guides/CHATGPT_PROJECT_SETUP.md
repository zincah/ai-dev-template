# ChatGPT 앱별 프로젝트 운영 가이드

## 1. 프로젝트 생성과 지침 적용

ChatGPT에서 앱 하나당 프로젝트 하나를 생성하고 앱 이름으로 구분한다. 프로젝트의 지침 편집 기능에 [마스터 지침](../standards/planning/CHATGPT_PLANNING_MASTER.md) 본문을 복사한다. [공식 프로젝트 안내](https://learn.chatgpt.com/docs/projects)를 참고하되 메뉴 위치·사용 가능 기능은 사용하는 화면과 계정에서 확인한다.
프로젝트에 필요한 기획 템플릿과 [워크플로](../standards/planning/PLANNING_WORKFLOW.md)를 파일로 제공하거나 내용을 붙여 넣는다. 파일을 추가했다는 사실만으로 로컬 Git의 변경이 자동 반영된다고 가정하지 않는다.
회사 프로젝트는 회사 승인 계정·환경에서만 만든다. 비밀·고객 데이터는 제공하지 않는다.

## 2. 신규 기획과 상태 초기화

[로컬 사용 가이드](USAGE.md)의 명령으로 앱 저장소를 준비한다. [시작 프롬프트](../prompts/chatgpt/START_NEW_PROJECT.md)에 아이디어·사용자·제약을 입력한다.
상태 문서는 templates/planning/PLANNING_STATUS_TEMPLATE.md를 앱 docs/PLANNING_STATUS.md로 복사한다. 실제 시작 정보를 확인한 후 Phase 1 IN_PROGRESS, 나머지 NOT_STARTED로 갱신한다. 기존 프로젝트라면 초기화하지 말고 최신 상태·문서를 먼저 제공한다.

## 3. 단계별 기획과 문서 작성

| 단계 | 작성·검토할 문서 |
|---|---|
| 1 | IDEA_BRIEF.md |
| 2 | PRD.md |
| 3 | FUNCTIONAL_REQUIREMENTS.md, NON_FUNCTIONAL_REQUIREMENTS.md, MVP_SCOPE.md |
| 4 | USER_FLOW.md, SCREEN_SPEC.md |
| 5 | PLANNING_REVIEW.md, HANDOFF.md |

한 번에 하나의 주요 결정을 다룬다. 단계가 끝나면 완료 조건·결정·미결정·문서 버전을 요약하고 사용자 승인 전에 다음 단계로 넘어가지 않는다. 사용자는 “Phase 2 PRD v0.2를 승인합니다”처럼 대상을 명시한다. AI의 제안을 승인으로 취급하지 않는다.
세부 FR/NFR 원문은 각 요구사항 문서에만 둔다. 제품 방향은 PRD, 범위는 MVP_SCOPE, 화면 표현은 SCREEN_SPEC에서 ID로 연결한다. 모바일은 SCR을 정의하고 서버 단독은 자체 UI 해당 없음의 근거와 API 소비자 흐름을 기록한다.

## 4. 상태 갱신과 저장

[상태 규칙](../standards/planning/PLANNING_STATUS_RULES.md)의 8개 시점마다 요약을 갱신한다. 매 대화 시작에 최신 PLANNING_STATUS와 변경된 문서·버전을 제공한다. 사용자 승인 날짜·증거를 기록한다.
파일을 직접 수정할 수 없는 환경에서는 ChatGPT가 파일명과 갱신된 Markdown 또는 정확한 변경안을 제공하고 사용자가 앱 저장소 docs/에 반영한다. 저장·Git 커밋 후 필요하면 ChatGPT 프로젝트의 사본도 갱신한다. 저장을 확인하기 전에는 반영 완료로 표시하지 않는다.

## 5. 변경 관리와 최종 검토

확정 사항의 변경은 REQUIREMENT_CHANGES에 CHG로 제안한다. 영향 분석 → 사용자 승인 → 확정 문서 반영 → 참조 검증 → APPLIED 순서다. 영향받은 승인 단계는 REVIEW로 돌리고 재승인을 받는다.
[기획 검토 프롬프트](../prompts/chatgpt/PLANNING_REVIEW.md)를 실행한다. Critical을 해결하고 Major 잔여 위험은 해결 또는 명시적 수용을 기록한다. 최종 사용자 승인 후에만 Phase 5와 전체 상태를 APPROVED로 갱신한다.

## 6. Codex 인계

승인된 문서를 Git에 저장하고 경로·기준 커밋을 전달한다. [인계 가이드](CHATGPT_TO_CODEX.md)를 따른다. 대화·업로드·Codex 작업 파일의 자동 동기화는 전제하지 않는다.
개인 개발자는 필수 문서를 짧은 표로 유지하고 별도 와이어프레임·시장 조사·ERD는 필요할 때만 추가한다. 빈 양식을 한 번에 전부 채울 필요는 없다.
