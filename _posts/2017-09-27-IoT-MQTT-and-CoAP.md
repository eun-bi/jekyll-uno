---
title:  "[IoT] 경량 프로토콜 MQTT / CoAP"
date:   2017-09-27 20:28:24
categories: [IoT]
tags: [IoT]
comments: true
---


사물인터넷을 위한 경량화된 통신 프로토콜 중 대표적인 두 가지를 정리해보고자 한다.  
`MQTT`와 `CoAP` 은 저전력 통신이나 대역폭이 작은 네트워크에서 동작할 수 있도록 설계한 `경량 통신 프로토콜`이다.  



### **MQTT (Message Queue for Telemetry Transport)**

![image1](http://eun-bi.github.io/images/posting/1224_7.png)

- Publish-Subscribe 모델
  - Publisher가 Topic을 발행하면 Topic을 구독하는 모든 클라이언트에게 message를 전송한다.
    (이 때, Topic을 발행하는 Publisher와 Topic을 구독하는 Subscriber는 모두 Broker에 대한 클라이언트)

- MQTT Broker : 각종 장치에서 보내주는 메시지를 수집하고 수집한 메시지를 다시 필요한 장치들에게 전송해주는 역할
(중간에서 서버 역할을 함)
   - 대표적인 MQTT Broker 프로그램 : ‘Mosuitto’, ‘RabbitMQ’ 등

- TCP 기반  
![image2](http://eun-bi.github.io/images/posting/1224_8.png)  

- 세 단계의 QOS(Quality of Service)를 제공
: 장치들의 처리 능력, 네트워크 대역폭, 메시지 오버헤드 등 주변상황에 맞게 시스템이 동작하기 위함
   - QOS = 0 : 메시지가 최대 한 번 전송 or 전혀 전송되지 않음
   메시지 손실 위험이 늘어나지만 가장 빨리 전송
   - QOS = 1 : 메시지가 적어도 한 번 전송
   수신자가 수신할 때까지 다시 송신  
    → 수신자가 메시지를 중복으로 수신하고 처리할 가능성이 있음
   - QOS = 2 : 메시지는 항상 한 번 전송
   메시지의 핸드셰이크 과정을 추적 → 중복 처리 가능성 X
   안전하고 높은 품질을 보장하지만 가장 느린 전송

- 암호화가 포함되어 있지 않음 - 'openSSL' 활용
  → 통신에 오버헤드를 더함   


### **CoAP (Constrained Application Protocol)**

![image3](http://eun-bi.github.io/images/posting/1224_9.png)

- Request-Response 모델 (HTTP와 동일)
- REST 구조 기반  
 → GET, PUT, POST, DELETE 등의 메소드, 응답 코드 등을 사용
- 확인형(Confirmable), 비확인형(Non-confirmable), 승인(Acknowledge), 리셋(Reset) 네 가지 메시지 형 정의
  - 신뢰성 있는 메시지를 전송할 경우 확인형 메시지를 전송
  - 수신자가 자료나 요청을 전달 받았을 경우에는 승인 메시지를 전송
  - 수신자가 수신한 자료나 요청을 처리할 수 없을 경우에는 승인 메시지 대신 리셋 메시지를 전송
  - 비확인형 메시지는 주기적으로 센서 자료 값을 얻어오는 경우처럼 모니터링 방식의 경우 확인이나 응답도 요구되지 않는 메시지에 사용
- UDP 기반  
![image4](http://eun-bi.github.io/images/posting/1224_10.png)


### **MQTT와 CoAP 비교**

![image4](http://eun-bi.github.io/images/posting/1224_11.png)






---
기존 포스팅에서 옮겨옴  
(<https://blog.naver.com/uko02111/221106656428>)  
