---
title:  "[Django] 자주 사용하는 명령어 정리"
date:   2018-01-19 1:19:24
categories: [Django]
tags: [Django]
comments: true
---


이전 동아리에서 파이썬 스터디를 했었는데, 그 때 파이썬을 익히고 후에 뭘 할 지 고민하다가 `Django` 란 웹 애플리케이션 프레임워크를 공부해보자! 해서 입문하게 되었다.  


백엔드는 해도 해도 어렵고.. 게다가 다른 언어에 비해 간단한 파이썬 문법에 쉽게 익숙해지지 않아 처음엔 적응하는데 힘들고 학기 중에는 도저히 따로 공부할 시간이 안 돼서 그 때 공부했던걸 토대로 방학을 맞이하여 다시 정리해보고자 한다!  

---  

**가상환경 실행**  

```command
[가상환경명]\Scripts\activate
```  


**django-admin을 이용해 프로젝트 생성**  

```command
django-admin startproject [프로젝트명]
```  


**Migrations 파일 생성**  

```command
python manage.py makemigrations
```  

**Migration 을 데이터베이스에 저장 (실제 테이블 생성 및 수정)**  

```command
python manage.py migrate
```  

**생성한 프로젝트 내에 애플리케이션 생성**  

```command
python manage.py startapp [애플리케이션명]
```  

**서버 실행**  

```command
python manage.py runserver
```  


---

**Reference**  
- djangogirls  
 [https://tutorial.djangogirls.org/ko/](https://tutorial.djangogirls.org/ko/)
- 예제로 배우는 파이썬 프로그래밍  
 [http://pythonstudy.xyz/Python/Django](http://pythonstudy.xyz/Python/Django)  



 ---
 기존 포스팅에서 옮겨옴  
 (<https://blog.naver.com/uko02111/221189078746>)  
