### 빌더 패턴이란?
기존 생성자로 생성하던 객체를 아래와 같이 빌더 패턴을 사용하여 객체를 생성하는 것이다.
```java
Member member = Member.builder()
                .name("ykm")
                .money("100")
                .height("185")
                .age("22")
                .where("seoul")
                .build();

```
### 왜 빌더패턴을 사용하나? 
1. 생성자를 사용하여 객체를 생성할 경우 생성자 인자가 많아질수록 가독성이 나빠진다.  
```java
Test test = new Test("ykm", "100", "185", "22", "seoul");
```
각 인자가 무엇을 의미하는 지 알 수 없다. 
빌더패턴을 사용하면 각 인자가 무엇을 의미하는지 알 수 있다. 
```java
Member member = Member.builder()
                .name("ykm")
                .money("100")
                .height("185")
                .age("22")
                .where("seoul")
                .build();

```
2. 인자의 순서는 상관없다.
생성자의 경우는 인자의 순서를 꼭 지켜야 값이 엉뚱한데 설정되지 않는다.
하지만 빌더패턴을 사용할 경우 어떤 값을 먼저 설정하던 상관없다.
```java
Member member = Member.builder()
                .money("100")
                .name("ykm")
                .age("22")
                .where("seoul")
                .height("185")
                .build();

```
### 빌더패턴을 사용하려면?  
Lombok 어노테이션인 @Builder를 사용하면 된다. 
@Builder를 적용하고자 하는 클래스 위에 작성하기만 하면 된다.  
```java
@Builder
class Member {
  ...
}
```


