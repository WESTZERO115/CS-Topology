## 목차
1) [시스템 구성 정보](#-시스템-구성-정보)
2) [프로세스 정보들](#-프로세스-정보들)
3) [Load average와 시스템 부하](#-load-average와-시스템-부하)
4) [free 명령어](#-free-명령어)
5) [swap](#-swap)
---

## 📎 시스템 구성 정보

`커널` `CPU` `메모리` `디스크` `네트워크정보`
<details>
<summary> <b>01. 알아야 하는 이유</b> </summary>
<div markdown="1">
 <br>
  시스템의 문제를 분석하고 확인하려면 현재 시스템의 구성 정보를 알아야 하는 것은 당연한 일입니다.<br>
   현재 사용 중인 커널 버전과 부팅 시 사용한 커널, 파라미터 그리고 하드웨어인 CPU와 메모리는 어떤 것을 사용하는지 등의 정보를 알아야 <br>알려진 커널 버그는 없는지, 하드웨어에 문제는 없는지 확인 가능하기 때문입니다.<br>
   서버에서 발생하는 이슈가 특정 하드웨어의 특정 펌웨어 버전 때문일 수도 있기 때문에 가장 먼저 하드웨어의 정보를 수집할 수 있어야 합니다.<br>
  CPU, 메모리, 디스크, 네트워크 카드 등은 서버를 이루는 중요한 리소스들이며 각각의 정보를 파악하는 것이 해결의 첫 번째 단계임을 명심해야 합니다.
</div>
</details>

<details>
<summary> <b>02. 중요 개념</b> </summary>
<div markdown="1">
  <br>
  
1) 바이오스(BIOS; Basic Input/Output System)란? <br>
[바이오스](https://terms.naver.com/entry.naver?docId=1169989&cid=40942&categoryId=32830)는 운영 체제 중 가장 기본적인 소프트웨어이자 컴퓨터의 입출력을 처리하는 펌웨어입니다.<br>
  쉽게 말해 컴퓨터에서 전원을 켜면 맨 처음 컴퓨터의 제어를 맡아, 가장 기본적인 기능을 처리해 주는 프로그램입니다.
2) 소켓과 코어 구분하기 <br>
소켓은 물리적인 CPU의 개수를 의미하고, 코어는 물리적인 CPU 안에 몇 개의 컴퓨팅 코어가 있는지를 의미합니다. <br>
3) Physical Memory Array & Memory Device <br>
메모리는 크게 Physical Memory Array 와 Memory Device 두 영역으로 나눌 수 있습니다. <br>
    - Physical Memory Array는 하나의 CPU 소켓에 함께 할당된 물리 메모리 그룹을 의미합니다. NUMA에서 각각의 CPU가 사용할 수 있는 로컬 메모리 개념에서 시작합니다. 시스템에 2개의 CPU 소켓이 있다면, Physical Memory Array도 2개입니다. 
    - Memory Device는 실제로 시스템에 꽂혀 있는 메모리를 의미하며, 메모리의 용량이 얼마인지 확인 가능합니다.
4) SCSI, IDE <br>
시스템이 디스크와 통신하기 위해 사용하는 방법 중 하나인 컨트롤러 부품의 타입입니다. <br>
    - IDE : 개인용 컴퓨터를 위한 방식 
    - SCSI : 서버용 컴퓨터를 위한 방식. 더 많은 장치를 연결할 수 있어서 확장성이 좋고 더 빠른 접근 속도를 제공합니다.
5) sda, vda, hda <br>
    - hda : IDE 방식의 디스크
    - sda : SCSI 방식의 디스크와 최근에 나오는 SATA, SAS와 같은 일반적인 하드 디스크
    - vda : 가상 서버에서 흔히 볼 수 있는 디스크 타입입니다. XEN, KVM과 같이 하이퍼바이저 위에서 동작 중인 서버들에서 주로 볼 수 있습니다.
</div>
</details>

<details>
  <summary><b>03. Commands</b> </summary>
<div markdown="1">
 <br>
  
  - uname -a
  - dmesg | grep -i kernel | more
  - cat /proc/cmdline
  
```none
dmesg를 이용해 확인하는 커널 정보 외에 현재 사용 중인 커널의 컴파일 옵션도 확인해야 할 필요가 있습니다. 
커널의 기능 중 컴파일 옵션에 포함되어야만 사용할 수 있는 기능들이 있기 때문입니다. 
```
  
  - cat /proc/boot/config-&#96;uname -r&#96;  | more
  - dmidecode -t {bios | system | processor | memory}
