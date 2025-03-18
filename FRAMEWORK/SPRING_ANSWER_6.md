## 🔥 6. Spring Boot


### Spring Boot에서 Embedded Tomcat 이 어떻게 동작하는가?
1. Spring Boot Starter (spring-boot-starter-web)를 추가하면 내장 Tomcat이 자동으로 설정됨.
2. Spring Boot 실행 시 SpringApplication.run()이 실행되면서 TomcatServletWebServerFactory가 내장 Tomcat을 생성.
3. 내장 Tomcat이 DispatcherServlet을 등록하고, HTTP 요청을 받을 준비를 함.
4. 애플리케이션을 실행하면 java -jar 만으로 내장 Tomcat이 함께 실행됨.
5. 내장 Tomcat이 동작하는 핵심 클래스
   - TomcatServletWebServerFactory → 내장 Tomcat 서버를 생성하는 역할
   - ServletWebServerApplicationContext → Spring이 내장 서버를 실행하는 컨텍스트

###  Spring Boot에서 ApplicationRunner vs. CommandLineRunner 차이점
Spring Boot 애플리케이션이 실행된 후 특정 로직을 실행할 수 있도록 도와주는 인터페이스입니다
CommandLineRunner는 단순 문자열 인자 처리를 원할 때 사용하고, ApplicationRunner는 실행 인자를 좀 더 체계적으로 다루고 싶을 때 사용합니다.

