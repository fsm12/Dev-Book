# Section 1 인터넷 네트워크
마지막 공부날짜 : 2024.03.20.

</br></br>

## 인터넷 통신

클라이언트와 서버를 연결하는 버스가 1개일 경우 그대로 요청을 보내고 응답받는 형식으로 간단하게 통신할 수 있음
<img src="https://github.com/fsm12/Dev-Book/assets/74345771/53fe5782-19e0-47d1-81e6-60bd2f7f2197" width=350px alt="단일 클라이언트-서버 통신 방법">

하지만, 중간에 지나가야할 노드가 많은 경우 효율적인 통신을 위해선 누구에게 어떻게 보낼건지에 대한 특정 프로토콜(규약, 약속)이 필요함
<img src="https://github.com/fsm12/Dev-Book/assets/74345771/4344bb2a-31c8-4a01-9953-bc199ac6137b" width=350px alt="인터넷 상에서의 클라이언트-서버 통신 방법">


</br></br>

## IP (인터넷 프로토콜)
IP 프로토콜로 모든 노드에 **IP 주소**를 부여함

<img src="https://github.com/fsm12/Dev-Book/assets/74345771/abdf8c1c-1b1e-4acc-a12d-a9291ef3ea2b" width=350px alt="IP 주소를 가짐">

서로 통신할 때 IP 패킷에 **출발지IP, 목적지 IP, 메시지 내용 등** 의 정보를 담아서 보냄

|클라이언트 패킷 전달|서버 패킷 전달|
|:---:|:---:|
|<img src="https://github.com/fsm12/Dev-Book/assets/74345771/ef0fb9e3-b61b-487b-bd4a-47fece130aa8" width=350px alt="IP 주소를 가짐">|<img src="https://github.com/fsm12/Dev-Book/assets/74345771/6672f980-054c-4f68-971c-10eba06c575e" width=350px alt="IP 주소를 가짐">|

오고 가는 경로는 다를 수 있음

</br>

### IP 프로토콜의 한계
1. **비연결성** : **받을 대상**이 없거나 대상이 ***서비스 불능*** 상태여도 패킷이 전송됨
2. **비신뢰성** : 패킷이 가는 중에 ***사라지거나*** ***순서대로 도착***하지 않을 수 있음
3. **프로그램 구분** : 같은 IP를 사용한다면? 

</br></br>

## TCP, UDP

각 계층별로 애플리케이션 계층에서 생성된 전달 정보는 패킷에 담겨 순차적으로 **HTTP -> TCP -> IP -> Ethernet frame**이 덧씌워져 전달됨
<img src="https://github.com/fsm12/Dev-Book/assets/74345771/0425bde3-5583-4e86-bf5a-fb180ba2db71" width=1000px alt ="계층별 패킷 전달 예시 ">

### TCP의 특징
- 연결지향 O : TCP 3-way handshaking을 통한 가상연결
- 데이터 전달 보증 O : 잘 받았다는 응답을 전함
- 순서 보장 O : 후에 받아야할 패킷이 먼저 도착할 경우 폐기하고 다음 순서인 패킷을 보내달라 요청함

=> 신뢰할 수 있는 프로토콜로 현재는 대부분 TCP를 사용함

|분류|연결|해제|
|:--:|:--:|:--:|
|명명|TCP 3-way handshaking|TCP 4-way handshaking|
|흐름|<img src="https://github.com/fsm12/Dev-Book/assets/74345771/9d8cc0f4-4e59-4787-b2b7-a8d82a0f5292" width=430px alt ="TCP 3-way handshaking">|<img src="https://github.com/fsm12/Dev-Book/assets/74345771/b4a11535-92bd-424e-97a8-2664132cb403" width=430px alt ="TCP 4-way handshaking">|
|1|클라이언트나 서버 중 하나가 다른 쪽에</br>"동기화" 또는 SYN 플래그를 보내 연결 설정 시작</br>(연결을 생성하기 위해</br>클라이언트의 초기 시퀀스 번호가 서버로 전송됨)|연결의 한쪽(클라이언트 또는 서버)에서</br>FIN 플래그가 연결 종료 요청으로 전송| 
|2|SYN 플래그에 대한 응답으로</br>TCP 서버는 연결 설정을 위한 초기 시퀀스 번호와 함께</br>"승인" 또는 ACK 플래그를 보냄|FIN 플래그를 받은 사람이 상대방에게</br>닫기 요청에 대한 승인으로 ACK 플래그를 보냄| 
|3|ACK 플래그를 통해 클라이언트의 확인을 받은 후</br>서버의 SYN 플래그에 대한 응답을 보내면</br>연결 설정이 활성화|서버는 종료 신호로 FIN 플래그를 상대방에게 보냄| 
|4|x|최종 FIN 플래그를 수신한 TCP는</br>제안된 연결 종료에 대한 최종 승인으로</br>ACK 플래그를 보냄| 

</br></br>

### UDP의 특징
- 연결지향 X
- 데이터 전달 보증 X
- 순서 보장 X

=> 단순하고 빠르며, 기능을 추가하기 용이함

</br></br>

## PORT


</br></br>

## DNS


</br>
