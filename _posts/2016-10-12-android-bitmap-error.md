---
title:  "[Android] Bitmap too large to be uploaded into a texture 에러 해결"
date:   2016-10-12 02:43:24
categories: [Android]
tags: [Android]
comments: true
---

(이전에 작성했던 포스팅)

해결했던 문제도 계속 까먹고 다시 구글링하는 모습에 개발 관련 폴더를 만들었다.  

기록하는 좋은 습관 만들기


---

이미지를 적용하고 실행시키면 이미지는 보이지 않고 흰 화면만 보이는 문제.  
로그에는 _Bitmap too large to be uploaded into a texture_  라는 렌더링 오류가 뜬다.  

안드로이드 디바이스 해상도에 맞지 않게 이미지가 너무 커서 발생하는 문제로,  
구글링했더니 하드웨어 가속을 끄는 방법, 사이즈가 큰 이미지를 리사이징해서 띄우는 방법 등이 있었는데 제일 마음 편한 방법을 선택했다.  

각 디바이스 해상도에 맞는 이미지를 제공해주는 방법이다.  
`/res/drawable`에 drawable-hdpi, drawable-mdpi, drawable-xhdpi, drawable-xxhdpi, drawable-xxxhdpi
이미지를 각 해상도에 맞는 폴더에 넣어주면 된다.  


![image1](http://eun-bi.github.io/images/posting/1224_1.png)

이렇게 해 놓으면 알아서 디바이스에 맞는 해상도 이미지를 제공해주는 것 같다.(?)  
dp 개념도 언제 확실히 정리해야겠다.  

**+**

일종의 gui 가이드 툴? 인 [zeplin](https://zeplin.io/)을 디자인 하는 언니 덕분에 알게 됐는데,  
하나의 이미지를 올려도 알아서 위 형식으로 해상도별 이미지를 제공해주는 듯!  
디자이너랑 개발자랑 소통하기 좋은 툴이여서 유용하게 사용 중  

---

기존 포스팅에서 옮겨옴
(<https://blog.naver.com/uko02111/220834005460>)
