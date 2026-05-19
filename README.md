# Harness Bake-off

**같은 스펙을 어떤 하니스(harness)로 구현하느냐에 따라 결과물이 어떻게 달라지는가**를 누적적으로 거증하기 위한 실험 레포.

## 실험 디자인

- `spec/prompt.md` — 모든 하니스에 동일하게 던지는 자연어 한 문단.
- `spec/notes.md` — 의도된 모호 지점과 채점 기준. (하니스에는 주지 않음. 사람이 평가할 때만 사용)
- `runs/<harness>/` — 하니스별 실행 결과. 코드/계획문서/노트가 모두 들어감.
- `matrix.md` — 회차마다 한 줄씩 누적되는 가로 비교표.

## 적용 순서 (예정)

1. **claude-code-plan-mode** — Claude Code의 Plan Mode (Shift+Tab×2). 가장 가벼운 plan-first.
2. **kiro** — AWS Kiro. SDD/EARS의 정석.
3. **bmad** — BMAD-METHOD. 다역할 에이전트 팀 시뮬레이션 + SDD + HITL.
4. **superpower** — Superpowers (Anthropic 마켓플레이스 플러그인). 마크다운 스킬 폴더 기반의 다중 호스트 하니스.
5. **ouroboros** — 자기 참조 프레임워크. 에이전트가 자신의 스캐폴딩을 진화시키는 Do→Learn→Improve→Retry 루프.

> Cursor는 의도적으로 제외 — 대조군 없이 "설계 강한 하니스끼리의 비교"에 집중.

## v1 스코프 (현재 회차)

스펙은 **단일 사용자 데스크톱/웹 간트차트**로 의도적으로 좁힌다. 멀티유저·실시간 동기화·임계경로·리소스 레벨링은 v2/v3에서 같은 `spec/` 디렉토리에 누적한다.

## 진행 규칙

1. 한 하니스 1회차마다 `runs/<harness>/notes.md`를 채운다 (모델 버전·날짜·사람 개입 횟수 등).
2. 산출물 코드/계획문서는 같은 폴더 안에 둔다.
3. 끝나면 `matrix.md`에 한 줄 추가.
4. 같은 하니스를 다시 돌릴 때는 `runs/<harness>/v2/`처럼 하위 폴더로 누적.
