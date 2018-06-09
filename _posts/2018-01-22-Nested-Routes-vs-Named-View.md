---
title: Nested Routes vs Named View
description:
categories:
tags: Vue Frontend
---

![vuejs](https://i.ytimg.com/vi/DsuTwV0jwaY/maxresdefault.jpg)

![nested routes vs named view](../assets/images/vue-routers.png)

# Nested Routes
특정 URL에서 1개의 컴포넌트에 여러 개의 하위 컴포넌트를 갖는 것

# Named View
특정 URL에서 여러 개의 컴포넌트를 쪼개진 뷰 단위로 렌더링 하는 것
* 라우터로 특정 URL로 이동시, 해당 URL에 해당하는 여러 개의 View(컴포넌트)를 동시에 렌더링 한다.
* 각 컴포넌트에 해당하는 `name`속성과 `router-view`지정 필요
```html
<div id="app">
	<router-view name="nestedHeader"></router-view>
	<router-view></router-view>
</div>
```
```js
{
	path : '/home',
	// Named Router
	components: {
		nestedHeader: AppHeader,
		default: Body
	}
},
```
router-view에 설정한 ‘nestedHeader’라는 이름으로 AppHeader 컴포넌트가 불러와지고, default 값으로 Body를 주었으므로 Body태그로 컴포넌트가 띄워진다. 따라서 Named View는 name 속성을 지정해 주어서 그 이름에 맞게 바로 렌더링이 된다.

**다른 글**  
[Vue.js](https://groovypark.github.io/2017/10/20/Vue.js-Instance/){: target="_blank" }  
[Vue Components](https://groovypark.github.io/2017/11/06/Vue-Components/){: target="_blank" }  
[Vue 컴포넌트 통신](https://groovypark.github.io/2017/11/07/Vue-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%ED%86%B5%EC%8B%A0/){: target="_blank" }  
[Vue 라우터](https://groovypark.github.io/2017/11/09/Vue-%EB%9D%BC%EC%9A%B0%ED%84%B0/){: target="_blank" }  
[Vuex Tutorial](https://groovypark.github.io/2018/02/08/Vuex-Tutorial/){: target="_blank" }  