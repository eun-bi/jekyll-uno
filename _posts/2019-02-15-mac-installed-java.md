---
title:  "[JAVA] mac os에 java 설치하기"
date:   2019-02-15 22:34:24
categories: [JAVA]
tags: [JAVA]
comments: true
---

이번에 노트북을 `맥북 프로` 로 바꾸게 되어 window를 벗어났더니 ... 제일 수고스러운거는 그 많은 개발 프로그램들 다시 인스톨 해야한다. 익숙지 않아 어려운게 이만저만이 아니다. 그치만 하루 사용하고 든 생각은 확실히 내 기준 윈도우보다 깔끔하게 제공해준다는거(?)랑 트랙패드 사용도도 높고 키보드 키감도 굉장히 좋다 ! 또 무엇보다 내 낡았던.. 노트북에 비해선 상당히 빠르다는거가 최고. 그치만 다른 키보드 배치 (특히 command ^^)에 익숙해질 필요가 있다.  

여튼 제일 기본이 되는 .. java 를 설치하고 환경 변수를 설정하는 법을 정리해보려 한다. (mac에서 git 사용도 익히려 함)  + 안스랑 이클립스도 설치 완료 ..  


---  

먼저, [JDK을 다운로드](https://www.oracle.com/technetwork/java/javase/downloads/index.html) 한다. 이 때, 난 8버전으로 설치했고 운영체제에 맞는 파일을 다운받아 설치해주었다.  

설치 후, `터미널`에 명령어 작성  

```python
cd /Library/Java/JavaVirtualMachines
```  

```python
ls
```  
작성하면 설치한 jdk 버전을 확인할 수 있음  
ex) jdk1.8.0_201.jdk  

```python
cd /Library/Java/JavaVirtualMachines/위에서 확인한 jdk 버전/Contents/Home/
```  

```python
vi ~/.bash_profile
```  
i로 편집모드로 설정해 작성할 수 있도록 한 후,  

```python
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk버전/Contens/Home
```  
붙여넣기 한 후 :wq 해서 빠져나오면 환경변수 설정 완료!  


```python
java -version
```  
으로 설치된 java 버전을 확인할 수 있다 !  
