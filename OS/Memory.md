<details>
<summary>  가상 메모리(Virtual Memory)가 무엇이며, 사용하는 이유는? </summary>
<div markdown="1">
  <br>
  메모리 관리 기법의 하나로, 컴퓨터가 실제로 이용 가능한 메모리 자원을 추상화하여 이를 사용하는 사용자들에게 매우 큰 메모리로 보이게 만드는 것을 말합니다. 
어떤 프로레스를 실행할 때 프로세스 전체가 메모리에 적재되지 않고도 실행이 가능하도록 하는 기법입니다. 
</div>
</details>

<details>
<summary> 요구페이징(Demand Paging) 이란? </summary>
<div markdown="1">
  <br>
  가상메모리 관리 방법으로 실행하고자 하는 프로그램 전체를 메모리로 옮기지 않고 초기에 실행 프로세스에 필요한 것만 적재하는 전략을 말합니다.
</div>
</details>

<details>
<summary> Copy-on-Write(COW) 이란? </summary>
<div markdown="1">
  <br>
  folk()함수로 리소스가 복사되었을 때 복사본(자식프로세스)과 원본(부모프로세스)이 리소스를 공유하고, 복사본이 수정되었을 때만 새 리소스를 만드는 리소스 관리 기법입니다.
</div>
</details>

<details>
<summary> 커널(Kernel)이 무엇이며, 어떤 일을 하는가? </summary>
<div markdown="1">
  <br>
  커널은 운영 체제에 속해 있으며, 1)메모리를 할당하고 2)프로세스를 스케줄링하며 3)CPU를 제어하는 역할을 한다.
</div>
</details>

<details>
<summary> 시스템 콜(System call)이 무엇이며, 어떤 일을 하는가? </summary>
<div markdown="1">
  <br>
  시스템콜이란 운영체제가 커널에 접근하기 위한 인터페이스입니다. 
  유저 모드가 시스템 콜을 통해 커널 모드로 변환되어 실행되기 때문에 컴퓨터 자원에 대한 직접적인 접근을 차단할 수 있고, 프로그램을 다른 프로그램으로부터 보호할 수 있습니다.
</div>
</details>

<details>
<summary> 캐시(Cache) 란? </summary>
<div markdown="1">
  <br>
  데이터를 미리 복사해 놓는 임시 저장소이자 빠른 장치(RAM)와 느린 장치(CPU)에서 속도 차이에 따른 병목 현상을 줄이기 위한 메모리입니다.
</div>
</details>

<details>
<summary> 버퍼(Buffer) 란? </summary>
<div markdown="1">
  <br>
  주기억장치와 주변장치사이에서 임시목적으로 데이터를 보관해두기 위해 사용되는 메모리입니다. 
</div>
</details>
