## 🔥 4. Spring 트랜잭션 관리 (@Transactional)

### Spring에서 트랜잭션이란 무엇인가? (ACID 개념 포함)
- A(원자성) : 트랜잭션은 완전시 실행 또는 실패
- C(일관성) : 트랜잭션이 실행되기 전과 후에 데이터의 무결성이 유지되어야함
- I(격리성) : 여러 트랜잭션이 실핼될때 서로 영향을 미치면 안됨
- D(지속성) : 트랜잭션이 성공적으로 완료되면 데이터는 영구 저장되어야함


### @Transactional이 내부적으로 어떻게 동작하는가?
- @Transactional은 Spring AOP 기반으로 동작하며, 메서드 실행 전에 트랜잭션을 시작하고, 메서드가 정상적으로 완료되면 commit을 수행합니다.
만약 RuntimeException이 발생하면 자동으로 rollback됩니다. Spring의 PlatformTransactionManager 가 실제로 트랜잭션을 관리하며,
@Transactional이 적용된 메서드는 프록시 객체를 통해 실행되므로 내부 메서드 호출 시 주의가 필요합니다.


### 트랜잭션 전파(Propagation) 옵션 7가지 (REQUIRED, REQUIRES_NEW 등) 차이점
Spring 트랜잭션은 @Transactional(propagation = Propagation.XXX) 옵션을 통해 전파 방식을 설정할 수 있다
 
-  REQUIRED (기본값) → 기존 트랜잭션이 있으면 참여, 없으면 새로 생성.
-  REQUIRES_NEW → 항상 새로운 트랜잭션 생성.
-  NESTED → 기존 트랜잭션 내에서 중첩 트랜잭션 실행.
-  MANDATORY → 반드시 기존 트랜잭션이 있어야 실행 (없으면 예외 발생).
-  NEVER → 트랜잭션 없이 실행 (있으면 예외 발생).
-  NOT_SUPPORTED → 기존 트랜잭션을 중단하고 실행.
-  SUPPORTS → 트랜잭션이 있으면 참여하고, 없으면 트랜잭션 없이 실행.

###  트랜잭션 격리 수준(Isolation Level)과 Dirty Read, Phantom Read 문제 해결 방법

- 리드언커밋 : 커밋되지 않은 데이터를 다른 트랜잭션에서 읽을 수 있음 (Dirty Read)
- 리드커밋 : 커밋된 데이터를 읽을 수 있음 (Dirty Read 방지), 다만 같은 트랜잭션에서 Read 의 결과값이 변경될 수 있음(Non-Repeatable Read)
- 리피터블리드 : MYSQL 의 기본값이기도 하며 트랜잭션이 시작 된 후 같은 쿼리를 실행하면 항상 같은 데이터를 반환 다만 PHANTOM READ 발생 가능
- 시리얼라이저블 : 트랜잭션을 순차적으로 실행 모든 문제 해결 다만 성능이 많이 떨어짐

팬텀 리드는 DB 차원에서 막는 방법이 있으나 이건 스프링 챕터 이므로 다루진 않곘다.

###  @Transactional을 메서드 레벨과 클래스 레벨에 적용할 때 차이점
Spring은 구체적인 것(Method Level)을 우선 적용한다.
즉, 클래스 레벨의 @Transactional을 설정해도, 메서드에 따로 설정하면 메서드의 설정이 우선 적용된다.

###  Spring에서 트랜잭션 롤백이 실제로 어떻게 처리되는가?
Spring의 트랜잭션은 AOP를 기반으로 동작하며, 트랜잭션 경계를 관리한다. 예외가 발생하면 트랜잭션 매니저가 롤백을 수행하여 ACID 원칙을 보장한다.
내부적으로 PlatformTransactionManager가 관리한다.