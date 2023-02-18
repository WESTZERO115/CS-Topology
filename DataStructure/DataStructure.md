<details>
<summary> 시간복잡도는 무엇인가요? </summary>
<div markdown="1">
  <br>
 
  알고리즘을 이루고 있는 연산을 계산하는 데 걸리는 시간과 입력의 함수 관계입니다.
  효율적인 코드로 개선하는 데 쓰이는 척도가 됩니다.
  <img src="https://user-images.githubusercontent.com/70850937/187142016-bf9db9f4-4285-44a3-bca3-ec717db94c24.png" width="450" height="350"/>

  
</div>
</details>

<details>
<summary> 공간복잡도는 무엇인가요? </summary>
<div markdown="1">
  <br>
 프로그램을 실행시키고 완료하는 데 필요로 하는 자원 공간의 양입니다. 컴퓨터 성능의 발달로 인해 메모리 공간이 넘쳐나다 보니 중요도는 떨어졌습니다. <br>
  최근 대용량 시스템이 보편화되면서, 공간 복잡도보다 시간 복잡도가 우선이 되었습니다.

  
</div>
</details>

<br>

## 선형 자료구조 
<details>
<summary> 배열과 연결 리스트의 차이점은 무엇인가요? </summary>
<div markdown="1">
  <br>
배열은 인덱스만 알면 해당 내용을 알 수 있지만 연결 리스트는 인덱스를 하나씩 늘려가며 찾아야 내용을 알 수 있습니다. <br>
  데이터 추가와 삭제를 많이 하는 것은 연결리스트, 탐색을 많이 하는 것은 배열로 하는 것이 좋습니다.

</div>
</details>

<details>
<summary> 벡터(Vector)란 무엇인가요? </summary>
<div markdown="1">
  <br>
  
벡터는 동적인 요소를 할당할 수 있는 동적 배열입니다. `중복 접근`을 허용하고 `랜덤 접근`이 가능합니다. <br>
<br> 
  
  - 시간복잡도 <br>
  탐색 : O(1) <br>
  삽입/삭제 : O(n) 


</div>
</details>

<details>
<summary>스택(Stack)이란 무엇인가요? </summary>
<div markdown="1">
  <br>
스택(Stack)은 가장 마지막으로 들어간 데이터가 가장 첫 번째로 나오는 성질인(LIFO, Last In First Out) 자료구조입니다. <br>
  
push()함수로 자료를 삽입하고 pop()함수로 자료를 삭제합니다. <br>
top 변수는 스택이 비어있으면 -1의 값을 가집니다. <br>
<br>
-> 파이썬의 경우 `append()`와 `pop()`를 사용합니다. <br>
스택 자료구조를 활용해야 하는 상당수 알고리즘은 `재귀 함수`를 이용해서 간편하게 구현될 수 있습니다. 대표적인 예시가 바로 DFS 입니다.
  <br> 
  
  - 시간복잡도 <br>
  탐색 : O(1) <br>
  삽입/삭제 : O(n) 


</div>
</details>

<details>
<summary>큐(Queue)는 무엇인가요? </summary>
<div markdown="1">
  <br>
큐(Queue)는 먼저 들어간 데이터가 먼저 나오는 성질인 (FIFO, First In First Out) 자료구조입니다. <br>

enqueue()함수와 rear 변수를 사용해서 자료를 삽입하고, dequeue()함수와 front 변수를 사용해서 자료를 삭제합니다. <br>
<br>
-> 파이썬의 경우 deque 자료구조를 활용하며, `append()`와 `popleft()`함수를 이용합니다.
  
  <br> 
  
  - 시간복잡도 <br>
  탐색 : O(1) <br>
  삽입/삭제 : O(n) 


</div>
</details>

스택과 큐를 사용할 때는 삽입과 삭제 외에도 `오버플로우`와 `언더플로우`를 늘 고민해야 합니다.

<br>

## 비선형 자료구조
<details>
<summary>그래프(Graph)는 무엇인가요? </summary>
<div markdown="1">
  <br>
  
`정점(vertex)`과 `간선(edge)`으로 이루어진 유한집합입니다. <br>
그래프의 탐색은 하나의 정점으로부터 시작하여 차례대로 모든 정점을 한 번씩 방문하는 것입니다. <br>
  <br> 
  
  - 시간복잡도 <br>
  탐색 : O(1) <br>
  삽입/삭제 : O(n) 


</div>
</details>

<details>
<summary> 트리(Tree)는 무엇인가요? </summary>
<div markdown="1">
  <br>
트리를 거꾸로 엎어놓은 것 같은 모양을 하고 있는 비선형 계층적인 자료구조입니다. <br>
자료를 노드(node)라고 하며, 노드끼리의 연결선을 간선(edge)라고 합니다. <br>
 <br>
  
1) `이진트리(Binary Tree)`는 모든 노드가 최대 2개의 서브 트리를 가지고 있는 트리입니다. <br> 
    <img width="350" height="250" src="https://user-images.githubusercontent.com/65750746/196020700-118a4cdd-ddbb-4e08-89c8-94af1d5ef864.png">
