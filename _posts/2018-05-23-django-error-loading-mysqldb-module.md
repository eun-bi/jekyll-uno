---
title:  "[Django] Error loading MySQLdb module 에러 해결"
date:   2018-05-23 4:17:24
categories: [Django]
tags: [Django]
comments: true
---


윈도우에서는 MySQL 라이브러리를 import하는 과정에서 문제가 없었는데 ubuntu 환경에서 django 에 MySQL db를 연결하는 도중 예상치 못한 에러가 발생하였다.  


```command
ImportError: No module named 'MySQLdb'
```  

import error 가 떠서 mysqlclient 만 설치해주면 되는건데,,  
설치하려고 보니까  


![image](http://eun-bi.github.io/images/posting/1225_4.png)  

이건 뭐지 ,, 생전 처음보는 에러 발견  


```command
Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-install-ayr7zfwa/mysqlclient/
```  

구글링 결과 pip랑 python 버전 관련 문제인 것 같은데 도무지 해결을 못 하다가 드디어 해결했다.  


```Command
sudo apt-get install python-dev python3-dev
sudo apt-get install libmysqlclient-dev
pip3 install pymysql --user
pip3 install mysqlclient --user
```  

그냥  pip3 install pymysql 할 경우, 나의 경우는 permission error 가 뜨길래 뒤에 --user 옵션을 주었다.

이 방법으로 `mysqlclient` install 완료 !  


---
기존 포스팅에서 옮겨옴
(<https://blog.naver.com/uko02111/221281936857>)
