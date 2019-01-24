---
title:  "[Blog] Jekyll을 사용한 Github 블로그 정착기 + todo"
date:   2018-12-24 10:36:24
categories: [blog]
tags: [blog]
comments: true
---


기존에는 네이버 블로그 ([https://uko02111.blog.me/](https://uko02111.blog.me/))에 일상글 및 개발 중 헷갈렸던 이슈들을 기술하곤 했었는데,
따로 분류해서 관리하는게 좋을 것 같아서 (미루고 미뤄왔던..) 개발 전용 블로그를 새로 개설 했다 !!!

개발용 블로그로 티스토리, Github page 등 어떤 걸 사용할까 고민하다, Github page 로 선택하였다.
`Jekyll` 이란 정적 사이트 개발 툴로, markdown 을 사용하여 쉽게 구축할 수 있다.

블로그를 구축하면서 느낀 점은, 처음에는 '생각보다 쉽지 않다' 였다.
하지만 뭐든 처음이 두려운 법 .. 지금은 어느정도 숙지되어 오히려 더 편리한 것 같다.

무엇보다 좋은 점은 Git 사용을 생활화 할 수 있다는 점 !  
게시글을 작성할 때 에디터도 따로 제공해주지 않아서 게시글을 작성하고 push 하는 형태인데,
개발에 익숙하지 않은 사람은 조금 구축이 힘들 것 같지만 구축해가는 재미가 있는 것 같다.

하나 하나 직접 적용하고 생성할게 많아서 정리하고자 todo 리스트를 작성해보았다.



### **Todo - all done !**

- **Jekyll 테마 적용**
: 선택을 잘 하지 못하는 병에 걸려 테마 고르는데도 한참 걸렸다는,,
      테마가 다양하고 디자인도 다 예쁘다. ([Jekyll 테마](http://jekyllthemes.org/))
- **Github 블로그 구조에 대해 익히기**
: 보통 Jekyll 을 적용한 블로그는 구조가 비슷한데 구조가 복잡하지는 않아 몇 번 보고 익혔다.
그 중 `_config.yml` 파일은 기본 설정을 할 수 있는 파일이고 `_posts` 폴더 내에서 게시글들을 작성하고 관리할 수 있다.
- **markdown 문법 익히기**
: 블로그 게시글 작성을 위해 생소한 markdown 문법을 익히는 중.. 에디터는 Atom 사용중이다.
- **댓글 기능 적용을 위한 Disqus 및 페이스북 플러그인 사용**
: 기본적으로 댓글 기능이 제공되어 있지 않은 테마라 [Disqus](https://disqus.com/) 와 [페이스북 플러그인](https://developers.facebook.com/docs/plugins/comments/#configurator)으로 댓글 기능을 추가하였다.
- **방문자 통계를 위한 Google Analytics 사용**
: Jekyll 은 자체적으로 방문자 통계를 제공해주지 않기 때문에 가시적으로 방문자 통계를 제공하는 [애널리틱스](https://analytics.google.com/analytics)를 사용해 확인할 수 있게 되었다.
- **카테고리 생성**
: 내가 적용한 테마는 tag 기능을 제공해주지만 카테고리 기능은 제공해주지 않아서 따로 생성하였다.  

**+ 19.01.24 추가**  
- **검색엔진에 등록**  
: Jekyll 로 만든 깃허브 블로그는 검색할 시에 안 나와서 따로 등록을 해줘야 한다.. 수동으로 하나하나 설정해가는 재미 ^^ .. 그래도 다행인 것을 필요한 `sitemap.xml` 과 `feed.xml`파일이 내가 적용한 테마에는 생성되어 있어서 따로 작성하지 않아도 되었다. google에서 검색할 경우 노출되게 하기 위해 [Google Search Console](https://search.google.com/search-console/about?hl=ko&utm_source=wmx&utm_medium=wmx-welcome)에 사이트맵을 등록하였다.
![image1](http://eun-bi.github.io/images/posting/0124_9.PNG)  
또한, 네이버에서도 검색이 가능하도록 [네이버 웹마스터도구](https://search.google.com/search-console/about?hl=ko&utm_source=wmx&utm_medium=wmx-welcome)에 사이트를 등록하였다. (아직 등록 확인 중..)

- **광고를 위한 Google AdSense 사용**  
: 하나 하나 직접 추가해서 구현해야한다는 점이 조금은 귀찮을 수도 있지만 다양하게 확장할 수 있다는 점이 깃허브 블로그의 가장 큰 장점인 것 같다. 직접 광고도 추가해서 조금이나마 수익을 얻을 수도 있다는 것을 알아 추가하기로..! [Google AdSense](https://www.google.com/intl/ko_kr/adsense/start/#/?modal_active=none)에서 생성한 코드를 html 파일의 head 사이에 추가해주었다. (1일 정도 소요된다해서 확인 중..)

**+ (추가 예정)**

---
개발용 블로그 개설은 올해 To do 리스트 중 하나였는데 이루게 되어서 뿌듯하다.  
여태껏 공부했던거 복습할겸 정리도 하고 개발 중 헷갈린 것들도 작성해서 꾸준히 기록해놔야겠다.  
