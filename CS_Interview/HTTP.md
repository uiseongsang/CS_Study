# HTTPS가 동작하는 방식에 대해서 설명 해 주세요
HTTPS는 암호화 프로토콜을 사용하여 통신을 암호화합니다.

- 이 프로토콜은 이전에는 보안 소켓 계층(SSL), 개선되어 전송 계층 보안(TLS) 기술을 사용합니다.
- 이 프로토콜은 비대칭 공개키 암호화 방식을 활용하여 통신을 보호합니다. 보안 시스템에서는 두개의 서로 다른 키를 사용하여 두 당사자 간의 통신을 암호화 합니다.
- 공개키
    - 서버와 상호작용하기 위해 모든 유저가 사용할 수 있는 키
    - 공개키로 암호화 된 정보는 개인키로만 해독 가능
- 개인키
    - 웹사이트 소유자가 관리, 비공개로 유지
    - 공개키로 암호화된 정보를 해독하는데 사용
