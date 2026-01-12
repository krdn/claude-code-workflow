# 빠른 참조 (Cheatsheet)

> **학습 경로**: [시작하기](getting-started.md) → [핵심 원칙](principles.md) → [모범 사례](best-practices.md) → 빠른 참조 | [↑ 목차](../README.md)

Claude Code 사용 시 빠르게 참조할 수 있는 요약 문서입니다.

## 자주 사용하는 프롬프트

### 코드 분석

| 상황 | 프롬프트 예시 |
|------|--------------|
| 구조 분석 | `이 파일의 구조를 분석해줘` |
| 함수 이해 | `이 함수의 로직을 설명해줘` |
| 의존성 파악 | `이 모듈이 의존하는 파일들을 찾아줘` |
| 성능 분석 | `이 코드에서 성능 문제가 있을 수 있는 부분을 찾아줘` |

### 버그 수정

| 상황 | 프롬프트 예시 |
|------|--------------|
| 에러 분석 | `이 에러를 분석하고 수정해줘: [에러 메시지]` |
| 빌드 에러 | `빌드 시 다음 에러가 발생해: [에러]. 수정해줘` |
| 테스트 실패 | `이 테스트가 실패하는 원인을 분석하고 수정해줘` |
| 런타임 에러 | `npm run dev 실행 시 다음 에러가 발생해: [에러]` |

### 리팩토링

| 상황 | 프롬프트 예시 |
|------|--------------|
| 함수 분리 | `이 긴 함수를 작은 함수들로 분리해줘` |
| 중복 제거 | `중복된 코드를 공통 함수로 추출해줘` |
| 타입 개선 | `any 타입을 구체적인 타입으로 변경해줘` |
| 네이밍 | `변수명과 함수명을 더 명확하게 변경해줘` |

### 코드 작성

| 상황 | 프롬프트 예시 |
|------|--------------|
| 새 기능 | `사용자 인증 기능을 구현해줘` |
| 테스트 | `이 API에 대한 테스트 코드를 작성해줘` |
| API 추가 | `GET /users 엔드포인트를 추가해줘` |
| 컴포넌트 | `버튼 컴포넌트를 React로 만들어줘` |

## CLAUDE.md 필수 항목

프로젝트 루트에 `CLAUDE.md` 파일을 생성하세요.

```markdown
# 프로젝트명

## 개요
프로젝트 설명 (1-2문장)

## 기술 스택
- 언어: TypeScript 5.x
- 프레임워크: React 18
- 데이터베이스: PostgreSQL
- 인프라: Docker, AWS

## 빌드/테스트 명령어
- 설치: `npm install`
- 개발: `npm run dev`
- 빌드: `npm run build`
- 테스트: `npm test`
- 린트: `npm run lint`

## 코딩 컨벤션
- ESLint + Prettier 사용
- 함수형 컴포넌트 선호
- 파일명: kebab-case
- 컴포넌트: PascalCase
- 함수/변수: camelCase

## 주의사항
- API 키 하드코딩 금지
- .env 파일 커밋 금지
- 프로덕션 DB 직접 접근 금지
```

### 체크리스트

- [ ] 프로젝트 개요 작성
- [ ] 기술 스택 명시
- [ ] 빌드/테스트 명령어 포함
- [ ] 코딩 컨벤션 정의
- [ ] 보안 주의사항 명시

## Hooks 이벤트 요약

`~/.claude/settings.json`에 설정합니다.

| 이벤트 | 용도 | 예시 |
|--------|------|------|
| `PreToolUse` | 도구 실행 전 검증 | 커밋 전 린트/테스트 실행 |
| `PostToolUse` | 도구 실행 후 자동화 | 파일 수정 후 자동 포맷팅 |
| `Notification` | 알림 전송 | Slack 알림 |
| `Stop` | 세션 종료 시 | 리소스 정리 |

### 예제: 자동 린트

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "command": "npx eslint --fix ${file}",
        "timeout": 30000
      }
    ]
  }
}
```

### 예제: 커밋 가드

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "pattern": "git commit",
        "command": "npm run lint && npm test",
        "on_error": "block",
        "timeout": 120000
      }
    ]
  }
}
```

## MCP 서버 빠른 설정

`~/.claude/settings.json`에 설정합니다.

### PostgreSQL

```json
{
  "mcpServers": {
    "postgres": {
      "command": "npx",
      "args": [
        "@modelcontextprotocol/server-postgres",
        "postgresql://user:pass@localhost:5432/dbname"
      ]
    }
  }
}
```

### SQLite

```json
{
  "mcpServers": {
    "sqlite": {
      "command": "npx",
      "args": [
        "@modelcontextprotocol/server-sqlite",
        "/path/to/database.db"
      ]
    }
  }
}
```

### GitHub

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "${GITHUB_TOKEN}"
      }
    }
  }
}
```

## 유용한 명령어

### Claude Code CLI

```bash
# 기본 시작
claude

# 프롬프트와 함께 시작
claude "이 프로젝트를 분석해줘"

# 특정 파일 분석
claude "src/main.ts 파일을 분석해줘"

# 컨텍스트 저장
claude "/context save"

# 도움말
claude --help
```

### 자주 쓰는 슬래시 명령어

| 명령어 | 설명 |
|--------|------|
| `/help` | 도움말 표시 |
| `/clear` | 대화 내용 초기화 |
| `/context save` | 컨텍스트 저장 |
| `/compact` | 대화 압축 |

## 관련 문서

- [시작하기](getting-started.md) - 기본 설치 및 사용법
- [핵심 원칙](principles.md) - 7가지 사용 원칙
- [모범 사례](best-practices.md) - MCP, Hooks, 팀 협업
- [프롬프트 예제](../examples/prompts/) - 상세 프롬프트 모음
- [Hooks 예제](../examples/hooks/) - 자동화 설정 예제
- [MCP 예제](../examples/mcp/) - MCP 서버 설정 예제
