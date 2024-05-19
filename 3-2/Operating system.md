## Chapter 1: Introduction

#### *==Objectives==*
- 컴퓨터 시스템의 기본 구성을 설명한다
- 운영체제의 주요 구성 요소에 대한 그랜드 투어를 제공한다
- 다양한 유형의 컴퓨팅 환경에 대한 개요를 제공한다
- 여러 오픈 소스 운영체제를 탐구하자

#### *==What Operating Systems Do==*

==운영체제란 무엇인가==
- 컴퓨터  사용자와 컴퓨터 하드웨어 간의 중개 역할을 하는 프로그램

==운영 체제 목표==
1. 사용자 프로그램을 실행하고 사용자 문제를 더 쉽게 해결한다
2. 컴퓨터 시스템을 편리하게 사용할 수 있도록 한다
3. 컴퓨터 하드웨어를 효율적으로 사용한다

==Computer System Structure==
컴퓨터 시스템은 다음과 같은 네 가지 구성 요소로 나눌 수 있다
- 하드웨어 - 기본적인 컴퓨팅 리소스 제공
	-> CPU, 메모리, I/O 장치
- 운영체제 - 다양한 애플리케이션 및  사용자 간의 하드웨어 사용 제어 및 조정
- 응용 프로그램 - 시스템 리소스를 사용하여 사용자의 컴퓨팅 문제를 해결하는 방법을 정의
	-> 워드 프로세서, 컴파일러, 웹 브라우저, 데이터베이스, 비디오게임
- 사용자
	-> 사람, 기계, 기타 컴퓨터

![[Pasted image 20240317184838.png]]

==What Operating Systems Do==
- 시점에 따라 다름  
- 사용자는 편리함, 사용 편의성 및 우수한 성능을 원함
- 리소스 활용에 신경 쓰지 않음  
- 그러나 메인프레임이나 미니컴퓨터와 같은 공유 컴퓨터는 모든 사용자를 행복하게 유지해야 함
- 워크스테이션과 같은 전용 시스템의 사용자는 전용 리소스가 있지만 서버의 공유 리소스를 자주 사용 
- 휴대용 컴퓨터는 리소스가 부족하고 사용성과 배터리 수명에 최적화되어 있음
- 장치나 자동차에 내장된 컴퓨터와 같이 사용자 인터페이스가 거의 없거나 전혀 없는 컴퓨터도 있음

==Operating System Definition==
1. OS is a resource allocator (리소스 할당자)
	-  모든 리소스를 관리한다
	-  효율적이고 공정한 리소스 사용에 대한 상반된 요청간에 결정
2. OS is a control program (제어 프로그램)
	- 프로그램의 실행을 제어하여 오류 및 컴퓨터의 부적절한 사용을 방지한다
3. 보편적으로 인정되는 정의는 없다
4. "운영체제를 주문할 때 공급자가 배송하는 모든 것"이 적절한 근사치 (하지만 천차만별)
5. "컴퓨터에서 항상 실행되는 유일한 프로그램"은 kernel 이다.
6. 다른 모든 것
	- 시스템 프로그램 또는 응용 프로그램

==Computer Startup==
- 부트스트랩 프로그램은 전원을 켜거나 재부팅할 때 로드된다
	1. 일반적으로 펌웨어로 알려진 ROM 또는 EPROM에 저장된다
	2. 시스템의 모든 측면을 초기화한다
	3. 운영 체제 커널을 로드하고 실행을 시작한다

#### *==Computer-System Organization==*

==Computer System Organization (컴퓨터 시스템 조직)==
![[Pasted image 20240317190211.png]]
- 컴퓨터 시스템 운영
	1. 공유 메모리에 대한 엑세스를 제공하는 하나 이상의 CPU, 장치 컨트롤러가 공통 버스를 통해 연결된다
	2. 메모리 사이클을 위해 경쟁하는 CPU와 디바이스의 동시 실행

==Computer-System Operation (컴퓨터 시스템 운영)==
- I/O 장치와 CPU가 동시에 실행할 수 있다
- 각 장치 컨트롤러는 특정 장치 유형을 담당한다 
- 각 장치 컨트롤러에는 로컬 버퍼가 있다
- CPU가 데이터를 메인 메모리에서 로컬 버퍼로 이동한다  
- I/O는 장치에서 컨트롤러의 로컬 버퍼로 이동한다
- 장치 컨트롤러가 CPU에 인터럽트를 발생시켜 동작을 완료했음을 알린다

