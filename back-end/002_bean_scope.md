# 002_bean_scope

## 1. 스프링의 IoC 컨테이너와 Bean 의 관계, 그리고 Bean Scope 에 대해서 간략하게 설명해주세요

- IoC 는 제어의 역전(Inversion of Control) 이라는 뜻으로 개발자가 외부 라이브러리를 호출하는 것이 아닌, 외부 라이브러리가 개발자의 코드를 호출합니다.(의존성 주입(DI, Dependency Injection)) IoC 방식으로 개발을 하게 되면 개발자는 자기가 개발하는 코드에만 온전히 신경 쓸 수 있고, 모듈이 바뀌어도 시스템에 영향이 가지 않습니다. 거기에 의존성과 객체의 생성과 소멸 또한 IoC 컨테이너에 의해 관리됩니다. Bean은 스프링의 IoC 컨테이너에서 사용하는 객체를 나타내는 용어 입니다. 객체를 IoC 컨테이너에 등록 시켜 Bean 으로써 사용하려면 2가지 방법이 있는데, 하나는 Annotation 을 사용하는 방법 Component Scan(@Controller, @Service, @Repository or @Configuration 과 @Bean 을 사용), 그리고 또 하나는 application.xml 를 생성하여 등록하는 방법이 있습니다.

- Bean Scope 는 Bean 을 어떻게 쓸지에 대한 범위를 정하는 것으로 대표적인 것이 싱글톤(singleton) 과 프로토타입(prototype) 이 있습니다. 싱글톤은 앱이 구동하는 동안 하나의 객체만 사용하는 것이고, 프로토타입은 앱에서 호출 시 (getBean 메서드 사용) Bean이 생성이 됩니다.

## 참고

- <https://ko.wikipedia.org/wiki/%EC%A0%9C%EC%96%B4_%EB%B0%98%EC%A0%84>
- <https://velog.io/@probsno/Bean-%EC%8A%A4%EC%BD%94%ED%94%84%EB%9E%80>
- <https://cnu-jinseop.tistory.com/36>
- <https://ooeunz.tistory.com/107>
- <https://luckydavekim.github.io/development/back-end/spring-framework/create-spring-bean>
- <https://velog.io/@probsno/Bean-%EC%8A%A4%EC%BD%94%ED%94%84%EB%9E%80>
- <https://atoz-develop.tistory.com/entry/Spring-%EC%8A%A4%ED%94%84%EB%A7%81-%EB%B9%88Bean%EC%9D%98-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%83%9D%EC%84%B1-%EC%9B%90%EB%A6%AC>
- <https://gmlwjd9405.github.io/2018/11/10/spring-beans.html>
- <https://medium.com/@jang.wangsu/di-inversion-of-control-container-%EB%9E%80-12ecd70ac7ea>
- <https://velog.io/@gillog/Spring-Annotation-%EC%A0%95%EB%A6%AC>
