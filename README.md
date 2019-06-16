# Dev_BasicKnowledge
💻 궁금한 것, 알아야할 것 찾아보고 정리하는 공간 ✏️

<br>
시작 : 2019.03.01 ~
(정리중ing~)
<br>

### Concept

- [객체지향 프로그래밍](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Concept/Object-Oriented%20Programming.md)
- [클린코드 & 리팩토링](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Concept/Clean%20Code%20%26%20Refactoring.md)
- [TDD(Test Driven Development)](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Concept/TDD(Test%20Driven%20Development).md)
- [브라우저 동작 방법](<https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Concept/%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%20%EB%8F%99%EC%9E%91%20%EB%B0%A9%EB%B2%95.md>)

### [Data Structure](<https://github.com/kim6394/Dev_BasicKnowledge#자료구조>)

- [스택 & 큐](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Data%20Structure/Stack%20%26%20Queue.md)
- [힙](<https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Data%20Structure/Heap.md>)

### Algorithm

- [퀵소트](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Algorithm/QuickSort.md)
- [머지소트](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Algorithm/MergeSort.md)
- [힙소트](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Algorithm/HeapSort.md)
- 카운팅소트
- Radix소트



### Operation System

- [프로세스 vs 스레드](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Operation%20System/Process%20vs%20Thread.md)
- [데드락](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Operation%20System/DeadLock.md)
- [페이징 & 세그먼테이션](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Operation%20System/Paging%20and%20Segmentation.md) ([PDF](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Operation%20System/Paging%20and%20Segmentation.pdf))
- [페이지 교체 알고리즘](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Operation%20System/Page%20Replacement%20Algorithm.md)
- [메모리](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Operation%20System/Memory.md)

### Database

- [트랜잭션](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Database/Transaction.md)

### Design Pattern

