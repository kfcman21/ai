# Copilot Studio 교육용 AI Agent

초등 교육 현장에서 쓰는 Copilot Studio 멀티 에이전트의 배포 저장소입니다.
페이지 소스와 구축 문서를 함께 관리합니다.

## 서비스

| 에이전트 | 배포 주소 | 소스 |
|---|---|---|
| 교육활동 AI Agent Builder | <https://kfcman.link/agency> | `index.html` |
| 지능형 과학교실 실험 AI Agent | <https://kfcman.link/co-science> | `co-science/index.html` |

두 페이지 모두 OCI 서버의 nginx로 서비스되며, GitHub Pages에도 미러링됩니다.

## 문서

| 문서 | 내용 |
|---|---|
| [Edu Agent Builder 구축 패키지](docs/Edu-Agent-Builder-구축패키지.md) | EA1~EA5 + 부모 지침, 붙여넣기용 전문 |
| [Science Lab Agent 구축 패키지](docs/Science-Lab-Agent-구축패키지.md) | SA1~SA5 + 부모 지침, 마이크로비트 연계 |

각 문서에 에이전트별 이름·Description·모델·Instructions 전문과 연결 설정, 테스트 시나리오, 알려진 한계가 정리되어 있습니다.

## 구성 패턴

두 에이전트 모두 같은 구조를 씁니다.

```
부모 에이전트 (라우팅·통합)
├── 성취기준 매핑      ← 지식 소스 필요
├── 활동/코드 생성
├── 데이터/평가
├── 산출물 작성
└── 안전 검토
```

**핵심 원칙** — 성취기준을 확정한 뒤에야 다음 단계로 넘어갑니다. 지식 소스 없이 운영하면 존재하지 않는 성취기준 코드를 만들어내므로, 성취기준 담당 에이전트에는 반드시 NCIC 교육과정 PDF를 업로드해야 합니다.

## 배포

`main` 브랜치에 병합되면 `deploy` 워크플로가 GitHub Pages로 배포합니다.
OCI 서버 반영은 `scp`로 별도 진행합니다.

```
/var/www/kfcman-agency/index.html
/var/www/kfcman-co-science/index.html
```

## 브랜치 규칙

`main`에는 직접 푸시하지 않습니다. 작업 브랜치를 만들고 PR로 병합합니다.

- `feature/...` 기능 추가
- `fix/...` 버그 수정
- `docs/...` 문서
- `design/...` 디자인 수정
- `chore/...` 기타
