# WAS(Web Application Server)와 WS(Web Server)의 차이를 설명해주세요
## WAS(Web Application Server)
* 비즈니스 로직을 넣을 수 있음
* Tomcat, PHP, ASP, .NET등

## WS(Web Server)
* 비즈니스 로직을 넣을 수 없음
* Nginx, Apache 등

### 정의
웹 브라우저와 같은 클라이언트로부터 HTTP 요청을 받아들이고 정적인 컨텐츠(html,css)를 반환

### 역할
클라이언트의 HTTP통신에 대한 처리를 담당
-> 웹 브라우저한테 요청 받은 정적 컨텐츠과 동적 컨텐츠를 전달

### 정적 컨텐츠 VS 동적 컨텐츠
정적 컨텐츠: 모든 클라이언트에게 동일한 웹페이지를 보여준다.
동적 컨텐츠: 사용자에 따라 웹페이지를 보여준다.
-> Web Server에는 client의 요청과 응답에 대해서만 수행하는 부분만 남기고 다른 동적 컨텐츠를 위한 질의와 구성들은 WAS로 분리한다.

### CGI (Common Gateway Interface)
웹 서버들간의 정보를 주고받는 일종의 규칙. 따라서 앞에서 말한 WAS는 이러한 CGI 규격에 맞게 설계된 서버
