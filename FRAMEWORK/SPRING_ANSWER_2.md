## 🔥 2. Spring IoC (Inversion of Control) & DI (Dependency Injection)

###  IoC(제어의 역전)란 무엇이며, Spring이 이를 어떻게 구현하는가?
-  IoC(Inversion of Control, 제어의 역전)는 객체의 생성과 관리의 주체가 개발자가 아닌 프레임워크(Spring)로 넘어가는 개념입니다.
   전통적인 Java 애플리케이션에서는 객체를 개발자가 직접 생성(new 키워드)하고 관리했지만,
   Spring은 IoC 컨테이너를 통해 객체를 생성하고, 의존성을 자동으로 주입하여 관리합니다.
   Spring은 이를 구현하기 위해 Bean Factory, ApplicationContext 같은 IoC 컨테이너를 제공합니다

   
### DI(의존성 주입)의 개념과 종류 (Constructor Injection vs. Field Injection vs. Setter Injection)
- **"DI(Dependency Injection, 의존성 주입)는 객체 간의 의존성을 외부에서 주입하는 방식으로,
  IoC를 구현하는 주요 방법 중 하나입니다.
    Spring에서 DI는 3가지 방식으로 제공됩니다.
    
- 생성자 주입 (Constructor Injection) 🔥 (추천!)
  - 생성자를 통해 의존성을 주입하는 방식.
  - final 키워드 사용 가능하여 불변 객체 유지.
  - 순환 참조 문제를 사전에 방지 가능.

- 필드 주입
    - @Autowired를 필드에 직접 붙여 의존성을 주입하는 방식.
    - final을 사용할 수 없어 테스트가 어려움.

- 세터 주입
  - Setter 메서드를 통해 주입하는 방식.
  - 선택적 의존성(필수 아님)일 경우 사용.

    
### Spring Bean이란 무엇이며, 어떻게 관리되는가?
- Spring Bean은 Spring IoC 컨테이너에서 관리되는 객체입니다. 애플리케이션 실행 시 ApplicationContext가 자동으로 Bean을 생성하고 관리하며,
  개발자는 @Component, @Service, @Repository, @Controller 등의 어노테이션을 사용해 Bean으로 등록할 수 있습니다. 또한, @Bean을 활용하여 수동으로 등록할 수도 있습니다.


### Bean Scope (Singleton, Prototype, Request, Session, Application)의 차이점
- Spring에서 Bean의 Scope(범위)는 5가지가 있으며, 기본값은 Singleton입니다.
  1. Singleton (기본값)
     - 애플리케이션 실행 시 단 하나의 인스턴스만 생성하여 공유.
  2. Prototype
     - 요청할 때마다 새로운 인스턴스 생성, 상태를 유지하는 객체에 적합.
  3. Request 
     - HTTP 요청마다 새로운 Bean 생성.
  4. Session (웹 애플리케이션 전용)
     - HTTP 세션마다 하나의 Bean 생성.
  5. Application
     - ServletContext당 하나의 Bean 생성.


### @Bean vs. @Component vs @Configuration 차이점
- @Component는 자동 스캔 방식, @Bean은 개발자가 직접 정의하는 방식입니다.
- Spring 내부적으로 @Configuration은 CGLIB 프록시 기반으로 처리되지만, @Component는 일반적인 POJO로 처리된다. 
- 즉, @Configuration이 @Bean을 정의할 때는 싱글턴을 유지하지만, @Component는 그렇지 않다
- @Configuration은 CGLIB 프록시를 사용하여 싱글턴을 보장한다.  @Component는 일반 객체로 취급되며, @Bean을 여러 번 호출하면 매번 새로운 객체가 생성된다.