==Common Functions of Interrupts (인터럽트의 공통 기능)==
- 인터럽트는 일반적으로 인터럽트 벡터를 통해 모든 서비스 루틴의 주소를 포함하는 인터럽트 서비스 루틴에 제어권을 전달한다
- 인터럽트 아키텍처는 인터럽트된 명령의 주소를 저장해야 한다  
- 트랩 또는 예외는 오류 또는 사용자 요청으로 인해 발생하는 소프트웨어에서 생성된 인터럽트이다
- 운영 체제가 인터럽트 구동된다

==Interrupt Handling (인터럽트 처리)==
- 운영체제는 레지스터와 프로그램 카운터를 저장하여 CPU의 상태를 보존한다
- 발생한 인터럽트 유형을 결정한다:  
	1. polling
	2. vectored interrupt system (벡터형 인터럽트 시스템 ) 
- 각 인터럽트 유형에 대해 어떤 조치를 취해야 하는지를 결정하는 코드 세그먼트가 따로 있다

==Interrupt Timeline==
![[Pasted image 20240317190634.png]]

==I/O Structure==
- I/O가 시작되면 I/O 완료 시에만 사용자 프로그램으로 컨트롤이 돌아간다  
	1. 다음 인터럽트가 발생할 때까지 CPU를 대기한다
	2. 대기 루프(메모리 액세스를 위한 경쟁)  
	3. 최대 한 번에 하나의 I/O 요청이 미결 상태이며 동시 I/O 처리가 없다
- I/O가 시작된 후, 제어가 I/O 완료를 기다리지 않고 사용자 프로그램으로 돌아간다
	1. System call(시스템 호출) – 사용자가 I/O 완료를 기다릴 수 있도록 OS에 요청 
	2. Device-Status Table 에는 각 I/O 장치의 유형, 주소 및 상태를 나타내는 항목이 포함되어 있다 
	3. 디바이스 상태를 결정하고 인터럽트를 포함하도록 테이블 항목을 수정하기 위해 I/O 디바이스 테이블로 OS 인덱스

==Storage Definitions and Notation Review (스토리지 정의 및 표기법 검토)==

```
컴퓨터 저장의 기본 단위는 비트입니다. 비트는 0과 1 두 가지 값 중 하나를 포함할 수 있습니다. 컴퓨터에 있는 다른 모든 저장은 비트 모음을 기반으로 합니다. 비트 수가 충분하다면 컴퓨터가 숫자, 문자, 이미지, 영화, 소리, 문서, 프로그램 등 몇 가지를 표현할 수 있는지 놀랍습니다. 바이트는 8비트이며 대부분의 컴퓨터에서 가장 작은 편리한 저장 청크입니다. 예를 들어, 대부분의 컴퓨터에는 비트를 이동하라는 명령이 없지만 바이트를 이동하라는 명령이 있습니다. 덜 일반적인 용어는 단어로, 주어진 컴퓨터 아키텍처의 고유 데이터 단위입니다. 단어는 하나 또는 그 이상의 바이트로 구성됩니다. 예를 들어, 64비트 레지스터와 64비트 메모리 주소 지정을 가진 컴퓨터에는 일반적으로 64비트(8바이트) 워드가 있습니다. 컴퓨터는 한 번에 바이트가 아니라 고유 워드 크기로 많은 작업을 실행합니다.

컴퓨터 스토리지는 대부분의 컴퓨터 처리량과 함께 일반적으로 바이트 및 바이트 모음으로 측정되고 조작됩니다.

A kilobyte, or KB, is 1,024 bytes

a megabyte, or MB, is 1,024'2 bytes

a gigabyte, or GB, is 1,024'3 bytes

a terabyte, or TB, is 1,024'4 bytes

a petabyte, or PB, is 1,024'5 bytes

컴퓨터 제조업체들은 종종 이 숫자들을 반올림하여 1메가바이트는 100만 바이트, 1기가바이트는 10억 바이트라고 말합니다. 네트워킹 측정은 비트 단위로 주어지는데, 이는 네트워크가 한 번에 데이터를 조금씩 이동시키기 때문입니다.
```

==Storage Structure==
- 메인 메모리 – CPU가 직접 액세스할 수 있는 대용량 스토리지 미디어만 제공  
	1. Random access  
	2. Typically volatile (일반적으로 휘발성)
