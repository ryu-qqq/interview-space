## 🔥 2. MySQL 아키텍처 및 내부 동작

###  MySQL의 주요 구성 요소 (Connection Layer, SQL Layer, Storage Engine Layer)
- Connection Layer: 클라이언트와 연결을 관리
- SQL Layer: 쿼리 파싱 및 실행 계획 수립
- Storage Engine Layer: 데이터 저장 및 검색 수행

   
### InnoDB가 MyISAM보다 성능적으로 뛰어난 이유 (ACID, MVCC 지원, Row-Level Lock 등)
- InnoDB는 Row-Level Lock을 지원하여 동시성을 높이고, 트랜잭션을 지원하며, MVCC를 활용하여 성능을 향상시킵니다


### MySQL의 데이터 저장 방식 (B+ Tree 기반 인덱스 구조, 데이터 페이지 관리)
- MySQL은 B+ Tree 기반 인덱스를 사용하여 데이터를 저장합니다. 데이터는 페이지 단위(16KB)로 관리되며, 디스크 I/O를 최소화하도록 설계되어 있습니다.

 
### MySQL의 Undo Log, Redo Log, WAL(Write-Ahead Logging) 개념 및 역할
- Undo Log는 트랜잭션 롤백을 위해 이전 데이터를 저장하고, Redo Log는 장애 발생 시 데이터를 복구하는 역할을 합니다. WAL은 변경 사항을 먼저 로그에 기록한 후 데이터 파일에 반영하는 방식으로 데이터 일관성을 보장합니다.


### MySQL에서 WAL(Write-Ahead Logging)이 어떻게 데이터 무결성을 보장하는가?
- 

### MySQL의 버퍼 풀(Buffer Pool)과 InnoDB의 메모리 관리 방식은?
-  MySQL의 InnoDB는 버퍼 풀을 사용해 자주 사용하는 데이터를 메모리에 캐싱하여 디스크 I/O를 최소화합니다. LRU(Least Recently Used) 알고리즘을 적용해 메모리 관리 성능을 최적화합니다.