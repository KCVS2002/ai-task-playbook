# 파일 가져오기와 적용

## 1. Codex에게 가져오게 하기: 기본 경로

> 이 공개 저장소의 README.md와 workflow.md를 현재 작업 공간 안의 별도 참고 폴더로 다운로드해줘. 과제 파일과 기존 지침은 유지하고, 저장한 경로를 알려줘. 그다음 현재 과제에 맞는 질문과 계획을 정리해줘.
>
> https://github.com/KCVS2002/ai-task-playbook

원격 파일을 실제로 읽었는지, 저장한 경로가 어디인지 확인합니다.
지원되지 않는 웹 검색 도구가 있다고 가정하지 말고, 허용된 터미널 다운로드나 Git Clone을 사용합니다.

## 2. 터미널로 전체 저장소 가져오기

아래는 Linux 계열 셸의 예시입니다. 현재 과제 작업 폴더에서 실행합니다.
`reference-playbook` 폴더가 이미 있으면 다른 비어 있는 이름을 사용하고 기존 폴더를 덮어쓰지 않습니다.

```bash
git clone --depth 1 https://github.com/KCVS2002/ai-task-playbook.git reference-playbook
```

명령은 일반 셸에 입력합니다. Codex가 실행 중이면 별도 터미널을 사용하거나 Codex에게 같은 다운로드를 요청합니다.

- 과제 작업 위치를 유지합니다. `cd reference-playbook`로 과제 위치를 바꾸지 않습니다.
- IDE 탐색기에서 `reference-playbook/workflow.md`를 클릭해 엽니다.
- 파일 목록이 늦게 갱신되면 탐색기를 새로고침합니다.
- Codex에게 `reference-playbook/README.md`와 `reference-playbook/workflow.md`를 읽으라고 요청합니다.
- 새 도구가 필요해지면 `reference-playbook/TOOLBOX.md`를 읽게 합니다.
- 가져온 참고 폴더에 실제 과제 결과를 저장하거나 원격으로 Push하지 않습니다.

## 3. 파일 하나만 가져오기

Git이 없어도 기존 curl이 있다면 공개 Raw 파일을 다운로드할 수 있습니다.
아래 명령은 읽기용 문서만 저장합니다. 다운로드한 코드를 자동 실행하지 않습니다.
대상 경로가 이미 있으면 다른 파일명을 사용합니다.

```bash
curl -fL --connect-timeout 10 --max-time 30 https://raw.githubusercontent.com/KCVS2002/ai-task-playbook/main/workflow.md -o reference-workflow.md
```

IDE에서 `reference-workflow.md`를 열면 됩니다.
이 파일만 받았다면 연결된 TOOLBOX나 Skill은 아직 로컬에 없으므로 필요한 파일을 추가로 가져옵니다.
주소가 막히면 다른 경로나 도구로 차단을 우회하지 말고 허용 범위를 문의합니다.
공개 저장소 읽기에는 일반적으로 개인 GitHub 토큰을 입력할 필요가 없습니다.

## 4. Skill을 활용하는 두 가지 방식

### A. 파일을 직접 읽게 하기: 먼저 사용할 방식

> reference-playbook/skills/verify-deliverable/SKILL.md를 읽고, 현재 결과물을 필수조건별로 검증해줘.

일반 Markdown 지침을 명시적으로 적용하는 방법입니다. 정식 Skill 등록을 요구하지 않습니다.

### B. 작업 폴더에 Skill로 등록하기: 지원될 때만

현재 일반 Codex 문서는 프로젝트의 `.agents/skills`를 설명합니다.
대회 고정 버전이 같은 위치와 명령을 지원하는지 먼저 확인합니다.

1. 기존 `.agents`와 Skill, 제공된 프로젝트 지침을 확인합니다.
2. 허용되고 지원될 때에만 필요한 Skill 폴더 하나를 빈 대상 경로로 복사합니다.
3. `/skills`가 있다면 목록에 보이는지 확인합니다.
4. 목록에 없다면 등록을 성공했다고 보고하지 말고 A 방식으로 직접 읽습니다.

이름 예시: `.agents/skills/playbook-verify-deliverable/SKILL.md`.
같은 이름의 기존 Skill이나 설정을 덮어쓰지 않습니다.
등록을 위해 Codex를 업데이트하거나 플랫폼 관리 설정을 수정하지 않습니다.

## 5. Plugin 패키지는 선택 사항

이 저장소에는 `plugin.json`과 호환용 `.codex-plugin/plugin.json`이 있으며,
`skills/` 아래의 세 Skill만 묶습니다. MCP, 계정 연결, 설치 스크립트, 실행 Hook은 포함하지 않습니다.

대회 버전의 `/plugins` 또는 도움말에 로컬 패키지·저장소 설치가 지원되는지 확인하고,
지원되는 설치 경로가 있을 때만 사용합니다.
저장소 URL만 입력하면 자동 설치된다고 가정하지 않습니다.
설치가 어렵다면 별도 설정 없이 4-A 방식으로 읽습니다.

## 6. 마지막으로 구분할 것

| 상태 | 확인 방법 |
|---|---|
| 다운로드됨 | 로컬 경로와 파일 내용을 확인 |
| 지침을 읽음 | Codex가 실제 내용을 요약하거나 적용 |
| Skill로 등록됨 | 해당 환경의 목록에서 확인 |
| Plugin 설치됨 | 설치 목록·버전·활성 상태 확인 |
| MCP 연결됨 | 도구 목록과 무해한 시험 호출 확인 |

이 상태들은 서로 다릅니다. 실제 확인한 범위만 완료로 보고합니다.
