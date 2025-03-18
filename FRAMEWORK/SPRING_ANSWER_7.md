## 🔥 7. Spring Security


### Spring Security란 무엇이며, 어떻게 인증/인가를 관리하는가?
1. Spring Boot Starter (spring-boot-starter-web)를 추가하면 내장 Tomcat이 자동으로 설정됨.
2. Spring Boot 실행 시 SpringApplication.run()이 실행되면서 TomcatServletWebServerFactory가 내장 Tomcat을 생성.
3. 내장 Tomcat이 DispatcherServlet을 등록하고, HTTP 요청을 받을 준비를 함.
4. 애플리케이션을 실행하면 java -jar 만으로 내장 Tomcat이 함께 실행됨.
5. 내장 Tomcat이 동작하는 핵심 클래스
   - TomcatServletWebServerFactory → 내장 Tomcat 서버를 생성하는 역할
   - ServletWebServerApplicationContext → Spring이 내장 서버를 실행하는 컨텍스트

###  Spring Security에서 인증(Authentication)과 인가(Authorization)의 차이
개념	설명	HTTP 상태 코드
- 인증 (Authentication)	사용자가 누구인지 확인하는 과정 (로그인)	401 Unauthorized
- 인가 (Authorization)	인증된 사용자가 어떤 권한이 있는지 확인하는 과정	403 Forbidden

### Spring Security의 주요 구성 요소 (SecurityFilterChain, UserDetailsService, AuthenticationProvider)
1. SecurityFilterChain
   - Spring Security는 필터 기반 구조이며, 인증 요청을 처리하기 위해 여러 개의 필터를 가진다.
   - Security Filter Chain은 여러 개의 보안 필터로 구성되며, `DelegatingFilterProxy를` 통해 Spring IoC 컨테이너에서 관리된다. 이 필터들이 순차적으로 실행되며, 인증/인가를 처리한다.
2. SecurityContext
   - 사용자가 인증되면 SecurityContext에 인증 정보(Authentication 객체)를 저장한다.
   - 이 인증 정보는 ThreadLocal을 이용하여 각 요청마다 유지된다.
   - SecurityContextHolder가 내부적으로 ThreadLocal을 활용하여 인증 정보를 관리한다.
3. UserDetailsService → 사용자 정보를 로드하는 인터페이스, AuthenticationProvider → 인증 로직을 수행하는 객체


### JWT (JSON Web Token) 기반 인증 방식과 기존 세션 기반 인증 방식 차이점
1. 세션 기반 인증 (Session Authentication)
- 사용자가 로그인하면 서버에서 세션을 생성하고, 세션 ID를 클라이언트에 저장.
- 클라이언트가 API를 요청할 때마다 세션 ID를 서버로 전송하여 인증 확인.
- 단점: 서버가 상태를 관리해야 하므로, 확장성이 떨어짐.

2. JWT 기반 인증 (Stateless Authentication)
- 로그인 시 JWT 토큰을 생성하여 클라이언트에게 전달.
- 클라이언트가 요청할 때 JWT를 Authorization: Bearer 헤더에 포함하여 전송.
- 서버는 JWT의 서명을 검증하여 사용자를 인증.
- 장점: 서버가 세션을 관리할 필요 없어 확장성이 뛰어남.