```none
장비의 모델명은 어떤 제조사에서 만들었느냐만큼 중요한 정보입니다. 모델명을 통해 해당 장비가 어느 정도의 성능을 낼 수 있는지 확인할 수 있기 때문입니다.
```

```none
# dmidecode -t system | grep -i size:
# free -m
위 각각의 명령어에서 확인한 전체 메모리 크기가 다르다면 시스템의 메모리 인식에 문제가 있는 것입니다.
```
  - cat /proc/cpuinfo
  - lscpu
```none
/dev/sda는 Logical Volume 즉, RAID 컨트롤러를 통해서 만들어진 논리적 볼륨이며 실제 물리적 디스크의 정보까지는 확인할 수 없습니다. 
이 때 smartctl 옵션을 잘 사용하면 실제 물리적 디스크의 정보까지 확인할 수 있습니다.
```
  - df -h
  - smartctl -a /dev/sda -d cciss, 0
```none
하드웨어적 이슈를 확인할 때 네트워크 카드 정보는 유용하게 사용됩니다. 간혹 특정 모델에서 버그나 이슈 등이 보고될 때 자신의 서버가 해당되는지 파악해야 하며, 
커널 드라이버를 업데이트할 때도 해당하는 펌웨어 드라이버를 정확하게 찾기 위해서입니다.
```
  - lspci
  - lspci | grep -i ether
```none
ethtool 명령어를 통해 해당 네트워크 카드가
1. 어느 정도의 속도까지 지원이 가능한지
2. 현재 연결되어 있는 속도는 얼마인지
3. 네트워크 연결은 정상적인지를 확인할 수 있습니다.
특히 서버가 의도했던 것만큼 속도가 나오지 않을 때 2번(Speed)은 가장 먼저 살펴보아야 할 항목입니다.
서버가 연결한 네트워크 케이블이 불량이거나, 연결할 때의 옵션이 잘못되어 있으면 속도가 원하는 만큼 설정이 되지 않을 수 있습니다.
+ 추가적으로 ethtool을 통해 네트워크 카드의 여러 세팅 정보도 확인 가능합니다. 시스템의 성능에 중요한 옵션인 -g,-G,-k,-K,-i를 알아두면 좋습니다.
```
  - ethtool eth0  
  - ethtool -g eth0
  - ethtool -G eth0 rx 255
  - ethtool -k eth0
</div>
</details>

## 📎 프로세스 정보들
`시스템의 상태` `VIRT & RES & SHR` `Memory Commit` `프로세스 상태(D,S)` `프로세스 우선순위(PR,NI)`
<details>
<summary> <b>01. 알아야 하는 이유</b> </summary>
<div markdown="1">
  <br>
 
  리눅스에는 시스템의 상태를 살펴볼 수 있는 다양한 명령들이 있습니다. <br>
그리고 top 명령은 시스템의 상태를 전반적으로 가장 빠르게 파악할 수 있는 방법 중 하나입니다. (프로세스, CPU, 메모리, swap 등등)
</div>
</details>

<details>
<summary> <b>02. 중요 개념</b> </summary>
<div markdown="1">
  <br>
 
  1) VIRT, RES, SHR이란? <br>
현재 프로세스가 사용하고 있는 메모리와 관련된 값입니다.
   - VIRT : task(프로세스)가 사용하고 있는 가상 메모리의 전체 용량. 실제로는 할당되지 않습니다.
   - RES : task가 사용하고 있는 물리 메모리의 양. 즉 실제 메모리에 올려서 사용하고 있는 물리 메모리 크기를 말합니다.
   - SHR : 다른 프로세스와 공유하고 있는 shared memory의 양. glibc 라이브러리가 대표적입니다.
<img width="380" height="280" alt="image" src="https://user-images.githubusercontent.com/65750746/193470862-c86d8bad-4947-4ac8-9959-ed1cf349e6aa.png">

2) Memory Commit <br>
 VIRT로 표현되는 가상 메모리는 프로세스가 커널로부터 사용을 예약받은 메모리라고 생각할 수 있습니다.<br>
