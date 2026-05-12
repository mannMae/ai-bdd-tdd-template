# Antigravity AI-BDD-TDD Template (Submodule)

이 저장소는 **Google Antigravity(Gemini) 기반 AI Agent와 협업하여 BDD-TDD 방법론을 실천하기 위한 규칙 저장소**입니다.
이 저장소를 프로젝트의 Git Submodule로 연결하면, 여러 프로젝트에서 동일한 AI 협업 규칙을 일관되게 적용하고 쉽게 업데이트할 수 있습니다.

## 🚀 왜 이 템플릿을 Submodule로 쓰나요?
프로젝트마다 AI 규칙을 복사해서 붙여넣으면, 프로세스가 개선될 때마다 모든 프로젝트를 일일이 수정해야 합니다.
Git Submodule을 사용하면 중앙 레포지토리(이 저장소)에서 규칙을 한 번만 업데이트하고, 각 프로젝트에서는 `git submodule update --remote` 명령어로 최신 워크플로우를 즉시 반영할 수 있습니다.

## 🏁 서브모듈로 프로젝트에 적용하기

새 프로젝트에 이 템플릿을 서브모듈로 추가하는 방법은 다음과 같습니다:

1. **서브모듈 추가**: 프로젝트 최상단 디렉토리에서 아래 명령어를 실행하여 이 저장소를 `.agents` 폴더로 가져옵니다.
   ```bash
   git submodule add https://github.com/mannMae/ai-bdd-tdd-template.git .agents
   ```

2. **초기 진입점 생성**: `AGENTS.sample.md` 파일을 부모 프로젝트의 최상단(root) 경로에 `AGENTS.md`라는 이름으로 복사합니다.
   ```bash
   cp .agents/AGENTS.sample.md ./AGENTS.md
   ```

3. **팀원 공유**: 다른 팀원들이 이 프로젝트를 클론할 때는 다음 명령어를 사용해야 서브모듈까지 한 번에 가져올 수 있습니다.
   ```bash
   git clone --recursive <your-project-url>
   ```
   (이미 클론한 후라면 `git submodule update --init --recursive` 실행)

## 📂 서브모듈 내부 구조 (`.agents/`)

- **`rules/`**: Antigravity가 자동으로 감지하고 로드하는 BDD-TDD 라이프사이클 및 검증 게이트 규칙들입니다.
- **`docs/`**: RTM, User Flow 등을 저장할 문서 폴더의 뼈대입니다. 부모 프로젝트에서 필요에 따라 참조하여 작성하세요.
- **`AGENT_README.md`**: 이 문서입니다. (루트 프로젝트의 README.md와 이름이 충돌하지 않도록 변경됨)
- **`AGENTS.sample.md`**: 부모 프로젝트의 최상단에 복사해야 할 초기 진입점 샘플 파일입니다.

## 🔄 최신 규칙으로 업데이트하기
AI 협업 프로세스가 개선되어 이 중앙 템플릿 레포지토리가 업데이트되었다면, 각 프로젝트에서는 아래 명령어로 최신 규칙을 동기화할 수 있습니다:

```bash
git submodule update --remote .agents
git add .agents
git commit -m "Update AI BDD-TDD rules to latest"
```
