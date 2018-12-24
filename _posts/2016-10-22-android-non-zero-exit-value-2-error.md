---
title:  "[Android] finished with non-zero exit value 2 에러 해결"
date:   2016-10-22 2:58:24
categories: [Android]
tags: [Android]
comments: true
---


```java
com.android.build.api.transform.TransformException:
com.android.ide.common.process.ProcessException:
org.gradle.process.internal.ExecException:
Process 'command
'C:\Program Files\Java\jdk1.8.0_65\bin\java.exe''
finished with non-zero exit value 2
```



빌드하자마자 나는 에러로, 봐도 왜 에러인지 이해가 안돼서 구글링 했더니 봐도 이해가 안되는 에러,,
추가한 라이브러리의 메소드 수가 많거나, 라이브러리를 중복선언해서 생긴 문제라고 하는데
결론은 라이브러리 문제인걸로 .. !


결국은 어떻게 해서 해결하긴 했는데 왜 해결됐는지도 의문
`build.gradle 에 defaultConfig` 안에  **multiDexEnabled true**  를 넣어주었더니 간단히 해결



```java
defaultConfig {
       multiDexEnabled true
}
```


---
기존 포스팅에서 옮겨옴
(<https://blog.naver.com/uko02111/220842432781>)
