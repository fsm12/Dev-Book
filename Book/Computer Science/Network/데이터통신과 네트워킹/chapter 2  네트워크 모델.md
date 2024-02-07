# Chapter 2: 네트워크 모델

</br>

## 1. 프로토콜 계층화
### 1) 시나리오
* ( Maria – Ann ) : Face-To-Face
* ( Maria – 편지(평문) – 편지봉투(암호문) – 배송 – 편지봉투(암호문) – 편지(평문) - Ann ) : 암호화, 복호화

### 2) 프로토콜 계층화의 원칙: 계층 대 계층 통신
1. if) 양방향 통신 => 각 계층이 각 방향으로 한가지씩, 상반되는 두 가지 작업을 수행할 수 있도록 만들어야 함
2. 양측의 각 계층에 있는 객체는 서로 같아야 함

### 3) 논리적 연결
각 계층에 그 계층에서 생성된 객체가 통과할 수 있는 논리적 연결이 있다고 생각할 것

</br>

## 2. TCP/IP 프로토콜 그룹
### 1) 계층적 구조
* Physical(하드웨어 장치), Data link(Network Interface), Internet, Transport, Application
   - 계층적 : 상위 계층 프로토콜은 1개 이상의 하위 계층 프로토콜로부터 제공되는 서비스들의 지원을 받는다는 의미
   - 모듈 ~= 장치
   - [그림 2.5 참조]

### 2) TCP/IP 프로토콜 그룹의 계층
* Network, Transport, Application : End to End => Internet
* Physical, Data Link : Hop to Hop (Hop = Host or Router) => Link
   - 최상위 계층(Network, Transport, Application)에서는 데이터가 Router or Switch에 의해 변하지 말아야 함
   - 아래 두 계층(Physical. Data Link)에서는 오로지 Router에서만 변함 (Router가 목적지 루트를 지정해줌)

### 3) 각 계층에 대한 설명
(PPT 3장 참조)


### 4) Encapsulation & Decapsulation
* Encapsulation: 통신을 할 때 제어와 주소 정보를 가지고 있는 헤더가 계층을 내려가며 데이터에 추가되는 것
* Decapsulation: 추가정보를 제거하고 수신지의 계층까지의 응용 데이터만을 내보내는 것

=> 발신지에서는 오로지 캡슐화만 목적지에서는 오로지 역 캡슐화만 이루어지는데, Router에서는 둘 다 이루어짐

### 5) 주소 지정	
![image](https://github.com/fsm12/Dev-Book/assets/74345771/71e64091-0b67-4182-8679-6df256bee700)


### 6) Multiplexing & Demultiplexing

</br>

## 3. OSI 모델
### 1) OSI(7계층) 대 TCP/IP(5계층)
* (TCP/IP의 Application Layer) = (OSI의 Session Layer, Presentation Layer, Application Layer) 

### 2) OSI 모델의 실패
1. TCP/IP 그룹에 많은 돈과 시간 투자되어 완성됨
2. OSI 모델의 일부 계층이 완전히 정의되지 않음
3. TCP/IP보다 충분히 높은 수준의 성능을 보여주지 못함
