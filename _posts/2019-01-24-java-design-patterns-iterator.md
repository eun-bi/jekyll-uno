---
title:  "[디자인패턴] Iterator 패턴"
date:   2019-01-24 11:41:24
categories: [디자인패턴]
tags: [디자인패턴]
comments: true
---




#### **Iterator 패턴 (반복자)**  

무엇인가 많이 모여있는 것 중에서 하나씩 `순서대로` 끄집어내어 열거하면서 전체를 처리하는 일을 할 때 사용  
- for 문에서 여러 원소가 모여있는 배열의 각 원소를 차례대로 선택하는데 사용되는 루프 변수 i의 역할  

**클래스 다이어그램**  
![image1](http://eun-bi.github.io/images/posting/0124_8.PNG)  
- Iterator (반복자) : 원소를 하나씩 끄집어낼 때 사용할 공통된 메소드(hasNext() 와 next())를 선언한 인터페이스  
- ConcreteIterator (구체적인 반복자) : Iterator 인터페이스를 실제로 구현하는 클래스  
- Aggregate(집합체) : Iterator를 만들어내는 인터페이스  
- ConreateAggregate(구체적인 집합체) : Aggregate 인터페이스를 실제로 구현하는 클래스로 ConcreteIterator(구체적인 반복자) 객체를 생성  

**패턴 활용 예제**  
책꽂이에 책을 넣은 후 순서대로 하나씩 끄집어 내어 책 이름을 표시하는 프로그램  
![image2](http://eun-bi.github.io/images/posting/0127_1.PNG)  
- BookShelf 클래스 : 책꽂이 (Aggregate 구현)
- BookShelfIterator 클래스 : 책꽂이에서 책을 하나씩 끄집어낼 때 사용하는 Iterator  
- code : [Github](https://github.com/eun-bi/java-design-patterns/tree/master/Iterator/src/example)  


**장점 및 특징**  
1. 하나를 수정했을 시, 코드 수정을 줄일 수 있음
 -각 집합체의 원소를 끄집어낼 때 Iterator 의 hasNext() 와 next() 메소드를 사용하므로 집합체가 어떻게 원소를 가지고 있는지 상관이 없음. 따라서 집합체 구현 부분이 수정이 되더라도 iterator 를 이용해 원소를 끄집어내는 방법은 동일하므로 수정할 필요가 없음
2. 여러 종류의 Iterator 추가 용이
3. Aggregate 클래스와 Iterator 클래스는 밀접하게 관련

---
**Reference**
- 영진닷컴, 『Java 언어로 배우는 디자인 패턴 입문』  
