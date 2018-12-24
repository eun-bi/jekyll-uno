---
title:  "[Android] Android 패키지명 변경"
date:   2017-09-07 00:52:24
categories: [Android]
tags: [Android]
comments: true
---

패키지 디렉토리를 선택해서 개별적으로 수정하기 위해서는
안드로이드 스튜디오 내에서 패키지의 논리적구조를 햡쳐서 보여주는 옵션을 해제해줘야 한다.

![image](http://eun-bi.github.io/images/posting/1224_3.PNG)  

`Compact Empty Middle Packages` 체크를 해제!

디렉토리 우클릭 후 Refactor > Rename 해서 디렉토리명 변경 후
Android Monitor 에서 'Do Refactor' 버튼 클릭

`+`
`bulid,gradle > applicationId` 에도 변경된 패키지명을 적용해줘야 한다.


---
기존 포스팅에서 옮겨옴
(<https://blog.naver.com/uko02111/221091129739>)
