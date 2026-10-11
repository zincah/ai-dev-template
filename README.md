# AI 앱 개발 표준 템플릿

ChatGPT에서 기획하고 Codex에서 설계·구현·리뷰하는 한국어 문서 표준입니다.
Flutter iOS/Android를 중심으로 하며 Spring Boot는 선택 사항입니다. 앱 실행 코드나 서버 뼈대는 포함하지 않습니다.

## 빠른 시작

1. 새 앱 저장소에 templates/AGENTS.md를 AGENTS.md로, templates/docs/를 docs/로, standards/를 standards/로 복사합니다. 기존 파일이 있으면 덮어쓰지 말고 비교·병합합니다.
2. 프로젝트 AGENTS.md의 자리표시자와 실제 도구 버전·명령을 채웁니다.
3. prompts/CHATGPT_PLANNING.md와 기획 템플릿을 ChatGPT에 전달하고 확정 결과를 docs/에 저장합니다.
4. HANDOFF의 확정·미결정을 검토한 뒤 Codex 설계 프롬프트로 설계 문서와 TASKS를 작성합니다.
5. TASK 하나씩 구현 프롬프트로 실행하고 리뷰 프롬프트로 검토합니다.

자세한 절차: [사용 가이드](guides/USAGE.md)

## 지침 구성

- AGENTS.md: 이 템플릿 저장소 자체에 적용하는 공통 지침과 저장소 규칙
- standards/COMMON_AGENTS.md: 앱 저장소에서 명시적으로 읽도록 한 재사용 공통 지침
- templates/AGENTS.md: 앱별 기술 결정과 작업 명령을 채우는 파일
- standards/FLUTTER.md 및 SPRING_BOOT.md: 필요한 기술에만 적용

전역 ~/.codex/AGENTS.md는 자동 설치·수정하지 않습니다. 앱 저장소에 공통 지침을 함께 복사하므로 전역 설정 없이 사용할 수 있습니다. 임의 이름의 standards 문서는 자동 로딩을 기대하지 않고 프로젝트 AGENTS.md에서 읽도록 지시합니다.
공식 참고: [AGENTS.md 안내](https://learn.chatgpt.com/docs/agent-configuration/agents-md)

## 유지 관리와 보안

VERSION으로 사용한 표준 버전을 기록합니다. 앱별 결정은 프로젝트에서 관리하며 템플릿 업데이트를 앱에 자동 덮어쓰지 않습니다. 변경 시 차이를 검토해 필요한 규칙만 반영합니다.
회사 업무는 승인된 환경에서만 수행하며 기밀 자료를 개인 환경으로 무단 반출하지 않습니다. 자세한 필수 규칙은 standards/COMMON_AGENTS.md에 있습니다.
이 저장소는 로컬 Git 관리용이며 원격 저장소 생성·업로드는 별도 작업입니다.
