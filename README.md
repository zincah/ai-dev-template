# AI 앱 개발 표준 템플릿

ChatGPT에서 기획하고 Codex에서 설계·구현·리뷰하는 한국어 문서 표준입니다.
Flutter iOS/Android를 중심으로 하며 Spring Boot는 선택 사항입니다. 앱 실행 코드나 서버 뼈대는 포함하지 않습니다.

## 빠른 시작

1. [사용 가이드](guides/USAGE.md)의 `$DEV_HOME` 기반 명령으로 새 앱 저장소를 준비합니다. 기획 원본은 새 이름으로 복사하고 standards/와 프로젝트 AGENTS.md를 함께 둡니다. 기존 파일은 비교·병합합니다.
2. 프로젝트 AGENTS.md의 자리표시자와 실제 도구 버전·명령을 채웁니다.
3. ChatGPT 프로젝트에 기획 마스터 지침·필요한 템플릿을 제공하고 시작 프롬프트로 5단계를 진행합니다. 단계별 승인 결과와 상태를 docs/에 저장합니다.
4. 최종 검토·사용자 승인 후 HANDOFF와 기준 커밋으로 Codex에 전달합니다. 아키텍처 제안 승인 후 상세 설계·TASKS를 작성합니다.
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

## 전체 AI 개발 프로세스

아이디어 발굴 → ChatGPT 서비스 기획 → 요구사항 정의 → UX·화면 명세 → 기획 최종 검증 → Codex 인수인계 → 시스템 아키텍처 설계 → 개발 계획 → 기능별 구현 → 테스트·코드 리뷰 → 앱 출시.
Flutter/Dart iOS·Android 중심이며 Java/Spring Boot 단독 또는 연계도 지원합니다. macOS의 `$DEV_HOME` 경로와 GitHub 버전 관리를 사용합니다.

## ChatGPT 서비스 기획 표준

- [마스터 지침](standards/planning/CHATGPT_PLANNING_MASTER.md): 앱별 ChatGPT 프로젝트 지침에 복사합니다.
- [5단계 워크플로와 템플릿 선택표](standards/planning/PLANNING_WORKFLOW.md): 아이디어 → 제품 → 요구사항 → UX → 최종 검토·인계.
- [PLANNING_STATUS 운영](standards/planning/PLANNING_STATUS_RULES.md): 현재 단계·결정·미결정·승인·다음 작업을 요약합니다.
- [요구사항 변경 관리](standards/planning/REQUIREMENT_CHANGE_RULES.md): CHG 제안·영향 분석·사용자 승인·반영·재검토.
- [기획 품질 검증](standards/planning/PLANNING_QUALITY.md): 10개 검토 항목, Critical/Major/Minor와 완료 기준.
- [ChatGPT 프로젝트 설정](guides/CHATGPT_PROJECT_SETUP.md), [Codex 인계](guides/CHATGPT_TO_CODEX.md).
- [신규 기획 시작](prompts/chatgpt/START_NEW_PROJECT.md), [최종 검토 프롬프트](prompts/chatgpt/PLANNING_REVIEW.md).

문서 템플릿은 templates/planning/에서 찾습니다. 기존 PRD/MVP/USER_FLOW/SCREEN_SPEC/HANDOFF 작성 원본은 templates/docs/에 유지·확장했고 planning의 동일 목적 파일은 원본 사용 안내입니다. 새 앱의 MVP 원본은 MVP_SCOPE.md입니다. 기존 앱은 MVP.md와 REQ ID를 유지할 수 있습니다.
단계별 필수 문서는 짧은 표로 작성하고 상세 FR/NFR를 여러 파일에 복제하지 않습니다. 서버 단독은 자체 화면 항목에 해당 없음과 근거를 적고 API 소비자 흐름을 정의합니다. 선택 문서와 적용 조건은 워크플로 표를 참고합니다.

## 새 앱 기획 예시

```text
개인 습관 기록 앱을 기획하고 싶습니다.
사용자는 운동 여부를 간단히 기록하고 싶은 사람입니다.
Flutter iOS/Android를 생각하고 서버 도입은 미정입니다.
제공한 마스터 지침과 START_NEW_PROJECT에 따라 상태를 초기화하고
Phase 1의 문제·사용자·핵심 가치 질문 하나부터 시작해 주세요.
```

ChatGPT가 파일을 수정할 수 없으면 갱신된 Markdown을 받아 앱 저장소 docs/에 저장합니다. Git에 커밋한 승인 문서와 HANDOFF를 Codex가 읽도록 전달합니다. ChatGPT·Codex 대화나 파일의 자동 동기화를 가정하지 않습니다.

## 디렉터리 구성

```text
ai-dev-template/
├── AGENTS.md / README.md / VERSION
├── standards/
│   ├── COMMON_AGENTS.md / FLUTTER.md / SPRING_BOOT.md
│   └── planning/
│       ├── CHATGPT_PLANNING_MASTER.md / PLANNING_WORKFLOW.md
│       ├── PLANNING_STATUS_RULES.md / REQUIREMENT_CHANGE_RULES.md
│       ├── PLANNING_QUALITY.md
│       └── phases/ (01~05 단계 운영 규칙)
├── templates/
│   ├── AGENTS.md
│   ├── docs/ (기존 기획 원본·아키텍처·DB·API·TASKS·DECISIONS)
│   └── planning/ (11종 템플릿과 원본 안내)
├── prompts/
│   ├── CHATGPT_PLANNING.md / CODEX_DESIGN.md
│   ├── CODEX_IMPLEMENT.md / CODEX_REVIEW.md
│   └── chatgpt/ (START_NEW_PROJECT.md / PLANNING_REVIEW.md)
└── guides/
    ├── USAGE.md
    ├── CHATGPT_PROJECT_SETUP.md
    └── CHATGPT_TO_CODEX.md
```

## 향후 개선 후보

실제 앱 한 개에 적용한 뒤 반복되는 문서 항목을 줄이고, 필요하면 ID 참조 검사·GitHub 체크리스트 자동화를 추가합니다. 현재는 기획·설계·개발 문서만 제공하며 앱 실행 코드는 포함하지 않습니다.
