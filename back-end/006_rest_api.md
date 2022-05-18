# 006_rest_api

## REST API

### REST API 란?
- Representational State Transfer 라는 용어의 약자
- HTTP Method 별로 역할을 명시한게 특징

### REST API 설계 방법
- GET: 조회 (READ)
- POST: 생성 (INSERT)
- PUT: 갱신 (UPDATE)
- DELETE: 삭제 (DELETE)

1. URI는 정보의 자원을 표현해야 한다.
2. 자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE)로 표현한다.

### REST API 설계 시 주의
1. 슬래시 구분자(/)는 계층 관계를 나타낸다.
2. URI 마지막 문자로 슬래시(/)를 포함하지 않는다.
3. 하이픈(-)은 URI 가독성을 높이는데 사용
4. 밑줄(_)은 URI에 사용하지 않는다.
5. URI 경로에는 소문자가 적합하다.
6. 파일 확장자는 URI에 포함시키지 않는다.

### HTTP 응답 상태 코드

200 : 정상 수행
201 : 리소스 생성 성공

400 : 클라이언트 요청 부적절
401 : 클라이언트 미인증
403 : 리소스가 존재하지만 응답하고 싶지 않음
404 : 리소스가 없어 응답할 수 없음
405 : 사용 불가능한 method 이용

301 : URI가 변경되었을 때
500 : 서버에 문제가 있는 경우