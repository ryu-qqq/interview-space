## 🔥 5. Spring MVC (Web Application)


### Spring에서 요청이 들어왔을 때의 흐름 (Request → Controller → Service → Repository → Response)
1. 클라이언트가 HTTP 요청을 보낸다
2. Filter 체인 실행(서블릿 레벨)
3. DispatcherServlet (요청을 받음 SPRING MVC 진입점)
4. HandlerInterceptor (스프링 관리 레벨)
5. HandlerMapping (적절한 컨트롤러 찾기)
6. HandlerAdapter(컨트롤러 실행)
7. HandlerMethodArgumentResolver (컨트롤러 메서드 파라미터 처리)
8. Controller
9. HttpMessageConverter (ResponseEntity, @ResponseBody 일경우 JSON 응답)
10. ViewResolver (HTML 경우 VIEW 결정)


###  Spring MVC에서 @Controller vs. @RestController 차이점
- @Controller → View를 반환하는 웹 애플리케이션에서 사용.
- @RestController → JSON 응답을 반환하는 REST API에서 사용.


###  Spring MVC에서 Model, ModelAndView, ResponseEntity 의 차이점
- Model → View에 데이터를 전달할 때 사용 (Thymeleaf, JSP)
- ModelAndView → View + Model을 함께 반환할 때 사용
- ResponseEntity → REST API 응답을 커스텀할 때 사용 (JSON 응답, 상태 코드 포함)
