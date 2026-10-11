# {{프로젝트명}} 작업 지침

작업 시작 시 standards/COMMON_AGENTS.md와 아래 문서를 읽고 적용한다.
- docs/PRD.md, docs/MVP.md, docs/HANDOFF.md
- docs/ARCHITECTURE.md, docs/TASKS.md, docs/DECISIONS.md
- 변경 기능에 해당하는 docs/USER_FLOW.md, docs/SCREEN_SPEC.md, docs/DATABASE.md, docs/API.md

## 프로젝트 결정
- 프로젝트 유형: {{Flutter 단독 / Flutter + Spring Boot / Spring Boot 단독}}
- 코드 위치: {{예: app/ 및 backend/ — 실제 구조에 맞게 수정}}
- Flutter/Dart 버전: {{확정 버전 또는 미결정}}
- Java/Spring Boot 버전, 빌드 도구: {{선택 시 기입, 미사용이면 해당 없음}}
- 상태관리/라우팅/저장소/인증: {{선택 근거는 DECISIONS.md}}
- 실행 명령 및 작업 디렉터리: {{실제 확인한 명령}}
- 검증 명령 및 작업 디렉터리: {{실제 확인한 명령}}

## 작업 방식
TASKS의 한 작업 단위로 구현하고 수용 기준을 확인한다. 요구사항 충돌은 위치와 영향을 보고한다. 차단되지 않는 부분은 진행하고 중요한 미결정은 사용자에게 확인한다. 변경한 계약과 결정 문서를 함께 갱신한다.
Flutter 변경은 standards/FLUTTER.md, 서버 변경은 standards/SPRING_BOOT.md를 읽는다. 서버 미사용 프로젝트에는 서버 규칙을 적용하지 않는다.
