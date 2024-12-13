---
published: true
title: 💚 자료구조 - Java 메모리 구조(Stack, Heap)
author: LeeNaYoung
date:   2024-12-12 11:57:02 +09:00
categories: [CS]
tags: [CS]
---

# 자바 메모리 구조

<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/66e94205-4dae-45da-8e3a-82b6d959d4d9" class="popup img-link"><img src="https://github.com/user-attachments/assets/66e94205-4dae-45da-8e3a-82b6d959d4d9" alt="1" loading="lazy"></a>
출처 : [이미지](https://velog.io/@b2b2004/Java-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EA%B5%AC%EC%A1%B0Method-Stack-Heap)

자바 프로그램이 실행되면 JVM(자바 가상 머신)은 OS로부터 메모리를 할당 받고 그 메모리를 용도에 따라서 여러 영역으로 나누어 관리한다.

`JVM`의 메모리 공간(Runtime Data Area)는 크게 Method(Static) 영역, Stack 영역, Heap 영역으로 구분되고 데이터 타입(자료형)에 따라 각 영역에 나눠서 할당되게 된다.

```java
class Solution {
    public int solution void main(String[] args) { // 매개변수
        int answer = 10; // 지역변수
    }
}

public calss Counter {
	private int state = 0; // 인스턴스 변수
    public static int gage = 100; // 클래스 변수

	public int get() {
	   return state;
	}
}
```

|변수명  |선언 위치  |설명  |
|--|--|--|
|클래스 변수  |클래스 영역  |클래스 영역에서 타입 앞에 static이 붙는 변수, 객체를 공유하는 변수로 여러 객체에서 공통으로 사용하고 싶을 때 정의
인스턴스 변수  | 클래스 영역 | 클래스 영역에서 static이 아닌 변수, 개별적인 저장 공간으로 객체/인스턴스마다 다른 값 저장 가능
지역 변수  |메서드 영역  |메서드 내에서 선언되고 메서드 수행이 끝나면 소멸되는 변수, 초깃값을 지정한 후 사용할 수 있음  |
| 매개 변수 | 메서드 영역 | 메서드 호출 시 '전달하는 값'을 가지고 있는 인수 |



### 메모리 구조

- 애플리케이션에 할당되는 메모리는 내부적으로 여러 영역으로 나뉨

- stack 메모리 : 함수나 메서드의 지역 변수(local variable)와 매개 변수(parameter)가 저장됨. 함수나 메서드가 호출될 때마다 스택 프레임(stack frame)이 쌓임.

- heap 메모리 : 객체가 저장됨.


# Method(Static) 영역

- JVM이 동작해서 클래스가 로딩될 때 생성

- JVM이 읽어들인 클래스와 인터페이스에 대한 런타임 상수 풀, 멤버 변수(필드), 클래스 변수(Static 변수), 상수(final), 생성자(constructor), 메서드(method) 등을 저장하는 공간

- Method(Static) 영역에 있는 것은 어느곳에서나 접근 가능

- Method(Static) 영역의 데이터는 프로그램의 시작부터 종료가 될 때까지 메모리에 남아있음. 


# Stack 영역

- 기본 자료형, 지역변수, 매개변수가 저장되는 메모리

- 메서드 내부의 기본 자료형에 해당하는 변수 적재

-  `Heap` 영역에 생성된 데이터의 참조 값이 할당됨

- 메서드가 호출될 때 메모리에 할당, 메서드 종료시 메모리에서 삭제됨.

- 자료구조 `Stack` 구조, `LIFO(Last In First Out)`

- 각 `Thread` 마다 자신만의 `Stack`을 가짐

- `Thread`는 다른 `Thread`에 접근할 수 없으나 `static`, `Heap` 영역을 공유하여 사용 가능하다.

# Heap 영역

- `JVM`이 관리하는 프로그램 상에서 데이터를 저장하기 위해 런타임 시 동적으로 할당하여 사용하는 영역 참조형(Reference Type) 데이터 타입을 갖는 객체(인스턴스), 배열 등이 저장되는 공간

- 단 `Heap` 영역에 있는 오브젝트들을 가리키는 레퍼런스 변수는 `stack`에 적재

- `Heap` 영역은 `Stack` 영역과 다르게 보관되는 메모리가 호출이 끝나더라도 삭제되지 않고 유지됨. 그러다 어떤 참조 변수도 `Heap` 영역에 있는 인스턴스를 참조하지 않게 된다면, `GC`(가비지 컬렉터)에 의해 메모리에서 청소됨.

- `Stack`은 스레드 갯수마다 각각 생성되지만 `heap`은 몇개의 스레드가 존재하든 상관없이 단 하나의 `heap` 영역만 존재



# 그림 설명

```java
public class MemoryExample {
    public static void main(String[] args) {
        int x = 10;          // 기본 타입 (스택)
        String name = "John"; // 참조 타입 (힙)
        
        Person person1 = new Person("Alice", 25);  // 객체 생성 (힙)
        Person person2 = person1;  // 참조 복사
    }
}

class Person {
    String name;     // 참조 타입 필드
    int age;         // 기본 타입 필드
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```
<a href="https://github.com/LeeNaYoung240/LeeNaYoung240.github.io/assets/107848521/a4537881-3c6d-441c-b5b0-33a0ed9bf518" class="popup img-link"><img src="https://github.com/user-attachments/assets/a4537881-3c6d-441c-b5b0-33a0ed9bf518" alt="1" loading="lazy"></a>


스택(Stack) 메모리 특성

-   `args`: 메인 메서드의 인자
-   `x`: 숫자 10
-   `name`: 문자열을 가리키는 주소
-   `person1`, `person2`: 객체를 가리키는 참조값
- 특징 : 후입선출(LIFO) 구조, 정적 메모리 할당

힙(Heap) 메모리 특성

-   "John"이라는 문자열 객체
-   Person 객체 (name과 age 가지고 있음)
- 특징 : 동적 메모리 할당, 가비지 컬렉터 관리

---

# 참고 🙇🏻‍♀️

[참고한 블로그1](https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EA%B7%B8%EB%A6%BC%EC%9C%BC%EB%A1%9C-%EB%B3%B4%EB%8A%94-%EC%9E%90%EB%B0%94-%EC%BD%94%EB%93%9C%EC%9D%98-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EC%98%81%EC%97%AD%EC%8A%A4%ED%83%9D-%ED%9E%99)


[참고한 블로그 2](https://velog.io/@b2b2004/Java-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EA%B5%AC%EC%A1%B0Method-Stack-Heap)