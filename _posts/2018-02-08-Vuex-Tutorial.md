---
title:  Vuex Tutorial
description: 
categories: 
tags: Vue Frontend
---

![Vuex Tutorial](https://i.ytimg.com/vi/BGAu__J4xoc/maxresdefault.jpg)

## Vuex Tutorial 강의

[YouTube Vuex Tutorial 강의 링크](https://www.youtube.com/watch?v=BGAu__J4xoc)  

**The Net Ninja** 이분 강의 정말 잘하시는 것 같다.  
다른 Vuex 강의들은 보면서 어렵다고 느껴졌었는데 정말 짧고 쉽게 설명해서 좋았다.  
Vuex 강의 말고도 많이 있다. 강추합니다 👍 👍

[The Net Ninja 채널 링크](https://www.youtube.com/channel/UCW5YeuERMmlnqo4oq8vwUpg)

## 필요한 설치

* vue cli를 이용하여 templete 설치  
  `vue init webpack-simple vuex-playlist`
* vuex-playlist 폴더로 이동한 뒤 npm 설치  
  `npm install`  
  `npm run dev` 를 하면 실행된다.
* vuex 설치  
  `npm install vuex --save`
* `...mapGetters` 와 같은 es6문법 사용을 위한 설치  
  (나는 stage-3가 적혀있었다.)  
  `npm install -preset -stage-2 --save-dev`  
  .babelrc에 ["stage-2"]에 추가

## 소스코드

<script src="https://gist.github.com/groovypark/0897c8b35f8b7e191b9266418263526d.js"></script>

## 전체 코드

Branch에 강의 순서대로 올려져있다.  
[https://github.com/iamshaunjp/vuex-playlist](https://github.com/iamshaunjp/vuex-playlist)

## 결과 화면

![vuex tutorial result screen](/assets/images/vuex-tutorial.png)

Vuex에서 getters를 이용하여 계산된 새로운 객체를 생성한다.  
mutation을 이용하면 컴포넌트에서 methods를 직접 사용하지 않고 store에서 값을 변경수 있다.  
또한 위의 사진과 같이 디버깅하기 좋다.  
actions는 비동기 작업을 할 수 있다. action으로 mutation에 대한 commit을 한다.

**다른 글**  
[Vue.js](https://groovypark.github.io/2017/10/20/Vue.js-Instance/){: target="_blank" }  
[Vue Components](https://groovypark.github.io/2017/11/06/Vue-Components/){: target="_blank" }  
[Vue 컴포넌트 통신](https://groovypark.github.io/2017/11/07/Vue-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%ED%86%B5%EC%8B%A0/){: target="_blank" }  
[Vue 라우터](https://groovypark.github.io/2017/11/09/Vue-%EB%9D%BC%EC%9A%B0%ED%84%B0/){: target="_blank" }  
[Nested Routes vs Named View](https://groovypark.github.io/2018/01/22/Nested-Routes-vs-Named-View/){: target="_blank" }  