---
title:  "[디자인패턴] Template Method 패턴"
date:   2019-01-30 17:49:24
categories: [디자인패턴]
tags: [디자인패턴]
comments: true
---


#### **Template Method 패턴**  
`상위 클래스`에 템플릿 역할을 하는 메소드가 정의되어 처리의 흐름을 결정하고, `하위 클래스`에서 추상 메소드들을 실제로 구현해 구체적인 내용을 결정하는 디자인 패턴  


**클래스 다이어그램**  
![image1](http://eun-bi.github.io/images/posting/0130_1.PNG)  

- AbstractClass(추상 클래스) : 추상 메소드들을 호출한 템플릿 메소드 구현한 클래스로 처리의 흐름을 결정  
- ConcreteClass(구체적 클래스) : 추상 클래스를 상속받아 구현한 클래스로 구체적인 내용을 결정  

**패턴 활용 예제**  

Template Method가 선언되어 있는 추상 클래스를 상속받은 하위 클래스에서 실제로 일을 처리하는 Template Method 패턴을 이용해 문자열 상하좌우에 문자를 붙여서 출력하는 프로그램  

![image2](http://eun-bi.github.io/images/posting/0130_2.PNG)  
code : [Github](https://github.com/eun-bi/java-design-patterns/tree/master/Template-Method/src/example)  

- AbstractDisplay 클래스 (추상 클래스) : open(), print(), close() 는 추상메소드로 display() 메소드안에서 호출됨. 이 때, display() 메소드 내에서 처리의 흐름을 결정하였으므로 Template Method임
- CharDisplay 클래스, StringDisplay 클래스 (구체적 클래스) : open(), print(), close() 메소드를 구현하여 구체적인 실제 내용을 결정

**장점 및 특징**  
- 로직을 공통화 할 수 있음
-Template Method 패턴을 사용하지 않고 각각의 하위 클래스에 공통된 메소드가 반복되어 작성될 경우, 로직을 바꿔야 하는 경우 모든 클래스를 수정해야 함. Template Method 패턴을 사용할 경우에 부모 클래스인 추상 클래스에 공통된 로직을 집중시켜 수정이 줄어 들고 반복 작성하지 않아도 됨


---
**Reference**
- 영진닷컴, 『Java 언어로 배우는 디자인 패턴 입문』  
