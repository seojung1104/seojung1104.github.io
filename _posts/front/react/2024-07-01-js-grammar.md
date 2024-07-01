---
title: js 기초
author: junghoon
date: 2024-07-01 12:00:00 +0800
categories: [front, js]
tag: [front, js]
---

#### 변수 타입
- var: 함수내에서 만 지역변수 취급, 
- let: if, for, 함수 지역변수 취급, 
- const: 상수

#### string 입력
아래와 같이 3가지 타입으로 입력 가능하다
\` 은 변수도 입력 가능하다
python에서 f'{변수}'
```js
let s1 = 'abc'
let s2 = "abc"
let s3 = `abc`

let a = 10
let b =3.14
let c = 'hello'
let s4 = `a=${a} b= ${b} c= ${c} `

```

#### function 타입

```js
// 1번
function f1(a,b){
    return a+b
}

// 2번
let f1 = function (a,b){
    return a+b
}
// 3번 화살표 함수
let f1 = (a,b)=>{ return a+b }

// 4번
let f1 = (a,b)=> a+b
```

#### array 사용법

```js
var arr = ['aaa','bbb','ccc','ddd','eee']

// 값 입력
arr.push('fff')
var arr2 = arr.concat('www') // 새로운 배열객체 반환

// 요소 삭제 및 입력
arr.splice(1,2,'hhh','iii') // 1번 째 인덱스 부터 2 개요소 삭제하고, 이후의 값('hhh', 'iii') 추가

// for 문 사용
for(let n in arr){
    // index 출력
    console.log(n)
}

for(let n of arr){
    //요소 출력
    console.log(n)
}
// function arrFn (v,i){
//     console.log(v,i)
// }
// arr.forEach(arrFn)

//     arr.forEach( 
//         function arrFn (v,i){
//         console.log(v,i)
//     }
// )


let arr = [10,20,30,40,50]
// map 으로 for 문처럼 사용가능
let narr = arr.map(v=>v+2)
console.log(narr)

//Filter 기능
let farr = arr.filter(v=> v>=30)
console.log(farr)

function rfn(r,c){
    console.log(r,c)
    return r+c
}

// 이전값 사용 가능
let result = arr.reduce( rfn )
```

#### json
```js
let j = {'aa':10, 'bb':20 , 'cc':30}
console.log(j['aa'], j.aa)

for(let n in j){ // json 은 in 만 됨
    console.log(n, j[n])
}
```

json array
```js
let jarr=[{'name':'홍길동','age':20},{'name':'이순신','age':30}
,{'name':'임꺽정','age':40}]

// array 라 of 가능함
for ( let j of jarr){ 
    console.log(j.name, j.age)
}
// json to string
let sarr = JSON.stringify(jarr)
console.log(sarr)
//string to json
let oarr = JSON.parse(sarr)
console.log(oarr)
```


#### 구조분해
```js
let arr =['a','b','c','d']
let [ a,b,c,d] = arr
// 인덱스 요소 값 입력
console.log(   a,b,c,d)

// h에 'a' , rest에 'b','c','d' 배열 형태로 들어감
let [h, ...rest] = arr
console.log(h,rest)

// 각 키에 맞는 값이 들어감
let j = {'aa':10, 'bb':20 ,'cc':30}
let {aa,cc} =j
console.log(aa,cc)
```

#### class

```js
class student
{
    constructor(name, age) // constructor(this,name,age)
    {
        console.log('constructor')
        this.name=name
        this.age =age
    }
    setName(name){ //setName(this, name)
        this.name=name
    }
}

var std1 = new student('t1',1) // == std1.constructor(std1, 't1', 1) 자바스크립트 컴파일러에 의해 추가됨
var std2 = new student('t2',2)
console.log(std1)
std1.setName('www')
console.log(std1)
```