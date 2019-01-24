---
title:  "[디자인패턴] UML(Unified Modeling Language)"
date:   2019-01-16 21:02:24
categories: [디자인패턴]
tags: [디자인패턴]
comments: true
---

디자인 패턴 공부를 위한 기본 클래스 다이어그램 개념 및 작성법 공부 중 ..  완전히 내 것으로 만들기 !

---

####**UML(Unified Modeling Language)**
시스템을 시각화하거나 요구 사항 명세서 또는 설계를 문서화하기 위한 표현 방법으로 클래스나 인터페이스의 `관계를 표현`하기 위해 사용  


####**클래스 다이어그램**  
클래스나 인스턴스, 인터페이스 등 간의 `정적인 관계`를 표현  

![image1](http://eun-bi.github.io/images/posting/0124_1.PNG)  
각각의 클래스는 직사각형으로 표현하며 클래스 간의 관계에 따라 이어지는 선의 모양이 결정된다.

**상속(extends) 관계**  

```Java
/* 상위 클래스 (부모 클래스) */
abstract class ParentClass{
  int field1;
  static char field2;
  abstract void methodA();
  double methodB(){
    // ...
  }

/* 하위 클래스 (자식 클래스, 파생 클래스)*/
  class childClass extends ParentClass{
    void methodA(){
      // ...
    }
    static void methodC(){
      // ...
    }
  }
}
```  
![image2](http://eun-bi.github.io/images/posting/0124_2.PNG)  
상속 관계는 두 클래스 간의 관계를 화살표가 붙은 `실선`으로 표현한다. 이 때, 화살표는 하위 클래스에서 상위 클래스로 향한다. `추상클래스`인 PrentClass 클래스와 `추상메소드`인 methodA의 이름은 `이탤릭체`로 표현하며 `정적 변수`인 field2와 `정적 메소드`인 methodC 의 이름에는 `밑줄`을 추가한다.  

- 추상 클래스(abstract class) : 추상 메소드를 하나 이상 가지고 있는 클래스   
- 추상 메소드(abstract method) : 구현 부분이 없는 메소드로 자식 클래스가 구현  
- 정적 필드(static field) : 객체가 아니라 클래스에 포함된 변수로 객체마다 하나씩 생성되지 않음  
- 정적 메소드(static method) : 객체가 아니라 클래스에 포함된 메소드로 정적 메소드나 정적 필드만을 접근할 수 있음  



**인터페이스 구현(implements)**  
```Java
interface Printable{
  abstract void print();
  abstract void newPage();
}

class PrintClass implements Printable{
  void print(){
    // ...
  }

  void newPage(){
    // ...
  }
}
```  
![image3](http://eun-bi.github.io/images/posting/0124_3.PNG)  
PrintClass 클래스가 Printable `인터페이스`를 구현하고 있으므로 PrintClass는 반드시 print()와 newPage() 메소드를 구현해야 한다. 인터페이스와 구현 클래스의 관계는 화살표가 붙은 `점선`으로 표현한다. 이 때, 화살표는 구현 클래스에서 인터페이스로 향한다.  
- 인터페이스(interface) : 구현 부분이 생략되어 있는 메소드들의 이름만 선언되어 있는 특수한 클래스  


**집합(Aggregation) 관계**  
```Java
class Color{
  // ...
}

class Fruit{
  Color color;
  // ...
}

class Basket{
  Fruit[] fruits;
  // ...
}
```  
![image4](http://eun-bi.github.io/images/posting/0124_4.PNG)  
Bascket 클래스는 Fruit 클래스의 인스턴스를 가지며 Fruit 클래스는 Color 클래스의 인스턴스를 가진다. 가지고 있는 인스턴스 변수를 클래스 다이어그램에 작성해줘야 하며 `마름모`가 붙은 실선으로 표현한다.  

**액세스 제어**  
```Java
class Something{
  private int priateField;
  protected int protectedField;
  public int publicField;
  int packageField;

  private void privateMethod(){}

  protected void protectedMethod(){}

  public void publicMethod(){}

  void packageMethod(){}
}
```  
![image5](http://eun-bi.github.io/images/posting/0124_5.PNG)  
- +가 붙은 경우 : public인 메소드나 필드를 나타내며 모든 경우 액세스 가능  
- -가 붙은 경우 : private인 메소드나 필드를 나타내며 동일한 클래스에서만 액세스 가능
- #이 붙은 경우 : proteced인 메소드나 필드를 나타내며 동일한 클래스나 하위 클래스 또는 패키지 내의 클래스만 액세스 가능  
- ~이 붙은 경우 : 동일한 패키지 내에서만 액세스할 수 있는 메소드나 필드  


**연관(Association) 관계**  
![image6](http://eun-bi.github.io/images/posting/0124_6.PNG)  
클래스간의 관계를 나타내기 위해 클래스를 연결하고 그 위에 관계를 나타내는 이름을 붙이며 삼각형 방향으로 해석한다.  

####**시퀀스 다이어그램**  
프로그램이 동작할 떄, 객체들 사이의 메소드들이 어떤 순서로 실행(호출) 되는지를 표현한 것으로 `동적인 관계`를 표현한다.  
```Java
class Client{
  Server server = new Server();
  void work(){
    server.open();
    server.print("Hello");
    server.close();
  }
  // ...
}

class Server{
  Device device = new Device();
  void open(){
    // ...
  }
  void print(String s){
    device.write(s);
    // ...
  }
  void close(){
    // ...
  }
  // ...
}

class Device{
  void write(String s){
    // ...
  }
}
```  
![image7](http://eun-bi.github.io/images/posting/0124_7.PNG)  
각각의 인스턴스는 직사각형 안에 `콜론 :` 뒤에 클래스명을 표기하며 인스턴스 아래 점선은 생명선으로 인스턴스가 존재하는 동안 존재한다. 객체가 cpu를 얻어서 실행이 되어 활동하는 동안에는 직사각형으로 표시한다. 또한, 객체 간 호출과 반환을 화살표로 표시한다.  



---
**Reference**
- 영진닷컴, 『Java 언어로 배우는 디자인 패턴 입문』
