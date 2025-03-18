# FRAMEWORK - SPRING

## 🔥 1. Spring 기본 개념
-  Spring Framework란 무엇인가?
-  Spring이 왜 등장했으며, 어떤 문제를 해결하기 위해 만들어졌는가?
-  Spring의 핵심 특징 (DI, AOP, PSA, POJO 기반 개발 등)
-  Spring MVC와 Spring Boot의 차이점
-  Spring Boot가 Spring MVC보다 더 편리한 이유는?
-  Spring Boot Starter란 무엇이며, 어떤 역할을 하는가?
-  Spring Boot에서 @SpringBootApplication이 내부적으로 하는 일은?

### 🔥 [SPRING_ANSWER_1.md](SPRING_ANSWER_1.md) 답안 

## 🔥 2. Spring IoC (Inversion of Control) & DI (Dependency Injection)
-  IoC(제어의 역전)란 무엇이며, Spring이 이를 어떻게 구현하는가?
-  DI(의존성 주입)의 개념과 종류 (Constructor Injection vs. Field Injection vs. Setter Injection)
-  Spring Bean이란 무엇이며, 어떻게 관리되는가?
-  Bean Scope (Singleton, Prototype, Request, Session, Application)의 차이점
-  @Bean vs. @Component vs. @Configuration 차이점


### 🔥 [SPRING_ANSWER_2.md](SPRING_ANSWER_2.md) 답안


## 🔥 3. Spring AOP (Aspect-Oriented Programming)
-  AOP(관점 지향 프로그래밍)란 무엇이며, 왜 필요한가?
-  AOP의 주요 개념 (Advice, JoinPoint, Pointcut, Aspect, Weaving)
-  Spring에서 AOP를 적용하는 방법 (@Aspect, @Around, @Before, @After 등)
-  AOP가 Spring 내부에서 어떻게 동작하는가? (프록시 패턴 기반, CGLIB vs. JDK 동적 프록시 차이점)
-  AOP가 Bean의 생명주기에 미치는 영향
-  Spring AOP와 AspectJ AOP의 차이점

### 🔥 [SPRING_ANSWER_3.md](SPRING_ANSWER_3.md) 답안


## 🔥 4. Spring 트랜잭션 관리 (@Transactional)
-  Spring에서 트랜잭션이란 무엇인가? (ACID 개념 포함)
-  @Transactional이 내부적으로 어떻게 동작하는가?
-  트랜잭션 전파(Propagation) 옵션 7가지 (REQUIRED, REQUIRES_NEW 등) 차이점
-  트랜잭션 격리 수준(Isolation Level)과 Dirty Read, Phantom Read 문제 해결 방법
-  @Transactional을 메서드 레벨과 클래스 레벨에 적용할 때 차이점
-  Spring에서 트랜잭션 롤백이 실제로 어떻게 처리되는가?


### 🔥 [SPRING_ANSWER_4.md](SPRING_ANSWER_4.md) 답안


## 🔥 5. Spring MVC (Web Application)
-  Spring에서 요청이 들어왔을 때의 흐름 (Request → Controller → Service → Repository → Response)
-  Spring MVC에서 @Controller vs. @RestController 차이점
-  Spring MVC에서 Model, ModelAndView, ResponseEntity 의 차이점


### 🔥 [SPRING_ANSWER_5.md](SPRING_ANSWER_5.md) 답안

## 🔥 6. Spring Boot
-  Spring Boot에서 Embedded Tomcat이 어떻게 동작하는가?
-  Spring Boot에서 ApplicationRunner vs. CommandLineRunner 차이점


## 🔥 7. Spring Security
-  Spring Security란 무엇이며, 어떻게 인증/인가를 관리하는가?
-  Spring Security에서 인증(Authentication)과 인가(Authorization)의 차이
-  Spring Security의 주요 구성 요소 (SecurityFilterChain, UserDetailsService, AuthenticationProvider)
-  JWT (JSON Web Token) 기반 인증 방식과 기존 세션 기반 인증 방식 차이점


## 🔥 8. Spring과 JPA (Spring Data JPA)
-  Spring Data JPA란 무엇이며, 기존 JPA와의 차이점
-  JPA에서 EntityManager란 무엇이며, 어떻게 동작하는가?
-  JPA의 1차 캐시와 2차 캐시의 차이점
-  Spring Data JPA에서 @Transactional과 EntityManager의 관계
-  Lazy Loading과 Eager Loading의 차이 및 N+1 문제 해결 방법 (Fetch Join, Batch Size 등)


## 🔥 9. Spring에서 성능 최적화 방법
-  Spring에서 Bean Scope를 적절히 활용하여 메모리 최적화하는 방법
-  Spring에서 Caching을 활용하는 방법 (@Cacheable, @CachePut, @CacheEvict)
-  Spring에서 DB Connection Pool을 설정하는 방법 (HikariCP vs. Tomcat Pool)
-  Spring에서 Redis를 활용한 세션 관리 최적화 방법
-  Spring에서 API 응답 속도를 최적화하는 방법 (Gzip, HTTP/2, Response Streaming 등)


## 🔥 10. Spring 면접에서 자주 나오는 질문
-  Spring Framework의 핵심 개념을 설명하시오.
-  Spring에서 IoC와 DI의 차이점은 무엇인가?
-  Spring AOP란 무엇이며, 어떻게 동작하는가?
-  Spring에서 @Transactional을 사용할 때 주의해야 할 점은?
-  Spring MVC의 동작 흐름을 설명하시오.
-  Spring Boot에서 AutoConfiguration이 어떻게 동작하는가?
-  Spring Security에서 JWT 기반 인증을 어떻게 구현하는가?
-  Spring에서 JPA의 Lazy Loading이란 무엇이며, N+1 문제를 어떻게 해결할 것인가?