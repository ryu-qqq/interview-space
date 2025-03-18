## 🔥 4. MySQL 트랜잭션 & ACID & MVCC

### MySQL에서 트랜잭션이란 무엇인가?
- 랜잭션(Transaction)이란 데이터베이스에서 하나의 논리적인 작업 단위를 의미하며, 여러 SQL 작업을 하나의 단위로 묶어 실행할 수 있도록 합니다.

### ACID(Atomicity, Consistency, Isolation, Durability) 개념과 MySQL에서의 적용 방식
- 원자성
- 일관성
- 격리성
- 지속성


### InnoDB에서 트랜잭션이 어떻게 동작하는가? (Undo Log & Redo Log 활용)
- B+ Tree는 B-Tree와 달리 모든 데이터가 리프 노드에 저장되어 있고, 리프 노드끼리 연결되어 있어 범위 검색(ORDER BY, BETWEEN)에 최적화되어 있습니다. 또한, 균형 트리 구조를 유지하여 검색 속도를 일정하게 유지할 수 있습니다.

 
### Read Uncommitted, Read Committed, Repeatable Read, Serializable의 차이


### MySQL에서 Dirty Read, Phantom Read, Non-Repeatable Read 문제 발생 원리


### MVCC(Multi-Version Concurrency Control)란 무엇이며, 어떻게 동작하는가?
- MVCC는 트랜잭션이 서로 간섭하지 않도록 여러 버전의 데이터를 관리하는 동시성 제어 방식입니다.
- MySQL InnoDB는 MVCC를 사용하여 REPEATABLE READ 격리 수준에서 성능을 향상시킴.

### MySQL에서 트랜잭션 롤백이 발생하면 실제로 어떤 일이 벌어지는가?
- 트랜잭션이 ROLLBACK되면, Undo Log를 사용하여 데이터를 원래 상태로 복구합니다.
- 트랜잭션 실행 시 변경 전 데이터를 Undo Log에 저장
- ROLLBACK 실행 시 Undo Log를 참고하여 원래 상태로 복구
- COMMIT 후에는 ROLLBACK이 불가능