-> 크기가 9이고 높이가 3인 이진 트리 예시

2) `포화이진트리(Perfect Binary Tree)`는 트리의 모든 잎의 레벨이 동일하고, 내부 노드들은 모두 2개의 자식을 가지는 트리를 말합니다. 즉, 각 레벨의 노드가 꽉 차있는 이진트리입니다.   
    <img width="350" height="250" src="https://user-images.githubusercontent.com/65750746/196020874-26deb7c5-6f47-4f85-acb7-14c99c75ae15.png">

3) `완전이진트리(Complete Binary Tree)`는 포화 이진 트리의 잎들을 오른쪽부터 순서대로 제거하여 노드가 왼쪽부터 채워지는 이진트리입니다.
    <img width="350" height="250" src="https://user-images.githubusercontent.com/65750746/196020951-5aa65167-f0e7-4128-ad10-ea072c37bdc1.png">

4) `이진탐색트리(BST, Binary Search Tree)`는 노드의 오른쪽 하위 트리에 노드 값보다 큰 값이 들어있고, 왼쪽 하위 트리에 노드값보다 작은 값이 들어있는 트리입니다. 삽입 순서에 따라 선형적일 수 있습니다. <br>
    <img width="350" height="250" src="https://user-images.githubusercontent.com/65750746/196021050-9f4035cc-c015-48de-86d1-014816c8dd79.png">

    - 시간복잡도 <br>
    탐색 : O(1) <br>
    삽입/삭제 : O(n) 


</div>
</details>

<details>
<summary> 그래프와 트리의 차이점은 무엇인가요? </summary>
<div markdown="1">
  <br>
  
  그래프와 트리 둘다 정점과 간선으로 이루어져있습니다. 하지만 트리는 그래프 중의 하나로, 계층적 데이터의 집합입니다.

</div>
</details>

<details>
<summary> 힙(Heap)은 무엇인가요? </summary>
<div markdown="1">
  <br>
  
 `완전 이진 트리 기반`의 자료구조이며, 최소힙과 최대힙 두 가지가 있습니다.
  
  1) `최대힙` : 루트 노드에 있는 키는 모든 자식에 있는 키 중에서 가장 커야 합니다. 또한, 각 노드의 자식 노드와의 관계도 이와 같은 특징이 재귀적으로 이루어져야 합니다. <br>
  2) `최소힙` : 루트 노드에 있는 키는 모든 자식에 있는 키 중에서 가장 작아야 합니다. 또한, 각 노드의 자식 노드와의 관계도 이와 같은 특징이 재귀적으로 이루어져야 합니다.
  
  <br> 
  
  - 시간복잡도 <br>
  삽입/삭제 : O(logN) 


</div>
</details>

<details>
<summary> 우선순위 큐는 무엇인가요? </summary>
<div markdown="1">
  <br>
  
우선순위 대기열이라고도 하며, 대기열에서 우선순위가 높은 요소가 우선 순위가 낮은 요소보다 먼저 제공되는 자료구조입니다. <br>
  힙을 기반으로 구현됩니다. 
  
  <br> 
  
  - 시간복잡도 <br>
  삽입/삭제 : O(logN) 


</div>
</details>

<details>
<summary> 맵(Map)은 무엇인가요? </summary>
<div markdown="1">
  <br>
  
특정 순서에 따라 키(key)와 매핑된 값(value)의 조합으로 형성된 자료구조입니다. <br>
  map<string, int> 형태로 구현됩니다. <br>
  해시테이블을 구현할 때 사용되며, 정렬을 보장하지 않는 unordered_map과 정렬을 보장하는 map 두 가지가 있습니다. 
  
  <br> 
  
  - 시간복잡도 <br>
  
  1) map <br>
  탐색 : O(logN) <br>
  삽입/삭제 : O(logN) <br>
  
  2) unordered_map <br>
    탐색 : O(1) 
  


</div>
</details>
  
 <details>
<summary> 셋(Set)은 무엇인가요? </summary>
<div markdown="1">
  <br>
  
집합이라는 의미를 가지며 순서가 없고 중복을 허용하지 않습니다.
  
  <br> 
  
  - 시간복잡도 <br>
  탐색 : O(logN) <br>
삽입/삭제 : O(logN + a) 


</div>
</details>
   
<details>
<summary> 해시테이블(Hash Table)은 무엇인가요? </summary>
<div markdown="1">
  <br>
  
해싱(Hashing)은 임의의 길이의 값을 해시함수를 사용하여 고정된 크기의 값으로 변환하는 작업입니다. <br>
해시테이블(Hash Table)이란 해시함수를 사용하여 변환한 값을 색인(index)로 삼아 키(key)와 데이터(value)를 저장하는 자료구조입니다.
  
  <br> 
  
  - 시간복잡도 <br>
  탐색 : O(1) <br>
삽입/삭제 : O(1) 


</div>
</details>
