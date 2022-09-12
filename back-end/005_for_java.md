# 005_for_java

스프링 관련
- 서블릿 관련 질문
- 대표적인 자바 안티패턴 코드
- 객체지향 설계원칙

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
- Java 스트림은 순차 및 병렬 처리를 모두 지원합니다.

스트림 특징
- 데이터를 저장하지 않고 소스 데이터 구조, 즉 컬렉션에서 작동합니다.
- 프로그래밍 언어에 적합한 람다와 같은 기능적 인터페이스를 사용합니다.
- Java 스트림은 소모품입니다. 스트림을 순회하려면 매번 생성해야 합니다.
- Java 스트림은 순차 및 병렬 처리를 모두 지원합니다.
- 모든 Java 스트림 API 인터페이스와 클래스는 java.util.stream 패키지에 있습니다.
- 스트림은 수정할 수 없습니다. 즉 스트림에서 요소를 추가하거나 제거할 수 없습니다.
- 스트림은 작업을 언급하는 것만으로 내부적으로 반복됩니다.

컬렉션
- Set, List 또는 Map과 같은 특정 데이터 구조에 현재 데이터 구조가 가지고 있는 모든 데이터를 저장/보유합니다.
- 그들은 기능적 인터페이스를 사용하지 않습니다.
- 다시 만들지 않고 여러 번 순회할 수 있습니다.
- 병렬 처리를 지원하며 병렬 처리는 고성능 달성에 매우 도움이 될 수 있습니다.
- IntStream, LongStream 및 DoubleStream 과 같은 기본 유형에 대한 특정 클래스는 자동 박싱을 사용하는 컬렉션에서 int, long과 같은 기본 데이터 유형이 사용되며 이러한 작업에 많은 시간이 걸릴 수 있기 때문에 컬렉션에 사용됩니다.
- 이들은 수정 가능합니다. 즉, 컬렉션에서 요소를 쉽게 추가하거나 제거할 수 있습니다.
- 컬렉션은 루프를 사용하여 외부에서 반복됩니다.

Mutable, immutable 에 대해
- https://cdy0510.github.io/2018/05/10/mutable-immutable/

Exception 종류, 발생 원인
- https://sorjfkrh5078.tistory.com/104

Exception 전역 관리
- @ControllerAdvice란? : 모든 Controller에서 발생할 수 있는 예외를 잡아 처리해주는 어노테이션입니다.
- @ExceptionHandler란? : @Controller, @RestController 어노테이션이 적용된 Bean 내에서 발생하는 예외를 잡아서 하나의 메서드에서 처리를 해주는 기능입니다.
Contoller, RestController에서만 적용이 가능합니다.(@Service 같은 빈에서는 적용이 안됩니다.)
- https://kdg-is.tistory.com/221?category=983893
- https://tecoble.techcourse.co.kr/post/2020-07-28-global-exception-handler/

AOP (Aspect Oriented Programming)
- https://3months.tistory.com/74
- https://devlog-wjdrbs96.tistory.com/398
- https://yadon079.github.io/2021/spring/spring-aop-core

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
- Test Driven Development
- Domain Driven Design

Optional 사용 경험
- Java 8 에서 부터 사용하는 것으로 스트림 처럼 메소드 체이닝 형식으로 Null 체크를 할 수 있다.
- House house = getRandomHouse();
Optional.of(house)
        .map(House::getOwner)
        .map(House::getName)
        .ifPresent(n -> System.out.println("House owner : " + n));

Optional.of(house)
        .map(House::getAddress)
        .ifPresent(a -> System.out.println("House address : " + a));
- https://hbase.tistory.com/212
- https://mangkyu.tistory.com/203

Future 패턴에 대해서
- Javascript Async, Await, Promise 에 대해서도
- https://heekim0719.tistory.com/384
- https://javabom.tistory.com/96

Mybatis & JPA 비교

