---
layout: single
title: "JavaScript[배열, 반복문]"
categories: JavaScript
toc: true
author_profile: false
sidebar:
    nav: "docs"
# 검색 불가
# serch: false 

---



## 	배열



- 여러 데이터를 하나의 변수에 할당하여 관리하기 위한 데이터 타입

- 하나의 배열에 여러 자료형의 데이터를 넣을 수 있다.

- 인덱스를 이용한 접근이 가능하여 검색에서 빠른 성능을 보여준다.

  

```javascript
//선언하는 방법
let myArray = [10,32,123,34];

//요소에 접근하기
console.log(myArray[0]); //10
console.log(myArray[3]); //34

//요소 수정
//myArray의 0번째 인덱스 값을 10에서 99로 변경
myArray[0] = 99;
console.log(myArray[0]); //99

//요소 추가
//값이 배열의 마지막에 추가된다.
myArray.push('apple');
console.log(myArray);  //[99, 32, 123, 34, "apple"]

//요소 삭제

//pop [배열의 가장 마지막 인덱스를 삭제] 
//두번 pop을 하면 뒤에서부터 apple, 34를 삭제
myArray.pop();
myArray.pop();
console.log(myArray); //[99, 32, 123]

//shift [배열의 첫 번째 값 삭제]
//맨 앞의 값인 99를 삭제
myArray.shift();
console.log(myArray); //[32, 123]

//배열의 길이
//배열의 인덱스는 0부터 시작해 3까지 있지만 길이는 4이다.
console.log(myArray.length)  //2

//배열의 마지막 값 출력
console.log(myArray[myArray.length - 1]) //123
```



### 	배열 안에 배열이 있는 경우



```javascript
let Array = [3,44,[25,26,27]];
console.log(Array); //[3, 44, [25, 26, 27]]
console.log(Array[0]); //3
console.log(Array[1]); //44
console.log(Array[2]); //[25, 26, 27]

//배열 안에 인덱스에 접근
console.log(Array[2][1]); //26
```



### 	배열 메소드

```javascript
//slice

let Array = [3,44,25,26,27];
//(시작[포함],끝[미포함])  1번째 인덱스부터 3번째 인덱스 전까지 출력
let newArray = Array.slice(1,3);
//음수의 경우에는 맨 뒤에서 부터 
let newArray2 = Array.slice(-3);
//양수 하나의 경우 앞의 인덱스부터 끝까지 
let newArray3 = Array.slice(2);
console.log(newArray);  //[44, 25]
console.log(newArray2);  //[25, 26, 27]
console.log(newArray3);  //[44, 25, 26, 27]

//split

//R로 된 문자마다 끊어서 단어로 만든다.
let arr = "COMPUTERPROGRAMMING";
console.log(arr.split('R')); //["COMPUTE", "P", "OG", "AMMING"]

//splice

//첫번째 시작점, 두번째 삭제할 요소의 개수, 세번째 추가하고 싶은 요소
let num = [1,2,3,4,5];
//2번인덱스부터 1개 값을 삭제하고 10일 추가
num.splice(2,1,10);
console.log(num); // [ 1, 2, 10, 4, 5 ]
let ann=num.splice(-3); //[10, 4, 5]
//5 = -1번인덱스 4= -2번인덱스 10 = -3번인덱스
console.log(ann); 

//filter 
//조건에 맞는 요소들만 새로운 배열로 반환

let array = [1,2,32,42,52];

//값이 10보다 큰 요소만 new_array 배열로 반환
//바로 함수를 작성하는 방법
let new_array = array.filter((value) => value > 10);
console.log(new_array);   //[32, 42, 52]

//밖에 함수를 선언하고 callback 하는 방법
function newarray(value) {
  return value > 10;
}
let new_array = array.filter(newarray);
console.log(new_array);  //[32, 42, 52]

//concat 
//주어진 배열에 기존 배열을 합쳐서 새로운 배열 반환
let arr = [1,2,3];
let arr2 = [4,5,6];
console.log(arr.concat(arr2));  //[1, 2, 3, 4, 5, 6]

// 배열 3개 이어 붙이기
let new_arr = [1,2,3];
let new_arr2 = [4,[5,6]];
new_arr.concat(new_arr2);
console.log(new_arr.concat([5,6])); //[1, 2, 3, 5, 6]

let test1 = [1, 2];
let test2 = [3, 4];
let test3 = [5, 6];

let test = test1.concat(test2, test3);
console.log(test); //[1, 2, 3, 4, 5, 6]

//filter, concat
//concat으로 합친 배열의 중복을 삭제하는 방법

let arr=[1,2,3,4];
let arr2=[3,4,5,6];
//배열 두개 합치기
let new_arr=arr.concat(arr2);
console.log(new_arr);  //[1, 2, 3, 4, 3, 4, 5, 6]

//중복된 값 삭제
let result = new_arr.filter((el,index) => new_arr.indexOf(el)===index);
console.log(result); //[1, 2, 3, 4, 5, 6]
//아니면 set 배열을 이용

//Array.prototype.fill()

const array1 = [1, 2, 3, 4];

// 인덱스 2번부터 4번전까지 0으로 채운다.
console.log(array1.fill(0, 1, 4));
//[1, 0, 0, 0]

// 인덱스 1번부터 끝까지 5로 채운다.
console.log(array1.fill(5, 2));
//[1, 2, 5, 5]

//전부 6으로 채운다.
console.log(array1.fill(1));
// expected output: [1, 1, 1, 1]

//find

const array1 = [5, 12, 8, 130, 44];
//조건에 만족하는 첫번째 값을 출력
const found = array1.find(element => element > 10);

console.log(found);//12

//forEach

//for 대신 사용해서 요소에 하나씩 접근
const array1 = ['a', 'b', 'c'];
array1.forEach(element => console.log(element)); //"a" //"b" //"c"


//map
//모든 요소에 대해 주어진 함수를 호출한 결과를 모아 새로운 배열
const array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);
console.log(map1); //[2, 8, 18, 32]
```



## 	반복문

 - 반복되는 작업을 쉽게 할 수 있다.
 - 조건을 만족할 때 꺄지 또는 무한으로 코드를 반복하게 만들어준다.
 - 사람이 계산하기에는 많은 시간이 소요되는 일도 빠르게 할 수 있다.
 - 많은 일을 반복적으로 사람이 하게 되면 실수가 발생할 수 있는데 방지가 가능하다.

​	

```javascript
//사용하는 방법
for(let i=1;i<11;i++){
  console.log(i); //1,2,3,4,5,6,7,8,9,10
}

for(let i=0;i<10;i++){
  console.log(i+1); //1,2,3,4,5,6,7,8,9,10
}

```



### 	배열과 반복문을 함께 자주 사용하는 이유

	- 배열 안에 요소를 넣어주려면 반복문을 이용하여 한번에 넣을 수 있다.
	- 반복문을 이용하여 배열의 인덱스를 하나씩 순회하여 배열을 출력할 수 있다.
	- 가독성이 좋아지고 오류 수정도 용이하다.

```javascript
//값을 하나씩 넣어줄 수 있지만 1000개의 값을 넣을 경우 코드가 엄청 길어지고 오래걸린다.
let arr= [1,2,3,4,5,6,7,8,9,10...998,999,1000];
//반복문을 이용하여 쉽게 1000개의 요소를 삽입 가능하다.
let arr2=[];
for(let i=1;i<1001;i++){
  arr2.push(i);
}
```



