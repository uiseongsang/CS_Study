# 프로그래밍 패러다임 
명령형 - 절차적. 객체지향

선언형 - 함수형

![image](https://github.com/uiseongsang/CS_Study/assets/40707686/013ef191-4a0b-42a1-9171-720e71d6e399)

# 명령형 프로그래밍 패러다임


왕이 되어 아래 사람들한테 명령을 하는거 처럼

컴퓨터에서 명령을 순서대로 내려 수행을 시키는 거다.

## 절차적 프로그래밍
해당 명령 지침을 절차적으로 나눌 수 있다.

절차는 함수가 아니다. 절차랑 함수의 차이점은 함수는 값을 리턴하지만 절차는 아니라는 점이다.

### 기본적인 절차적 프로그래밍 예제

```
  public void static main(string[] args){
    int sum = 0;
    for(int i = 1; i < 11; i++) {
      sum += i;
    }

    System.out.println("Sum is " + sum);
  }
```

### 사용하는 이유
* 간단하다
* 쉽게 프로그램 플로우를 추적할 수 있다
* 강력한 모듈화 또는 구조화 기능을 갖추고 있다
* 메모리가 적게 필요하다

## 객체지향 프로그래밍
객체지향 프로그래밍의 핵심은 캡슐화,추상화,다형성,상속이다.

### 기본적인 객체지향 프로그래밍 예제

```
  class Tv{
    String color;
    boolean power;
    int channel;

    void power() {power = !power; }
    void channelUp() { ++channel; }
    void channelDown() { --channel; }
  }
```

### 사용하는 이유
* 상속을 통한 코드 재사용
* 다형성을 통한 유연성
* 캡슐화를 통한 데이터 숨기기 -> 높은 보안성

# 선언형 프로그래밍 패러다임
제어 흐름에 대해 언급하지 않고 계산 논리를 표현하는 프로그램 작성 스타일을 가지고 있다.

달성 방법을 지시하는 대신 달성해야 할 목표에 초점을 맞춘다.

## 함수형 프로그래밍
수학에 뿌리를 두고 있으며 언어 독립적이다.

## 특징
* 짧은 기능의 프로그램을 구성
* 모든 코드는 함수 내에 있다
* 모든 변수의 범위는 함수로 지정

자바는 Java 8 버전부터 함수형 프로그래밍을 지원하기 위해 람다(lambda)와 스트림(stream)이 도입되었다. 

람다와 스트림을 사용하면 함수형 프로그래밍 스타일로 자바 코드를 작성할 수 있다.

### 일반적인 코드
```
interface Calculator {
    int sum(int a, int b);
}

class MyCalculator implements Calculator {
    public int sum(int a, int b) {
        return a+b;
    }
}

public class Sample {
    public static void main(String[] args) {
        MyCalculator mc = new MyCalculator();
        int result = mc.sum(3, 4);
        System.out.println(result);  // 7 출력
    }
}
```

### 람다를 적용한 코드
```
interface Calculator {
    int sum(int a, int b);
}

public class Sample {
    public static void main(String[] args) {
        Calculator mc = (int a, int b) -> a +b;  // 람다를 적용한 코드
        int result = mc.sum(3, 4);
        System.out.println(result);
    }
}
```

### 사용하는 이유
* 코드의 양이 줄어든다
* 읽기 쉬운 코드를 만들 수 있다
* 범용 기능을 재사용할 수 있어 신속한 SW 개발이 가능
* 유닛 테스트가 쉽다
* 기능이 매우 간단하기 때문에 전반적인 응용 프로그램은 덜 복잡하다
* 디버깅이 더 쉽다
* 수학적 계산 작업
* 동시성 또는 병렬성을 목표로 하는 애플리케이션 작업
