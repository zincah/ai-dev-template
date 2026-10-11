# ChatGPT 기획 프롬프트

아래 아이디어를 모바일 앱 기획으로 구체화해 주세요.
아이디어: {{내용}}
대상 사용자와 해결할 문제: {{내용}}
제약·예산·기간: {{내용 또는 미결정}}
Flutter iOS/Android가 기본이며 서버 도입은 필요성을 먼저 검토해 주세요.
제공한 기획 템플릿 선택표를 사용하고 PRD, MVP_SCOPE(기존 앱은 MVP), USER_FLOW, SCREEN_SPEC, HANDOFF 및 단계별 상세 문서를 작성하세요.
질문은 한 번에 하나의 주요 의사결정에 집중하고 확정 사항·가정·미결정을 구분하세요. 새 앱은 FR/NFR/FLOW/SCR ID, 기존 앱은 REQ 대응 관계를 연결하고 실패 흐름과 수용 기준을 포함하세요.
기술 스택을 임의 확정하지 마세요. 합성 데이터만 사용하고 기밀 자료를 요청하지 마세요.
마지막에 Codex에 전달할 문서 목록과 설계에 필요한 미결정을 정리하세요.

## 표준화된 5단계 운영

기존 간단 입력 형식은 유지합니다. 제공된 CHATGPT_PLANNING_MASTER와 PLANNING_WORKFLOW를 적용하고 [신규 시작 프롬프트](chatgpt/START_NEW_PROJECT.md)로 연결하세요.
새 앱은 FR/NFR ID·MVP_SCOPE를 사용하고, 기존 REQ/MVP는 HANDOFF의 대응표·원본 경로를 따릅니다. 각 단계 종료 시 상태를 REVIEW로 두고 사용자 승인 후 APPROVED로 변경하세요. 파일 접근이 없으면 갱신할 Markdown을 제공하고 자동 저장·동기화를 가정하지 마세요.
