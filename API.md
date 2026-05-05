# API 명세 형식 정리

API 명세는 프론트엔드와 백엔드가  
서버 통신 규칙을 정리하는 문서이다.

---

## 1. protocol

통신 방식

예시
- HTTP
- HTTPS
- Socket

```
protocol : HTTP
```

---

## 2. path

API 주소

```
/users
/users/{id}
/board/write
```

---

## 3. method

요청 방식

- GET -> 조회
- POST -> 생성
- PUT -> 수정
- DELETE -> 삭제
- socket -> 실시간 통신

예시
```
method : GET
```

---

## 4. payload

클라이언트가 서버로 보내는 데이터

형태

```
key=value
```

또는

```
{
  "name": "kim"
}
```

예시
```
{
  "title": "hello",
  "content": "test"
}
```

---

## 5. response

서버가 반환하는 데이터

예시
```
{
  "id": 1,
  "title": "hello"
}
```

---

## 6. struct

데이터 타입 구조 정의

예시
```
id : Long
title : String
content : String
```

---

## 7. 로직 처리

API가 내부적으로 어떻게 동작하는지 설명

예시

사용자 요청  
-> Controller 요청 수신  
-> Service 로직 처리  
-> Repository DB 접근  
-> 응답 반환

---

# 전체 예시

protocol
```
HTTP
```

path
```
/board
```

method
```
POST
```

payload
```
{
  "title": "hello",
  "content": "test"
}
```

response
```
{
  "message": "작성 완료"
}
```

struct
```
title : String
content : String
```

로직 처리

사용자 글 작성 요청  
-> Controller 요청 처리  
-> Service 저장 로직 실행  
-> Repository DB 저장  
-> 응답 반환
