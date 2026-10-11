# 기획 품질 검토 프롬프트

제공한 기획 문서를 검토해 주세요. [품질 규칙](../../standards/planning/PLANNING_QUALITY.md)과 [검토 템플릿](../../templates/planning/PLANNING_REVIEW_TEMPLATE.md)을 함께 제공합니다.
입력: HANDOFF, PLANNING_STATUS, PRD, FUNCTIONAL_REQUIREMENTS, NON_FUNCTIONAL_REQUIREMENTS, MVP_SCOPE, USER_FLOW, SCREEN_SPEC 및 변경이 있으면 REQUIREMENT_CHANGES.
접근 가능한 문서의 버전과 미제공 문서를 먼저 명시하세요. 미제공 자료를 읽었다고 말하거나 모든 항목이 통과했다고 가정하지 마세요.

1. MVP 기능의 요구사항 ID
2. 핵심 기능 완료 조건
3. FR·SCR 연결(서버 단독은 근거·소비자 흐름)
4. 정상·예외 흐름
5. 요구사항 간 충돌
6. 중요한 미확정 사항
7. 데이터 저장·삭제·보관
8. 보안·개인정보
9. MVP 과다 범위
10. Codex 설계 시작 가능성

위 10개 항목을 각각 근거 문서·ID와 함께 평가하세요. 지적은 Critical/Major/Minor로 분류하고 REV ID, 영향, 조치, 담당자·기한, 재검증 상태를 PLANNING_REVIEW.md에 기록하세요.
Critical이 남으면 완료·승인 상태로 바꾸지 마세요. Major는 해결 또는 사용자 위험 수용을 요구하고 후속 조치를 남기세요. 확정 요구사항은 임의 수정하지 말고 CHG로 제안하세요.
PLANNING_STATUS의 Phase 5를 REVIEW 또는 차단 시 BLOCKED로 갱신하는 안을 제공하세요. 사용자 승인 없이 APPROVED로 변경하지 마세요. 파일 수정이 불가능하면 갱신할 Markdown을 제공하세요.
