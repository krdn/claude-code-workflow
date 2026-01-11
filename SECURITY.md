# 보안 정책 (Security Policy)

## 지원 버전

이 프로젝트는 문서 및 워크플로 가이드 저장소입니다. 최신 버전의 문서가 항상 권장됩니다.

| 버전 | 지원 상태 |
|------|----------|
| main 브랜치 | ✅ 지원 |
| 이전 커밋 | ❌ 지원 안함 |

## 보안 취약점 신고

### 신고 대상

다음과 같은 보안 관련 문제를 발견하셨다면 신고해 주세요:

- **예제 코드의 보안 취약점**: 안전하지 않은 코드 패턴, 취약한 예제
- **민감한 정보 노출**: 실수로 포함된 API 키, 비밀번호, 개인정보
- **악성 콘텐츠**: 악성 링크, 피싱 시도, 유해한 콘텐츠
- **잘못된 보안 가이드**: 보안에 취약한 방법을 권장하는 문서

### 신고 방법

#### 일반적인 보안 이슈

공개적으로 논의해도 되는 보안 관련 개선사항:

1. [Issue 생성](https://github.com/krdn/claude-code-workflow/issues/new/choose)
2. `type: bug` 라벨 사용
3. 제목에 `[Security]` 접두사 추가

```
예시: [Security] examples/hooks의 안전하지 않은 명령어 실행 예제
```

#### 민감한 보안 이슈

공개적으로 논의하기 어려운 민감한 보안 문제:

1. **GitHub Security Advisories** 사용
   - [Security 탭](https://github.com/krdn/claude-code-workflow/security) → "Report a vulnerability"

2. 또는 **비공개 이슈** 생성
   - 메인테이너에게 직접 연락

### 신고 내용

보안 이슈 신고 시 다음 정보를 포함해 주세요:

```markdown
## 보안 이슈 설명
[문제에 대한 명확한 설명]

## 영향받는 파일
[파일 경로 및 라인 번호]

## 재현 단계
1. [첫 번째 단계]
2. [두 번째 단계]
3. ...

## 예상되는 위험
[이 취약점이 악용될 경우 발생할 수 있는 문제]

## 권장 수정 방법 (선택)
[알고 있다면 수정 방법 제안]
```

## 응답 시간

| 심각도 | 초기 응답 | 해결 목표 |
|--------|----------|----------|
| 긴급 (Critical) | 24시간 이내 | 48시간 이내 |
| 높음 (High) | 48시간 이내 | 1주일 이내 |
| 중간 (Medium) | 1주일 이내 | 2주일 이내 |
| 낮음 (Low) | 2주일 이내 | 다음 릴리스 |

## 보안 모범 사례

### 예제 코드 작성 시

이 프로젝트의 예제 코드를 작성하거나 수정할 때 다음을 준수해 주세요:

#### DO ✅

```bash
# 환경 변수 사용
export API_KEY="${CLAUDE_API_KEY}"

# 안전한 파일 권한
chmod 600 ~/.config/credentials
```

```javascript
// 입력 검증
const sanitizedInput = validateInput(userInput);

// 안전한 경로 처리
const safePath = path.resolve(baseDir, path.basename(filename));
```

#### DON'T ❌

```bash
# 하드코딩된 시크릿
API_KEY="sk-1234567890abcdef"

# 위험한 명령어 실행
eval "$USER_INPUT"
```

```javascript
// SQL 인젝션 취약
db.query(`SELECT * FROM users WHERE id = ${userId}`);

// 경로 조작 취약
fs.readFile(userProvidedPath);
```

### 문서 작성 시

- 실제 API 키, 토큰, 비밀번호를 예제에 포함하지 마세요
- 플레이스홀더 사용: `your-api-key`, `<TOKEN>`, `xxxxxxxx`
- 보안에 취약한 방법을 권장하지 마세요
- 위험한 명령어에는 경고 문구를 추가하세요

```markdown
⚠️ **주의**: 이 명령어는 예시입니다. 프로덕션 환경에서는
적절한 보안 조치를 취하세요.
```

## 보안 업데이트

보안 관련 업데이트는 다음을 통해 공지됩니다:

- [GitHub Releases](https://github.com/krdn/claude-code-workflow/releases)
- [GitHub Security Advisories](https://github.com/krdn/claude-code-workflow/security/advisories)

## 감사의 말

보안 취약점을 책임감 있게 신고해 주신 분들께 감사드립니다. 신고자의 동의 하에 기여자로 인정해 드립니다.

## 참고 자료

- [GitHub Security Best Practices](https://docs.github.com/en/code-security)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Claude Code 공식 보안 가이드](https://docs.anthropic.com/claude-code/security)
