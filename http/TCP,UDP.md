# TCP, UDP
IP 스택의 4계층
* 응용 계층 - HTTP, FTP
* 전송 계층 - TCP, UDP
* 인터넷 계층 - IP
* 네트워크 인터페이스 계층

![image](https://github.com/uiseongsang/CS_Study/assets/40707686/a9ac2db3-0f71-4a3d-aa3b-92bcdfe57de7)
<br>
LAN(Local Area Network): 서로 연결된 소규모 네트워크

애플리케이션에서 hello world 메시지 작성 > 소켓 라이브러리를 통해 전달 > TCP 정보 생성(메시지 데이터 포함) > IP 패킷 생성(TCP 데이터 포함) > LAN 카드로 서버에 전송

## TCP/IP 패킷 정보
IP 패킷 정보(출발지 IP, 목적지 IP, 기타등등) 안에 TCP 세그먼트(출발지 Port, 목적지 Port, 전송 제어, 순서, 검증 정보...)가 있다.

## TCP 특징
전송 제어 프로토콜(Transmission COntrol Protocl)

* 연결지향 - TCP 3 way handshake (가상 연결)
* 데이터 전달 보증
* 순서 보장
* 신뢰할 수 있는 프로토콜
* 현재는 대부분 TCP 사용

## UDP 특징
사용자 데이터그램 프로토콜(User Datagran Protocol)

* 하얀 도화지에 비유(기능이 거의 없음)
* 연결지향 - TCP 3 way handshake X
* 데이터 전달 보증 X
* 순서 보장 X
* 데이터 전달 및 순서가 보장되지 않지만, 단순하고 빠름
* 정리
  * IP와 거의 같다 + PORT + 처크섬 정도만 추가
  * 애플리케이션에서 추가 작업 필요
