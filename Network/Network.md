## 네트워크의 기초
<details>
<summary> 네트워크란 무엇인가요? </summary>
<div markdown="1">
  <br>
 
  `노드`와 `링크`가 서로 연결되어 있거나 연결되어 있지 않은 집합체를 의미합니다.

  
</div>
</details>

<details>
<summary> 좋은 네트워크란 무엇인가요? </summary>
<div markdown="1">
  <br>
 
 `많은 처리량`을 처리할 수 있으며 `지연 시간이 짧고` `장애 빈도가 적으며` `좋은 보안`을 갖춘 네트워크를 말합니다.

  
</div>
</details>

<details>
<summary> 처리량(throughput)이란 무엇인가요? </summary>
<div markdown="1">
  <br>
 
 링크를 통해 전달되는 단위 시간 당 데이터양을 말합니다. 
 단위는 bps를 사용합니다. <br>
사용자들이 많이 접속할 때마다 커지는 트래픽, 네트워크 장치 간의 대역폭, 네트워크 중간에 발생하는 에러, 장치의 하드웨어 스펙에 영향을 받습니다. <br>
 
  
</div>
</details>

<details>
<summary> 대역폭(bandwidth)이란 무엇인가요? </summary>
<div markdown="1">
  <br>
 
 주어진 시간 동안 네트워크 연결을 통해 흐를 수 있는 최대 비트 수입니다.
  <br>
  <br>
 ![xmfo](https://user-images.githubusercontent.com/70850937/188811733-c1239fdf-3955-4d16-a416-f71d730815d4.png)

 
</div>
</details>

<details>
<summary> 지연 시간(latency)이란 무엇인가요? </summary>
<div markdown="1">
  <br>
 
 요청이 처리되는 시간을 말하며 어떤 메시지가 두 장치 사이를 왕복하는데 걸린 시간을 말합니다. <br>
매체 타입(무선,유선), 패킷 크기, 라우터의 패킷 처리 시간에 영향을 받습니다.
 
  
</div>
</details>

<details>
<summary> 네트워크의 구조라고도 불리는 토폴로지를 알아두어야 하는 이유는 무엇일까요? </summary>
<div markdown="1">
  <br>
 
토폴로지가 중요한 이유는 `병목 현상`을 찾을 때 중요한 기준이 되기 때문입니다. <br>
[ 트리, 버스, 스타, 링, 메시 ]
 
  
</div>
</details>

<details>
<summary> 버스 토폴로지에 대해 설명해 보세요. </summary>
<div markdown="1">
  <br>
 
중앙 통신 회선 하나에 여러 개의 노드가 연결되어 공유하는 네트워크 구성을 말하며 근거리 통신망에서 사용합니다. <br>
  설치 비용이 적고 신뢰성이 우수하며 중앙 통신 회선에 노드를 추가하거나 삭제하기 쉽습니다. 스푸핑이 가능하다는 문제점이 있습니다.
 
  
</div>
</details>

<details>
<summary> 병목 현상의 주된 원인은 무엇인가요? </summary>
<div markdown="1">
  <br>

- 서버 CPU, 메모리 사용량이 많을 때
- 비효율적인 네트워크 구성
- 네트워크 대역폭
- 네트워크 토폴로지
</div>
</details>


<details>
<summary> ping(Packet INternet Groper)이란 무엇입니까? </summary>
<div markdown="1">
  <br>

네트워크 상태를 확인하려는 대상 노드를 향해 일정 크기의 패킷을 전송하는 명령어입니다. <br>
해당 노드의 패킷 수신 상태와 도달하기까지의 시간, 해당 노드까지 네트워크가 잘 연결되어 있는지 확인 가능합니다. <br>
TCP/IP 프로토콜 중에 `ICMP 프로토콜`을 통해 동작하며, ICMP를 지원하지 않는 기기를 대상으로는 실행할 수 없습니다. 네트워크 정책상 ICMP나 traceroute를 차단하는 대상일 때도 사용 불가합니다.
</div>
</details>

<details>
<summary> netstat 명령어에 대해 설명해 보세요. </summary>
<div markdown="1">
  <br>

접속되어 있는 서비스들의 네트워크 상태를 표시합니다. <br>
네트워크 접속, 라우팅 테이블, 네트워크 프로토콜 등 리스트를 보여줍니다.
</div>
</details>

## TCP/IP 4계층 모델
<details>
<summary> OSI 7계층과 TCP/IP 4계층의 차이는 무엇인가요? </summary>
<div markdown="1">
  <br>

OSI 7계층은 TCP/IP 계층과 다르게 애플리케이션계층을 링크계층, 데이터링크계층, 물리계층으로 나눠서 설명하고, 인터넷계층을 네트워크 계층으로 부른다는 점이 다릅니다.
  
</div>
</details>


<details>
<summary> 가상회선 패킷 교환 방식과 데이터그램 패킷 교환 방식에 대해 설명해 보세요. </summary>
<div markdown="1">
  <br>

  - 가상회선 패킷 교환 방식 : 각 패킷에는 가상회선 식별자가 포함되며 모든 패킷을 전송하면 가상회선이 해제되고 패킷들은 `전송된 순서대로 도착`하는 방식입니다.
- 데이터그램 패킷 교환 방식 : 패킷이 독립적으로 이동하며 `최적의 경로를 선택`합니다. 하나의 메시지에서 분할된 여러 패킷은 `서로 다른 경로로 전송`될 수 있으며, `도착한 순서가 다를 수 있는 방식`입니다.
  

</div>
</details>

<details>
<summary> 3-way handshake과정을 상세히 설명해 보세요. </summary>
<div markdown="1">
  <br>
  
  <img width="800" height="400" src="https://user-images.githubusercontent.com/70850937/188816648-a4a77a43-9d7f-4b87-889a-ee747d354b2c.png"> <br>

  <br>
  

  1) `SYN` 단계 : 클라이언트는 서버에 클라이언트의 ISN을 담아 SYN을 보냅니다. ISN은 새로운 TCP 연결의 첫 번째 패킷에 할당된 임의의 시퀀스 번호를 말하며, 이는 장치마다 다를 수 있습니다.
  2) `SYN + ACK` 단계 : 서버는 클라이언트의 SYN을 수신하고, 서버의 ISN을 보내며 승인번호로 클라이언트의 ISN + 1을 보냅니다.
  3) `ACK` 단계 : 클라이언트는 서버의 ISN + 1한 값인 승인번호를 담아 ACK를 서버에 보냅니다.

  
