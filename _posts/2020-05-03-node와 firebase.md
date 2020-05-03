---
layout: post
title: "node와 firebase"
tags: [node,firebase]
comments: true
---

node 설정파일과 firebase service
<!--more-->

## node.js 프로젝트 설정 파일

### eslint.json

* 자바스크립트는 인터프리트 방식이라 컴파일을 하지 않음 -> 오타가 있어도 컴파일 에러 발생 안함
* eslint는 컴파일러처럼 소스코드를 분석해서 오타같은 문법 오류 찾아줌
* ```eslint --init```

### package.json

* node.js 프로젝트 설정 파일
* 현재 프로젝트의 name,version,author....
* 생성 명령은 ```npm init```

### package-lock.json

* 프로젝트에 필요한 라이브러리들의 정확한 버전이 자동으로 등록됨

### application framework class library

* 개발에 필요한 골격에 해당하는 클래스들을 모아놓은 라이브러리

## Firebase service

### firebase realtime database

* 데이터를 서버에 저장하기 위한 서비스로 관계형 데이터베이스가 아님
* key, value 구조로 저장하고 조회

> ```firebase.database().ref([데이터베이스 이름]).on('value',(snapshot) =>{ let a=snapshot.val(); });```<br>
> on()은 맨 처음 한번 실행됐다가 디비에서 값이 변하면 그때 또 한번 실행됨

### 동기와 비동기

* 동기는 내가 직접 읽어오는 방식
* 비동기는 내가 받는 방식

