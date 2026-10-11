# Codex 설계 프롬프트

이 프로젝트 AGENTS.md, standards/COMMON_AGENTS.md 및 연결 기획 규칙을 읽어 주세요.
HANDOFF.md를 기준으로 PLANNING_STATUS, PRD, FUNCTIONAL_REQUIREMENTS, NON_FUNCTIONAL_REQUIREMENTS, MVP_SCOPE, USER_FLOW, SCREEN_SPEC, PLANNING_REVIEW를 확인하세요. 실제 경로는 앱의 docs/ 아래입니다. 변경이 있으면 REQUIREMENT_CHANGES도 읽으세요. 기존 앱의 MVP.md·REQ ID는 HANDOFF의 원본 경로와 대응표를 따르세요.

1. 기획 문서·버전·승인을 확인하세요. 읽지 못한 문서를 명시하세요.
2. 요구사항 일관성, Critical, 주요 미결정, 기존 코드와 기술 제약을 검토하세요.
3. 승인된 MVP 범위에서 아키텍처 대안·추천·근거·위험을 제안하세요. Flutter 모바일과 Spring Boot 단독/연계를 프로젝트 유형에 맞춰 검토하세요.
4. 이번 첫 요청은 아키텍처 제안까지입니다. 사용자 승인 전에 상세 설계·구현 코드를 작성하지 마세요.
5. 사용자가 제안을 승인하면 그 승인 버전을 기록하고 docs/ARCHITECTURE, DATABASE, API, DECISIONS를 상세화한 뒤 TASKS로 작업을 분할하세요. 불필요한 DB/API는 해당 없음과 이유를 남기세요.
6. 구현은 별도 CODEX_IMPLEMENT 요청에서 시작하세요.

FR/NFR·화면·수용 기준을 TASK에 연결하세요. 기획에 없는 기능을 추가하지 마세요. 기획 변경이 필요하면 CHG 요청과 문서·데이터·설계·구현 영향 분석을 먼저 보고하고 사용자 승인을 받으세요. Critical 또는 승인 누락이 있으면 해당 기획 단계로 되돌리는 조치를 제안하세요.