</div>
</details>

<details>
<summary> TIME_WAIT이 무엇인지, 왜 필요한지 설명해 주세요. </summary>
<div markdown="1">
  <br>

TCP 연결 해제 과정에서 소켓이 바로 소멸되지 않고 일정 시간 유지되는 상태를 말합니다. <br>
지연 패킷이 발생할 경우를 대비하고 두 장치의 연결이 닫혔는지 확인하기 위해 필요합니다. <br>
CentOS와 우분투는 60초, 윈도우는 4분으로 설정되어 있으며 운영체제마다 조금씩 다를 수 있습니다.
  
</div>
</details>

## 네트워크 기기
<details>
<summary> L4스위치와 L7스위치의 공통점은 무엇이고, 차이점은 무엇인가요? </summary>
<div markdown="1">
  <br>

1. 차이점 <br>
L4스위치는 인터넷 계층을 처리하는 기기로 스트리밍 관련 서비스에서는 사용할 수 없으며 메시지는 인식하지 못하고 <br>
  `IP`와 `포트`(특히 포트)를 기반으로 트래픽을 분산합니다. <br>
반면 L7스위치(=로드밸런서)는 `IP`, `포트` 외에도 `URL`, `HTTP 헤더`, `쿠키` 등을 기반으로 트래픽을 분산합니다.

1. 공통점 <br>
둘 다 헬스 체크를 통해 정상적인 서버 또는 비정상적인 서버를 판별하는데, 헬스 체크는 전송 주기와 재전송 횟수 등을 설정한 이후 반복적으로 서버에 요청을 보내는 것을 말합니다.
  
</div>
</details>
