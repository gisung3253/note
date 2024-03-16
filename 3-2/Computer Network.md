## Chapter 1. Introduction

#### *==Roadmap==*
- 인터넷이란?
- 프로토콜이란?
- Network Edge : 호스트, 엑세스 네트워크, 물리적 미디어
- Network core : 패킷/회로 스위칭, 인터넷 구조
- 성능 : 손실, 지연, 처리량 
- 보안
- 프로토콜 계층, 서비스 모델
- 기록


#### ==*what is the Internet?*==
The Internet : a "nuts and bolts" view

![[Pasted image 20240316191942.png]]
수십억개의 연결된 컴퓨터 장치
- hosts = end systems
- running network apps at Internet's "edge"

![[Pasted image 20240316191957.png]]
패킷 스위치 : 패킷 스위치는 네트워크에서 데이터를 전송하는 장치를 가리킨다. 이 장치들은 패킷(데이터의 작은 조각)을 받아서 목적지로 전달하는 역할을 한다.
- routers, switches

![[Pasted image 20240316192008.png]]
Communication links
- 섬유, 구리, 라디오, 위성
- 전송 속도 : bandwidth(대역폭)

![[Pasted image 20240316192016.png]]
Networks
- collection of devices, routers, links : 조직에 의해 관리된다.

![[Pasted image 20240316192054.png]]

Internet : "network of networks"
- 상호연결된 ISPS

프로토콜은 어디에나 있다
- 전송, 메세지 수신 제어
- 예 : HTTP (Web), 스트리밍 비디오, Skype, TCP, IP, WIFI, 4G, Ethernet

인터넷 표준
- RFC : Request for Comments
- IETF : Internet Enginnering Task Force

![[Pasted image 20240316193247.png]]

The Internet : a "service" view

애플리케이션에 서비스를 제공하는 Infrastructure
- 웹, 스트리밍 비디오, 멀티미디어 원격 회의, 이메일, 게임, 전자 상거래, 소셜 미디어, 상호 연결된 appliances ...

분산 어플리케이션에 대한 프로그래밍 인터페이스 제공
- "hooks"를 사용하여 인터넷 전송 서비스에 "connect" 할 수 있는 앱을 전송/수신 할 수 있다.
- 우편 서비스와 유사한 서비스를 제공

![[Pasted image 20240316193832.png]]






#### ==*What's protocol?*==

Human protocols
- "시간이 어떻게 됩니까?"
- "질문이 있습니다"
- 서론

... 발송된 특정 메세지
... 메세지 수신 시 수행되는 특정 작업 또는 기타 이벤트

Network protocols
- 인간과는 다른 컴퓨터 (devices)
- 프로토콜에 의해 관리되는 인터넷에서의 모든 통신 활동

```
프로토콜은 네트워크 엔티티 간에 주고 받는 메시지의 형식, 순서, msg 전송, 수신에 대한 조치를 정의한다
```

![[Pasted image 20240316194358.png]]



#### ==*Network edge: hosts, access network, physical media*==

==인터넷의 구조를 자세히 살펴보자==

![[Pasted image 20240316194702.png]]
Network edge
- hosts : clients and servers
- 종종 데이터 센터에 있는 서버

![[Pasted image 20240316194937.png]]
Access networks(접속망), physical media (물리적 미디어)
- 유선, 무선 통신 링크

![[Pasted image 20240316194953.png]]
Network core
- 상호 연결된 라우터
- 네트워크

==Access networks and physical media==

Q : 엔드 시스템을 엣지 라우터에 연결하는 방법은?
- 주거용 출입망
- 기관 접속망(학교, 회사)
- 모바일 엑세스 네트워크 (WiFi, 4G,/5G)

찾아볼 것들
- 액세스 네트워크의 전송 속도(비트/초)?
- 사용자 간의 공유 액세스 또는 전용 액세스?

==Access networks: cable-based access==

![[Pasted image 20240316195623.png]]
주파수 분할 다중화 (FDM) : 서로 다른 주파수 대역에서 전송되는 서로 다른 채널

