# 프로세스와 스레드
프로세스: 실행 중인 프로그램, 자원(resource -> 메모리, CPU)과 스레드로 구성

스레드: 프로세스 내에서 실제 작업을 수행.

모든 프로세스는 최소한 하나의 스레드를 가지고 있다.

프로세스 : 스레드 = 공장 : 일꾼

# 멀티스레드
두개 또는 그 이상의 스레드를 사용

대부분의 프로그램이 멀티스레드로 작성되어 있지만 멀티스레드 프로그래밍이 장점만 있는 것은 아니다.

## 장점
* 시스템 자원을 보다 효율적으로 사용할 수 있다.
* 사용자에 대한 응답성(responseness)이 향상된다.
* 작업이 분리되어 코드가 간결해 진다

> 여러 모로 좋다

## 단점
* 동기화(synchronization)에 주의해야 한다.
* 교착상태(dead-lock)가 발생하지 않도록 주의해야 한다.
* 각 스레드가 효율적으로 고르게 실행될 수 있게 해야 한다. (기아:굶어 죽는것)

> 프로그래밍할 때 고려해야 할 사항들이 많다

# 스레드의 구현과 실행
Thread 클래스를 상속 <<< Runable 인터페이스를 구현

자바는 단일 상속만 허용하기 떄문에 인터페이스로 구현하는 게 더 좋다.

## Runable 인터페이스를 구현

```
Runnalbe r = new MyThread();
Thread t1 = new Thread(r);
t1.start();
```

## 스레드의 실행 - start()
* 스레드를 생성한 후에 start()를 호출해야 스레드가 작업을 시작한다.

> OS 스케줄러가 실행순서 결정

## 스레드 종류
1. 사용자 스레드 (main 스레드)
2. 데몬 스레드 (보조 스레드)

> 실행 중인 사용자 스레드가 하나도 없을 때 프로그램은 종료된다.

