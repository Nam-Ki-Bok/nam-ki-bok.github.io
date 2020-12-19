---
title:  "[Java] 템플릿 메소드(Template Method) 구현"
excerpt: ""

categories:
  - Java

tags:
---

## 🥟 Template Method

템플릿 메소드는 <a href="https://nam-ki-bok.github.io/java/Java_singleton/" style="color:#0FA678">[Java] Singleton pattern</a> 과 같은 디자인 패턴이다.

리팩토링 수업에서 교수님이 말씀하시기를 하위 클래스 안에 두 메소드가 같은 순서로 비슷한 일을 한다면

그 일들을 시그니처가 같은 두 개의 메소드로 만들어 두 원본메소드를 같게 한 뒤 상위 클래스로 올리라고 하셨다..

이 때 상위 클래스로 올린 뒤 추상 메소드로 바꿔버리면 된다.

솔직히 이렇게 글로만 설명하면 정말 이해도 안가고 무슨 이야기인지도 모른다..

바로 예제 코드를 통해 이해해보자

## 🍜 Template Method 구현

우선 이해하기 쉽게 상황을 가정해보자.

Car 라는 추상 클래스를 만든 뒤 AICar, ManualCar 클래스를 만들어 상속 받을 것 이다.

```java
package template;

public abstract class Car {

    public abstract void drive();
    public abstract void stop();

    public void startCar() {
        System.out.println("시동을 켭니다");
    }

    public void turnOff() {
        System.out.println("시동을 끕니다.");
    }

    final public void run() {
        startCar();
        drive();
        stop();
        turnOff();
    }
}
```

Car 라는 추상 클래스를 보면 **drive, stop** 메소드는 추상 메소드로 구현이 되어있다.

반면 **startCar, turnOff** 메소드는 구현이 되어있다.

이유는 자동차마다 시동을 걸고, 시동을 끄는 행위는 똑같지만 운전하고, 멈추는 행위는 각자 다르기 때문이다.

**run** 메소드를 보면 자동차가 시동을 걸고, 운전을 하고, 멈추고, 시동을 끄는 행위를 구현 해 두었다.

이렇게 하위 클래스의 동작 방식, 즉 시나리오를 정해둔 메소드를 템플릿 메소드라고 한다.

여기서는 **final public void run()** 메소드가 템플릿 메소드이다.

---

```java
package template;

public class AICar extends Car{

	@Override
	public void drive() {
		System.out.println("자율 주행합니다");
		System.out.println("자동차가 스스로 방향을 전환합니다.");
	}

	@Override
	public void stop() {
		System.out.println("스스로 멈춥니다.");		
	}
}
```

<br>

```java
package template;

public class ManualCar extends Car{

	@Override
	public void drive() {
		System.out.println("사람이 운전합니다");
		System.out.println("사람이 핸들을 조작합니다");
	}

	@Override
	public void stop() {
		System.out.println("브레이크로 정지합니다");
	}
}
```

추상 클래스 Car 를 상속받은 AICar, ManualCar 클래스를 만들었다.

이 클래스들은 추상 메소드인 drive, stop 메소드를 구현 해주어야 한다.

---

```java
package template;

public class Main {

	public static void main(String[] args) {
		
		System.out.println("=== 자율주행 하는 자동차 ===");
		Car myCar = new AICar();
		myCar.run();
		
		System.out.println("=== 사람이 운전하는 자동차 ===");
		Car hisCar = new ManualCar();
		hisCar.run();
	}
}
```

그리고 템플릿 메소드를 실행해보면 내가 정한 시나리오가 차 종류에 맞게 실행이 된다.

여기서 템플릿 메소드를 final 로 선언한 이유는 이 시나리오를 모든 하위 클래스가 동일하게 사용하고 변경되면 안되기 때문이다.

즉 정리하자면 템플릿 메소드는 하위 클래스들의 로직 흐름을 제어하는 역할이다.

<br>