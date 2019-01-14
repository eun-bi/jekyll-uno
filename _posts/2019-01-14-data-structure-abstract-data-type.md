---
title:  "[자료구조] 추상자료형 (ADT:Abstract Data Type)"
date:   2019-01-14 21:35:24
categories: [자료구조]
tags: [자료구조]
comments: true
---

**추상자료형 (Abstract Data Type) (ADT) 이란 ?**  

구체적인 기능의 완성과정을 언급하지 않고, 순수하게 기능이 무엇인지를 나열한 것  


**ex) 지갑에 대한 추상자료형**
  -  카드 삽입    
  -  카드 추출    
  -  동전 삽입    
  -  동전 추출    
  -  지폐 삽입    
  -  지폐 추출  

**구조체 wallet**  

-지폐와 동전의 저장이 가능한 지갑 구조체  
:Wallet 이라는 자료형의 정의  

```Java
 typedef struct _wallet {
    int coin100Num;   // 100원짜리 동전의 수
    int bill5000Num;  // 5,000원짜리 지폐의 수
} Wallet;
```  

**Wallet 의 ADT**  

-Wallet 을 기반으로 제공할 수 있는 기능 관련 연산  
:구조체 정의만으로 자료형의 정의가 완성되는 것이 아님. 구조체에서 필요로 하는 연산을 함수를 이용해 정의해야  자료형의 정의가 완성됨  

```Java
int TakeOutMoney(Wallet * pw, int coinNum, int billNum); // 돈을 꺼내는 연산
void PutMoney(Wallet * pw, int coinNum, int billNum);    // 돈을 넣는 연산
```  

**구조체 Wallet의 정의는 ADT에 포함시켜야하는가?**  

```Java
int main(void){
   Wallet myWallet;
   PutMoney(&myWallet, 5, 10);
   ret = TakeOutMoney(&myWallet, 2, 5);
}
```  

이 책의 저자는 필요하다면 포함시켜도 되지만, 불필요한 것을 포함시키는 것은 바람직하지 못하다고 함. 돈을 넣고 꺼내는데, 구조체 Wallet의 멤버가 어떻게 구성되었는지 상관없기 때문에 굳이 포함시키지 않아도 된다는 것임.  

자료구조의 정의한 추상자료형(ADT) 를 기반으로 자료구조를 활용하는 main 을 정의해 구현할 수 있음. 이 때, 그 내부 구현을 알지 못해도 활용할 수 있도록 구현할 수 있음.  


---  

**Reference**  
- 책 <윤성우의 열혈 자료구조>  
(2016-1학기에 들었던 자료구조 수업 책 복습 중 )
