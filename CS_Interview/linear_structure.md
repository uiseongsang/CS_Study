# 선형 자료구조 
연결 리스트, 배열, 스택, 큐이 있다

## 선형구조의 종류
## 1. 리스트, 배열
연속적인 기억공간에 배정하며 각 요소들은 동일 데이터 타입으로 쌍으로 표현된다.

정적인 데이터 타입으로 배열의 크기는 한 번 정하면 크기를 변경 할 수 없다.

### 특징
* 가장 간단한 자료구조
* 접근 속도가 빠름 (장점)
* 삽입, 삭제 시 자료의 이동으로 최대 O(n)시간이 걸린다 (단점)

### Array vs List(ArrayList)
1. Array: 정적배열
2. List(ArrayList): 동적배열(크기가 가변적으로 늘어난다)
	- 생성 시점에 작은 연속된 공간을 요청해서 참조형 변수들을 담아 놓는다.
    - 값이 추가될 때 더 큰 공간이 필요하면 더 큰 공간을 받아서 저장하니깐 상관없다.

### ArrayList 실습 
```
ArrayList<Integer> intList = new ArrayList<Integer>(); // 선언 + 생성

/* 추가 */
intList.add(99);
intList.add(15);

System.out.println(intList.get(1)) // 첫번쨰 list를 출력


/* 수정 */
intList.set(1,10); // 2번째 있는 15를 10으로 바꾸기
System.out.println(intList.get(1)) // 첫번쨰 list를 출력

/* 삭제 */
intList.remove(0)
System.out.println(intList.get(0)) // 0번쨰 list를 출력

// 출력값:
// 15
// 10
// 15

/* 클리어 */
intList.clear();

```
>ArrayList<Integer> intList = new ArrayList<Integer>();
  여기서 Integer 참조 변수를 사용해야한다!!!

## 2. 연결 리스트(Linked List)
메모리에 남는 공간을 요청해서 여기 저기 나누어서 실제 값을 담기
  실제 값이 있는 주소값으로 목록을 구성하고 저장하는 자료구조.

### 특징
* 삽입, 삭제 작업이 용이하다
* 기억공간이 연속적으로 놓여있지 않아도 저장이 가능하다
* 접근 속도가 느리다
* 중간 노드의 연결이 끊어지면 다음 노드를 찾기 힘들다

### LinkedList 실습
```
LinkedList<Integer> linkedList = new LinkedList<Integer>();

// 추가
linkedList.add(1);
linkedList.add(66);

// 수정
linkedList.set(1,44);

// 삽입
linkedList.add(1, 88);

// 삭제
linkedList.remove(0);
```

## ArrayList
순서가 있는 데이터의 집합 
> Array는 최초의 길이를 알아야하지만 List는 처음에 길이를 몰라도 만들 수 있다.

### LinkedList vs ArrayList
기본적인 기능은 동일하지만
LinkedList 값은 나누어져 있어서 조회하는 속도가 **"느리다"**
But 값을 추가하거나, 삭제할 떄는 ArrayList보다 **"빠르다"**

## 3. Stack
스택은 수직으로 값을 쌓아놓고, 넣었다가 빼는 자료구조이다.
FILO(First In Last Out)인셈이다.
주된 기능은 push,pop,peek,isEmpty이 있다.
  스택은 주로 최근 저장된 데이터를 나열하고 싶거나, 데이터의 중복 처리를 막고 싶을 떄 사용한다.

### 특징
* 자료의 삽입, 삭제 작업이 한쪽 방향에서만 이뤄진다

### Stack 실습
  ```
Stack<Integer> intStack = new Stack<Integer>();
  
  intStack.push(10);
    intStack.push(3);
  
  // 다 지워질 때 까지 출력
  while(!intStack.isEmpty()) {
  	System.out.println(intStack.pop());
  }
```
 
>  peek()는 C++에 top()이랑 같은거다 가장 위에 있는 데이터를 보여준다

## Queue
  FIFO(Frist In First Out)
  add,peek,poll(꺼낸다),isEmpty,size 기능이 있다
  
  Queue는 생성자가 없는 인터페이스이라서
  생성자가 없는 인터페이스는 new 연산자로 생성을 할 수 없어서 대신 LinkedList<>()를 써서 생성을 한다.

### 특징
* 큐는 연결리스트로 구현할 수 있다
* 창구 업무처럼 서비스 순서를 기다리는 등의 대기 행렬 처리에 사용한다

### Queue 실습

```
  Queue<Integer> intQueue = new LinkedList<>(); // queue를 생성, 선언
  
intQueue.add(10);
    intQueue.add(3);
  
  // 다 지워질 때 까지 출력
  while(!intQueue.isEmpty()) {
  	System.out.println(intQueue.poll());
  }

