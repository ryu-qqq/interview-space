## 🔥 1. CS(Computer Science) 기본 개념
-  컴퓨터 구조(CPU, RAM, 디스크, 캐시 메모리 등) 이해하기
-  컴퓨터가 프로그램을 실행하는 과정 (전원 → 부팅 → OS 로드 → 프로세스 실행)
-  CPU와 GPU의 차이 및 각자의 역할
-  프로세스와 스레드의 차이 (멀티프로세싱 vs. 멀티스레딩)
-  Stack과 Heap 메모리의 차이 및 관리 방식
-  동기(Synchronous) vs. 비동기(Asynchronous) 개념
-  블로킹(Blocking) vs. 논블로킹(Non-Blocking) 개념

## 🔥 2. OS(Operating System) 기본 개념
-  운영체제(OS)의 역할과 주요 기능 (프로세스 관리, 메모리 관리, 파일 시스템, I/O 관리 등)
-  커널(Kernel)이란 무엇이며, OS 내부에서 어떻게 동작하는가?
-  유저 모드(User Mode)와 커널 모드(Kernel Mode) 차이
-  시스템 콜(System Call)이란 무엇이며, 왜 필요한가?
-  컨텍스트 스위칭(Context Switching)이란 무엇이며, 왜 발생하는가?
-  OS의 인터럽트(Interrupt) 처리 방식과 인터럽트 벡터 테이블

## 🔥 3. 프로세스 & 스레드 관리
-  프로세스(Process)란 무엇이며, 어떻게 동작하는가?
-  멀티스레딩(Multithreading)이란 무엇이며, 어떻게 동작하는가?
-  멀티프로세스(Multiprocessing) vs. 멀티스레드(Multithreading) 차이점
-  프로세스의 상태 변화 (New → Ready → Running → Blocked → Terminated)
-  프로세스 스케줄링 알고리즘 (FCFS, SJF, RR, Priority Scheduling 등)
-  스레드(Thread)란 무엇이며, 프로세스와의 차이점은?
-  POSIX Thread (pthread)와 Java Thread의 차이점
-  싱글스레드(Single Thread)와 멀티스레드(Multi Thread)의 차이점
-  Race Condition(경쟁 상태)란 무엇이며, 이를 방지하는 방법은?

## 🔥 4. 프로세스 간 통신(IPC, Inter-Process Communication)
-  프로세스 간 통신(IPC)이란 무엇인가?
-  IPC 기법 종류 및 차이점 (Shared Memory, Message Queue, Pipe, Signal, Socket 등)
-  Shared Memory vs. Message Queue 차이점
-  Named Pipe vs. Anonymous Pipe 차이점
-  프로세스 간 통신에서 동기화(Synchronization)를 보장하는 방법

## 🔥 5. 동기화 & 경쟁 상태 해결
-  동기화(Synchronization)란 무엇이며, 왜 필요한가?
-  뮤텍스(Mutex) vs. 세마포어(Semaphore) 차이점
-  데드락(Deadlock) 발생 원인과 해결 방법 (Banker's Algorithm, 교착 상태 예방 기법)
-  교착 상태(Deadlock)와 기아 상태(Starvation) 차이점
-  락(Lock)과 모니터(Monitor) 차이점

## 🔥 6. 메모리 관리 & 가상 메모리
-  물리 메모리 vs. 가상 메모리 차이점
-  페이징(Paging)과 세그멘테이션(Segmentation) 차이
-  페이지 폴트(Page Fault)란 무엇이며, 어떻게 처리되는가?
-  TLB(Translation Lookaside Buffer)란 무엇이며, 메모리 접근 속도를 어떻게 최적화하는가?
-  Demand Paging과 Swapping의 차이점
-  메모리 할당 방식 (First Fit, Best Fit, Worst Fit 차이)
-  메모리 단편화(Internal Fragmentation vs. External Fragmentation) 문제 해결 방법

## 🔥 7. 파일 시스템 & I/O 관리
-  파일 시스템(File System)이란 무엇이며, OS에서 어떻게 관리되는가?
-  Ext4, NTFS, FAT32 등의 파일 시스템 차이점
-  파일 시스템에서 Journaling이란 무엇이며, 왜 필요한가?
-  디스크 스케줄링 알고리즘 (FCFS, SSTF, SCAN, C-SCAN 등) 비교
-  RAID (Redundant Array of Independent Disks) 레벨 종류 및 차이점 (RAID 0, 1, 5, 10 등)

## 🔥 8. 운영체제 성능 최적화 & 문제 해결
-  CPU 바운드(CPU-Bound) vs. I/O 바운드(I/O-Bound) 차이점
-  Linux에서 CPU 사용률과 메모리 사용량을 모니터링하는 방법 (top, htop, vmstat, iostat 등)
-  컨텍스트 스위칭 비용을 줄이는 방법 (CPU Affinity, Thread Pool 등)

## 🔥 9. 면접에서 자주 나오는 CS & OS 질문
-  프로세스와 스레드의 차이점은?
-  멀티스레딩이 성능을 무조건 향상시키는가?
-  멀티프로세싱 vs. 멀티스레딩 차이점은?
-  뮤텍스(Mutex)와 세마포어(Semaphore)의 차이점은?
-  페이징과 세그멘테이션의 차이점은?
-  데드락(Deadlock)이란 무엇이며, 이를 해결하는 방법은?
-  TCP와 UDP의 차이점은?
-  HTTP와 HTTPS의 차이점은?
-  3-Way Handshake 과정에서 SYN Flooding 공격이란 무엇인가?
-  프로세스가 실행될 때, OS 내부에서 어떤 과정이 수행되는가?
-  가상 메모리란 무엇이며, 어떻게 동작하는가?
-  CPU 캐시 메모리가 왜 중요한가? (L1, L2, L3 Cache 차이)