---
title:  "[Android] 앱 배포를 위한 Release APK, keystore 생성"
date:   2017-09-06 23:55:24
categories: [Android]
tags: [Android]
comments: true
---

구글 플레이 스토어에 업로드하기 위해서는
기존에 빌드될 때 생성되는 debug apk 가 아닌 Release apk 가 필요하다.

Android Studio 에서
`Run > Build > Generate Signed APK...`

기존에 존재하는 key store 가 없을 시 create new... 클릭 후
key가 생성될 path, password, 개발자 정보를 적은 후 OK
설정한 path 에 들어갈 경우 `.jks 파일`이 저장된 것을 확인할 수 있다.

또한, 프로젝트 파일 > app 경로에 apk 파일이 추출된 것을 확인할 수 있음!

![image](http://eun-bi.github.io/images/posting/1224_2.PNG)


**successfully !**

**+**
추후에는 이미 key store 를 등록했으므로, path 랑 password을 입력하면 됨

---
기존 포스팅에서 옮겨옴
(<https://blog.naver.com/uko02111/221091096750>)
