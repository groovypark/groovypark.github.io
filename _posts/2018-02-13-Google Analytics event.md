---
title:  구글 애널리틱스(Google Analytics), 구글 태그 매니저(Google Tag Manager) 이벤트 설정
description: 
categories: 
tags: google
---

![Google Analytics, Google Tag Manager](http://sungjunlee.com/content/images/2019/04/ga-gtm.png)

# 구글 애널리틱스 이벤트 설정


이벤트 설정이란, 여기 아래 사진에 나오는 이벤트이다. 앞으로 밑에서 계속 나올 이벤트 카테고리와 액션은 사진에 있는 표에 표시될 이름이다.
![Google Analytics](/assets/images/analytics.png)

[Event Tracking, Analytics for Web (analytics.js), Google Developers](https://developers.google.com/analytics/devguides/collection/analyticsjs/events)  

공식 문서를 보면

```javascript
// 이렇게
ga('send', 'event', 'Videos', 'play', 'Fall Campaign');
// 또는 이렇게
ga('send', {
  hitType: 'event',
  eventCategory: 'Videos',
  eventAction: 'play',
  eventLabel: 'Fall Campaign'
});
```

하라고 되어있다. 그래서 버튼이 클릭 되었을때 아래와 같이 저 코드를 넣었지만 이벤트는 생성되지 않았다.

```javascript
modalBtn.onclick = function(event) {
  ga('send','event','mainPageAppLink','buttonclick','handys');
};
```

# 구글 태그 매니저


그래서 직접 코드를 삽입할 필요 없이 Google Tag Manager를 이용하면 편하다고 해서 새로 만들어보았다.  
구글 애널리틱스 아카데미에서 구글 태그 관리자 기초 과정을 듣고 따라했다.  
[Google Analytics Academy](https://analytics.google.com/analytics/academy/)  
문서 백 번보는 것보다 이거 한번 처음부터 끝까지 따라해보면 완전 이해될 것이다.👍🏼  


![Google Analytics](/assets/images/tag-manager1.png)
구글애널리틱스와 연결하기 위해서는 태그를 생성하여 위 사진과 같이 설정한 다음,  
Tracking ID에 구글애널리틱스 추적 ID를 넣으면 된다.(ex. UA-XXXXXXXXX-1)  
추적 ID는 구글애널리틱스 관리에서 추적정보에 있는 추적 코드로 들어가면 나와있다. 


이제 이벤트를 설정하기 위해서 또다른 태그를 만든다.  
![Google Analytics](/assets/images/tag-manager2.png)

아까 위에서 보았던 이 코드는 위 사진에 있는 카테고리, Action에 들어가는 부분이다.  
구글태그매니저에서는 라벨을 설정해주지 않았다.

```javascript
modalBtn.onclick = function(event) {
  ga('send','event','mainPageAppLink','buttonclick','handys');
};                      // '카테고리이름', '액션이름', '라벨이름'
```

위와 같이 설정을 하는데, Track Type에 Event를 등록하기 위해서는 아래와 같이 Variables에서 Event를 추가해줘야 한다.
![Google Analytics](/assets/images/tag-manager3.png)

다시 아까 위에있는 태그 추가 화면에서 Triggering을 등록하기 위해서 Triggers를 새로 만들어야 한다.  
나는 필터를 id값으로 확인하였다. 따라서 해당하는 아이디 값이 클릭되었을 때 이벤트가 발생하는 것이다.
![Google Analytics](/assets/images/tag-manager4.png)

PREVIEW를 누르면 적용된 화면이 뜨는데, 해당하는 버튼을 클릭했을 때 이벤트가 실행되었다고 뜨는 모습을 볼 수 있다. 

# 결론


삽질을 거듭하여 결국 구글 커뮤니티에 질문을 올렸더니 바로 해결되었다... 하지만 삽질한 덕분에 gtag와 태그매니저를 잘 사용할 수 있게 되었다.  

## 구글 커뮤니티


[Solved:  Google Analytics Event Tracking not working - The Google Advertiser Community - 1636048](https://www.en.advertisercommunity.com/t5/forums/v3_1/forumtopicpage/board-id/Code_Implementation/message-id/11851#M11849)

문제는 결국 ga -> gtag였다...

## 구글 에널리틱스 데모 계정


목표설정을 하는 것이 좀 이해가 어려웠는데 데모계정에 기본적인 설정들이 되어있어서 참고하고 이해하는데 도움이 되었다.
[데모 계정 액세스](https://analytics.google.com/analytics/web/?utm_source=demoaccount&utm_medium=demoaccount&utm_campaign=demoaccount#report/visitors-overview/a54516992w87479473p92320289/)
