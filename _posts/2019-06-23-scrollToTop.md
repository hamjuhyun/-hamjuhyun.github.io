---
layout: post
title: scroll To Top javascript
---

#### 소스보기  
[스크롤to탑](https://github.com/hamjuhyun/jucandoit91/blob/master/project/scrollEvent/index.html)

 ![scroll to top 이미지](https://raw.githubusercontent.com/hamjuhyun/jucandoit91/master/project/scrollEvent/scrollToTop.jpg)

```javascript
//변수설정
 var 버튼;
 var 문서;
 var 문서의 스크롤 위치;
 var 문서의 offset;
 var 문서의 총 높이;
 
 문서 총 높이 = 문서.scrollHeight;
 문서의 offset = 문서의 총 높이 / 4;  // 4분의 1 지점에서 보이게 할거라서 설정해두었음. 4로 
 
 window.addEventListener('scroll', scrollFn);
 
 function scrollFn() {
  문서의 스크롤 위치 = 문서.scrollTop;
  버튼.className = (문서 스크롤 위치 > 문서의 offset) ? 'visible' : '';
 }
 
 버튼.addEventListener('click', 위로가기);
 
 function 위로가기(event) {
  event.preventDefault() //위로 튕기지 않게 설정해줌.
  scrollToTop();
 }
 
 function scollToTop() {
  var scrollInterval = setInterval(function() {
    if (문서의 스크롤 위치 != 0) {
      window.scrollBy(0, -55);
    } else {
      clearInterval(scrollInterval);
    }
  }, 15);
 }
```
