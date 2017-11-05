---
title: Vue Components
description: 
categories: 
tags: Vue Frontend
---

![vuejs](https://i.ytimg.com/vi/DsuTwV0jwaY/maxresdefault.jpg)

# 컴포넌트 등록

![Vue Components](https://kr.vuejs.org/images/components.png)
화면에 비춰지는 뷰의 단위를 쪼개어 재활용이 가능한 형태로 관리하는 것이 컴포넌트이다. 상위컴포넌트, 하위컴포넌트가 존재하는 것이 Vue의 기본적인 규격이다.

# 전역 & 지역 컴포넌트 등록

* 컴포넌트를 뷰 인스턴스에 등록해서 사용할 때 다음과 같이 global하게 등록할 수 있다.
    ```javascript
    Vue.component('my-component',{
        // ...
    })
    ```
* local하게 등록하는 방법은 다음과 같다.
    ```javascript
        var cmp = {
            data: function() {
                return {
                    // ...
                };
            }
            template: '<hr>',
            methods: {}
        }

        //아래 Vue 인스턴스에서만 활용할 수 있는 로컬(지역) 컴포넌트 등록
        new Vue({
            components: {
                'my-cmp': cmp
            }
        })
    ```

[Vue Components](https://gist.github.com/groovypark/b642e5dc8c17d85e660baea34627eccb.js)
<script src="https://gist.github.com/groovypark/b642e5dc8c17d85e660baea34627eccb.js"></script>

Vue.component 를 쓰게되면 컴포넌트를 전역으로 등록하게 된다. my-component안의 내용은 template에서 html요소로 구성된다. 그리고 새로 Vue 인스턴스를 만들게 되면, 컴포넌트가 등록되었기 때문에 `<my-component></my-component>` 부분이 template 내용으로 치환이 되면서 `<div>A global component!</div>`로 바뀌게 될 것이다.<br/>
변수 cmp안에 동일한 내용을 넣고, 새로운 인스턴스에서 components안에 태그명과 컴포넌트의 내용(변수)를 넣어 지역으로 컴포넌트를 등록한다.`<my-local-component></my-local-component>` 부분이 cmp의 template 내용으로 치환이 되면서 `<div>A local component!</div>`로 바뀌게 될 것이다.<br/>

## 전역 & 지역 컴포넌트 차이점

글로벌 컴포넌트는 Vue 접근자에 바로 등록되는 것이기 때문에 인스턴스를 생성할 때마다 재활용 할 수 있다. 하지만 로컬 컴포넌트는 해당 인스턴스에만 사용할 수 있다. 따라서 로컬 컴포넌트는 인스턴스를 등록할 때 app2를 등록하지 않게 되면 app에서는 컴포넌트 2개가 모두 보이지만, app2에서는 'my-component'만 뜨고 'my-local-component'는 뜨지 않게 된다.</br>
app과 app2 모두 보이게 하기 위해서는 다음과 같이 app2를 추가하여 인스턴스를 2개 등록하면 된다.

```javascript
new Vue({
        el: '#app2',
        components: {
          // 태그명 : 컴포넌트의 내용
          'my-local-component': cmp
        }
      })
```

이것이 바로 글로벌 컴포넌트와 로컬 컴포넌트의 차이점이다.