- 보조 스토리지 – 대용량 nonvolatile(비휘발성) 스토리지를 제공하는 메인 메모리 확장  
- 하드 디스크 – 자기 기록 재료로 덮인 단단한 금속 또는 유리 플래터  
	1. 디스크 표면은 논리적으로 트랙으로 나뉘며 섹터로 세분화됨
	2. 디스크 컨트롤러는 장치와 컴퓨터 사이의 논리적 상호작용을 결정함
- Solid-state disks – 하드 디스크보다 빠른 비휘발성  
	1. 각종 기술  
	2. 더욱 인기를 얻고 있음

==Storage Hierarchy (스토리지 계층)==
- 계층별로 구성된 스토리지 시스템  
	1. Speed  
	2. Cost
	3. Volatility(변동성)  
- Caching – 더 빠른 스토리지 시스템으로 정보 복사, 주 메모리를 보조 스토리지용 캐시로 볼 수 있음
- Device Driver - 각 장치 컨트롤러가 I/O를 관리하기 위한
	1. 컨트롤러와 커널 간의 균일한 인터페이스를 제공

![[Pasted image 20240317191645.png]]

==Caching==
- 컴퓨터의 여러 수준에서 수행되는 중요한 원리(하드웨어, 운영 체제, 소프트웨어)  
- 사용 중인 정보가 더 느린 스토리지에서 더 빠른 스토리지로 일시적으로 복사됨  
- 정보가 있는지 확인하기 위해 먼저 빠른 스토리지(캐시) 확인  
	1. 그렇다면, 캐시에서 직접 사용하는 정보(빠른)  
	2. 그렇지 않은 경우 데이터를 캐시에 복사하여 캐시에 사용
- 캐시 중인 스토리지보다 작은 캐시  
	1. 캐시 관리 중요 설계 문제  
	2. 캐시 크기 및 교체 정책

==Direct Memory Access Structure (다이렉트 메모리 엑세스 구조)==
- 메모리 속도에 가까운 속도로 정보를 전송할 수 있는 고속 I/O 장치에 사용됨
- 장치 컨트롤러가 CPU 개입 없이 버퍼 스토리지의 데이터 블록을 메인 메모리로 직접 전송
- 바이트당 하나의 인터럽트가 아니라 블록당 하나의 인터럽트만 생성

==How a Modern Computer Works (현대 컴퓨터의 작동 원리)==
![[Pasted image 20240317191841.png]]
(폰노이만 구조)

#### *==Computer-System Architecture==*

==Computer-System Architecture==
- 대부분의 시스템은 단일 범용 프로세서를 사용
	1. 대부분의 시스템에는 특수 목적 프로세서도 있음  
- 사용 및 중요도가 증가하는 Multiprocessors 시스템  
	1. 병렬 시스템(parallel systems), 긴밀하게 결합된 시스템(tightly-coupled systems)으로도 알려져 있dma  
	2. 이점:  
		- 처리량 증가  
		- 규모의 경제  
		- 신뢰성 향상 – 우아한 성능 저하 또는 내결함성  
	3. 두 가지 유형:  
		- Asymmetric Multiprocessing(비대칭 다중 처리) – 각 프로세서에는 특정 작업이 할당됨
		-  Symmetric Multiprocessing(대칭 다중 처리) – 각 프로세서가 모든 작업을 수행함

==Symmetric Multiprocessing Architecture==
![[Pasted image 20240317192543.png]]

==A Dual-Core Design==
- Multi-chip and multicore
- 모든 칩을 포함하는 시스템
- 여러개의 개별 시스템이 포함된 Chassis

![[Pasted image 20240317192700.png]]

==Clustered Systems==
- 멀티프로세서 시스템처럼 여러 시스템이 함께 작동
	1. 일반적으로 SAN(Storage-Area Network)을 통해 스토리지를 공유
	2. 장애에도 끄떡없는 고가용성(high-availability) 서비스를 제공  
		- Asymmetric clustering은 핫 스탠바이 모드에서 시스템 하나를 사용
		- Symmetric clustering은 여러 노드가 애플리케이션을 실행하고 서로를 모니터링
	3. 일부 클러스터는 고성능 컴퓨팅(HPC)용
		- 병렬화(parallelization)를 사용하려면 응용 프로그램을 작성
	4. 일부는 충돌하는 작업을 피하기 위해 DLM(distributed lock manager)을 배포

