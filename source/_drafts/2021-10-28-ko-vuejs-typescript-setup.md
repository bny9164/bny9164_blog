---
title: vuejs typescript기반 프로젝트 생성하기
tags:
  - vuejs
  - typescript
  - vuejs proejct
thumbnail: /images/post/2021-10-28/vuejs.png
categories:
  - 한국어
  - 학습
  - vuejs
date: 2021-10-28 16:07:06
---

<br>

`vuejs`는 vanillajs기반으로도 개발할 수 있지만 3.0부터는 typescript기반으로도 개발할 수 있게 되었습니다.

`vue-cli`로 typescript기반 프로젝트를 생성하는 방법을 소개하겠습니다.

**※nodejs가 설치되어 있다고 가정하고 진행합니다.**

<br>

`nodejs`로 `vue cli`를 설치합니다.

```git
$ npm install -g @vue/cli
```

아래의 명령어로 vue cli의 버전을 확인할 수 있습니다.

```git
$ vue --version
>> @vue/cli 4.5.14
```

설치가 되었다면 프로젝트를 생성해봅시다.

```git
$ vue create <project_name>
```

<br>

위 명령어를 입력하면 아래와 같은 옵션이 나오는데 `Manually select features`를 선택합니다.

![](/images/post/2021-10-28/vuejs2.jpeg)

<br>

그 다음으로는 사용할 옵션을 선택하게 됩니다. 스페이스바로 해당 옵션을 선택할 수 있습니다. 아래와 같이 선택 후 "enter"를 입력합니다.

![](/images/post/2021-10-28/vuejs3.jpeg)

<br>

그 다음으로 vue.js의 버전을 선택할 수 있는데 최신 버전을 선택합니다.

![](/images/post/2021-10-28/vuejs4.jpeg)

<br>

그 후 차례대로 아래와 같이 선택합니다.

![](/images/post/2021-10-28/vuejs5.jpeg)

<br>

![](/images/post/2021-10-28/vuejs6.jpeg)

위에서 ESline와 Pretter를 선택하면 보다 일관성있게 코드를 작성할 수 있게 됩니다.

- ESLint는 코드를 더 일관되게 만들고 버그를 방지하기 위해 ECMA스크립트/JavaScript 코드에서 발견되는 패턴을 식별하고 보고하는 도구입니다.
- Prettier은 의견을 제시하는 코드 포맷터이다. 코드를 구문 분석하여 최대 줄 길이를 고려하여 자체 규칙으로 재인쇄하여 필요할 때 코드를 줄 바꿈으로써 일관된 스타일을 적용합니다.

<br>

그리고 이어서 **테스팅툴**을 선택합니다.

![](/images/post/2021-10-28/vuejs7.jpeg)

<br>

마지막으로 config파일을 선택하게 되는데 아래와 같이 특정하게 config파일을 관리하는 옵션을 선택합니다.

![](/images/post/2021-10-28/vuejs8.jpeg)

다 되었다면 설치가 진행됩니다.

<br>

![](/images/post/2021-10-28/vuejs9.jpeg)

<br>

설치가 완료된 후

```git
cd <project_name>
npm run serve
```

<br>

명령어를 입력하면 아래와 같이 서버가 정상적으로 실행되는 걸 확인할 수 있습니다.

<br>

![](/images/post/2021-10-28/vuejs10.jpeg)
