## 🔥 1. Spring 기본 개념

###  Spring Framework 란 무엇인가? or Spring이 왜 등장했으며, 어떤 문제를 해결하기 위해 만들어졌는가?
-  Spring은 Java 기반 웹 애플리케이션을 쉽게 개발할 수 있도록 도와주는 프레임워크입니다.
   과거에는 Servlet과 JSP를 사용해 웹 애플리케이션을 개발했지만, XML 설정이 많고 객체 간의 강한 결합으로 인해 유지보수가 어려웠습니다.
   Spring은 이를 해결하기 위해 `IoC 컨테이너와 DI(의존성 주입)를 제공하여 객체 생성을 관리하고`,
   `AOP(관점 지향 프로그래밍)로 공통 기능을 모듈화`하여 코드의 중복을 줄이며,
   `MVC 패턴을 제공하여 웹 요청을 효과적으로 처리`합니다.
   또한, Spring Boot를 통해 복잡한 설정 없이 빠르게 애플리케이션을 실행할 수 있습니다.

   
### Spring의 핵심 특징 (IOC, DI, AOP, PSA, POJO 기반 개발 등)

- IOC
  - 제어의 역전 
  - 제어를 개발자가아닌 스프링이 관리, 객체의 생명 주기를 스프링이 관리
  - 결합도를 낮추고 유지보수를 쉽게 만들어줌


- DI
  - 객체간의 의존관계를 스프링이 자동으로 주입해줌
  - IOC 의 개념을 구현한게 DI 직접 구현하지 않고 외부에서 주입받도록 설계
  - 결합도를 낮추고 객체간의 관계를 유연하게 관리 할 수 있음
  - 생성자 주입을 추천 final 키워드를 사용해서 불변성 유지
  - 테스트 코드 작성시 mock 용이
  - 필드 주입 비추천 - final 사용 안함, 의존성 확인 어려움, 세터 주입 비추천 - 객체가 불변성 유지하기 어려움

- PSA
  - 서비스 추상화, 특정 기술에 종속되지 않도록 인터페이스 기반으로 추상화해주는 것.
  - 특정 기술(JDBC, JPA, 트랜잭션, 메시징 등)에 종속되지 않도록 추상화하는 것을 의미
  - JdbcTemplate 을 예로 들어보면 과거엔 트랜잭션을 열고 닫고 트라이 캐치문안에서 쿼리를 실행하고 결과를 뽑아서 등등 이런걸 처리헀다면 이제는 JdbcTemplate 이 내부에서 세부 구현을 추상화해줘서
  개발자는 쉽게 쿼리를 호출 할 수 있음

- POJO
  - 과거에는 EJB(Enterprise Java Beans) 같은 기술을 쓰면,  EJB 컨테이너에서만 동작하도록 강제되었음.
  - 현재는 옛날 방식의 일반적인 자바 객체(POJO)로 스프링 프레임 워크 없이 실행 가능

    
### Spring MVC와 Spring Boot의 차이점 && Spring Boot가 Spring MVC보다 더 편리한 이유는? && Spring Boot Starter란 무엇이며, 어떤 역할을 하는가?
- Spring MVC는 전통적인 웹 프레임워크로 XML 설정이 필요하고, WAS를 따로 설정해야 하지만, Spring Boot는 설정 자동화와 내장 웹 서버를 제공하여 더 쉽게 개발할 수 있도록 만든 프레임워크입니다. 
- Spring Boot 의 주요 장점은 AutoConfiguration을 통해 설정 없이 바로 실행 가능하며, 내장 웹 서버(Embedded Tomcat, Jetty)를 제공해 java -jar 만으로 서버를 실행할 수 있습니다. 
또한, Spring Boot Starter를 통해 의존성 관리를 자동화하여 개발자가 라이브러리를 직접 추가하지 않아도 한 줄 설정만으로 필요한 기능을 쉽게 추가할 수 있습니다.


### Spring Boot에서 @SpringBootApplication 이 내부적으로 하는 일은?
- @SpringBootApplication은 Spring Boot의 핵심적인 설정을 자동으로 적용하는 메타 어노테이션입니다. 이 어노테이션은 내부적으로 @SpringBootConfiguration, @EnableAutoConfiguration, @ComponentScan을 포함하고 있으며,
  이를 통해 설정 클래스 역할을 수행하고, 자동 설정을 활성화하며, 하위 패키지의 Bean을 자동으로 스캔하여 등록할 수 있습니다. 특히 @EnableAutoConfiguration은 Spring Boot의 자동 설정을 활성화하여, spring.factories 파일을 참고해 필요한 설정을 자동으로 로드하는 역할을 합니다.