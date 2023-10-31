[WAS(Web Application Server)와 WS(Web Server)의 차이](Spring/WAS_WS.md)
에서 "JAVA 이러한 CGI규격을 맞추기 위한 기술을 가지고 있는데 그것을 서블릿이라고 한다."

-> WS,WAS,CGI 대해서 모른다면 보시는걸 추천드립니다.

# 서블릿(Servlet)
클라이언트 요청을 처리하고, 그 결과를 반환하는 Servlet 클래스의 구현 규칙을 지킨 자바 웹 프로그래밍 기술

-> 자바를 사용하여 웹을 만들기 위해 필요한 기술

EX) 사용자가 로그인을 할 때, 사용자는 ID,PW를 입력하고 로그인 버튼을 누른다.

그떄 서버는 클라이언트의 ID,PW를 확인하고, 다음 페이지를 띄워주어야 하는데, 이러한 역할을 수행하는 것이 바로 서블릿입니다.

## 서블릿 특징
* 클라이언트의 요청에 대해 동적으로 작동하는 웹 어플리케이션 컴포넌트
* Html을 사용하여 요청에 응답한다
* Java Thread를 이용하여 동작한다.
* MVC 패턴에서 Controller로 이용된다.
* HTTP 프로토콜 서비스를 지원하는 javax.servlet.http.HttpServlet 클래스를 상속받는다.
* UDP보다 처리 속도가 느리다
* HTML 변경 시 Servlet을 재컴파일해야 하는 단점이 있다.

일반적으로 웹서버는 정적인 페이지만을 제공. 그렇기 떄문에 동적인 페이지를 제공하기 위해서 웹서버는 WAS에 도움을 요청하여 동적인 페이지를 작성해야 합니다.

-> 웹서버가 동적인 페이지를 제공할 수 있도록 도와주는 어플리케이션이 서블릿이며, 동적인 페이지를 생성하는 어플리케이션이 CGI입니다.

## Servlet 동작 방식
1. Client가 URL을 입력하면 HTTP Request가 Servlet Container로 전송합니다.
2. 요청을 전송받은 Servlet Container는 HttpServletRequest, HttpServletResponse 객체를 생성합니다.
3. web.xml을 기반으로 Client가 요청한 URL이 어느 서브릿에 대한 요청인지 찾습니다.
4. 해당 서블릿에서 service 메소드를 호출한 후 Client의 GET, POST 여부에 따라 DoGet() OR DoPost()를 호출합니다.
5. DoGet() OR DoPost() 메소드는 동적 페이지를 생성한 후 HttpServletResponse 객체에 응답을 보냅니다.
6. 응답이 끝나면 HttpServletRequest, HttpServletResponse 두 객체를 소멸시킵니다.

# Servlet Container
서블릿을 관리해주는 컨테이너

서버에 서블릿을 만들었다고 해서 스스로 작동하는 것이 아니고 서블릿을 관리해주는 것이 서블릿 컨테이너이다.

서블릿이 어떠한 역할을 수행하는 정의서라고 보면, 서블릿 컨테이너는 그 정의서를 보고 수행한다고 볼 수 있습니다. 서블릿 컨테이너는 클라이언트의 요청(Request)을 받아주고 응답(Response)할 수 있게, 웹 서버와 소켓으로 통신하며 대표적인 예로 톰캣(Tomcat)이 있습니다. 톰캣은 실제로 웹 서버와 통신 하여 JSP와 Servlet이 작동하는 환경을 제공해줍니다.

## Servlet Container 역할
1. 웹서버와의 통신 지원
2. 서브릿 생명주기 관리
3. 멀티쓰레드 지원 및 관리
4. 선언적인 보안 관리

출처: https://mangkyu.tistory.com/14