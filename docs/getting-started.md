# 시작하기

> **학습 경로**: 시작하기 → [핵심 원칙](principles.md) → [모범 사례](best-practices.md) | [↑ 목차](../README.md)

Claude Code를 효과적으로 사용하기 위한 기본 가이드입니다.

## 설치

```bash
npm install -g @anthropic-ai/claude-code
```

## 기본 사용법

```bash
# 현재 디렉토리에서 Claude Code 시작
claude

# 특정 프롬프트와 함께 시작
claude "이 프로젝트의 구조를 분석해줘"

# 특정 파일에 대해 질문
claude "src/main.ts 파일을 분석해줘"
```

## CLAUDE.md 설정

프로젝트 루트에 `CLAUDE.md` 파일을 생성하여 프로젝트 컨텍스트를 제공하세요.

```markdown
# 프로젝트 개요
이 프로젝트는 ...

## 기술 스택
- Node.js 20
- TypeScript 5.x
- React 18

## 빌드 및 테스트
- 빌드: `npm run build`
- 테스트: `npm test`

## 코딩 컨벤션
- ESLint + Prettier 사용
- 함수형 컴포넌트 선호
```

## 주요 기능

### 1. 코드 분석
```bash
claude "이 함수의 로직을 설명해줘"
claude "이 코드에서 성능 문제가 있을 수 있는 부분을 찾아줘"
```

### 2. 코드 작성
```bash
claude "사용자 인증 기능을 구현해줘"
claude "이 API에 대한 테스트 코드를 작성해줘"
```

### 3. 버그 수정
```bash
claude "이 에러를 수정해줘: [에러 메시지]"
claude "빌드 에러를 분석하고 수정해줘"
```

### 4. 리팩토링
```bash
claude "이 코드를 더 읽기 쉽게 리팩토링해줘"
claude "중복 코드를 제거해줘"
```

## 효과적인 프롬프트 작성

### 좋은 예시
```
"src/components/Button.tsx 파일에서 onClick 핸들러에
디바운싱을 적용해줘. 딜레이는 300ms로 설정해."
```

### 개선이 필요한 예시
```
"버튼 고쳐줘"
```

## 다음 단계

- [핵심 원칙](principles.md) - Claude Code 사용 핵심 원칙
- [모범 사례](best-practices.md) - 생산성을 높이는 모범 사례
