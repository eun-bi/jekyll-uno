---
title:  "[Django] Django-MySQL 연동"
date:   2018-01-15 3:33:24
categories: [Django]
tags: [Django]
comments: true
---


Django는 기본적으로 sqlite 데이터베이스를 사용하는데,  
간단한 설정만으로 MySQL 데이터베이스를 사용할 수 있어서 연동하게 되었다.  

---  

먼저, `pymysql` 을 설치해준다.  

```command
pip install pymysql  
```  

추가로 settings.py의 맨 위에 작성해준다.  

```python
import pymysql

pymysql.install_as_MySQLdb()
```  
`settings.py` 의 DATABASES 부분을 수정해준다.  
원래는 sqlite를 사용하므로 수정해 MySQL DB와 연결해준다.  

![image1](http://eun-bi.github.io/images/posting/1225_1.png)  

이 경우, 위에 작성한 데이터베이스명과 동일한 데이터베이스가 존재하지 않을 시에 에러가 발생한다 ..  
따라서 MySQL Workbench에서 미리 데이터베이스를 생성해줘야 한다.  

```command
python manage.py makemugrations
python manage.py migrate
```  

migrate 해 주면 데이터베이스 연동 완료!  

![image2](http://eun-bi.github.io/images/posting/1225_2.png)  


Workbench 에서 데이터베이스가 django와 연동되어 테이블이 자동으로 생성된 것을 확인할 수 있다.  


![image3](http://eun-bi.github.io/images/posting/1225_3.png)  



---
기존 포스팅에서 옮겨옴  
(<https://blog.naver.com/uko02111/221185182121>)  
