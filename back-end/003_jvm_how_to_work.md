# 003_jvm_how_to_work

## JVM 동작원리

1. 프로그램이 실행되면 JVM 은 OS 로 부터 이 프로그램이 필요로 하는 메모리를 할당받는다.
  (JVM 은 이 메모리를 용도에 따라 여러 영역으로 나누어 관리한다.)

2. 작성한 자바 소스(java)를 자바 컴파일러를 통해 자바 바이트 코드(class)로 컴파일 한다.

3. 컴파일된 바이트코드를 JVM의 클래스 로더로 전달한다.

4. 로딩된 class 파일들은 Execution engine 을 통해 해석된다.

5. 해석된 바이트 코드는 Runtime Data Areas 에 배치되어 실질적인 수행이 이루어지게 된다.

## 힙 메모리 관리

- Java에서는 개발자가 프로그램 코드로 메모리를 명시적으로 해제하지 않기 때문에 가비지 컬렉터(Garbage Collector)가 더 이상 필요 없는 (쓰레기) 객체를 찾아 지우는 작업을 한다.

## 가비지 컬렉션

- https://kotlinworld.com/340

## 참고

- https://swk3169.tistory.com/181
- https://asfirstalways.tistory.com/158

## 힙 메모리 분석

- https://blog.naver.com/pcmola/222038466393