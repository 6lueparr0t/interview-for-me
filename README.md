# Interview for me

- 면접 완료 후 좋은 회사 들어갈 때 까지, 해당 내용 정리하기
- https://github.com/JaeYeopHan/Interview_Question_for_Beginner

## 정리 할 내용 (정리 후 삭제)

```text
사내 인프라 구축 AWS 서비스 어떻게 되어있냐 + 각각에 대한 설명
스프링 관련 개념
- 서블릿 관련 질문
- 대표적인 자바 안티패턴 코드
- 객체지향 설계원칙
- 디비 인덱스 : 클러스터드 / 논클러스터드 차이

A 회사 (B2C 서비스)
1. 인덱스 내부 구조(인덱스 자료 구조로 뭐 쓰는지)
2. 공간 정보(GIS) 관련 정보 인덱스 하는 방법 들
3. CAP 정리 + 이유
4. 해시 함수를 왜 쓰는지 + 동작 원리…?
5. HTTPS 프로토콜 + 프로토콜 동작 원리
6. HTTP 프로토콜 특징 + 내부적으로 어떤 방식으로 도는지
7. 뉴스 피드 서비스 설계 해보기
8. MSA 관련 질문들
 - SAGA, 서킷브레이크, CQRS 패턴 왜 쓰는지 + 어떤식으로 설계 했는지
9. secret(API key 같은거) 관련 데이터를 어떤식으로 다루는지
10. 자바 GC 동작 원리 + 자바 레퍼런스 종류 뭐있는지 + 어떤식으로 쓰이는지
11 진행했던 프로젝트 관련 설명
12. DB 정규화 종류 뭐있는지 + 상황 설정 하면서 어떤식으로 쓰이는지

B 회사 (게임사)
1. 인덱스 내부 구조(클러스티드 인덱스, 논 클러스티드 인덱스)
2. Rand 함수의 내부 동작 원리
3. 진행했던 프로젝트
4. 프로세스, 스레드의 차이점을 각 OS 별로 아는대로 다 설명 하시오
 - 버전 별로 어떻게 도는지 까지 설명 했던거 같네요
5. 자바 GC 동작 원리 + 자바 레퍼런스 종류 뭐있는지 + 어떤식으로 쓰이는지
6. Multi tenency architecture 설계에 대해서
7. 메모리 할당 알고리즘 이 어떤 식으로 도는지
8. HTTPS 프로토콜 + 프로토콜 동작 원리
9. HTTP 프로토콜 특징 + 내부적으로 어떤 방식으로 도는지
10. webRTC 가 대충 어찌 도는지 간략하게만? 물어봄
11. webGL, OpenGL 관련 질문 간략하게

+ 해싱 함수 만들때 소수로 나머지 연산 하는 이유도..?

geohash 관련 내용

공통 /
1. CSS 기초지식
2. JS ES5 / ES6 차이
3. this에 대해 설명
4. HTML4 / HTML5 차이
5. 홈페이지 렌더링 / 사용자에게 보이는 원리 설명
6. 클로저에 대해 설명
7. GET, POST가 어떻게 다른가
8. git 경험 여부

A사(리액트, TS, B2C) / 
1. 포트폴리오 리액트 관련 질문
2. 상태(형상)관리 구현 방법
3. TS 경험 여부

B사(하드코딩, B2B) / 
1. 뷰 or 리액트 도입 예정인데 경험해봤냐
2. MVC, MVP, MVVM 아는 만큼 설명
3. HTTP 0.9 / 1.0의 차이 설명

API 설계 할때 참고
https://jsonapi.org/format/
https://github.com/ksundong/backend-interview-question
https://github.com/Integerous/goQuality-dev-contents

애자일에 대한 이해와 설명
스크럼에 대해서
스프린트 리뷰에 대해서
Git 브랜치 전략과 관리
IaC 사용 경험 (code formation / 테라폼 같은)
MSA 관련 경험과 설계 방법 & 예시
ㄴ 현재 서비스의 일부를 MSA 로 바꾼다면? 어떻게 바꿀 것인지
DevOps 의 탄생 배경과 하는 일
롤링업데이트, 블루그린, 카나리에 대해서
뷰와 리액트의 차이 & 장단점
eventually consistency 에 대해서 (DB 쪽)

RESTful API 에 대해서

디비에서 인덱싱쓰는 이유
인덱싱 예시 : 비트리 인덱싱
데이터베이스 정규화는 왜 하는거 + 역정규화
장고에서 prefetch, select_related 설명
CORS 란? CORS에서 오리진의 범위
JWT의 장점
요청부터 응답까지의 한 사이클
사용자의 요청이 몰렸을 때 문제 해결하는 방법
반대로 서버는 요청을 견디는데 디비에 과부하가 올때
redis등으로 캐시를 사용해본 경험
CDN 활용경험
CDN의 두가지 유형
로드밸런서란 무엇인가
Nginx를 활용할수있는 것들
nginx의 로드밸런서와 aws 로드밸런서에 대한 설명

스프링부트 특징 및 장점
- IoC
- Bean scope
- 내장서버(톰캣) 등
- Lombok 에서 지원하는 Annotation 을 활용해서 런타임 시 특정 기능을 사용하기 위한 정보 제공
- Maven, Gradle 을 사용해 프로젝트 관리를 할 수 있음

스트림 API 사용 시
- 원본의 데이터를 변경하지 않음
- 일회용
- 내부 반복으로 작업을 처리
- https://www.geeksforgeeks.org/difference-between-streams-and-collections-in-java/
- Java 스트림은 순차 및 병렬 처리를 모두 지원합니다.

Mutable, immutable 에 대해
- https://cdy0510.github.io/2018/05/10/mutable-immutable/

Exception 종류, 발생 원인
- https://sorjfkrh5078.tistory.com/104

Exception 전역 관리
- https://kdg-is.tistory.com/221?category=983893

AOP (Aspect Oriented Programming) 에 대해서

Collection 종류
- List(ArrayList, LinkedList 등), Set, Map, Vector
- https://lelecoder.com/78 참고

Test Code 사용 방법
- Junit 버전별 차이
- Unit Test 방법

멀티스레드에서의 작업
- Thread-safe 하게 작업해야함
- 두 개 이상의 스레드가 race condition에 들어가거나 같은 객체에 동시에 접근해도 연산결과의 정합성이 보장될 수 있게끔 메모리 가시성이 확보된 상태를 의미합니다.
- java.util.concurrent 패키지 하위의 클래스를 사용합니다.
- 인스턴스 변수를 두지 않습니다.
- Singleton 패턴을 사용합니다. 이 때, 일반적으로 구현하는 Singleton Pattern은 Thread-safe 하지 않습니다.
  - https://github.com/ksundong/TIL/blob/master/DesignPattern/singleton-pattern.md
- 동기화(syncronized) 블럭에서 연산을 수행합니다.
- ConcurrentHashMap 사용

TDD, DDD 에 대해

Optional 사용 경험

Future 패턴에 대해서
- Javascript Async, Await, Promise 에 대해서도

Mybatis & JPA 비교

JPA 성능 최적화
- N+1
- 영속성 (데이터가 없어지지 않고 유지됨)

메시징 큐 사용 경험
- Kafka
- Consumer, Producer 구조
- Dead Letter Queue

REST API 에 대해서
- REST API 설계 방법
- https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html

트랜잭션의 필요성
```
