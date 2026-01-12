# 모범 사례

> **학습 경로**: [시작하기](getting-started.md) → [핵심 원칙](principles.md) → 모범 사례 | [↑ 목차](../README.md)

Claude Code를 사용한 생산성 높은 개발을 위한 모범 사례입니다.

## 세션 관리

### 컨텍스트 유지
- 관련 작업은 같은 세션에서 수행
- 새 세션 시작 시 필요한 컨텍스트 제공

### 세션 정리
```bash
# 대화 내용 요약 저장
claude "/context save"
```

## MCP 서버 활용

### 데이터베이스 연동
```json
{
  "mcpServers": {
    "postgres": {
      "command": "mcp-server-postgres",
      "args": ["postgresql://..."]
    }
  }
}
```

### 외부 API 연동
브라우저, 파일 시스템 등 다양한 MCP 서버 활용

## 훅 자동화

### Pre-commit 훅
커밋 전 자동으로 린트, 테스트 실행

### 빌드 훅
코드 변경 후 자동 빌드 확인

## 팀 협업

### 공유 CLAUDE.md
팀 전체가 사용하는 공통 컨텍스트 파일 관리

### 코드 리뷰 워크플로
PR 리뷰에 Claude Code 활용

## 학습 및 개선

### 실패에서 배우기
작동하지 않은 프롬프트 분석 및 개선

### 패턴 축적
효과적인 프롬프트 패턴을 문서화
