---
layout: single
title: "Semantic Web, Semantic Tags 이해"
categories: css
toc: true
author_profile: false
sidebar:
    nav: "docs"
# 검색 불가
# serch: false 



---



## Semantic Web?

### 등장배경

웹 기술의 발전으로 수많은 정보들이 추적되는데 무분별한 정보의 축적은 오히려 많은 문제들을 불러온다.

컴퓨터가 스스로 해석, 가공할 수 없어 사용자가 직접 개입하여 처리하여야 했다.

### 의미

의미론적인 웹이라는 뜻으로 기계가 이해할 수 있는 형태로 제작된 웹이다.

## Semantic Tags?

과거 무분별한 태그 사용으로 인해 사람이 직접 개입해야 하는 비효율적인 시스템을 개선하고자, 의미있는 태그들을 개발하기 시작했다.

### non-semantic Tag 와 semantic Tag 비교

- 태그에 대한 설명이 없다.
- form, table, img. 등 의미를 명확하게 설명하고 있는 것을 볼 수 있다.

![image-20220214185503003](../images/2022-02-14-semantic_web/image-20220214185503003.png)

### Semantic Tag의 계속적인 발전 "HTML5"

- article, aside, footer, header, main, nav, section 등 부분의 성격에 따라 쓰는 태그들이 등장한다.

<img src="../images/2022-02-14-semantic_web/image-20220214185741401.png" alt="image-20220214185741401" style="zoom:35%; float:left;" /><img src="../images/2022-02-14-semantic_web/image-20220214185845642.png" alt="image-20220214185845642" style="zoom:55%; float:right;" />



















## img vs div backgroung-image

- 먼저 두 태그를 간단하게 비교하자면 img태그를 사용시 alt속성에 문자열을 넣을 수 있다. 
- alt속성에 작성된 문자열은 meta정보가 되며, 검색엔진은 alt속성에 지정된 문자열을 인식하게 된다.
- alt 속성으로 에러 발생시 이미지가 깨져도 어떠한 이미지 인지 알 수 있지만 background-image는 의미있는 태그가 아닌 그냥 속성으로 에러시 어떠한 정보도 알 수 없다.
- div background-image의 경우 단순한 이미지 첨부일 뿐, 어떠한 정보도 담지 않는다.
- 결론은 이미지의 정보가 들어가고 검색엔진으로 웹에 잘 노출 되도록 하기 위해선 img 태그를 사용하고 그저 웹 디자인과 같은 미적요소를 보여주기 위해서 background-img를 사용하는게 좋을 것 같습니다.

[참조] : <https://chanho-yoon.github.io/web/web-semanticWeb-semanticTag/>

[참조] : <https://velog.io/@geonoo99/Semantic-Web-%EA%B3%BC-Semantic-Tag-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0>

 



