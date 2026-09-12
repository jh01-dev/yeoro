# 여로 (Yeoro)

도쿄를 시작으로 일본 여행 정보를 쉽게 찾고 공유하는 여행 커뮤니티 프로젝트입니다.

## 기술 스택

- Frontend: React, TypeScript, Vite
- Backend: Java 21, Spring Boot, Gradle
- Database: PostgreSQL, Flyway
- Authentication: Google OAuth 2.0
- File storage: AWS S3 (도입 예정)

## 저장소 구조

```text
yeoro/
├── frontend/   # React 애플리케이션
├── backend/    # Spring Boot 애플리케이션
└── docs/       # 개발 문서와 아키텍처 결정
```

백엔드는 DDD와 헥사고날 아키텍처를 학습하기 위해 도메인별 모듈과 Port/Adapter 구조를 사용합니다.

## 로컬 실행

### Backend

```bash
cd backend
./gradlew bootRun
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

## 현재 단계

- 프로젝트 기본 구조 생성
- 사용자 및 소셜 로그인 도메인 설계 진행 중

