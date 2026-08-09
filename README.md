# Coding Multi Model Agent

Copilot Studio로 만든 코딩용 Multi Model AI Agent의 배포 저장소입니다.

## 구성

| 에이전트 | 모델 | 역할 |
|---|---|---|
| Coding Multi Model Agent | Claude Sonnet 5 | 라우팅·결과 통합 |
| CA1-Sonnet5-Coder | Claude Sonnet 5 | 코드 작성·리팩터링 |
| CA2-Opus5-Architect | Claude Opus 5 | 설계·장문 문서 |
| CA3-GPT55-DevChat | GPT-5.5 Chat | 개념 설명·브레인스토밍 |
| CA4-GPT56-Debugger | GPT-5.6 Reasoning | 디버깅·검증 |
| CA5-GitHub-Ops | Claude Sonnet 5 | 커밋·PR·배포 |

## Actions

| 이름 | 대상 | 용도 |
|---|---|---|
| ExecuteCode | Azure Container Apps 동적 세션 | 생성 코드 자동 검증 |
| GitHub Ops (6종) | GitHub REST API | 저장·커밋·PR·배포 |
| RunOrcaJob | 사내 Orca 브리지 | 사내 시스템 실행 |

## 배포

`main` 브랜치에 푸시하거나 Actions 탭에서 `deploy` 워크플로를 수동 실행하면
GitHub Pages로 배포됩니다.

## 브랜치 규칙

`main`에는 직접 푸시하지 않습니다. 작업 브랜치를 만들고 PR로 병합합니다.

- `feature/...` 기능 추가
- `fix/...` 버그 수정
- `docs/...` 문서
- `chore/...` 기타
