# 프로젝트명

> 프로젝트 한 줄 설명

## 개요

프로젝트에 대한 간단한 설명을 작성합니다.

## 기술 스택

- **언어**: TypeScript 5.x
- **프레임워크**: React 18 / Next.js 14
- **데이터베이스**: PostgreSQL
- **인프라**: Docker, AWS

## 프로젝트 구조

```
src/
├── components/    # UI 컴포넌트
├── services/      # 비즈니스 로직
├── utils/         # 유틸리티 함수
├── types/         # 타입 정의
└── hooks/         # 커스텀 훅
```

## 빌드 및 실행

```bash
# 의존성 설치
npm install

# 개발 서버
npm run dev

# 빌드
npm run build

# 테스트
npm test

# 린트
npm run lint
```

## 코딩 컨벤션

- ESLint + Prettier 사용
- 함수형 컴포넌트 선호
- 파일명: kebab-case
- 컴포넌트명: PascalCase
- 함수/변수명: camelCase

## 환경 변수

```bash
# .env.example
DATABASE_URL=postgresql://...
API_KEY=your-api-key
```

## 주요 기능

1. **기능1**: 설명
2. **기능2**: 설명
3. **기능3**: 설명

## 주의사항

- 프로덕션 DB에 직접 쿼리 금지
- API 키 하드코딩 금지
- `.env` 파일 커밋 금지

## 참고 문서

- [API 문서](docs/api.md)
- [아키텍처 결정 기록](docs/adr/)
