---
layout: post
title: "store와 localStorage"
tags: [vue]
comments: true
---

store와 localStorage 차이
<!--more-->

대부분의 뷰에서 사이드바를 보이게 했다.<br>
그런데 사이드뷰에 항상 보여야 되는 요소들을 사이드바를 불러올 때마다 항상 get으로 읽어와야하는건 너무 불필요한것 같다고 느꼈다.<br>
딱 한번만 변수에 저장하고 그 변수를 호출하는 방식이면 괜찮을것 같은데...<br>
그래서 찾아보니 일종의 전역변수 개념이라고 볼 수 있는 store와 localStorage가 있다는 걸 알게 되었다.

### store

사용하려면 먼저 vuex가 설치되어있어야 한다.<br>
 ../store/index.js에  정의해서 사용한다.
* state:  사용자가 상태를 저장
* mutations: state를 변경시키기 위한 메소드 집합
* actions: 주로 state에 반영하기 전 데이터를 조회하고 가공하는 역할을 수행

> dispath()를 통해 action에 속한 메서드를 실행시킴

<br>
그런데 부모자식이 아닌 서로 관계없는 컴포넌트에서 state에 저장된 값을 확인하자 원하는 값이 아닌 초기화된 값이 확인됨!<br>
검색해보니 해결 방법은 [vuex-persistedstate](https://www.npmjs.com/package/vuex-persistedstate)를 이용하는 것이다!<br>
실제로도 해결이 됨
<br>

### localStorage

* WebStorage API여서 따로 설치해야되는 것이 없음
* 도메인과 브라우저별로 저장
* key-value 저장소(value는 문자열로 저장됨)
* ``` localStorage.setItem(key,value)```, ``` localStorage.getItem(key)```

<br>
그런데 value에 객체가 저장된다면 Object로 인식하기 때문에 제대로 저장되거나 읽어지지 않음.<br> 

해결 방법은 저장할때는 String형으로 저장해야 돼서  ```JSON.stringify()```를 이용하고 읽어올때는 Object형으로 변환해야돼서 ```JSON.parse()```를 이용한다는 것이다. 
