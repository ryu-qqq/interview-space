# RDB - MYSQL

## 🔥 1. MySQL 기본 개념
- MySQL이란 무엇인가?
- MySQL이 RDB(Relational Database)인 이유는?
- MySQL의 주요 특징과 다른 RDBMS(Oracle, PostgreSQL, MSSQL)와의 차이점
- MySQL의 주요 스토리지 엔진(InnoDB vs. MyISAM vs. Memory vs. CSV) 차이점

## 🔥 2. MySQL 아키텍처 및 내부 동작
- MySQL의 주요 구성 요소 (Connection Layer, SQL Layer, Storage Engine Layer)
- InnoDB가 MyISAM보다 성능적으로 뛰어난 이유 (ACID, MVCC 지원, Row-Level Lock 등)
- MySQL의 데이터 저장 방식 (B+ Tree 기반 인덱스 구조, 데이터 페이지 관리)
- MySQL의 Undo Log, Redo Log, WAL(Write-Ahead Logging) 개념 및 역할
- MySQL에서 WAL(Write-Ahead Logging)이 어떻게 데이터 무결성을 보장하는가?
- MySQL의 버퍼 풀(Buffer Pool)과 InnoDB의 메모리 관리 방식

## 🔥 3. MySQL 인덱스 (B+ Tree & 성능 최적화)
- MySQL에서 인덱스란 무엇인가? (목적 & 역할)
- 클러스터드 인덱스 vs. 논클러스터드 인덱스 차이점
- B+ Tree가 MySQL에서 인덱스로 사용되는 이유 (B-Tree와의 차이점 포함)
- MySQL에서 "인덱스가 없다면" 어떤 문제가 발생하는가?
- MySQL 인덱스의 성능 저하 원인 (Fragmentation, Cardinality, Selectivity)
- Composite Index(복합 인덱스)란 무엇이며, 언제 사용하는가?
- Covering Index란 무엇이며, 성능을 어떻게 향상시키는가?
- Full-Text Index란 무엇인가? (LIKE 검색 vs. Full-Text 검색 차이점)
- 인덱스가 효율적으로 사용되지 않는 경우 (함수 사용, 와일드카드 검색 등)
- MySQL에서 인덱스를 올바르게 설계하는 방법 (Best Practices)

## 🔥 4. MySQL 트랜잭션 & ACID & MVCC
-  MySQL에서 트랜잭션이란 무엇인가?
-  ACID(Atomicity, Consistency, Isolation, Durability) 개념과 MySQL에서의 적용 방식
-  InnoDB에서 트랜잭션이 어떻게 동작하는가? (Undo Log & Redo Log 활용)
-  MySQL에서 Isolation Level(격리 수준)의 종류와 차이점
-  Read Uncommitted, Read Committed, Repeatable Read, Serializable의 차이
-  MySQL에서 Dirty Read, Phantom Read, Non-Repeatable Read 문제 발생 원리
-  MVCC(Multi-Version Concurrency Control)란 무엇이며, 어떻게 동작하는가?
-  MySQL에서 트랜잭션 롤백이 발생하면 실제로 어떤 일이 벌어지는가?

## 🔥 5. MySQL 락(Lock) & 동시성 제어
-  MySQL에서 Lock이 필요한 이유와 Lock의 종류
-  Row-Level Lock vs. Table-Level Lock 차이점
-  Shared Lock(공유 락) vs. Exclusive Lock(배타 락) 차이점
-  InnoDB의 Next-Key Lock과 Gap Lock이란? (팬텀 리드 방지 기법)
-  MySQL에서 Deadlock이 발생하는 원인과 해결 방법
-  MySQL에서 특정 테이블이 Lock에 의해 대기 중인지 확인하는 방법 (SHOW ENGINE INNODB STATUS)
-  MySQL에서 Lock을 회피하거나 최적화하는 방법 (Index 활용, Transaction 분리 등)

## 🔥 6. MySQL 성능 최적화 (쿼리 튜닝)
-  MySQL에서 쿼리 실행 계획을 확인하는 방법 (EXPLAIN, ANALYZE 활용)
-  EXPLAIN 결과에서 type, key, rows, Extra 필드의 의미 분석
-  Slow Query Log를 활용한 성능 저하 쿼리 탐지 방법
-  MySQL에서 서브쿼리 vs. JOIN 성능 비교 (어떤 경우에 어떤 방식을 선택해야 하는가?)
-  MySQL에서 GROUP BY 성능을 최적화하는 방법
-  ORDER BY 정렬 성능을 최적화하는 방법 (Sorting Buffer, Index 활용 등)
-  MySQL에서 COUNT(*)가 성능에 미치는 영향과 최적화 방법
-  MySQL에서 SELECT * 사용이 비효율적인 이유 (Projection Pruning)

## 🔥 7. MySQL 페이징 (LIMIT OFFSET vs. Keyset Pagination)
-  MySQL에서 OFFSET 기반 페이징의 성능 문제점
-  MySQL에서 OFFSET이 클수록 성능이 떨어지는 이유 (불필요한 데이터 스캔 문제)
-  커서 기반 페이징(Keyset Pagination)이 OFFSET보다 성능이 좋은 이유
-  MySQL에서 페이징 성능을 최적화하는 방법 (WHERE 조건 + 인덱스 활용)

## 🔥 8. MySQL Replication & High Availability
-  MySQL Replication(복제)이란 무엇인가?
-  Master-Slave Replication vs. Multi-Master Replication 차이점
-  MySQL Replication에서 비동기/반동기/완전 동기 복제 차이점
-  MySQL Replication을 사용할 때 발생할 수 있는 데이터 정합성 문제
-  MySQL에서 GTID(Global Transaction ID)를 활용한 복제 설정 방법
-  MySQL에서 자동 Failover를 구현하는 방법 (MHA, Orchestrator, ProxySQL)
-  MySQL에서 Read/Write 분리를 어떻게 구현하는가?

## 🔥 9. MySQL 데이터 마이그레이션 & 무중단 배포
-  MySQL에서 데이터 마이그레이션이 필요한 이유와 전략
-  MySQL에서 데이터 마이그레이션 시 발생할 수 있는 문제점 및 해결 방법
-  Zero-Downtime Migration (무중단 데이터 마이그레이션) 구현 방법
-  MySQL에서 Dual-Writing + Shadow Read를 이용한 데이터 마이그레이션 전략
-  MySQL에서 대량의 데이터를 Insert/Update 할 때 성능을 최적화하는 방법 (Batch Processing 활용)
-  MySQL과 NoSQL을 혼합해서 사용하는 하이브리드 데이터 모델 적용 사례

## 🔥 10. 면접에서 나올만한 MySQL 심화 질문
-  MySQL에서 특정 쿼리가 느린 원인을 어떻게 분석할 것인가?
-  MySQL에서 트랜잭션이 롤백될 때 실제로 어떤 과정이 발생하는가?
-  MySQL Replication에서 데이터 정합성을 보장하는 방법은?
-  MySQL의 B+ Tree 인덱스가 실제로 어떻게 동작하는가?
-  MySQL에서 Deadlock이 발생하면 어떻게 해결할 것인가?
-  MySQL에서 Full-Text Search는 어떻게 동작하는가?

