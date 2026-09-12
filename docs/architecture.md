# 백엔드 아키텍처

여로 백엔드는 하나의 Spring Boot 애플리케이션 안에서 도메인 경계를 나누는 모듈러 모놀리스로 시작합니다.

## 의존성 방향

```text
adapter/in -> application -> domain
adapter/out -----------^ (Port 구현)
```

- `domain`: 업무 상태와 반드시 지켜야 하는 규칙
- `application`: Use Case의 실행 순서와 트랜잭션 조율
- `application/port/in`: 외부에서 실행할 수 있는 Use Case 인터페이스
- `application/port/out`: DB와 외부 서비스에 요구하는 인터페이스
- `adapter/in`: HTTP 같은 입력 기술
- `adapter/out`: JPA, PostgreSQL, Google OAuth, S3 같은 출력 기술

## 사용자 모듈의 목표 구조

```text
user/
├── domain/model/
├── application/
│   ├── port/in/
│   ├── port/out/
│   └── service/
└── adapter/
    ├── in/web/
    └── out/persistence/
```

기능 구현 전에는 구조를 설명하는 `package-info.java`만 두고, 실제 Use Case가 생길 때 클래스를 추가합니다.

