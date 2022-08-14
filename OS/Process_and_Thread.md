<details>
<summary>  프로그램과 프로세스의 차이점은 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  - 프로그램: 작업을 위해 실행할 수 있는 파일의 단위를 의미하며, 저장장치에 저장되어 있는 정적인 상태를 말합니다. <br>
  - 프로세스: 메모리에 적재되어 CPU를 할당받아 실행 중인 프로그램을 의미하며, 실행을 위해 메모리에 올라온 동적인 상태를 말합니다.
</div>
</details>

<details>
<summary>  프로세스와 스레드의 차이점은 무엇인가요? </summary>
<div markdown="1">
  <br>
  프로세스는 컴퓨터에서 실행되고 있는 프로그램이고, 스레드는 프로세스 코드 절차에 따라 CPU에 작업 요청을 하는 프로세스의 실행 단위입니다. <br>
  프로세스와 달리 스레드는 코드, 데이터, 힙 영역을 통해 프로세스 자원을 공유할 수 있습니다. 프로세스와 달리 스레드는 자원을 공유하기 때문에 한 스레드에서 오류가 발생하면 같은 프로세스 내의 스레드 모두가 종료됩니다.
</div>
</details>

<details>
<summary>  PCB란 무엇인가요? </summary>
<div markdown="1">
  <br>
  프로세스 제어 블록이라고도 하며, 프로세스에 대한 메타데이터를 저장한 데이터입니다. <br>
</div>
</details>

<details>
<summary>  프로세스의 6가지 상태에 대해 설명해 주세요. </summary>
<div markdown="1">
  <br>
  
  - 생성(create) 상태 : PCB가 생성됩니다. <br>
  - 준비(ready) 상태 : 프로세스가 CPU를 얻을 때까지 기다리는 상태입니다. <br>
  - 실행(running) 상태 : CPU를 얻어 실제 작업을 실행하는 상태입니다. <br>
  - 대기 상태(waiting) : 입출력을 요구한 프로세스가 입출력이 완료될 때까지 기다리는 상태입니다. <br>
  - 중단 상태(blocked) : 어떤 이벤트가 발생한 이후 기다리며 프로세스가 차단된 상태입니다. <br>
  - 완료(terminated) 상태 : 실행 중인 프로세스가 작업을 마쳐 PCB가 사라진 상태입니다.
</div>
</details>

<details>
<summary>  프로세스가 도중에 중지되는 경우, 그 원인과 다시 실행할 수 있는 방법은 무엇일까요? </summary>
<div markdown="1">
  <br>
  
  - 원인 : 인터럽트 혹은 시스템 콜 등에 의해 프로세스가 중지될 수 있습니다. <br>
  - 다시 실행할 수 있는 방법 : PCB 안에 해당 프로세스의 정보(프로그램카운터와 같은 실행 정보 등)가 저장되어 있기 때문에 추후에 실행 가능한 상태가 되면 PCB를 통해 다시 실행할 수 있습니다.
</div>
</details>

<details>
<summary>  프로세스의 메모리 구조는 어떻게 구성되어 있습니까? </summary>
<div markdown="1">
  <br>
  동적인 스택과 힙, 그리고 데이터 영역과 코드 영역으로 구성되어 있습니다. <br>
  스택에는 지역변수, 매개변수, 함수가 저장되고 <br>
  데이터 영역에는 전역변수, 정적변수가 저장되며 BSS 영역과 Data 영역으로 나뉩니다.
</div>
</details>

<details>
<summary>  문맥교환 즉, 컨텍스트 스위칭(Context Switching)이란 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  CPU를 차지하던 프로세스가 나가고 새로운 프로세스를 받아들이는 작업을 말합니다. PCB, 프로세스 컨트롤 블록이 교환됩니다. <br>
  실행상태에서 나가는 PCB에 지금까지의 작업내용을 저장하고, 실행 상태로 들어오는 PCB의 내용으로 CPU가 다시 세팅됩니다. <br>
  
  - 컨텍스트 스위칭이 일어날 때 유휴 시간(idle time) 발생
  - 컨텍스트 스위칭에 드는 비용이 캐시 미스
</div>
</details>

<details>
<summary>  Inter Process Communication (IPC)란 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  Inter Process Communication으로, 독립적인 프로세스끼리 데이터를 주고받고 공유 데이터를 관리하는 메커니즘을 뜻합니다.
</div>
</details>

<details>
<summary>  교착상태(deadlock)의 개념과 원인에 대해 말해주세요. </summary>
<div markdown="1">
  <br>
  
  두 개 이상의 프로세스들이 서로가 가진 자원을 기다리며 중단된 상태입니다. <br>
  원인으로는 상호배제, 비선점, 점유대기, 환형대기가 있습니다.<br>
  
  - 상호배제 : 한 프로세스가 자원을 독점하고 있으며 다른 프로세스들은 접근하지 못하는 상태
  - 비선점 : 다른 프로세스의 자원을 강제적으로 가져오려는 상태(빼앗을 수 없음)
  - 점유대기 : 한 프로세스가 자원을 점유하고 있으면서 다른 자원을 기다리는 상태
  - 환형대기(원형대기) : 2개의 프로세스가 서로의 자원을 요구하는 상태
</div>
</details>

<details>
<summary>  스택을 스레드마다 독립적으로 할당하는 이유가 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  각 스레드가 독립적인 실행 흐름을 갖기 위해서는 독립적인 함수 호출이 보장되어야 하기 때문입니다.
</div>
</details>

<details>
<summary>  fork()와 exec()에 대해 설명해보세요. </summary>
<div markdown="1">
  <br>
  
  - fork() 시스템 호출을 하면 PCB를 포함한 부모 프로세스 영역의 대부분이 자식 프로세스에 복사되어 똑같은 프로세스가 만들어집니다. 
  - exec() 시스템호출은 프로세스는 그대로 둔 채 내용만 바꾸는 시스템 호출입니다. 현재의 프로세스가 완전히 다른 프로세스로 전환됩니다. 
</div>
</details>

<details>
<summary>  공유자원이란 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  각 프로세스, 스레드가 함께 이용할 수 있는 모니터, 프린터, 메모리, 파일, 변수, 데이터 등의 자원이나 변수 등을 의미합니다.
</div>
</details>
<details>
<summary>  임계영역(critical section)이란 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  공유 자원에 접근하는 순서에 따라 결과가 달라지는 영역입니다.
</div>
</details>
<details>
<summary>  세마포어란 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  간단한 정수 값과 두가지 함수 wait()/P(), signal()/V()로 공유자원에 대한 접근을 처리합니다.<br>
  (임계구역에 진입하기 전에 사용 중으로 놓고 임계구역에 들어갑니다. 이후에 도착하는 프로세스는 앞의 프로세스가 작업을 마칠 때까지 기다립니다. 프로세스가 작업을 마치면 세마포어는 다음 프로세스에 임계구역을 사용하라는 동기화 신호를 보냅니다. )
  
</div>
</details>