프로세스는 malloc()과 같은 시스템 콜로 자신이 필요로 하는 메모리의 영역을 할당해 줄 것을 요청합니다. 이에 대해 커널은 가용한 공간이 있다면 성공 메시지와 함께 해당 프로세스가 사용할 수 있도록 가상의 메모리 주소를 전달해 줍니다. 그러나 이때에도 물리 메모리에 해당 영역이 할당된 것은 아닙니다. <br>
이런 동작 방식을 Memory Commit이라고 하며, vm.overcommit_memory 커널 파라미터를 통해 동작 방식을 정의할 수 있습니다.<br>
--> 정리하면, [ **Memory Commit이란 프로세스가 커널에 필요한 만큼의 메모리 요청 시 커널이 프로세스에 사용 가능한 메모리 영역을 주고 실제로 할당은 하지 않지만 해당 영역을 프로세스에 주었다는 것을 저장해 두는 일련의 과정** ]을 말합니다. <br>
그 후 프로세스가 할당받은 메모리 영역에 실제로 쓰기 작업을 하면 페이지 폴트(page fault)가 발생하며, 그제서야 커널은 실제 물리메모리에 프로세스의 가상 메모리 공간을 매핑합니다. 이것은 Page Table이라 불리는 커널의 전역 변수로 관리됩니다. 그리고 이렇게 물리 메모리에 바인딩된 영역이 RES로 계산됩니다.
 
3) Memory Commit을 사용하는 이유<br>
여러 이유가 있지만 가장 큰 이유는 fork()와 같은 새로운 프로세스를 만들기 위한 콜을 처리해야 하기 때문입니다.<br>
fork() 시스템 콜을 사용하면 커널은 현재 실행 중인 프로세스와 똑같은 프로세스를 하나 더 만들게 되는데, 대부분 fork() -> exec()
시스템 콜을 통해 전혀 다른 프로세스로 변합니다. 따라서 이때 확보한 메모리 영역이 대부분 쓸모 없어질 수 있습니다.<br>
그래서 COW(Copy-On-Write)기법을 통해 복사된 메모리 영역에 실제 쓰기 작업이 발생한 후에야 실질적인 메모리 할당을 시작합니다. 이 작업들을 지원하고 COW 기술을 사용하기 위해 Memory Commit이 필요합니다. 
여러 이유가 있지만 가장 큰 이유는 fork()와 같은 새로운 프로세스를 만들기 위한 콜을 처리해야 하기 때문입니다.<br>

4) 프로세스의 상태
  - R : Running 
  - D : UnInterruptable sleep
  - S : Interruptable sleep
  - T : Traced or stopped
  - Z : Zombie
D와 S 상태의 차이는 요청한 리소스를 즉시 사용할 수 있는지 여부입니다.<br>
S상태의 프로세스가 많은 것이 시스템에 큰 영향을 끼치지 않지만, D상태의 프로세스가 많다면 특정 요청이 끝나기를 기다리는 프로세스가 많다는 뜻이고, 이 프로세스들은 요청이 끝나면 R 상태로 돌아가야 하기 때문에 시스템의 부하를 계산하는 데 포함됩니다.
 
5) 프로세스의 우선순위<br>
PR은 우선순위이고, nice 값이라고 부르는 NI를 통해 우선순위를 조절합니다. 우선 순위를 조절할 때에는 늘 CPU Core의 수를 고려해야 합니다.
</div>
</details>

<details>
<summary> <b>03. Commands</b> </summary>
<div markdown="1">
  <br>
 
  - top -b -n 1
```none
-b : 순간의 top 정보를 확인하기 위한 옵션
옵션 없이 입력하면 주어진 Interval 간격(기본 3초)으로 화면을 갱신하면서 정보를 보여줍니다.
출력 결과 Tasks로 표현되는 부분이 바로 프로세스의 수와 관련된 정보입니다.

VIRT는 실제로 할당되지 않은 가상의 공간이기 때문에 해당 값이 크다고 해도 문제가 되지 않습니다. 
실제 사용하고 있는 메모리는 RES 영역이기 때문에 메모리 점유율이 높은 프로세스를 찾기 위해서는 RES 영역이 높은 프로세스를 찾아야 합니다.
```
</div>
</details>

## 📎 Load average와 시스템 부하
<details>
<summary> Commands </summary>
<div markdown="1">
  <br>
 
  - uptime
  - strace
  - cat /proc/loadavg
  - vmstat
  - cat /proc/sched_debug
</div>
</details>

## 📎 free 명령어

## 📎 swap
