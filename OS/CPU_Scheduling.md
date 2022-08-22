<details>
<summary>  CPU 스케줄링의 목적은 무엇인가요? </summary>
<div markdown="1">
  <br>
 
  모든 프로세스가 공평하게 작업하도록 하는 것입니다. <br>
CPU 이용률은 높이고, 주어진 시간에 많은 일을 하게 하고, 준비 큐(ready queue)에 있는 프로세스의 수는 적게 하고, 응답시간은 짧게 하는 것을 목표로 합니다.
  
</div>
</details>

<details>
<summary>  비선점형 스케줄링이 무엇인가요? </summary>
<div markdown="1">
  <br>
 
어떤 프로세스가 CPU를 점유하면 다른 프로세스가 이를 빼앗을 수 없는 스케줄링 방식입니다. <br>
선점형 스케줄링보다 작업량이 적고 문맥교환에 의한 낭비가 적다는 장점이 있습니다. <br>
하지만 CPU 사용시간이 긴 프로세스 때문에 CPU 사용시간이 짧은 여러 프로세스가 오랫동안 기다리게 되어 전체 시스템의 효율이 떨어집니다.
  
</div>
</details>

<details>
<summary>  비선점형 스케줄링 종류에 대해 설명해주세요. </summary>
<div markdown="1">
  <br>
 
  - FCFS(First Come First Served) : 준비 큐에 도착한 순서대로 CPU를 할당하는 알고리즘입니다.
  - SJF(Shortest Job First) : 준비 큐에 있는 프로세스 중에서 실행시간이 가장 짧은 프로세스를 가장 먼저 CPU를 할당하는 알고리즘입니다.
  - HRN(Highest Response Ratio Next) : 기다린 시간과 CPU 사용 시간을 고려하여 스케줄링하는 알고리즘입니다. SJF 스케줄링에서 발생할 수 있는 아사 현상을 해결하기 위해 만들어졌습니다.
  - 우선순위 : 준비 큐에 있는 프로세스의 순서를 무시하고 우선순위가 가장 높은 프로세스부터 CPU를 할당하는 알고리즘입니다.
  
</div>
</details>

<details>
<summary>  선점형 스케줄링이 무엇인가요? </summary>
<div markdown="1">
  <br>
 
 어떤 프로세스가 CPU를 할당받아 실행중이더라도 운영체제가 CPU를 강제로 빼앗을 수 있는 스케줄링 방식입니다. <br>
문맥교환과 같은 부가적인 작업으로 인해 낭비가 생기는 단점이 있습니다. <br>
그러나 하나의 프로세스가 CPU를 독점할 수 없기 때문에 빠른 응답시간을 요구하는 대화형 시스템이나 시분할 시스템에 적합합니다.
</div>
</details>

<details>
<summary>  선점형 스케줄링 종류에 대해 설명해주세요. </summary>
<div markdown="1">
  <br>
 
  - 라운드로빈(Round Robin) : 프로세스가 할당받은 시간(타임슬라이스)동안 작업을 하다가 시간 안에 작업을 끝내지 못하면 다시 준비 큐의 뒤로 가는 알고리즘입니다.
  - SRT(Shortest Remaining Time) : 프로세스의 작업시간이 더 짧은 프로세스를 CPU에 할당하는 알고리즘입니다. 
  - 다단계 큐 : 우선순위에 따른 준비 큐를 여러 개 사용하고, 큐마다 라운드로빈이나 FCFS등 다른 스케줄링을 사용하는 알고리즘입니다.
</div>
</details> 


