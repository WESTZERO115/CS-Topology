<details>
<summary> 메모리계층을 구성하는 요소들에 대해 설명해보세요(속도, 기억용량)  </summary>
<div markdown="1">
  <br>
  
  keyword: `휘발성`, `속도`, `기억 용량`
  - 레지스터 : CPU 안에 있는 작은 메모리로, 휘발성 있음, 속도가 가장 빠름, 기억용량이 가장 적습니다.
  - 캐시 : L1, L2 캐시를 지칭하고, 휘발성 있음, 속도가 빠름, 기억용량이 적습니다. 
  - 주기억장치(RAM) : 휘발성 있음, 속도 보통, 기억용량이 보통입니다.
  - 보조기억장치(HDD,SDD) : 휘발성 있음, 속도 낮음, 기억용량이 많습니다.
</div>
</details>

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
<summary> 캐시 히트와 캐시 미스의 차이에 대해 말해보세요. </summary>
<div markdown="1">
  <br>
  
  - 캐시 히트 : 캐시에서 원하는 데이터를 찾는 경우
  - 캐시 미스 : 해당 데이터가 캐시에 없어서 주 메모리로 가서 데이터를 찾는 경우
</div>
</details>

<details>
<summary> 버퍼(Buffer) 란? </summary>
<div markdown="1">
  <br>
  주기억장치와 주변장치사이에서 임시목적으로 데이터를 보관해두기 위해 사용되는 메모리입니다. 
</div>
</details>

<details>
<summary> 페이지폴트(Page Fault) 이란? </summary>
<div markdown="1">
  <br>
  프로세스의 주소공간에는 존재하지만, 컴퓨터의 RAM에는 존재하지 않는 데이터에 접근했을 경우 발생합니다. 
  
</div>
</details>

<details>
<summary> 스와핑(Swapping) 이란? </summary>
<div markdown="1">
  <br>
  페이지폴트를 방지하기 위해 당장 사용하지 않는 영역을 하드디스크로 옮겨 다시 RAM에 , 사용하지 않으면 다시 하드디스크로 내림을 반복하면서 RAM을 효과적으로 관리하는 것을 말합니다.  
</div>
</details>

<details>
<summary> 페이지폴트와 스와핑의 발생 과정 </summary>
<div markdown="1">
  <br>
  
  1. CPU는 물리 메모리를 확인하여 해당 페이지가 없으면 트랩을 발생시켜 운영체제에 알립니다.
  2. 운영체제는 CPU의 동작을 잠시 멈춥니다.
  3. 운영체제는 페이지테이블을 확인하여 가상 메모리에 페이지가 존재하는지 확인하고, 없으면 프로세스를 중단하여 현재 물리메모리에 비어있는 프레임이 있는지 찾습니다. 물리메모리에도 없다면 스와핑이 발동됩니다.
  4. 비어 있는 프레임에 해당 페이지를 로드하고, 페이지 테이블을 업데이트합니다.
  5. 중단되었던 CPU를 다시 시작합니다. 
</div>
</details>

<details>
<summary> 스레싱(Thrashing) 이란? </summary>
<div markdown="1">
  <br>
  메모리의 페이지폴트율이 높은 것을 의미하며, 메모리에 너무 많은 프로세스가 동시에 올라가게 되면 스와핑이 많이 일어나서 발생합니다. 
  컴퓨터의 심각한 성능 저하를 초래합니다.
</div>
</details>

<details>
<summary> 메모리 분할 방식에 대해 설명해보세요. </summary>
<div markdown="1">
<br> 
  
  01. 연속 할당 <br>
   - 고정 분할 방식 : 메모리를 미리 나누어 관리하는 방식으로, 융통성이 없고 내부 단편화가 발생합니다. <br>
   - 가변 분할 방식 : 매 시점 프로그램의 크기에 맞게 동적으로 메모리를 나누어 사용하는 방식으로, 외부 단편화가 발생합니다. 최초적합(first fit), 최적적합(best fit), 최악적합(worst fit)이 있습니다. <br>
  
  02. 불연속 할당
  - 페이징(Paging) : 동일한 크기의 페이지 단위로 나누어 메모리의 서로 다른 위치에 프로세스를 할당합니다. 홀의 크기가 균일하지 않은 문제가 없어지지만 주소 변환이 복잡해질 수 있습니다.
  - 세그멘테이션(Segmentation) : 페이지 단위가 아닌 의미 단위인 세그먼트(segment)로 나누는 방식입니다. 공유와 보안 측면에서 좋으며 홀의 크기가 균일하지 않은 문제가 발생합니다.
  - 페이지드 세그멘테이션(Paged Segmentation) : 공유나 보안의 의미 단위인 세그먼트로 나누고, 물리적 메모리는 페이지로 나누는 것을 말합니다.
  
</div>
</details>

<details>
<summary> 페이지 교체 알고리즘 이란? </summary>
<div markdown="1">
  <br>
  
  - FIFO(First In First Out) : 가장 먼저 온 페이지를 교체 영역에 가장 먼저 놓는 방법입니다.
  - LRU(Least Recently Used) : 참조가 가장 오래된 페이지를 교체합니다. 오래된 것을 파악하기 위해 각 페이지마다 계수기와 스택을 두어야 하는 문제점이 있습니다.
  - NUR(Not Used Recently) : clock 알고리즘이라고 하며, 최근에 참조된 1 비트와 참조 되지 않은 0 비트를 가집니다. 시계 방향으로 돌면서 0을 찾고, 0 비트를 찾은 순간 해당 프로세스를 교체하고 1 비트로 바꿉니다.
  - LFU(Least Frequently Used) : 가장 참조 횟수가 적은 페이지를 교체합니다. 
</div>
</details>


