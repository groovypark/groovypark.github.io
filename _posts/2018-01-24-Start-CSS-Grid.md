---
title: Start CSS Grid
description: 
categories: 
tags: CSS Frontend
---

![css grid](https://cssgrid.io/images/GRID-social-share.png)

# Downloads

1. 동영상 강의 신청
  [CSS Grid — Learn all about CSS Grid with Wes Bos in this free video series!](https://cssgrid.io/)
1. Firefox Developer 다운로드
  [Firefox Developer Edition](https://www.mozilla.org/ko/firefox/developer/?utm_campaign=cssgrid&utm_content=web&utm_source=wesbos)
1. 파일 다운로드
  [GitHub - wesbos/css-grid: Starter Files + Solutions to my CSSGrid.io Course](https://github.com/wesbos/css-grid)

# emmet

[Emmet — the essential toolkit for web-developers](https://emmet.io/)

* .container>.item*5
  ```html
  <div class="container">
      <div class="item"></div>
      <div class="item"></div>
      <div class="item"></div>
      <div class="item"></div>
      <div class="item"></div>
    </div>
  ```

* .item{$}*5
  ```html
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
  ```

* fz50
  ```css
  p {
    font-size: 50px;
  }
  ```

# CSS

자주 사용하는 나만의 색상이 있다면 따로 설정해 둘 수 있다.
  ```css
  :root {
    --yellow: #ffc600;
    --black: #272727;
  }

  p {
    color: var(--yellow);
    color: var(--black);
  }
  ```

# css-grid-fundamentals

<script src="https://gist.github.com/groovypark/053bb599f77633af47648667c9037da8.js"></script>