- [어댑터 패턴](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Design%20Pattern/Adapter%20Pattern.md)
- [싱글톤 패턴](https://github.com/kim6394/Dev_BasicKnowledge/blob/master/Design%20Pattern/Singleton%20Pattern.md)

<br>
<br><br>
<br>



## 자료구조

<br>

#### 배열(Array)

------

<u>정적으로 필요한만큼만 원소를 저장</u>할 수 있는 공간이 할당

이때 각 원소의 주소는 연속적으로 할당됨

index를 통해 O(1)에 접근이 가능함

삽입 및 삭제는 O(N)

지정된 개수가 초과되면? → **배열 크기를 재할당한 후 복사**해야함

<br>

#### 리스트(List)

------

<u>노드(Node)들의 연결</u>로 이루어짐

크기 제한이 없음 ( heap 용량만 충분하면! )

다음 노드에 대한 **참조를 통해 접근** ( O(N) )

삽입과 삭제가 편함 O(1)

<br>

#### ArrayList

------

동적으로 크기가 조정되는 배열

배열이 가득 차면? → 알아서 그 크기를 2배로 할당하고 복사 수행

재할당에 걸리는 시간은 O(N)이지만, 자주 일어나는 일이 아니므로 접근시간은 O(1)

<br>

#### 스택(Stack)

------

LIFO 방식 (나중에 들어온게 먼저 나감)

원소의 삽입 및 삭제가 한쪽 끝에서만 이루어짐 (이 부분을 top이라고 칭함)

함수 호출 시 지역변수, 매개변수 정보를 저장하기 위한 공간을 스택으로 사용함

<br>

#### 큐(Queue)

------

FIFO 방식 (먼저 들어온게 먼저 나감)

원소의 삽입 및 삭제가 양쪽 끝에서 일어남 (front, rear)

FIFO 운영체제, 은행 대기열 등에 해당

<br>

#### 우선순위 큐(Priority Queue)

------

FIFO 방식이 아닌 <u>데이터를 근거로 한 우선순위를 판단하고, 우선순위가 높은 것부터</u> 나감

구현 방법 3가지 (배열, 연결리스트, 힙)

##### 1.배열

간단하게 구현이 가능

데이터 삽입 및 삭제 과정을 진행 시, O(N)으로 비효율 발생 (**한 칸씩 당기거나 밀어야하기 때문**)

삽입 위치를 찾기 위해 배열의 모든 데이터를 탐색해야 함 (우선순위가 가장 낮을 경우)

##### 2.연결리스트

삽입 및 삭제 O(1)

하지만 삽입 위치를 찾을 때는 배열과 마찬가지로 비효율 발생

##### 3.힙

힙은 위 2가지를 모두 효율적으로 처리가 가능함 (따라서 우선순위 큐는 대부분 힙으로 구현)

힙은 **완전이진트리의 성질을 만족하므로, 1차원 배열로 표현이 가능**함 ( O(1)에 접근이 가능 )

root index에 따라 child index를 계산할 수 있음

```
root index = 0

left index = index * 2 + 1
right index = index * 2 + 2
```

**데이터의 삽입**은 트리의 leaf node(자식이 없는 노드)부터 시작

삽입 후, heapify 과정을 통해 힙의 모든 부모-자식 노드의 우선순위에 맞게 설정됨
(이때, 부모의 우선순위는 자식의 우선순위보다 커야 함)

**데이터의 삭제**는 root node를 삭제함 (우선순위가 가장 큰 것)

삭제 후, 마지막 leaf node를 root node로 옮긴 뒤 heapify 과정 수행

<br>

#### 트리(Tree)

------

사이클이 없는 무방향 그래프

완전이진트리 기준 높이는 logN

트리를 순회하는 방법은 여러가지가 있음

1.**중위 순회** : left-root-right

2.**전위 순회** : root-left-right

3.**후위 순회** : left-right-root

4.**레벨 순서 순회** : 노드를 레벨 순서로 방문 (BFS와 동일해 큐로 구현 가능)

<br>

#### 이진탐색트리(BST)

------

노드의 왼쪽은 노드의 값보다 작은 값들, 오른쪽은 노드의 값보다 큰 값으로 구성

삽입 및 삭제, 탐색까지 이상적일 때는 모두 O(logN) 가능

만약 편향된 트리면 O(N)으로 최악의 경우가 발생

<br>

#### 해시 테이블(Hash Table)

------

효율적 탐색을 위한 자료구조

key - value 쌍으로 이루어짐

해시 함수를 통해 입력받은 key를 정수값(index)로 대응시킴

충돌(collision)에 대한 고려 필요

<br>

##### 충돌(collision) 해결방안

해시 테이블에서 중복된 값에 대한 충돌 가능성이 있기 때문에 해결방안을 세워야 함

##### 1.선형 조사법(linear probing)

충돌이 일어난 항목을 해시 테이블의 다른 위치에 저장

```
예시)
ht[k], ht[k+1], ht[k+2] ...

※ 삽입 상황
충돌이 ht[k]에서 일어났다면, ht[k+1]이 비어있는지 조사함. 차있으면 ht[k+2] 조사 ...
테이블 끝까지 도달하면 다시 처음으로 돌아옴. 시작 위치로 돌아온 경우는 테이블이 모두 가득 찬 경우임

※ 검색 상황
ht[k]에 있는 키가 다른 값이면, ht[k+1]에 같은 키가 있는지 조사함. 
비어있는 공간이 나오거나, 검색을 시작한 위치로 돌아오면 찾는 키가 없는 경우
```

##### 2.이차 조사법

선형 조사법에서 발생하는 **집적화 문제를 완화**시켜 줌

```
h(k), h(k)+1, h(k)+4, h(k)+9 ...
```

##### 3.이중 해시법

재해싱(rehasing)이라고도 함

충돌로 인해 비어있는 버킷을 찾을 때 추가적인 해시 함수 h'()를 사용하는 방식

```
h'(k) = C - (k mod C)

조사 위치
h(k), h(k)+h'(k), h(k) + 2h'(k) ...
```

##### 4.체이닝

각 버킷을 고정된 개수의 슬롯 대신, 유동적 크기를 갖는 **연결리스트로 구성**하는 방식

충돌 뿐만 아니라 오버플로우 문제도 해결 가능

버킷 내에서 항목을 찾을 때는 연결리스트 순차 탐색 활용

##### 5.해싱 성능 분석

```
a = n / M

a = 적재 비율
n = 저장되는 항목 개수
M = 해시테이블 크기
```

<br>

##### 맵(map)과 해시맵(hashMap)의 차이는?

map 컨테이너는 이진탐색트리(BST)를 사용하다가 최근에 레드블랙트리를 사용하는 중

key 값을 이용해 트리를 탐색하는 방식임 → 따라서 데이터 접근, 삽입, 삭제는 O( logN )

반면 해시맵은 해시함수를 활용해 O(1)에 접근 가능

하지만 C++에서는 해시맵을 STL로 지원해주지 않는데, 충돌 해결에 있어서 안정적인 방법이 아니기 때문 (해시 함수는 collision 정책에 따라 성능차이가 큼) 



<br>

<br>

<br>

### 면접 준비하기

---

기술면접을 준비할 때는 절대 문제와 답을 읽는 식으로 하지 말 것

문제를 직접 푸는 훈련을 해야함

<br>

<br>

1. ##### 직접 문제를 풀수 있도록 노력하자

   > 포기하지말고, 최대한 힌트를 보지말고 답을 찾자

2. ##### 코드를 종이에 적자

   > 컴퓨터를 이용하면 코드 문법 강조나, 자동완성 기능으로 도움 받을 수 있기 때문에 손으로 먼저 적는 연습

3. ##### 코드를 테스트하자

   > 기본 조건, 오류 발생 조건 등을 테스트 하자. 왜냐하면 면접에서는 이 부분이 필수이기 때문

4. ##### 종이에 적은 코드를 그대로 컴퓨터로 옮기고 실행해보자

   > 종이로 적었을 때 실수를 많이 했을 것이다. 컴퓨터로 옮기면서 실수 목록을 적고 다음부터 저지르지 않도록 유의하자

<br>

<br>

#### 기술면접에서 필수로 알아야 할 것들

자료구조와 알고리즘은 코딩테스트와 기술면접에서 필수적인 부분

아래 나열된 영역은 모두 대비해야한다,

<br>

##### 자료구조

> 연결리스트(Linked Lists)
>
> 트리, 트라이(Tries), 그래프
>
> 스택 & 큐
>
> 힙(Heaps)
>
> Vector / ArrayList
>
> 해시테이블

<br>

##### 알고리즘

> BFS (너비 우선 탐색)
>
> DFS (깊이 우선 탐색)
>
> 이진 탐색
>
> 병합 정렬(Merge Sort)
>
> 퀵 정렬

<br>

##### 개념

> 비트 조작(Bit Manipulation)
>
> 메모리 (스택 vs 힙)
>
> 재귀
>
> DP (다이나믹 프로그래밍)
>
> big-O (시간과 공간 개념)

<br>

<br>

####  

#### 면접에서 문제가 주어지면 해야할 순서

1. 듣기

   > 문제 설명 관련 정보는 집중해서 듣자. 중요한 부분이 있을 수 있음

2. 예제

   > 직접 예제를 만들어서 디버깅하고 확인하기

3. 무식하게 풀기

   > 처음에는 최적의 알고리즘을 생각하지말고 무식하게 풀어보기

4. 최적화

   > BUD (병목현상, 불필요 작업, 중복 작업)을 최적화 시키며 개선하기

5. 검토하기

   > 다시 처음부터 실수가 없는지 검토하기

6. 구현하기

   > 모듈화된 코드 사용하기
   >
   > 에러를 검증하기
   >
   > 필요시, 다른 클래스나 구조체 사용하기
   >
   > 좋은 변수명 사용하기

7. 테스트

   > 개념적 테스트 - 코드 리뷰
   >
   > 특이한 코드들 확인
   >
   > 산술연산이나 NULL 노드 부분 실수 없나 확인
   >
   > 작은 크기의 테스트들 확인

<br>

면접관은 우리가 문제를 어떻게 풀었는 지, 과정을 알고 싶어하기 때문에 끊임없이 설명해야한다!

<br>

<br>

####  



#### 오답 대처법

---

면접에서 모든 문제의 정답을 맞춰야 할 필요는 없다.

면접관들은 답을 평가할 때 맞춤, 틀림으로 평가하지 않음

<br>

##### 중요하게 여기는 부분

- 얼마나 최종 답안이 최적 해법에 근접한가
- 최종 답안을 내는데 시간이 얼마나 걸렸나
- 얼마나 힌트를 필요로 했는가
- 얼마나 코드가 깔끔한가

<br>

또한 면접은 '상대평가'임. 즉, 문제가 어렵다면 다른 사람도 마찬가지이므로 너무 두려워하지 말 것

<br>

> 면접 기술문제는 보통 2~30분 안에 풀 수 있는 문제를 출제