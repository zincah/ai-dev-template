# HANDOFF 템플릿 사용 안내

## 문서 목적

사용자 승인된 기획 기준과 미결정을 Codex에 전달한다. 기존 문서와의 중복을 막기 위해 작성 원본은 [기존 HANDOFF 템플릿](../docs/HANDOFF.md) 한 곳에서 확장·관리한다.

## 작성 방법

이 안내 파일 대신 연결된 원본 전체를 실제 앱 docs/HANDOFF.md로 복사한다. Phase 5에 작성하고 기존 1~9절을 채운다. 최종 승인 후 파일을 Git에 저장한다. HANDOFF 안에 자신의 최종 커밋 해시를 미리 적는 대신 인계 시 실제 기준 커밋을 메시지와 PLANNING_STATUS에 기록한다.

## 필수 작성 항목

원본의 기존 번호별 항목과 “필수 작성 항목”을 채운다. 필수 문서와 기준 버전: HANDOFF, PLANNING_STATUS, PRD, FUNCTIONAL_REQUIREMENTS, NON_FUNCTIONAL_REQUIREMENTS, MVP_SCOPE, USER_FLOW, SCREEN_SPEC, PLANNING_REVIEW: {{버전표}}

## 작성 예시

습관 앱 기획 v0.1의 5단계를 사용자가 승인했고 Critical 0건이다. FR-001·NFR-001이 MVP 기준이며 Q-001 서버 도입 여부는 설계 시작 전에 결정해야 한다. Codex에는 먼저 아키텍처 제안까지만 요청하고 승인 전 상세 설계·구현을 시작하지 않는다.

## 검증 체크리스트

- [ ] 안내 파일이 아닌 연결된 원본을 복사했는가?
- [ ] 원본의 필수 항목과 검증 체크리스트를 완료했는가?
- [ ] 실제 앱에서 같은 목적의 문서를 두 개의 원본으로 관리하지 않는가?
