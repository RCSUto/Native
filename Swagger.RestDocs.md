# Swagger VS RestDocs 정리

## API 문서화란?

프론트엔드와 백엔드가 협업할 때  
API 요청 방식과 응답 형식을 정리하는 작업이다.

문서화 내용

- URL
- Method
- Request
- Response
- Status Code

---

## Swagger란?

Swagger는 API 문서를 자동 생성하는 도구이다.

특징
- 자동 문서 생성
- API 테스트 가능
- UI 제공
- 개발 속도 빠름

예시 접속 주소
```
http://localhost:8080/swagger-ui/index.html
```

---

## Swagger 장점

- 설정 쉬움
- 빠른 개발 가능
- 협업 편리

---

## Swagger 단점

- 실제 응답과 차이 가능
- 코드 의존적

---

## RestDocs란?

Spring RestDocs는 테스트 기반 API 문서 생성 도구이다.

동작 방식

테스트 작성  
-> API 실행  
-> 문서 생성

---

## RestDocs 장점

- 실제 테스트 기반
- 높은 정확성
- 실무 활용 많음

---

## RestDocs 단점

- 설정 복잡
- 학습 필요

---

## 비교

Swagger
-> 빠른 개발
-> 소규모 프로젝트 적합

RestDocs
-> 높은 정확성
-> 대규모 프로젝트 적합
