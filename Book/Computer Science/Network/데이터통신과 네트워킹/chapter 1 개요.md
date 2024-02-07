# chapter 1  개요

	1. 데이터 통신
	    * 데이터 : 사용자 간의 합의된 형태로 표현된 정보
	    * 데이터 통신 : 특정 형태의 전송 매체를 통해 두 장치 간에 데이터를 교환하는 것
 
	    * 효과적인 데이터 통신 시스템의 기본특성 : delivery, accuracy, timeliness, jitter
		1) 구성요소 (5) = Message, Sender, Receiver, medium, protocol
		2) 데이터 표현 (5) = 문자, 숫자, 화상, 음성(오디오), 동영상
		3) 데이터 흐름 방향 (3) = simplex mode, half-duplex mode, full-duplex mode


	2. 네트워크 : 전송 매체 링크로 서로 연결된 장치의 모임
	    * Router : 네트워크와 다른 네트워크를 연결하는 장치
	    * Switch : 장치들을 서로 연결하는 장치, 한쪽 링크에서 다른 쪽 링크로 데이터를 Forwarding 함
	    * Modem : modulation + demodulation, 데이터의 형태를 변경하는 장치

		1) 네트워크 평가 기준 (3) = Performance (evaluated by throughput & delay), Reliability, Security 
		2) 물리적 구조 
		    * 연결 유형 (2) = Point-to-point connection, Multi-point(Multi-drop)	
		    * 물리적 접속형태(Topology) (5) = Mesh, Star(Hub), Bus(Tap), Ring(Repeater)
                                                      , Hybrid(Star + Bus)


	3, 네트워크 유형
		1) LAN (Local Area Network) : Host들을 상호연결(1km 이내), 사용자가 소유, 빠름
		+) MAN (Metropolitan Area Network) : 대도시(수십 ~ 수백 km)
		2) WAN (Wide Area Network) : 연결장치들을 상호연결, 사용자에게 임대, 거리 제한 x
		   * WAN의 종류(2) : Point-to-point WAN, Switched WAN
		3) Switching (2) : Circuit-switched network (Switch), Packet-switched network (Router)
		4) Internet : internet(=서로 통신할 수 있는 두 개 이상의 네트워크)의 한 종류
		5) 인터넷 접속


	4. 인터넷 역사 (생략) => ppt 보고 암기
		1) 초기의 역사
		2) 인터넷의 탄생
		3) 오늘의 인터넷


	5. 표준과 관리조직
	  * Protocol : 통신을 통제하기 위한 규칙을 모아놓은 것 (통신규약)
	  * Protocol의 주요 요소 (3) : Syntax(구조/형식), Semantics(비트의 의미), Timing(전송 시기, 속도)

		1) 인터넷 표준 : 인터넷을 이용하여 작업하는 사람들에 해 완전한 시험을 거쳐 사용되는 규격
		   * Standard (4) : de Facto standard, de Jure standard, Proposed standard, Draft standard

		+) 표준기구
		    * Standard Creation Committee(표준 제정 위원회)
		       = ISO, ITU-T, ANSI, IEEE, EIA, TTA
		    * Forum(협의회)
		    * Regulatory Agency(법규 기관)

		2) 인터넷 관리
		  = ISOC, IAB, IETF, IRTF [그림 1.17 삽입]
