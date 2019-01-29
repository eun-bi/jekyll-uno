---
title:  "[디자인패턴] Adapter 패턴"
date:   2019-01-27 20:28:24
categories: [디자인패턴]
tags: [디자인패턴]
comments: true
---


#### **Adapter 패턴**  

이미 제공되어 있는 것을 그대로 사용할 수 없는 경우 `이미 제공되어 있는 것`과 `필요한 것` 사이의 간격을 메울 때 사용  

- 상속(inheritance) 을 이용한 Adapter 패턴
- 위임(delegation) 을 이용한 Adapter 패턴

**클래스 다이어그램**  
1. 상속을 이용한 Adapter 패턴  
![image1](http://eun-bi.github.io/images/posting/0129_1.PNG)  
: 필요한 메소드를 가지는 인터페이스를 구현(implements)하고 이미 제공되어 있는 클래스를 상속(extends) 받아 구현  
2. 위임을 이용한 Adpater 패턴  
![image2](http://eun-bi.github.io/images/posting/0129_2.PNG)  
: 필요한 메소드를 가지는 추상메소드를 상속(extends)받고 이미 제공되어 있는 클래스를 인스턴스화하여 구현  

- Target(대상) : 필요한 메소드를 제공(필요한 것)  
- Client(의뢰자) : Target 역할의 메소드를 이용  
- Adaptee(변경되는 측) : 이미 준비되어 있는 메소드를 제공(이미 제공되어 있는 것)  
- Adpater : Target 역할을 실제로 충족시키는 역할로 이미 제공되어 있는 것(Adaptee)과 필요한 것(Target) 사이의 간격을 메워줌

**패턴 활용 예제**  

문자열에 앞뒤에 괄호와 별표을 붙여 문자열을 표시하는 프로그램  
(Banner 클래스라는 기존의 클래스를 이용해서, 필요한 인터페이스(클래스)인 Print를 구현하는 PrintBanner 클래스를 이용해 일을 처리하는 프로그램)

1. 상속을 이용한 Adapter 패턴  
![image3](http://eun-bi.github.io/images/posting/0129_3.PNG)
code : [Github (example1_inheritance)](https://github.com/eun-bi/java-design-patterns/tree/master/Adapter/src/example1_inheritance)  

- Banner 클래스 (Adaptee) : 이미 제공되어 있는 것  
- Print 인터페이스 (Target) : 필요한 것 (인터페이스)  
- PrintBanner 클래스 (Adapter) : 필요한 것(Print 인터페이스)을 사용하기 위해 이미 제공하는 것(Banner 클래스)을 재활용 함. 이 때, 필요한 것(Print 인터페이스)을 구현(implements)하고 이미 제공하는 것(Banner 클래스)을 상속(extends)받아 구현  

2. 위임을 이용한 Adpater 패턴  
![image4](http://eun-bi.github.io/images/posting/0129_4.PNG)  
code : [Github (example2_delegation)](https://github.com/eun-bi/java-design-patterns/tree/master/Adapter/src/example2_delegation)  

- Banner 클래스 (Adaptee) : 이미 제공되어 있는 것  
- Print 클래스 (Target) : 필요한 것 (추상 클래스)  
- PrintBanner 클래스 (Adapter) : 필요한 것(Print 인터페이스)을 사용하기 위해 이미 제공하는 것(Banner 클래스)을 재활용 함. 이 떄, 필요한 것(Print 클래스)를 추상 클래스로 정의하였기 때문에 상속(extends) 받아 구현 함. java는 다중 상속을 지원하지 않기 때문에 이미 제공하는 것(Banner 클래스)을 상속받을 수 없으므로 Banner 클래스의 인스턴스에게 위임  


**패턴 활용 응용**  

"프로퍼티이름=값" 형식의 내용을 갖는 파일로부터 값을 읽어오거나 설정하는데 사용하는 클래스인 java.util.Properties를 이용해 파일을 읽고 쓰는 프로그램  

1. 상속을 이용한 Adapter 패턴  
![image5](http://eun-bi.github.io/images/posting/0129_5.PNG)  
code : [Github (application1_inheritance)](https://github.com/eun-bi/java-design-patterns/tree/master/Adapter/src/application1_inheritance)  

- java.util.Properties (Adaptee) : 이미 제공되는 것  
- FileIO 인터페이스 (Target) : 필요한 것 (인터페이스)  
- FileProperties (Adapter) :  필요한 메소드는 FileIO에 정의한 메소드들인데 이미 제공되는 클래스인 java.util.Properties에서 제공하므로 Properties 클래스의 메소드를 재활용 함. 이 때, FileIO 인터페이스를 구현(implements)하고 Properties 클래스를 상속(extends)받아 구현

2. 위임을 이용한 Adapter 패턴  
![image6](http://eun-bi.github.io/images/posting/0129_6.PNG)  
code : [Github (application2_delegation)](https://github.com/eun-bi/java-design-patterns/tree/master/Adapter/src/application2_delegation)  

- java.util.Properties (Adaptee) : 이미 제공되는 것  
- FileIO 클래스 (Target) : 필요한 것 (추상 클래스)  
- FileProperties (Adapter) : 필요한 메소드는 FileIO에 정의한 메소드들인데 이미 제공되는 클래스인 java.util.Properties에서 제공하므로 Properties 클래스의 메소드를 재활용 함. 이 때, 필요한 것인 FileIO 를 추상 클래스로 정의하였기 때문에 상속(extends) 받아 구현 함. java는 다중 상속을 지원하지 않기 때문에 이미 제공하는 Properties 클래스를 상속받을 수 없으므로 위임을 사용해 Properties 의 인스턴스를 가짐  


**장점 및 특징**  
- 코드의 재사용에 유용  
-기존의 클래스를 수정하지 않고도 필요한 클래스로 만들어 사용할 수 있음  
-기존 클래스의 코드가 없어도 메소드 프로토타입(메소드명, 인자 개수, 인자형, 반환형 등)만 알면 패턴 적용이 가능해 새로운 인터페이스(API)에 기존의 클래스를 맞춰 구현 가능  


---
**Reference**
- 영진닷컴, 『Java 언어로 배우는 디자인 패턴 입문』  
