# 기여 가이드

Claude Code Workflow 프로젝트에 기여해 주셔서 감사합니다!

## 시작하기

1. 이 저장소를 [Fork](https://github.com/krdn/claude-code-workflow/fork)합니다
2. 로컬에 클론합니다: `git clone https://github.com/YOUR_USERNAME/claude-code-workflow.git`
3. 브랜치를 생성합니다: `git checkout -b feature/amazing-feature`
4. 변경사항을 커밋합니다: `git commit -m 'feat: Add amazing feature'`
5. 푸시합니다: `git push origin feature/amazing-feature`
6. [Pull Request](https://github.com/krdn/claude-code-workflow/compare)를 생성합니다

## 기여 유형

| 유형 | 설명 | 위치 |
|------|------|------|
| 문서 개선 | 오타 수정, 설명 보완 | `docs/` |
| 워크플로 추가 | 새로운 워크플로 패턴 | `workflows/` |
| 예제 추가 | Hooks, MCP, 프롬프트 예제 | `examples/` |
| 템플릿 개선 | CLAUDE.md 템플릿 | `templates/` |

## 커밋 컨벤션

```
feat: 새 기능 추가
fix: 버그 수정
docs: 문서 수정
refactor: 리팩토링
chore: 기타 작업
```

**예시:**
```bash
git commit -m "feat: 테스트 워크플로 추가"
git commit -m "fix: getting-started.md 오타 수정"
git commit -m "docs: principles.md 예제 보완"
```

## Issue 생성

기여하기 전에 [Issue를 먼저 생성](https://github.com/krdn/claude-code-workflow/issues/new/choose)해 주세요.

| 템플릿 | 용도 |
|--------|------|
| 🐛 버그 리포트 | 오류, 버그 신고 |
| ✨ 기능 요청 | 새 기능, 개선 제안 |
| 📚 문서 개선 | 문서 수정/추가 |
| 🔄 워크플로 제안 | 새 워크플로 패턴 |
| ❓ 질문 | 사용법 질문 |

## Pull Request

PR 생성 시 [템플릿](/.github/PULL_REQUEST_TEMPLATE.md)이 자동으로 적용됩니다.

### 체크리스트

- [ ] 관련 Issue가 있으면 연결했나요? (`Fixes #123`)
- [ ] 커밋 메시지가 컨벤션을 따르나요?
- [ ] 문서 수정 시 오타가 없나요?
- [ ] 예제 코드가 올바르게 동작하나요?

## Labels

| 그룹 | 접두사 | 예시 |
|------|--------|------|
| 카테고리 | `category:` | `category: docs`, `category: workflow` |
| 영역 | `area:` | `area: hooks`, `area: mcp` |
| 타입 | `type:` | `type: bug`, `type: enhancement` |
| 우선순위 | `priority:` | `priority: high`, `priority: low` |

## 상세 가이드

더 자세한 내용은 Wiki를 참조하세요:

- [기여 가이드](https://github.com/krdn/claude-code-workflow/wiki/Contributing)
- [Labels 가이드](https://github.com/krdn/claude-code-workflow/wiki/Contributing-Labels)
- [Issue Templates 가이드](https://github.com/krdn/claude-code-workflow/wiki/Contributing-Issue-Templates)
- [Pull Request 가이드](https://github.com/krdn/claude-code-workflow/wiki/Contributing-Pull-Request)

## 행동 강령

이 프로젝트는 [Contributor Covenant 행동 강령](CODE_OF_CONDUCT.md)을 따릅니다.

- 서로 존중하고 건설적인 피드백을 제공합니다
- 다양한 의견과 경험을 환영합니다
- 커뮤니티의 성장에 기여합니다

자세한 내용은 [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)를 참조하세요.

## 도움이 필요하신가요?

- [GitHub Discussions](https://github.com/krdn/claude-code-workflow/discussions) - 일반 질문, 아이디어 공유
- [Issues](https://github.com/krdn/claude-code-workflow/issues) - 버그 리포트, 기능 요청

감사합니다! 🙏