![[Pasted image 20240316195747.png]]
HFC : 하이브리드 섬유 동출
- 비대칭 : 최대 40Mbps - 1.2Gbs 다운스트림 전송 속도, 30 - 100Mbps 업스트림 전송 속도

케이블, 파이버 네트워크는 ISP 라우터에 홈을 연결한다
- 가정에서는 케이블 headend에 액세스 네트워크를 공유한다

==Access networks: digital subscriber line (DSL)==

![[Pasted image 20240316200103.png]]
기존 전화선을 사용하여 중앙 사무실 DSLAM 으로 이동
- DSL 전화선을 통한 데이터는 인터넷으로 이동한다
- DSL 전화선을 통한 음성은 전화망으로 이동한다

24-52Mbps 다운스트림 전용 전송 속도
3.5-16Mbps 업스트림 전용 속도

==Access networks: home networks==

![[Pasted image 20240316211733.png]]

==Wireless access networks (무선접속망)==

공유 무선 엑세스 네트워크는 엔드 시스템을 라우터에 연결한다
- 기지국 또는 "access point"를 통해

![[Pasted image 20240316213044.png]]
무선 근거리 통신망 (WLAN)
- 일반적으로 건물 내 또는 건물 주변 (~100ft)
- 802.11b/g/n(WiFi): 11, 54, 450Mbps 전송 속도

![[Pasted image 20240316213055.png]]
광역 셀룰러 접속망
- 모바일, 셀룰러 네트워크 운영자 제공 (10's km)
- 10's Mbps
- 4G 셀룰러 네트워크 (5G 도래)

==Access networks: enterprise networks==

![[Pasted image 20240316213259.png]]
- 기업, 대학 등
- 유선, 무선 링크 기술의 혼합, 스위치와 라우터의 혼합 연결 (차이 사항은 이후에)
- 이더넷 : 100Mbps, 1Gbps, 10Gbps의 유선 엑세스
- WiFi : 11, 54, 450 Mbps의 무선 엑세스 포인트

==Host: sends packets of data (데이터 패킷을 보낸다) ==  

호스트 전송 기눙
![[Pasted image 20240316213522.png]]
- 응용프로그램 메시지를 받습니다
- 패킷이라고 알려진 길이 L비트의 더 작은 청크로 쪼개집니다
- 패킷을 전송 속도 R로 액세스 네트워크에 전송합니다
	- 링크 전송 속도, 링크 용량, 링크 대역폭

![[Pasted image 20240316213536.png]]

==Links: physical media==

bit : 송신기/수신기 사이의 전파
physical link : 송신기와 수신기 사이에 있는 것
guided media : 신호는 고체 매체에서 전파 된다
- 구리, 섬유, 동축
unguided media : 신호는 자유롭게 전파 된다
- 라디오

![[Pasted image 20240316213945.png]]
**Twisted pair (TP)**
절연 구리선 두 개
- Category 5 : 100 Mbps, 1 Gbps Ethernet
- Category 6 : 10 Gbps Ethernet

![[Pasted image 20240316214641.png]]
**동축 케이블**
동심동 도체 두 개
쌍방향
광대역
- 케이블의 여러 주파수 채널
- 채널당 100's Mbps

![[Pasted image 20240316214648.png]]
**광섬유 케이블**
가벼운 펄스를 운반하는 유리 섬유, 각각의 펄스는 약간씩
고속 작동
- 고속 점대점 전송 (10's-100's Gbps)
낮은 오류율
- 멀리 떨어진 중계기
- 전자파 소음에 영향을 받지 않는

**무선 라디오**
전자기 스펙트럼으로 전달되는 신호
물리적 "와이어" 없음
broadcast 및 "half-duplex"  (sender to receiver)
전파 환경 효과
- reflection
- 물건에 의한 방해
- 간섭

**무선 링크 유형**
지상파 전자레인지
- 최대 45Mbps 채널
무선랜
- 최대 100's Mbps
광역 (예: 셀룰러)
- 4G 셀룰러 : ~10's Mbps
위성
- 채널당 최대 45Mbps
- 270 msec 종단 지연
- geosynchronous versus lowearth-orbit

#### ==*Network core: packet/circuit switching, internet structure==*
