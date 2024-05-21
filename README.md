## spring 과 springBoot 의 차이점
  스프링(Spring)은 프레임워크이며, 스프링 부트(Spring Boot)는 스프링 프레임워크를 기반으로 한 도구
  스프링은 설정 파일을 작성해야 하지만, 스프링 부트는 자동 설정을 제공하여 간편하게 개발할 수 있음
  또한, 스프링 부트는 내장 서버를 제공하여 쉽게 웹 애플리케이션을 실행할 수 있다
  Spring은 스프링 프레임워크를 보다 세밀하게 제어하고자 하는 경우에,
  Spring Boot는 빠르고 간단하게 스프링 애플리케이션을 개발하고자 하는 경우에 사용된다
  
  **<https://www.inflearn.com/blogs/3315>**


## 스프링 프레임워크
* 핵심 기술 : 스프링 DI 컨테이너, AOP, 이벤트, 기타
* 웹 기술 : 스프링 MVC, 스프링 WebFlux
* 데이터 접근 기술 : 트랜잭션, JDBC, ORM 지원, XML 지원
* 기술 통합 : 캐시, 이메일, 원격접근, 스케줄링
* 테스트 : 스프링 기반 테스트 지원
* 언어 : Kotlin, Groovy
* 최근에는 스프링 부트를 통해서 스프링 프레임워크의 기술들을 편리하게 사용

> 프레임워크란 : **<https://www.castingn.com/sourcing/kkultip_detail/110>**


## 스프링 부트
* **스프링을 편리하게 사용할 수 있도록 지원, 최근에는 기본으로 사용**
* 단독으로 실행할 수 있는 스프링 애플리케이션을 쉽게 생성
* Tomcat 같은 웹 서버를 내장해서 별도의 웹 서버를 설치하지 않아도 됨
* 손쉬운 빌드 구성을 위한 starter 종속성 제공
* 스프링 3rd parth(외부) 라이브러리 자동 구성
* 메트릭, 상태 확인, 외부 구성 같은 프로덕션 준비 기능 제공
* 관례에 의한 간결한 설정

>참고 : 스프링부트는 스프링프레임워크와 별도로 사용할 수 있는것이 아니다. 
>스프링부트는 여러가지 것들을 편리하게 사용할 수 있는 기능들을 제공한다.
>스프링부트는 스프링 프레임워크를 사용해서 도와주는 기술이다.


## 스프링 핵심
* 스프링은 자바 언어 기반의 프레임워크
* 자바 언어의 가장 큰 특징 - **객체 지향 언어**
* 스프링은 객체 지향 언어가 가진 강력한 특징을 살려내는 프레임워크
* 스프링은 **좋은 객체 지향** 애플리케이션을 개발할 수 있게 도와주는 프레임워크

***

## 객체 지향 특징
* 추상화
* 캡슐화
* 상속
* **다형성**

## 객체 지향 프로그래밍
* 객체 지향 프로그래밍은 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러개의 독립된 단위,
  즉 **"객체"들의 모임**을 파악하고자 하는 것이다. 각각의 **객체는 메시지를 주고받고**, 데이터를 처리할 수 있다.(**협력**)
* 객체 지향 프로그래밍은 프로그램을 **유연하고 변경이 용이**하게 만들기 때문에 대규모 소프트웨어 개발에 많이 사용된다.


>클라이언트에 영향을 주지않고 새로운 기능을 제공할 수 있다.
>역할과 구현으로 세상을 구현했기 때문에 가능.

## 역할과 구현을 분리(java)
* 자바 언어의 다형성을 활용
  * 역할 = 인터페이스
  * 구현 = 인터페이스를 구현한 클래스, 구현 객체
* 객체를 설계할 때 **역할과 구현**을 명확히 분리
* 객체 설계시 역할(인터페이스)을 먼저 부여하고, 그 역할을 수행하는 구현 객체 만들기

***

## 오버로딩 & 오버라이딩
* 오버로딩(Overloading) : 자바의 한 클래스 내에 이미 사용하려는 이름과 같은 이름을 가진 메소드가 있더라도
  매개변수의 개수 또는 타입이 다르면, 같은 이름을 사용해서 메소드를 정의할 수 있다.
```java
class OverloadingTest {

	public static void main(String[] args) {
		OverloadingMethods om = new OverloadingMethods();

		om.print();
		System.out.println(om.print(3));
		om.print("Hello!");
		System.out.println(om.print(4, 5));
	}
}

class OverloadingMethods {
	public void print() {
		System.out.println("오버로딩1");
	}

	String print(Integer a) {
		System.out.println("오버로딩2");
		return a.toString();
	}

	void print(String a) {
		System.out.println("오버로딩3");
		System.out.println(a);
	}

	String print(Integer a, Integer b) {
		System.out.println("오버로딩4");
		return a.toString() + b.toString();
	}

}
```
```
오버로딩1
오버로딩2
3
오버로딩3
Hello!
오버로딩4
45
```

* 오버라이딩(Overriding) : 부모 클래스로부터 상속받은 메소드를 자식 클래스에서 재정의
```java
public class OverridingTest {

	public static void main(String[] args) {
		Person person = new Person();
		Child child = new Child();
		Senior senior = new Senior();
		
		person.cry();
		child.cry();
		senior.cry();
	}
}

class Person {
	void cry() {
		System.out.println("흑흑");
	}
}

class Child extends Person {
	@Override
	protected void cry() {
		System.out.println("잉잉");
	}
}

class Senior extends Person {
	@Override
	public void cry() {
		System.out.println("훌쩍훌쩍");
	}
}
```
```
흑흑
잉잉
훌쩍훌쩍
```

***

## 다형성의 본질
* 인터페이스를 구현한 객체 인스턴스를 **실행 시점에 유연하게 변경**할 수 있다.
* 다형성의 본질을 이해하려면 **협력**이라는 객체사이의 관계에서 시작해야 한다.
* **클라이언트를 변경하지 않고, 서버의 구현 기능을 유연하게 변경할 수 있다.**

## 스프링과 객체 지향
* 다형성이 가장 중요
* 스프링은 다형성을 극대화해서 이용할 수 있게 도와준다.
* 스프링에서 이야기하는 제어의 역전(IoC), 의존관계 주입(DI)은 다형성을 활용해서 역할과 구현을 편리하게 다룰 수 있도록 지원한다.
* 스프링을 사용하면 구현을 편리하게 변경할 수 있다.

***

