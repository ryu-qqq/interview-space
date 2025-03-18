## 🔥 3. Spring AOP (Aspect-Oriented Programming)

###  AOP(관점 지향 프로그래밍)란 무엇이며, 왜 필요한가?
- AOP(Aspect-Oriented Programming, 관점 지향 프로그래밍)는 핵심 로직과 공통 관심 사항(트랜잭션, 로깅, 보안 등)을 분리하여 유지보수성과 코드 재사용성을 높이는 프로그래밍 기법입니다
- 전통적인 OOP(객체 지향 프로그래밍)에서는 각 클래스에서 트랜잭션 관리, 로깅 등의 중복 코드가 반복될 수 있습니다. AOP를 사용하면 이러한 공통 기능을 별도의 모듈(Aspect)로 분리하여 핵심 로직에 영향을 주지 않고 재사용할 수 있습니다.
   
### AOP의 주요 개념 (Advice, JoinPoint, Pointcut, Aspect, Weaving)
1. Aspect (관점)공통 기능을 모아둔 모듈 (ex: 트랜잭션 관리, 로깅).
2. JoinPoint (조인 포인트)
   - AOP가 적용될 수 있는 모든 지점 (ex: 메서드 실행, 생성자 호출).
3. Pointcut (포인트컷)
   - AOP를 적용할 JoinPoint를 필터링하는 표현식.
4. Advice (어드바이스)
   - AOP에서 실행할 부가 기능 (ex: @Before, @After, @Around).
5. Weaving (위빙)
   - 실제로 AOP 코드를 대상 객체에 적용하는 과정

    
### Spring에서 AOP를 적용하는 방법 (@Aspect, @Around, @Before, @After 등)
- @Before: 메서드 실행 전 실행.
- @AfterReturning: 메서드 실행 후 정상 종료 시 실행.
- @AfterThrowing: 예외 발생 시 실행.
- @Around: 메서드 실행 전후에 실행 (핵심 로직을 직접 실행할 수 있음).

### AOP가 Spring 내부에서 어떻게 동작하는가? (프록시 패턴 기반, CGLIB vs. JDK 동적 프록시 차이점)

- Spring AOP는 프록시 패턴을 기반으로 동작하며, 대상 객체를 감싸는 프록시 객체를 생성하여 부가 기능(로깅, 트랜잭션 등)을 추가할 수 있습니다
- JDK 동적 프록시: 인터페이스가 존재하는 경우, java.lang.reflect.Proxy를 사용하여 프록시 객체를 생성합니다.
- CGLIB 프록시: 인터페이스가 없고 구체 클래스인 경우, CGLIB 라이브러리를 이용하여 대상 클래스를 상속한 프록시 클래스를 동적으로 생성합니다.
- JDK 동적 프록시는 인터페이스 기반으로 메서드 호출을 위임하는 방식이며, CGLIB 프록시는 바이트코드를 조작하여 메서드를 오버라이딩하는 방식으로 동작합니다."


###  AOP가 Bean의 생명주기에 미치는 영향
AOP가 적용된 Bean은 Spring IoC 컨테이너에서 관리될 때, 실제 객체가 아닌 프록시 객체로 감싸지기 때문에, 프록시 객체가 Spring의 라이프사이클을 대신 관리합니다.
즉, AOP가 적용되면 원본 객체를 직접 다루는 것이 아니라, 프록시 객체를 통해 메서드를 호출하게 되므로 초기화 과정(@PostConstruct 등)에서도 AOP 로직이 적용될 수 있습니다

###  Spring AOP와 AspectJ AOP의 차이점
- Spring AOP
  - 프록시 패턴 기반으로 동작하며, 메서드 실행 전에 프록시 객체가 인터셉트하여 부가 기능을 실행합니다.
  - 따라서 내부 호출(self-invocation)에는 AOP가 적용되지 않습니다.

- AspectJ AOP
  - 바이트코드를 직접 조작하는 방식으로, 컴파일 타임, 로드 타임, 런타임 등 다양한 Weaving 방식을 지원합니다.
  - Spring AOP와 달리 내부 호출에도 적용되며, 성능이 더 뛰어납니다. 하지만 바이트코드를 조작해야 하기 때문에 설정이 복잡하고 유지보수가 어렵습니다.

