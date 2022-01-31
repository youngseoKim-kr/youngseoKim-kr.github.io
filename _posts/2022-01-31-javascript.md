---
layout: single
title: "JavaScript[객체]"
categories: JavaScript
toc: true
author_profile: false
sidebar:
    nav: "docs"
# 검색 불가
# serch: false 

---



## 	Object

- key와 value으로 구성된 property의 정렬되지 않은 집합이다.
- 순서와 인덱스가 없다.
- 객체의 property는 속성을 나타내는 key와 그에 대한 value로 구성되어 데이터를 더욱 직관적으로 저장하고 불러올 수 있다.

```javascript
{key : value}
--------------------------------------
ex) {name: "kys", isDeveloper : true}
--------------------------------------
// 이런 형식도 가능
let object = {
  name:'kys',
  location : {
    country : 'korea',
    city : 'seoul'
  },
  age:33,
  dog:['호돌','호호']
}
key : name, location, age, dog
value : 'kys', {country : 'korea',city : 'seoul'}, 33, ['호돌','호호']
```



	### 	property

- 객체 안에 있는 하나의 값

- key와 value로 이루어진 값

  

### 	객체에 저장된 데이터 접근

- key를 이용해서 value에 접근

1. Dot Notation - 점을 이용해서 접근

   ```javascript
   let object = {
     name:'kys',
     location : {
       country : 'korea',
       city : 'seoul'
     },
     age:33,
     dog:['호돌','호호']
   }
   ----------------------------------
   console.log(object.name);  //"kys"
   console.log(object.location)  //[object Object] {city: "seoul",country: "korea" }
   ```

2. Bracket Notation - 괄호를 이용해서 접근

   ```javascript
   let object = {
     name:'kys',
     location : {
       country : 'korea',
       city : 'seoul'
     },
     age:33,
     dog:['호돌','호호']
   }
   ----------------------------------
   console.log(object['name']);  //"kys"
   console.log(object['location']);  //[object Object] {city: "seoul",country: "korea" }
   ```

차이점

- Dot Notation은 숫자로 된 키에 접근할 수 없고, 띄어쓰기가 포함된 키에는 포함될 수 없다.

- key에 변수가 포함되어 있으면 dot notation으로 접근할 수 없다.

  ```javascript
  let object = {
    name:'kys',
    location : {
      country : 'korea',
      city : 'seoul'
    },
    age:33,
    dog:['호돌','호호']
  }
  ----------------------------------
  let myname='name';
  console.log(object['name']); //"kys"
  console.log(object[myname]); //"kys"
  console.log(object.myname); //undefined
  // -> myname이라는 키가 없기 때문에 undefined 출력
  ```

  

  ### 	객체의 값을 추가, 수정, 삭제

  

  ```javascript
  let object = {
    name:'kys',
    location : {
      country : 'korea',
      city : 'seoul'
    },
    age:33,
    dog:['호돌','호호']
  }
  ----------------------------------
  //추가
  object.age2=100;
  console.log(object.age2); //100
  object['age3']=200;
  console.log(object.age3); //200
  
  console.log(object);
  //[object Object] {
    age: 33,
    age2: 100,
    age3: 200,
    dog: ["호돌", "호호"],
    location: [object Object] {
      city: "seoul",
      country: "korea"
    },
    name: "kys"
  }
  
  //수정
  object.age2=99;
  console.log(object.age2); //100
  object['age3']=99;
  console.log(object.age3); //200
  
  console.log(object);
  //[object Object] {
    age: 33,
    age2: 99,
    age3: 99,
    dog: ["호돌", "호호"],
    location: [object Object] {
      city: "seoul",
      country: "korea"
    },
    name: "kys"
  }
  
  //삭제
  delete object.age2;
  delete object['age3'];
  
  console.log(object)
  //[object Object] {
    age: 33,
    dog: ["호돌", "호호"],
    location: [object Object] {
      city: "seoul",
      country: "korea"
    },
    name: "kys"
  }
  ```

  

### 	객체와 배열이 섞인 복잡한 객체 만들어서 접근하는 방법

```javascript
let object = {
  name:'kys',
  location : {
    country : 'korea',
    city : 'seoul'
  },
  age:33,
  dog:['호돌','호호']
}
--------------------------------------------
console.log(object['location']['country']); //"korea"
console.log(object.location.city);  //"seoul"
console.log(object.dog[0]);  //"호돌"
console.log(object['dog'][1]);  //"호호"
```



### 	배열의 타입이 객체인 이유

- javascript의 데이터 타입에는 기본형과 참조형 타입이 있는데 객체는 참조형 타입이고 객체 하위에 배열이 있다.
- 객체는 순서와 관련된 메서드가 없어 순서와 관련된 배열이 만들어졌다.
- 데이터의 순서가 있는 경우 배열이 더 좋지만 순서가 없는 경우 객체를 사용하는게 적합하다.
