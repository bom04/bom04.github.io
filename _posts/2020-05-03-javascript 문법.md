---
layout: post
title: "javascript 문법1"
tags: [javascript]
comments: true
---

javascript 문법 정리
<!--more-->

## javascript 문법

### javascript 특징

* 약타입 언어로 변수의 자료형을 엄격히 구분하지 않음

### 타입 비교

* ```===```나 ```!==```로 비교하면 값 뿐만 아니라 타입도 비교해서 리턴함
* ```typeof```은 값의 타입을 리턴함

> typeof a=="string"


### 상수 const 변수

* 값을 변경할 수 없음
 
### undefined와 null의 차이
 
 * null은 값이 있으니 그 값이 null
 * undefined는 아얘 값이 없음

### 자료형

* number
* string
* boolean
* undefined
* function
* object

### Lazy evaluation

* ```&&```나 ```||``` 에서 실행할 필요가 없는 부분을 실행하지 않는 것을 의미

### 형 변환

* string->number: ```parseInt()```,```parseFloat()```,```Number()```
* number->string: ```toString()```,```String()```

### let과 var의 차이

* var은 가장 가까운 함수의 본문 블럭에 소속되고 동일한 이름의 변수가 있어도 에러 발생 안함
* let은 가장 가까운 { } 블럭에 소속되고 동일한 이름의 변수를 선언하면 에러 발생 => 자바의 지역변수와 비슷함

### Math 클래스

* Math.PI
* Math.round(): 반올림
* Math.pow(): 거듭제곱을 리턴
* Math.sqrt(): 제곱근을 리턴
* Math.abs(): 절대값을 리턴
* Math.floor(): 내림
* Math.ceil(): 올림
* Math.max(): 최대값 리턴
* Math.min(): 최소값 리턴
* Math.random(): 0이상 1미만 난수 리턴

### 배열 메소드 =>현재 메소드에 저장됨

> let [e1,e2, ...e3] = a

* toString()
* splice(삭제할 위치, 삭제할 항목 수, 삽입할 값)
* slice(시작 위치, 끝 위치): 배열의 부분 리턴 
* push(): 배열의 끝에 추가
* pop(): 배열의 끝에서 제거
* unshift(): 배열의 앞에 추가
* shift(): 배열의 앞에서 제거
* concat(): 두 배열 결합해서 새 배열 생성
* sort(): 값 정렬하고 원래 배열에 저장됨
* map(): 콜백 함수가 리턴하는 값들을 배열로 모아서 리턴

> a1.map((value)=>value*2)<br>
> a1.map((number,index)=>number*index)

* join(): 배열 원소들의 값을 결합한 문자열 리턴
* filter(): 배열 원소 각각에 대해서 콜백함수를 호출 후 배열로 리턴
* reduce(): 배열 원소 각각에 대해서 콜백 함수를 호출 후 배열로 리턴

> 바로 이전 호출의 리턴값이 현재 콜백 함수에서 계속 이용됨<br>
> 배열 원소의 합계나 최대값을 구할 때 이용할 수 있음

* forEach(): 각 원소에 대해 콜백함수 리턴
* every(): 배열 원소 모든 값을 콜백함수로 호출해서 사용
* find(): 모든 원소 각각에 대해 콜백 함수 호출, true를 리턴하는 첫번째 원소만을 리턴
* findIndex(): find()와 같음

### 문자열 메소드 => 새 문자열을 리턴함

* "를 출력하고 싶을때: ```\"```
*  indexOf(부분 문자열, 시작 위치): 부분 문자열 위치 리턴
* lastIndexOf(): 끝에서부터 찾음
* search(): 정규식으로 위치 찾기

> /[a-z]/<br>
> /정규식/g: 일치하는 부분 전부 치환(global)<br>
> /정규식/i: 대소문자 무시(ignore case)<br>
> ```[^A]```: 제외<br>
> ?: 바로 앞 정규식 0~1개인지<br>
> *: 0~여러개인지<br>
> +: 1~여러개인지<br>
> ^A: 선두에 A가 있는 문자열인지<br>
> $A: 맨 끝에 A가 있는 문자열인지<br>
> A{3}: A가 3번 반복되는지<br>
> A{1,3}: A가 1번~3번 반복되는지<br>
> \?: ? 문자가 있는지

* slice(시작 위치,끝 위치):  문자열 부분 리턴
* substring(): slice()와 같으나 음수 파라미터 못 씀
* substr(시작위치, 부분 문자열의 길이)
* replace(부분 문자열,치환할 문자열): 첫 번째 부분 문자열만 치환 됨
* toUpperCase(), toLowerCase()
* concat()
* trim(): 문자열 앞뒤의 공백 제거
* charAt()
* split(): 배열로 리턴

### 함수

* 가변 파라미터: ...a
* setTimeout(함수,시간,출력): id값이 리턴됨
* clearTimeout()

### 콜백 함수

* 다른 함수의 파라미터 값을 전달되어 호출되는 함수

### 화살표 함수

* 콜백함수를 간결하게 구현하기 위한 문법
* 자바의 람다식과 비슷함

### 객체 =>새 객체를 리턴함

* constructor(): 생성자 이름
* 속성과 메소드는 모두 public
* Object.assign(to,from): from객체의 속성을 to 객체에 넣음
* Object.entries(): 객체의 모든 속성 값이 들어있는 2차원 배열 리턴
* Object.keys(): 속성 key 목록 배열로 리턴
* Object.values(): 속성 value 목록 배열로 리턴
* Object.freeze(): 객체를 수정할 수 없는 상태로 변경
* Object.isFrozen()

### static 메소드

* 현재 객체를 의미하는 this를 사용할 수 없음
* 다른 객체의 속성이나 메소드를 사용하는 것은 가능함

### 함수형 프로그래밍과 절차적 프로그래밍

* 함수형 프로그래밍은 구체적인 실행 절차를 프로그래머가 결정하지 않음 
* multi thread를 처리 절차를 구현할 필요가 없어서 좋음(parallel() 이용)

> return Arrays.stream().parallel().mapToInt().filter().....

* 함수형은 데이터 처리 절차가 복잡하거나 대규모 병렬 처리가 필요한 빅데이터에서 많이 쓰임
* 비동기(asynchronous) I/O를 구현할 때도 함수형이 쓰임 

> spring async
