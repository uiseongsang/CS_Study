# Port
클라이언트에서 한번에 둘 이상의 서버와 연결 할때 구분하기 위해 사용한다.

IP 패킷 + TCP 세그먼트 = TCP/IP 패킷

TCP/IP 패킷 정보(출발지 IP & Port, 목적지 IP, Port, 전송 데이터...)

> 그래서 같은 IP 내에서 프로세스 구분이 가능하다
> <br> Ex) 게임(port:8090), 화상통화(port:21000), 웹 브라우저(port:10010)

* 0 ~ 65535 할당 가능
* 0 ~ 1023 잘 알려진 포트, 사용하지 않는 것이 좋음
  * FTP - 20, 21
  * TELNET - 23
  * HTTP - 80
  * HTTPS - 443