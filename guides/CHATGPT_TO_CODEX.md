# ChatGPT → Codex 인수인계

## 인계 준비

기획 원본은 앱 저장소 docs/에 저장한 승인된 Markdown이다. ChatGPT 대화나 파일이 Codex에 자동 공유된다고 가정하지 않는다. 파일 수정이 불가능한 ChatGPT 환경에서는 사용자가 제공받은 Markdown을 저장하고 버전·승인 기록을 확인한 뒤 Git에 커밋한다.
HANDOFF에 문서별 기준 버전, 승인 증거, 미결정·위험·차단 여부를 적는다. 자신의 마지막 커밋 해시를 문서에 미리 넣으려 하지 않는다. 인계 시 `git rev-parse HEAD` 결과를 메시지로 전달하고 필요하면 PLANNING_STATUS에 “전달 기준 커밋”으로 남긴다. 이후 상태 기록 커밋과 전달 기준 커밋을 구분한다.

## Codex 필수 확인 문서

1. HANDOFF.md: 설계 요청 범위·기준 버전
2. PLANNING_STATUS.md: 최신 단계·승인·미결정
3. PRD.md: 제품 방향과 범위
4. FUNCTIONAL_REQUIREMENTS.md: FR 원문
5. NON_FUNCTIONAL_REQUIREMENTS.md: NFR 원문
6. MVP_SCOPE.md: 포함·제외 ID
7. USER_FLOW.md: 정상·예외 사용자/소비자 흐름
8. SCREEN_SPEC.md: SCR 연결·상태, 서버 단독은 해당 없음·근거
9. PLANNING_REVIEW.md: 품질 검증·잔여 위험

변경이 있으면 REQUIREMENT_CHANGES, 맥락이 필요하면 IDEA_BRIEF도 읽는다. AGENTS.md와 공통·기술별 지침은 계속 적용한다.
기존 프로젝트는 HANDOFF에 MVP.md 원본 경로와 REQ 대응 관계를 명시한다. 기존 앱을 새 양식으로 조용히 덮어쓰지 않는다. 새 기준 적용 전 누락 문서와 전환 영향을 보고하고 사용자가 승인한 이관만 수행한다.

## 작업 순서와 승인 경계

문서 확인 → 요구사항 일관성 검토 → 미확정 확인 → 기술 제약 분석 → 아키텍처 제안 → 사용자 승인 → 상세 설계 → 개발 TASK 분할 → 별도 구현 요청에 따라 구현 시작.

첫 요청은 [CODEX_DESIGN](../prompts/CODEX_DESIGN.md)을 사용한다. 첫 응답은 아키텍처 대안·추천 근거·위험·질문까지이며, 승인 전에 상세 설계나 앱 코드를 작성하지 않는다. 승인 후 동일 채팅에서 ARCHITECTURE/DATABASE/API/TASKS/DECISIONS를 구체화한다. 구현은 [CODEX_IMPLEMENT](../prompts/CODEX_IMPLEMENT.md)에 TASK ID를 지정해 요청한다.
기획 문서에 없는 기능은 임의 추가하지 않는다. 변경이 필요하면 CHG 제안과 FR/NFR·화면·데이터·문서·설계·구현 영향을 먼저 보고하고 사용자 승인 후 반영한다. 기술 선택은 프로젝트별 ADR로 관리한다.

## 전달 메시지 예시

```text
이 저장소 docs/HANDOFF.md를 기준으로 기획을 인수인계합니다.
전달 기준 커밋: <git rev-parse HEAD 결과>
PLANNING_STATUS 및 HANDOFF에 기록한 문서 버전·승인을 확인하세요.
CODEX_DESIGN 프롬프트에 따라 우선 아키텍처 제안까지만 진행하세요.
차단 미결정이나 문서 충돌이 있으면 보고하고 기능을 추측해 추가하지 마세요.
```

Codex가 실제 읽은 문서·버전, 불일치, 차단 Q, 설계 시작 가능 여부를 보고하면 PLANNING_STATUS의 수신 확인과 인계 일시를 갱신한다. Critical이나 승인 누락이 있으면 기획 완료를 주장하지 말고 관련 단계로 돌아간다.

## 개발 이후

기존 Flutter·Spring Boot 검증 규칙과 TASK 수용 기준을 적용한다. 변경 사항은 기능 리뷰와 적절한 테스트로 확인한다. 출시 시 서명·스토어 정보·개인정보 고지·운영 설정·롤백 준비를 점검하고 실제 배포·스토어 제출은 별도 사용자 승인 범위에서 수행한다.
