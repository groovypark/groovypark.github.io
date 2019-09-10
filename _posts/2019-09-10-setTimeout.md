---
title: JavaScript setTimeout 숫자 증가 문제
description: 
categories: 
tags: JavaScript
---

![JavaScript](https://tech-dig.jp/wp/wp-content/uploads/2018/05/javascript.jpg)


## 문제 - 10이 10번 찍힘
```javascript
for (var i = 0; i < 10; i++) {
	setTimeout(function() {
		console.log(i);
	}, 1000);
}
```

## 해결 - 1초씩 숫자 증가

1. 함수로 빼기
    ```javascript
    timer = function(i) {
        setTimeout(function() {
            console.log(i);
        },i*1000);
    }
    for (let i = 0; i < 10; i++) {
        timer(i);
    }
    ```

2. setInterval 사용
    ```javascript
    i = 0;
    timer = setInterval(function() {
        console.log(i)
        i++;
        if(i === 10) {
            clearInterval(timer)
        }
    },1000);
    ```

## 해결 - 1초뒤 for문 실행

1. setTimeout안에서 for문 실행
```javascript
setTimeout(function(){
	for (var i=0; i < 10; i++) {
        console.log(i);
    }
}, 1000);
```

2. closure 사용 - for문의  i를 setTimeout에 즉시실행
    ```javascript
    for (var i = 0; i < 10; i++) {
        setTimeout(function(index) {
            return function() {
                console.log(index);
            };
        }(i), 1000);
    }
    ```

3. 즉시실행함수 - for문의  i를 함수에 즉시실행
    ```javascript
    for (var i = 0; i < 10; i++) {
        (function(index) {
            setTimeout(function() {
                console.log(index);
            }, 1000);
        })(i);
    }
    ```

4. 블록
    ```javscript
    for (let i = 0; i < 10; i++) {
    setTimeout(function() {
    console.log(i);
    }, 1000);
    }
    ```

---

**참고 링크**  
[https://webisfree.com/2017-06-15/settimeout()](https://webisfree.com/2017-06-15/settimeout()-%EC%82%AC%EC%9A%A9%EC%8B%9C-delay%EA%B0%80-%EC%A0%95%EC%83%81-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EB%8A%94-%EB%AC%B8%EC%A0%9C)  
[https://joshua1988.github.io/web-development/javascript/javascript-interview-3questions/](https://joshua1988.github.io/web-development/javascript/javascript-interview-3questions/)  
[https://steemit.com/js/@huna/js-settimeout](https://steemit.com/js/@huna/js-settimeout)  
