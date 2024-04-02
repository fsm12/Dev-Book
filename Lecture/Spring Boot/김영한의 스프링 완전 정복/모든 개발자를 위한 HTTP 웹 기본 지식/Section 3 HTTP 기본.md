# Section 3 HTTP 기본
마지막 공부날짜 : 2024.04.02.

</br></br>

## 모든 것이 HTTP
## HTTP란?

- **H**yper**T**ext **T**ransfer **P**rotocol의 약자
- 웹상에서 클라이언트와 서버간의 통신을 위한 프로토콜
- 비연결성, 무상태 특징을 가짐

### **비연결성 ( Connection-less )**

- 우편 시스템과 유사 - 연결 설정 및 연결 종료 불필요
- 패킷은 동일한 경로를 따르지 않음
- ex) UDP

### 연결 지향 ( **Connection-oriented** )

- 전화 시스템과 유사 - 연결 설정 및 연결 종료 필요
- 패킷은 동일한 경로를 따름
- ex) TCP

### **무상태 ( Stateless )**

- 클라이언트가 현재 상태에 따라 서버에 요청을 보내고 서버가 응답하는 네트워크 프로토콜 유형
- 서버가 서버 정보 또는 세션 세부 정보를 유지할 필요가 없음
- 서버 설계를 단순화 ⇒ 아키텍처 확장이 비교적 쉬움
- 복구해야 하는 상태가 없고, 장애가 발생한 서버가 충돌 후 다시 시작될 수 있기 때문에 충돌 시 더 잘 작동 O
- ex) HTTP, UDP, DNS

### **상태 ( Stateful )**

- 클라이언트가 서버에 요청을 전송하면 어떤 종류의 응답을 기대하고, 응답을 받지 못하면 요청을 다시 보냄
- 상태 저장 프로토콜을 사용하려면 서버가 상태 및 세션 정보를 저장해야 함
- 서버 설계를 복잡하고 무겁게 함 ⇒ 아키텍처 확장이 비교적 어렵고 복잡함
- 내부 상태의 상태 및 세션 세부 정보를 유지해야 하므로 상태 프로토콜은 충돌 시 잘 작동 X
- ex) FTP, TCP, Telnet

</br>

## HTTP 메시지 구조

![image](https://github.com/fsm12/Dev-Book/assets/74345771/b55684df-08ab-4a9d-8b0f-4463f1db35de)

- ***start-line*** = Request-line / Status-line
요청 혹은 응답의 자원(혹은 상태)이 작성되는 공간

```
Request-line
Format: [method]SP[request-target]SP[HTTP-version]CRLF
Ex        : GET /search?q=hello&hl=ko HTTP/1.1
```

```
Status-line
Format: [HTTP-version]SP[status-code]SP[reason-phrase]
Ex        : HTTP/1.1 200 OK
```

- ***HTTP 헤더***   
HTTP 전송에 필요한 모든 부가정보를 담는다.    
Ex: 메세지 바디의 내용 및 크기정보, 압축,인증, 요청(브라우저)정보 등 표준 헤더가 몹시 많다.    
필요한 경우 임의의 헤더를 추가 할 수 있다(Ex: catsbi: hihi)   

```
HTTP Header
Format: [header-field]:OSW[field-value]OSW
Ex        : Content-Type: application/json
```

- ***empty line (CRLF)***   
공백(Enter) Message Body와 구분하는 역할

- ***HTTP Message Body***   
실제 전송할 데이터
HTML 문서, 이미지, 영상, JSON 기타 byte로 표현가능한 모든 데이터