![[Pasted image 20240317193004.png]]

#### *==Operating-System Structure==*

==Operating System Structure==
- 효율성을 위해 필요한 Multiprogramming(Batch system)  
	1. 단일 사용자가 CPU 및 I/O 장치를 항상 분주하게 유지할 수 없음  
	2. 멀티프로그래밍은 작업(코드 및 데이터)을 구성하므로 CPU는 항상 실행해야 할 작업이 하나 있음
	3. 시스템의 전체 작업의 하위 집합은 메모리에 저장됨  
	4. job scheduling통해 선택 및 실행되는 하나의 작업  
	5. (예를 들어) I/O를 기다려야 할 때 OS가 다른 작업으로 전환됨 
  
- Timesharing (multitasking)은 CPU가 작동 중에 사용자가 각 작업과 상호 작용할 수 있을 정도로 자주 작업을 전환하여 대화형 컴퓨팅을 만드는 논리적 확장이다  
	1. Response time은 1초 미만이어야 함
	2. 각 사용자는 메모리에서 실행되는 적어도 하나의 프로그램을 갖는다 ->   process
	3. 여러 작업을 동시에 실행할 준비가 된 경우 -> CPU 스케줄링  
	4. 프로세스가 메모리에 맞지 않으면, swapping을 통해 프로세스를 안팎으로 이동하여 실행할 수 있음
	5. Virtual memory를 사용하면 메모리에 완전히 저장되지 않은 프로세스를 실행할 수 있음

==Memory Layout for Multiprogrammed System==

![[Pasted image 20240317193527.png]]

#### *==Operating-System Operations==*

==Operating-System Operations (운영체제의 운영)==
- Interrupt driven - 인터럽트 구동(하드웨어 및 소프트웨어)  
	1. 장치 중 하나에 의한 하드웨어 인터럽트  
	2. 소프트웨어 인터럽트(exception or trap 예외 또는 트랩):  
		- 소프트웨어 오류(예: 0으로 나누는 것)  
		- 운영체제 서비스 요청  
		- 다른 프로세스 문제로는 무한 루프, 프로세스 상호 수정 또는 운영 체제가 있음
- Dual-mode 작동으로 OS가 자체 및 기타 시스템 구성 요소를 보호할 수 있음
	1. User mode and kernel mode
	2. 하드웨어에서 제공하는 Mode bit  
		- 시스템이 사용자 코드 또는 커널 코드를 실행하는 시점을 구분할 수 있는 기능을 제공
		- 커널 모드에서만 실행 가능한, 권한으로 지정된 일부 명령어  
		- 시스템 호출에서 커널로 모드 변경, 호출에서 사용자에게 반환 재설정  
- 점점 더 많은 CPU가 멀티 모드 작업을 지원함  
	1. 즉, 게스트 VM의 VMM(virtual machine manager) mode
#### *==Process Management==*
#### *==Memory Management==*
#### *==Storage Management==*
#### *==Protection and Security==*
#### *==Kernel Data Structures==*
#### *==Computing Environments==*
#### *==Open-Source Operating Systems==*

## Chapter 2: Operating-System Structures

## Chapter 3: Processes

## Chapter 4: Threads & Concurrency

## Chapter 5: CPU Scheduling

## Chapter 6: Synchronization Tools

**critical section 문제를 해결하는 법 3가지**
1. Mutual Exclusion - critical section에는 하나의 프로세스만 진입
2. Progress - 코드가 중단되지 않는것
3. Bounded Waiting

**동기화 하드웨어**
- 동기화를 위해선 atomic한 연산이 수행되어야 하는데 그것은 하드웨어가 지원함(cpu)

**test_and_set()은 bounded-waiting을 만족하진 못함**
- 왼쪽 프로세스만 계속 돌 수도 있음

**cmpare_and_swap()도 bounded-waiting을 만족하지 못함**

**bounded-waiting Mutual Exclusion with test_and_set**
- n은 프로세스의 개수
- j = (i + 1)%n -> 프로세스가 만약 5개고 i가 5이면 다음은 1로 만들어줌






























## Chapter 7: Synchronization Examples






**classical problems of synchronization**
- bounded-buffer problem
- readers and writers problem
- dining-philosophers problem