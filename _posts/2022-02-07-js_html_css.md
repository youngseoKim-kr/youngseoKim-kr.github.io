---
layout: single
title: "JavaScript[객체]"
categories: JavaScript html css
toc: true
author_profile: false
sidebar:
    nav: "docs"
# 검색 불가
# serch: false 


---



## HTML, CSS란 무엇이며 필요한 이유

## 	

<img src="../images/2022-02-07-js_html_css/image-20220207152721419.png" alt="image-20220207152721419" style="zoom:50%;" align="left"/>

**HTML**(HyperText Markup Language)은 웹을 이루는 가장 기초적인 구성 요소로, 웹 콘텐츠의 의미와 구조를 정의할 때 사용합니다.
HTML은 웹 브라우저에 표시되는 글과 이미지 등의 다양한 콘텐츠를 표시하기 위해 "마크업"을 사용합니다. 
HTML 마크업은 다양한 "요소"를 사용하는데, 요소에는 다양한 태그가 존재합니다.



<img src="../images/2022-02-07-js_html_css/image-20220207152548685.png" alt="image-20220207152548685" style="zoom:50%;" align="left" />

**Cascading Style Sheets**(**CSS**)는 [HTML](https://developer.mozilla.org/ko/docs/Web/HTML)이나 [XML](https://developer.mozilla.org/ko/docs/Web/XML)(XML의 방언인 [SVG](https://developer.mozilla.org/ko/docs/Web/SVG), [XHTML](https://developer.mozilla.org/ko/docs/Glossary/XHTML) 포함)로 작성된 문서의 표시 방법을 기술하기 위한 [스타일 시트](https://developer.mozilla.org/ko/docs/Web/API/StyleSheet) 언어입니다. 화면에 표시되는 사진, 글씨의 크기나 색상 폰트등을 지정해 줍니다.



## HTML, CSS, JavaScript의 관계

HTML 은 홈페이지의 뼈대를 만들어주는 역할로 button, input box, text 등을 이용하여 홈페이지에 필요한 부분을 만들어준다.

<img src="../images/2022-02-07-js_html_css/image-20220207154419808.png" alt="image-20220207154419808" style="zoom:50%;" />

CSS 는 HTML을 이용하여 더 이쁜 버튼을 만들고 input box도 테두리를 둥글게 만드는 등을 할 수 있으며 위치도 잡아줄 수 있다.

위에 사진에 css를 추가하여 아래 사진처럼 만들 수 있다.

<img src="../images/2022-02-07-js_html_css/image-20220207154458397.png" alt="image-20220207154458397" style="zoom:50%;" />

JavaScript 는 button을 누르면 페이지 제일 하단부로 이동을 하는 동작이라던지 스크롤 반응이나 마우스 클릭 움직임에 따라 홈페이지에 기능을 추가할 수 있다.

<img src="../images/2022-02-07-js_html_css/image-20220207154526902.png" alt="image-20220207154526902" style="zoom:50%;" />

skills 버튼을 누르면 skills 부분으로 이동하는걸 JavaScript를 이용해서 기능을 추가할 수 있다.

## `.html,` `.css`, `.js`세 종류의 파일을 연결하는 방법

1. Html 파일에 style태그와 script태그를 이용해서 연결하기

![image-20220207155105048](../images/2022-02-07-js_html_css/image-20220207155105048.png)

2. css파일과 js 파일을 따로 만들어서 html 파일에 연결하기

![image-20220207155257017](../images/2022-02-07-js_html_css/image-20220207155257017.png)



## script 태그의 위치에 따른 차이점



### head 태그 내부에 script 태그 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document</title>
    <script src="main.js"></script>
</head>
<body>
</body>
</html>
```

<img src="../images/2022-02-07-js_html_css/image-20220207160134484.png" alt="image-20220207160134484"/>	

​	

HTML은 파싱 도중, **script 태그를 만나게 되면 중간에 파싱이 멈춘다**.
하향식으로 읽는 HTML문서는, head 태그 내부에 불러온 script 태그를 읽느라 
body 내부의 UI는 script 태그를 읽은 후에 사용자에게 보여주게 될 것이다.
HTML 파싱이 다 되기 전에 script 파일을 실행시키기 때문에 만약 script 파일이 DOM 요소를 조작한다면
 **존재하지 않는 DOM 요소에 접근하려는 시도로 예상치 못한 문제가 발생**할 수 있다.

-----



### head 태그 내부에 script 태그 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document</title>
</head>
<body>

	  <script src="main.js"></script>
</body>
</html>
```

​	![image-20220207160709264](../images/2022-02-07-js_html_css/image-20220207160709264.png)

이 방법은 HTML을 다운받고 파싱을 마친 후 script 파일을 읽기 때문에 전 방법보다 빠르다. 

그러나 웹을 사용하는데 있어서 사용자가 자바스크립트 없이는 어떠한 활동도 할 수 없다면?
**웹이 자바스크립트에 의존적이라면** HTML이 파싱이 다 돼도 의미가 없을 것이다.

-----



### async

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document</title>
    <script async src="main.js"></script>
</head>
<body>
</body>
</html>
```

![image-20220207160939484](../images/2022-02-07-js_html_css/image-20220207160939484.png)

async는 HTML파일을 파싱하다 script 태그를 만나면 HTML를 마저 파싱하는 동시에 script를 다운로드 시킨다.
그리고 실행시키는데 실행시키는 동안에는 HTML파싱이 멈추게 된다.

장점은 **자바스크립트에 의존적인 웹을 좀 더 빨리 실행**시킬 수 있다는 점. 
단점은 **결국에는 HTML파싱이 자바스크립트 파일을 실행시키는 동안에 멈추게 돼** 그냥 head부분에 넣는 1번의 상황에서 일어날 문제를 겪을 수 있다.

또한, 실행시켜야 할 script 태그가 여러개일 때, 순서에 상관 없이 먼저 다운로드 받아지는 script를 먼저 실행시키기 때문에 해당 프로젝트가 **script 파일의 실행 순서에 영향을 받는다면 문제**가 될 수 있다.

----



### defer

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document</title>
    <script async src="defer.js"></script>
</head>
<body>
</body>
</html>
```

![image-20220207161122233](../images/2022-02-07-js_html_css/image-20220207161122233.png)

defer은 HTML을 파싱하다 script 태그를 만나면 async와 마찬가지로 HTML을 파싱하면서 script는 동시에 다운로드만 시켜둔다.
차이점은 **HTML 파싱이 완료된 후에 script를 실행**시킨다는 점이다.

이는 위의 방법들 중 가장 이상적이라고 할 수 있는데,HTML파싱이 중간에 멈출 염려도 없고,
 2번의 단점도 개선**시킬 수 있다.여러개의 script 태그를 이용해도 **미리 다운을 다 받고 HTML도
 끝까지 파싱시킨 후에 순서대로 실행**되기 때문에 async의 단점을 보완할 수 있다.

따라서 defer을 이용하여 js 파일을 연결하는것이 이상적이다.

참고 : https://jae04099.tistory.com/entry/HTML-script-%ED%83%9C%EA%B7%B8%EB%8A%94-%EC%96%B4%EB%94%94%EC%97%90-%EC%9C%84%EC%B9%98-%ED%95%B4%EC%95%BC-%ED%95%A0%EA%B9%8C

## 웹 페이지에서 일어날 수 있는 이벤트의 종류

이벤트는 웹페이지에서 특정한 동작으로 어떤 사건에 대한 동작을 수행한다.

이벤트의 종류는 엄청나게 많지만 대표적으로 많이 쓰는 것만 정리한다.

![image-20220207161651648](../images/2022-02-07-js_html_css/image-20220207161651648.png)

![image-20220207161704210](../images/2022-02-07-js_html_css/image-20220207161704210.png)

![image-20220207161719180](../images/2022-02-07-js_html_css/image-20220207161719180.png)

![image-20220207161746148](../images/2022-02-07-js_html_css/image-20220207161746148.png)

나머지 자세한 내용은 https://developer.mozilla.org/ko/docs/Web/Events 에 전부 작성되어 있다.

참조 : https://jenny-daru.tistory.com/17



## 이벤트와 자바스크립트 함수와의 관계

이벤트가 발생할 때 실행할 동작을 자바스크립트 함수를 이용해서 작성할 수 있다.

```html
<input value="Try selecting some text in this element.">
<p id="log"></p>
```

```javascript
function logSelection(event) {
  const log = document.getElementById('log');
  const selection = event.target.value.substring(event.target.selectionStart, event.target.selectionEnd);
  log.textContent = `You selected: ${selection}`;
}

const input = document.querySelector('input');
input.addEventListener('select', logSelection);
```

![image-20220207163739934](../images/2022-02-07-js_html_css/image-20220207163739934.png)

Input box의 안에 값이 select 되면 select된 값이 화면에 출력하는 이벤트를 발생시킨다.