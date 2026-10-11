# 사용 가이드

## 개발 경로 설정

`DEV_HOME`은 개인 개발 작업 폴더를 가리키는 환경 변수입니다. 아래 경로는 예시이므로 각자의 위치로 설정하세요. 개인 설정 파일은 이 저장소에 포함하지 않습니다.

```sh
export DEV_HOME="$HOME/workspace"
```

macOS 기본 zsh에서는 자신의 `~/.zprofile`에 선언하고 새 로그인 터미널을 열거나 `source ~/.zprofile`로 적용합니다. 이미 선언되어 있다면 중복 추가하지 않습니다.
이 문서의 명령은 DEV_HOME이 설정된 셸에서 실행합니다. GUI에서 실행한 앱에 변수가 전달되지 않으면 프로젝트 폴더를 직접 열고, 터미널에서 `echo "$DEV_HOME"`으로 확인하세요.

## 1. 새 앱 시작

개인 앱은 $DEV_HOME 아래 원하는 앱 폴더를 만듭니다. 회사 앱은 회사가 승인한 위치·기기·계정에서 진행합니다.
아래는 새 폴더에만 사용하는 복사 예입니다. 이미 있는 폴더에는 실행하지 말고 파일별 차이를 비교하세요.

```sh
(
  set -eu
  : "${DEV_HOME:?먼저 DEV_HOME을 설정하세요}"
  TEMPLATE="$DEV_HOME/ai-dev-template"
  PROJECT="$DEV_HOME/my-new-app"
  mkdir "$PROJECT"
  cp "$TEMPLATE/templates/AGENTS.md" "$PROJECT/AGENTS.md"
  cp -R "$TEMPLATE/templates/docs" "$PROJECT/docs"
  cp -R "$TEMPLATE/standards" "$PROJECT/standards"
  cp "$TEMPLATE/VERSION" "$PROJECT/TEMPLATE_VERSION"
)
```

위 예제는 하위 셸에서 실행되며 mkdir가 실패하면 후속 복사를 중단합니다. 앱 코드는 설계에서 정한 위치에 별도로 생성합니다. 템플릿 저장소의 루트 AGENTS.md 대신 templates/AGENTS.md를 사용합니다.

## 2. 기획과 인계

ChatGPT에 기획 프롬프트와 필요한 템플릿 내용을 전달합니다. 대화만 믿지 말고 PRD → MVP → USER_FLOW → SCREEN_SPEC → HANDOFF 순서로 결과를 파일에 저장합니다.
REQ-001 → FLOW-001 → SCR-001처럼 참조하고, 수용 기준은 관찰 가능한 결과로 작성합니다.
예: “제목이 비어 있으면 저장되지 않고 제목 입력란에 오류가 표시된다.”
HANDOFF에 문서 버전, 확정 사항, 미결정과 영향, 보안 제약을 기록합니다. ChatGPT의 제안은 사용자 검토 전까지 확정으로 표시하지 않습니다.

## 3. Codex 설계

Codex에서 앱 폴더를 열고 CODEX_DESIGN 프롬프트를 전달합니다. 실제 저장된 문서 경로를 알려 주세요. 대화가 자동 공유된다고 가정하지 않습니다.
아키텍처, 데이터, API, TASKS, DECISIONS를 검토합니다. 로컬 앱이면 서버/API는 해당 없음으로 처리할 수 있습니다.
설계 완료 조건은 MVP 기능의 TASK 연결, 수용 기준, 기술 선택 근거, 차단 미결정 해소입니다.

## 4. 구현과 리뷰

CODEX_IMPLEMENT에 TASK ID를 넣어 작업합니다. 작은 사용자 기능 단위로 진행하고 TASK에 검증 결과를 남깁니다.
Flutter 명령은 pubspec.yaml이 있는 디렉터리에서, 서버 명령은 해당 Wrapper가 있는 디렉터리에서 실행합니다. 이 템플릿 저장소에는 실행 대상이 없습니다.
CODEX_REVIEW로 변경을 검토하고 발견 사항을 수정·재검증합니다. 완료 보고에는 변경 내용, 검증 결과, 미검증 사항을 포함합니다.

## 5. 지침과 변경 관리

AGENTS.md는 짧게 유지하고 세부 내용은 명시적으로 참조합니다. 작업 시작 시 Codex에 적용한 지침과 문서 목록을 요약하도록 요청하면 누락을 확인하기 쉽습니다.
전역 지침을 도입할 때는 기존 ~/.codex/AGENTS.md 및 AGENTS.override.md, 사용자 설정을 먼저 확인하고 수동 비교·병합합니다. 이 저장소는 전역 파일을 건드리지 않습니다.
필수 규칙은 보안·사용자 변경 보존·정직한 검증 보고입니다. 상태관리, 계층 구조, DB와 백엔드 도입은 프로젝트별 결정입니다.
새 버전은 별도 브랜치에서 비교하여 반영합니다. 기존 앱 문서를 새 빈 템플릿으로 교체하지 않습니다.

## 6. 회사 업무

재택근무 허용과 개인 기기·개인 AI 계정 사용 허용은 별개입니다. 회사 승인 범위를 확인하고 승인된 환경에서만 접근합니다.
승인이 없거나 불명확하면 합성 예제로 일반적인 설계만 논의합니다. 코드 일부, 화면 캡처, 로그, 데이터베이스 스키마도 기밀일 수 있으므로 임의 반출하지 않습니다.