JPA 성능 최적화
- 읽기 전용 쿼리 힌트 사용
- N+1 : 처음 실행한 SQL의 결과 수만큼 추가로 SQL을 실행하는 것을 N+1 문제 라고 한다.
  - 페치 조인을 해서 해결한다. (SELECT m FROM Member m JOIN FETCH m.orders)
  - 하이버네이트 @BatchSize 를 사용해서 지정된 사이즈 만큼 IN 절을 사용한다.
- 영속성 (데이터가 없어지지 않고 유지됨) : 
  - JPA의 핵심 내용은 엔티티가 영속성 컨텍스트에 포함되어 있냐 아니냐로 갈린다.
  - JPA의 엔티티 매니저가 활성화된 상태로 트랜잭션(@Transactional) 안에서 DB에서 데이터를 가져오면 이 데이터는 영속성 컨텍스트가 유지된 상태이다.
  - 이 상태에서 해당 데이터 값을 변경하면 트랜잭션이 끝나는 시적에 해당 테이블에 변경 내용을 반영하게 된다.
  - 따라서 우리는 엔티티 객체의 필드 값만 변경해주면 별도로 update()쿼리를 날릴 필요가 없게 된다.
  - 이 개념을 더티 체킹이라고 한다.

메시징 큐 사용 경험
- Kafka
- Consumer, Producer 구조
- Dead Letter Queue
- Consumer 는 브로커인 Kafka 에 pull message 요청을 하고, 처리할 수 있는 만큼의 메시지를 pull 해서 처리한다.

트랜잭션의 필요성
- 동작 방식

HashMap 충돌 해결
- 체이닝 (Separate Chaining) : 충돌이 발생하면 키에 해당하는 데이터들을 LinkedList 형태로 연결하는 방식이다. 
- 개방 주소법 (Open Addressing) : 충돌이 발생하면 다음 칸 또는 제곱만큼 건너뛴 칸 또는 다른 해시를 한 번 더 적용한 칸에 저장하는 방식이다.
- https://heepie.me/448
- https://rollroll2.tistory.com/17
- https://odol87.tistory.com/4
- https://mhwan.tistory.com/59

AWS NLB(L4 LB) VS ALB (L7 LB)

트랜잭션 격리 수준
- READ UNCOMMITTED
- READ COMMITTED
- REPEATABLE READ
- SERIALIZABLE
- https://joont92.github.io/db/%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-%EA%B2%A9%EB%A6%AC-%EC%88%98%EC%A4%80-isolation-level/

데이터베이스 Lock
- https://centbin-dev.tistory.com/entry/Database-Lock-%EC%A2%85%EB%A5%98-%EB%B0%8F-%EA%B8%B0%EB%8A%A5

가비지컬렉션의 힙 구조
- https://kotlinworld.com/340
- https://donghyeon.dev/java/2020/03/31/%EC%9E%90%EB%B0%94%EC%9D%98-JVM-%EA%B5%AC%EC%A1%B0%EC%99%80-Garbage-Collection/

Maven 과 Gradle
- https://hyojun123.github.io/2019/04/18/gradleAndMaven/

## 참고

- 스트림에 대해서 : https://www.geeksforgeeks.org/difference-between-streams-and-collections-in-java/
- Optional 의 이해 : https://hbase.tistory.com/212
- 카프카 이해 : https://team-platform.tistory.com/11
- 카프카 이해2 : https://server-engineer.tistory.com/843
- https://medium.com/@umanking/%EC%B9%B4%ED%94%84%EC%B9%B4%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-%EC%9D%B4%EC%95%BC%EA%B8%B0-%ED%95%98%EA%B8%B0%EC%A0%84%EC%97%90-%EB%A8%BC%EC%A0%80-data%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-%EC%9D%B4%EC%95%BC%EA%B8%B0%ED%95%B4%EB%B3%B4%EC%9E%90-d2e3ca2f3c2