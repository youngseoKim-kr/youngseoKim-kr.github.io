---
layout: single
title: "JavaScript[변수, 함수, 조건문, 연산자]"
categories: JavaScript
toc: true
author_profile: false
sidebar:
    nav: "docs"
# 검색 불가
# serch: false 

---



## javaScript 변수



변수를 선언하는 이유? 

변수를 어떤 방법으로 사용할지 컴퓨터에게 알려주는 과정으로 
서로 다른 변수의 타입이 있기 때문에 다른 특징들을 컴퓨터에게 알려줘야 한다.

let a=300;

| 기본 타입 | 참조 타입 |
| :-------: | :-------: |
|  Number   |  Object   |
|  String   |   Array   |
|  Boolean  | Function  |
| Undefined |           |
|   Null    |           |

Number = + , - , /(몫) , %(나머지) , * 
string = '문자열'
boolean = true, false

Undefined 와 Null의 차이
변수를 선언하고 Null이라는 값을 주어지면 Null인 상태이고
변수에 아무 값도 주어지지 않으면 undefined 이다.

```javascript
//문자열 길이 구하기
const mystring = 'Hello! wecode!!';
console.log(myString.length)  //15
console.log('Hello! wecode!!'.length)
```



## 함수

Input -> 기능수행 -> output

정의 -> 호출

```javascript
function sayHello(name){
  return 'hello, '+ name +'!';
}
let name = sayHello('kys');
console.log(name)  //hello, kys!
```

sayHello라는 함수를 만들고 parameter 값으로 argument 값인 kys를 넣어주고 sayhello 함수에서 return 값 (hello, keys!)를 name 변수에 넣어주고 그 name 변수를 console.log 로 찍어준다.

