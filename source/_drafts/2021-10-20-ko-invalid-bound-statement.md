---
title: Invalid bound statement (not found) 에러 처리
tags:
  - invalidboundstatement
  - myBatis
  - mybatis error
thumbnail: /images/post/2021-10-20/invalidbound1.jpg
categories:
  - 한국어 #(예) 깃허브
  - 학습 #- 서브카테고리명 #(예) 헥소
  - JAVA
---

![](/images/post/2021-10-20/invalidbound1.jpg)

<br>

현재 프로젝트의 경로는 위와 같다.

<br>

![](/images/post/2021-10-20/invalidbound2.jpg)

<br>

기존의 내 코드는 이렇게 되어 있었다.
설정파일들을 아무리 수정해봐도, 자료를 찾아봐도 에러가 해결되지 않았다.
발생한 에러는 아래와 같다.

<br>

```html
org.apache.ibatis.binding.BindingException: Invalid bound statement (not found):
com.bny.dao.UserDao.getUser at
org.apache.ibatis.binding.MapperMethod$SqlCommand.<init>(MapperMethod.java:235) at org.apache.ibatis.binding.MapperMethod.<init>(MapperMethod.java:53) at
    org.apache.ibatis.binding.MapperProxy.lambda$cachedMapperMethod$0(MapperProxy.java:62)
    at java.util.concurrent.ConcurrentHashMap.computeIfAbsent(Unknown Source) at
    org.apache.ibatis.binding.MapperProxy.cachedMapperMethod(MapperProxy.java:62)
    at org.apache.ibatis.binding.MapperProxy.invoke(MapperProxy.java:57)</init></init>
```

<br>

이 에러로 장작 4시간을 싸우고 있었던 것 같다.
온갖 방법들을 써가며 안되겠지 안되겠지 하는 찰나에...

<br>

```html
정보: Mapped URL path [/fonts/**] onto handler 'org.springframework.web.servlet.resource.ResourceHttpRequestHandler#1' 4월 09, 2019 6:02:20 오후 
    org.springframework.web.servlet.handler.SimpleUrlHandlerMapping registerHandler
정보: Mapped URL path [/images/**] onto handler 'org.springframework.web.servlet.resource.ResourceHttpRequestHandler#2' 4월 09, 2019 6:02:20 오후
    org.springframework.web.servlet.handler.SimpleUrlHandlerMapping registerHandler
정보: Mapped URL path [/js/**] onto handler 'org.springframework.web.servlet.resource.ResourceHttpRequestHandler#3' 4월 09, 2019 6:02:20 오후
    org.springframework.web.servlet.handler.SimpleUrlHandlerMapping registerHandler
정보: Mapped URL path [/sass/**] onto handler 'org.springframework.web.servlet.resource.ResourceHttpRequestHandler#4' 4월 09, 2019 6:02:20 오후
    org.springframework.web.servlet.handler.SimpleUrlHandlerMapping registerHandler
정보: Mapped URL path [/publishing/**] onto handler 'org.springframework.web.servlet.resource.ResourceHttpRequestHandler#5'testQuery xxxx@naver.com 20 4월 09, 2019 6:02:20 오후
    org.springframework.context.support.GenericApplicationContext doClose 
정보: Closing org.springframework.context.support.GenericApplicationContext@1081592: startup date [Tue Apr 09 18:02:19 KST 2019]; root of context hierarchy
```

<br>

성공적인 결과값

원인은 `nameSpace에` 있었다.

현재 `UserDaoImpl.java` 파일이 com.bny.dao 패키지에 있었는데 나는 `mapper.xml` 파일의 namespace와 java파일의 namespace가 일치만 하면 되는 줄 알았다. 하지만 namespace의 경로도 현재 java파일의 경로와 일치시켜야 제대로 작동되었다.

<br>

![](/images/post/2021-10-20/invalidbound3.jpg)

<br>

패키지 까지만 작성한 경우에는 그 패키지 내에 `파일이 한개만 있을 경우 자동 맵핑`이 되지만 두개 이상 있을 경우 파일명까지 namespace에 적어줘야 맵핑을 시키기 때문에 해당 `파일의 경로와 명까지 정확하게 작성`해야 정상적으로 작동이 된다.
