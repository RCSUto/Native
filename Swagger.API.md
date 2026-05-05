# Swagger / API 문서화 정리

## 1. API 문서화란?

API 문서화는 프론트엔드와 백엔드가 협업할 때  
API의 요청 방식과 응답 형식을 정리하는 작업이다.

문서화 내용

- URL
- HTTP Method
- Request Parameter
- Request Body
- Response Data
- Status Code

예시

GET /users

응답
``` id="0htl13"
{
  "id": 1,
  "name": "kim"
}
```

문서가 없으면

- 프론트엔드가 API 사용 어려움
- 협업 속도 저하
- 유지보수 어려움

---

# 2. Swagger란?

Swagger는 API 문서를 자동으로 생성해주는 도구이다.

Spring에서는 보통

- Springdoc OpenAPI
- Swagger UI

를 사용한다.

장점
- 자동 문서 생성
- API 테스트 가능
- UI 제공
- 협업 편리

---

## Swagger 의존성 추가

``` id="06ub8i"
implementation 'org.springdoc:springdoc-openapi-starter-webmvc-ui:2.0.2'
```

---

## Swagger 설정 후 접속

서버 실행 후 접속

``` id="s6h7cx"
http://localhost:8080/swagger-ui.html
```

또는

``` id="i0h62r"
http://localhost:8080/swagger-ui/index.html
```

---

# 3. Swagger 예시

``` id="uoq1ix"
@RestController
@RequestMapping("/users")
public class UserController {

    @GetMapping
    public List<User> getUsers() {
        return userService.findAll();
    }
}
```

Swagger UI에서 자동 문서 생성됨

표시 내용

- 요청 URL
- Method
- 파라미터
- 응답값

---

# 4. Swagger 어노테이션

## @Operation
API 설명 작성

``` id="5h5v5k"
@Operation(summary = "회원 조회")
```

---

## @Parameter
파라미터 설명

``` id="36izdc"
@Parameter(description = "회원 ID")
```

---

## @ApiResponse
응답 설명

``` id="0s4x84"
@ApiResponse(responseCode = "200")
```

---

# 5. Swagger 장점

- 빠른 문서 작성
- 자동 업데이트
- 테스트 가능
- 프론트 협업 편리

---

# 6. Swagger 단점

- 실제 응답과 차이 발생 가능
- 테스트 코드 기반 아님
- 코드 의존적

---

# 7. RestDocs란?

Spring RestDocs는 테스트 기반 API 문서 생성 도구이다.

테스트를 통과한 API만 문서화한다.

예시 흐름

테스트 작성  
-> API 실행  
-> 문서 생성

---

## RestDocs 장점

- 실제 테스트 기반
- 신뢰도 높음
- 정확한 문서 생성

---

## RestDocs 단점

- 설정 복잡
- 초기 학습 필요
- 작성 시간 더 걸림

---

# 8. Swagger VS RestDocs

Swagger

- 빠름
- 사용 쉬움
- UI 제공
- 테스트 가능

RestDocs

- 정확성 높음
- 테스트 기반
- 실무 선호

---

## 비교 정리

Swagger  
-> 빠른 개발  
-> 소규모 프로젝트 적합  

RestDocs  
-> 정확한 문서  
-> 대규모 프로젝트 적합  

---

# 최종 정리

API 문서화는 협업을 위해 중요하다.

Swagger  
-> 자동 문서 생성 도구

RestDocs  
-> 테스트 기반 문서 생성 도구

프로젝트 규모와 목적에 따라 선택한다.
