# JAVA

## 🔥 1. Java & JVM 기본 개념
-  Java의 핵심 특징 (OOP, Write Once Run Anywhere, Garbage Collection 등)
-  JVM(Java Virtual Machine)이란 무엇이며, 어떻게 동작하는가?
-  JVM의 주요 구성 요소 (ClassLoader, Runtime Data Area, Execution Engine)
-  JDK, JRE, JVM의 차이점은 무엇인가?
-  Java 컴파일 과정 (Java Code → Bytecode → Machine Code 변환 과정)
-  JVM이 실행 파일(.exe) 없이도 동작하는 이유

## 🔥 2. JVM 내부 구조 & 메모리 영역
-  JVM 메모리 구조 (Method Area, Heap, Stack, PC Register, Native Method Stack)
-  JVM의 Method Area와 Heap의 차이점
-  JVM Stack과 Heap의 차이점 (메서드 호출 시 어떤 데이터가 어디에 저장되는가?)
-  Java에서 객체가 메모리에 할당되는 과정 (Heap vs. Stack vs. Metaspace)
-  JVM에서 String Pool이란 무엇이며, 어떻게 동작하는가?
-  String 객체를 Heap에 생성하는 방식 vs. String Constant Pool에서 생성하는 방식 차이

## 🔥 3. JVM의 ClassLoader (클래스 로딩 과정)
-  JVM의 ClassLoader란 무엇이며, 어떤 역할을 하는가?
-  JVM의 클래스 로딩 과정 (Loading → Linking → Initialization)
-  JVM에서 ClassLoader의 종류 (Bootstrap, Extension, Application, Custom ClassLoader)
-  Class.forName()과 ClassLoader.loadClass()의 차이점
-  클래스가 한 번 로딩된 후 다시 로딩되지 않는 이유는?

## 🔥 4. Java의 Garbage Collection (GC)
-  Garbage Collection이란 무엇이며, 왜 필요한가?
-  Java의 GC 동작 원리 (Mark and Sweep, Generational GC 개념)
-  JVM의 GC 영역 (Young Generation, Old Generation, Metaspace)
-  Minor GC vs. Major GC vs. Full GC 차이점
-  JVM의 GC 알고리즘 종류 (Serial GC, Parallel GC, G1 GC, ZGC, Shenandoah GC)
-  GC 튜닝 방법 (-XX:+UseG1GC, -Xms, -Xmx, GC 로그 분석 등)
-  JVM에서 OutOfMemoryError가 발생하는 원인과 해결 방법

## 🔥 5. Java의 메모리 관리 & 성능 최적화
-  Java에서 Stack Overflow가 발생하는 원인과 해결 방법
-  Java에서 메모리 누수(Memory Leak) 발생 원인과 해결 방법
-  Soft Reference, Weak Reference, Phantom Reference 차이점
-  Java의 Escape Analysis란 무엇이며, 성능에 어떤 영향을 미치는가?
-  JVM의 TLAB(Thread Local Allocation Buffer)이란 무엇인가?
-  JVM의 JIT(Just-In-Time) Compiler란 무엇이며, 성능 최적화 방식

## 🔥 6. Java의 동시성 (멀티스레딩 & 병렬 처리)
-  Java에서 멀티스레딩이란 무엇이며, 어떻게 동작하는가?
-  Thread vs. Runnable의 차이점
-  Java의 Thread LifeCycle (NEW, RUNNABLE, BLOCKED, WAITING, TERMINATED)
-  Java의 synchronized 키워드가 내부적으로 어떻게 동작하는가? (Monitor Lock, Object Header, Biased Locking)
-  Java에서 Deadlock(교착 상태)이 발생하는 원인과 해결 방법
-  ReentrantLock vs. synchronized 차이점 및 언제 사용하는가?
-  ThreadLocal이란 무엇이며, 언제 사용해야 하는가?
-  ForkJoinPool과 ExecutorService의 차이점
-  Java에서 CompletableFuture를 활용한 비동기 프로그래밍

## 🔥 7. Java의 람다(Lambda) & 스트림(Stream)
-  람다 표현식(Lambda Expression)이란 무엇이며, 왜 등장했는가?
-  람다 표현식과 익명 클래스(Anonymous Class) 차이점
-  Java Stream API란 무엇이며, 내부적으로 어떻게 동작하는가?
-  Stream의 중간 연산(Intermediate Operation) vs. 최종 연산(Terminal Operation) 차이
-  parallelStream()을 사용할 때 주의해야 할 점 (병렬 처리 성능 이슈)
-  Stream에서 Lazy Evaluation이란 무엇인가?

## 🔥 8. Java의 예외 처리 (Exception Handling)
-  Checked Exception vs. Unchecked Exception 차이점
-  예외 전파(Exception Propagation)란 무엇인가?
-  try-with-resources란 무엇이며, 내부적으로 어떻게 동작하는가?
-  Java에서 OutOfMemoryError, StackOverflowError, ClassNotFoundException이 발생하는 원인

## 🔥 9. Java의 디자인 패턴
- 싱글톤(Singleton) 패턴이란 무엇이며, 어떻게 구현하는가? (Lazy vs. Eager Initialization)
- 팩토리(Factory) 패턴이란 무엇이며, 왜 필요한가?
- 전략(Strategy) 패턴 vs. 템플릿 메서드(Template Method) 패턴 차이점
- 옵저버(Observer) 패턴이란 무엇이며, 언제 사용하는가?
- 프록시(Proxy) 패턴과 데코레이터(Decorator) 패턴 차이점
- 빌더(Builder) 패턴이란 무엇이며, 언제 사용하는가?

## 🔥 10. 면접에서 자주 나오는 Java 질문
- JVM이란 무엇이며, 내부적으로 어떻게 동작하는가?
- JVM의 메모리 구조를 설명하시오.
- 클래스 로딩 과정(Loading, Linking, Initialization)을 설명하시오.
- Garbage Collection의 원리를 설명하시오.
- Java에서 멀티스레딩이란 무엇이며, 동기화 문제를 해결하는 방법은?
- synchronized 키워드와 ReentrantLock의 차이점은?
- 람다 표현식과 기존 익명 클래스의 차이점은?
- Stream API가 내부적으로 어떻게 동작하는가?
- Checked Exception과 Unchecked Exception의 차이점은?
- Singleton 패턴을 안전하게 구현하는 방법은?

