# CACHE - REDIS

## 🔥 1. Redis 기본 개념
- Redis란 무엇인가?
- Redis는 왜 In-Memory 데이터베이스인가?
- Redis의 주요 특징 (싱글 스레드 아키텍처, 고속 데이터 처리, 영속성 지원 등)
- Redis는 어떤 문제를 해결하기 위해 등장했는가?

## 🔥 2. Redis 자료구조 (데이터 타입)
✅ Redis에서 제공하는 자료구조(데이터 타입) 종류 및 특징
✅ 각 자료구조가 언제 사용되는지, 대표적인 사용 사례 설명 가능하도록 준비하기

- String (기본 Key-Value 저장 방식)
- List (Linked List 기반, 메시지 큐 활용 가능)
- Set (중복 없는 집합, 태그 시스템 등)
- Sorted Set (랭킹 시스템, 리더보드 구현)
- Hash (필드-값 저장, 사용자 프로필 저장)
- Bitmap (비트 단위 데이터 저장, 활성 사용자 체크)
- HyperLogLog (근사치 계산, 유니크 방문자 수 카운팅)
- Stream (로그 저장, 메시지 큐 역할)
- GeoSpatial (위치 기반 서비스, 거리 계산)

## 🔥 3. Redis의 인덱스 구조
-  Redis는 내부적으로 데이터를 어떻게 저장하는가?
-  Redis는 왜 B+ Tree가 아니라 Skip List와 Hash Table을 사용하는가?
-  Redis의 Sorted Set이 Skip List를 사용하는 이유는?
-  Redis의 Hash는 내부적으로 어떻게 동작하는가?

## 🔥 4. Redis 분산락(Distributed Lock)
-  Redis에서 분산락을 구현하는 방법 (SET NX + EX)
-  SET NX 방식의 문제점 (네트워크 장애, TTL 만료 이슈 등)
-  Redlock 알고리즘이란 무엇인가?
-  Redlock이 기존 락 방식보다 더 신뢰성이 높은 이유
-  Redlock을 사용할 때의 5단계 과정
-  Redlock을 위한 Redis 노드 구성 (독립적인 5개 노드 운영 필요)
-  Redis 클러스터에서 Redlock을 사용할 수 있는가? (아님, 독립적인 5개 노드 필요)

## 🔥 5. Redis Cluster (분산 환경)
-  Redis Cluster란 무엇인가?
-  Redis Cluster가 데이터를 어떻게 샤딩(Sharding)하는가?
-  해시 슬롯(Hash Slot) 개념과 키가 특정 노드에 저장되는 과정
-  키를 저장할 때 해시 슬롯을 계산하는 방법 (CRC16(key) % 16384)
-  클라이언트가 키 조회 시 요청이 어떤 과정을 거쳐 처리되는가?
-  잘못된 노드에 요청을 보낼 경우 MOVED 리디렉션이 어떻게 동작하는가?
-  Redis Cluster에서 특정 노드가 장애가 발생하면 어떻게 복구되는가?

## 🔥 6. Redis HA (고가용성)
-  Redis Sentinel이란 무엇인가?
-  Redis Sentinel과 Redis Cluster의 차이점
-  Redis Sentinel을 활용한 마스터-슬레이브(Master-Slave) 자동 Failover
-  Redis Sentinel을 활용한 장애 감지 및 자동 복구 과정
-  Redis Sentinel과 Redlock의 차이 (Sentinel은 Failover, Redlock은 분산락을 위한 알고리즘)

## 🔥 7. Redis 영속성 (데이터 보존)
-  Redis는 기본적으로 In-Memory DB인데, 데이터를 어떻게 영구적으로 저장하는가?
-  Redis의 AOF(Append-Only File) vs. RDB(Snapshot) 차이점
-  AOF와 RDB를 혼합하여 운영할 때의 장점과 단점
-  AOF 재작성(AOF Rewrite)이 필요한 이유
-  AOF 동작 방식 (fsync 매 시점, 매 초, 비동기 모드 차이)

## 🔥 8. Redis 성능 최적화
-  Redis가 싱글 스레드인데 왜 빠른가?
-  CPU 바운드가 아니라 I/O 바운드 작업을 수행하기 때문에 싱글 스레드에서도 성능이 좋음
-  Pipeline을 사용하여 여러 개의 요청을 동시에 처리하는 방법
-  Redis Key Naming Convention (키 길이, 네임스페이스 적용 방식 등)
-  TTL(Time-To-Live) 설정 및 만료 전략 (LRU, LFU, Random Eviction 등)

## 🔥 9. Redis vs. 다른 NoSQL
-  Redis vs. Memcached (주요 차이점, 언제 Redis를 선택해야 하는가?)
-  Redis vs. MongoDB (MongoDB는 Document Store, Redis는 Key-Value Store)
-  Redis vs. Kafka (Redis Stream과 Kafka의 차이, 메시지 큐로서 Redis의 한계점)

## 🔥 10. 면접에서 나올 수 있는 심화 질문
- Redis에서 특정 키를 조회할 때 어떤 과정을 거치는가?
- Redis Cluster에서 특정 키가 어떤 노드에 저장되는지 계산하는 과정은?
- Redis에서 B+ Tree를 사용하지 않고 Skip List를 사용하는 이유는?
- Redis에서 대량의 데이터를 저장할 때 메모리 효율을 높이는 방법은?
- Redis에서 데이터를 영구적으로 저장하려면 어떤 설정을 해야 하는가?
- Redlock을 사용해야 하는 환경과 사용하지 않아도 되는 환경의 차이는?
- Redis가 싱글 스레드인데도 빠른 이유는?
- Redis에서 캐시 만료 정책(Eviction Policy)에는 어떤 것들이 있는가?
- Redis에서 LRU(Least Recently Used)와 LFU(Least Frequently Used)의 차이점은?
- Redis를 사용한 분산 시스템에서 "Split Brain(노드 간 분리 현상)"이 발생하면 어떻게 해결할 수 있는가?

## 🔥 11. 면접을 위한 정리된 한 줄 요약(급한 사람)
-  Redis는 In-Memory Key-Value Store이며, 다양한 데이터 타입을 지원한다.
-  Redis Cluster는 데이터를 16,384개의 해시 슬롯(Hash Slot)으로 나누어 샤딩한다.
-  Redis에서 기본적인 분산락은 SET NX 방식을 사용하며, Redlock 알고리즘은 신뢰성을 보장하는 분산락 방식이다.
-  Redlock을 사용하려면 독립적인 5개의 Redis 노드가 필요하며, Redis 클러스터 환경에서는 적합하지 않을 수 있다.
-  Redis Sentinel은 마스터 장애 시 자동으로 Failover를 수행하는 HA 솔루션이다.
-  Redis의 영속성 방식에는 AOF(Append-Only File)와 RDB(Snapshot)가 있다.
-  Redis는 싱글 스레드 기반이지만 I/O 멀티플렉싱을 통해 매우 빠르게 동작한다.


