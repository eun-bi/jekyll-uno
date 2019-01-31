---
title:  "[디자인패턴] Factory Method 패턴"
date:   2019-01-31 10:36:24
categories: [디자인패턴]
tags: [디자인패턴]
comments: true
---


#### **Factory Method 패턴**  
`상위 클래스`에서 인스턴스 만드는 방법을 결정하고, `하위 클래스`에서 인스턴스를 실제로 생성하는 디자인 패턴  
- Main에서 직접 인스턴스를 생성하지 않고 `공장`을 통해 `구체적인 제품 생성`을 함  


**클래스 다이어그램**  
![image1](http://eun-bi.github.io/images/posting/0131_1.PNG)  

- Product (제품) : 제품을 표현한 추상 클래스  
- ConcreteProduct (구체적 제품) : 추상 클래스를 상속받아 구현한 클래스로 구체적인 제품을 나타내는 클래스  
- Creator (생산자) : 인스턴스를 만드는 방법 등 API를 결정하는 factory method를 선언한 클래스로 인스턴스를 만드는 방법을 결정  
- ConcreteCreator (구체적 생산자) : 추상 클래스를 상속받아 구현한 하위 클래스로 인스턴스를 실제로 생성  

**패턴 활용 예제**  

Factory Method가 선언되어 있는 추상 클래스를 상속받은 하위 클래스에서 실제로 인스턴스를 생성하는 Factory Method 패턴을 이용해 IDCardFactory 공장을 세우고 IDCard 를 생산하고 사용하는 프로그램  

![image2](http://eun-bi.github.io/images/posting/0131_2.PNG)  
code : [Github](https://github.com/eun-bi/java-design-patterns/tree/master/Factory-Method/src)  

- Factory 클래스 : createProduct() 메소드(제품 생산), registerProduct() 메소드 (제품 등록) 선언으로 인스턴스를 만드는 방법을 명시하였으므로 Factory method  
- IDCardFactory 클래스 (공장) : 추상 클래스를 상속받아 인스턴스(IDCard)를 실제로 생성하는 하위 클래스  

**장점 및 특징**  
1. 코드의 확장에 용이  
-프레임워크와 구체적인 공장 및 제품을 분리하여 구현해 같은 프레임워크를 이용해서 다른 '공장'과 다른 '제품'을 추가할 수 있음  
2. 클라이언트에서 직접 인스턴스를 생성하지 않고 `공장`을 통해 인스턴스를 생성하기 때문에 제품을 어떻게 생산하는지에 대해 몰라도 됨. 따라서, 생산되는 제품을 바꿔도 클라이언트의 코드는 바뀌지 않음  


---
**Reference**
- 영진닷컴, 『Java 언어로 배우는 디자인 패턴 입문』  
