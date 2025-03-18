## 🔥 7. Spring과 JPA (Spring Data JPA)

뻔한 대답말고 코드 레벨을 좀보고 답할걸 찾아봐야 겠다.
----


### Spring Data JPA란 무엇이며, 기존 JPA와의 차이점
Spring Data JPA는 기존 JPA(Java Persistence API)를 더 쉽게 사용할 수 있도록 추상화한 Spring 기반 ORM(객체-관계 매핑) 라이브러리입니다.
기존 JPA는 개발자가 EntityManager를 직접 다뤄야 하지만, Spring Data JPA는 이를 더 편리하게 추상화하여 사용성을 극대화합니다.


###  JPA에서 EntityManager란 무엇이며, 어떻게 동작하는가?
- EntityManager는 JPA에서 엔티티를 관리하는 핵심 객체로, 트랜잭션 범위 내에서 영속성 컨텍스트를 유지하며 데이터베이스와의 상호작용을 담당합니다.
- 영속성 컨텍스트(Persistence Context)를 관리하여 1차 캐시, 변경 감지, 트랜잭션 관리를 자동으로 수행.
- Spring Data JPA에서는 @Transactional이 적용된 메서드 내부에서 자동으로 EntityManager가 관리됨.

### JPA의 1차 캐시와 2차 캐시의 차이점
JPA에서는 성능 최적화를 위해 1차 캐시와 2차 캐시를 지원합니다.

1. 1차 캐시 (Persistence Context)
   - 각 EntityManager별로 관리되는 캐시 (트랜잭션 범위 내에서만 유지). 동일한 엔티티를 반복 조회할 때 DB가 아닌 캐시에서 가져옴.
2. 2차 캐시 (Shared Cache)
   - 애플리케이션 전체에서 공유되는 캐시 (별도로 설정 필요). Hibernate 의 경우 EHCache 등을 통해 2차 캐시 사용 가능.

### Spring Data JPA에서 @Transactional과 EntityManager의 관계

### Lazy Loading과 Eager Loading의 차이 및 N+1 문제 해결 방법 (Fetch Join, Batch Size 등)
