---
layout: post
title: "AWS와 Jupyter notebook"
tags: [AWS,Jupyter]
comments: true
---

AWS와 Jupyter notebook 설명과 설치 중 에러
<!--more-->

## AWS

### 인스턴스

* 서버
* 인스턴스에 접근하기 위해서는 인스턴스를 제어할 클라이언트가 필요함 ->ssh를 이용해서 제어함(그 과정에서 putty 프로그램을 이용함)

### key

* 인스턴스에 원격으로 접속할 때 사용하는 비밀번호와 같은 역할
* 한번만 발급되고 이후는 발급이 안되므로 안전한 곳에 보관이 필요함
* 그래서 도커의 이미지로 저장

## Jupyter notebook

* 인스턴스를 gui 환경에서 관리하려고 이용
* 서버의 외부에서 해당 서버에 웹 브라우저를 이용해서 접근할 수 있도록 ```https://퍼블릭ip:8888```로 접속

### 설정중 에러

1. ``` sudo jupyter-notebook --allow-root```하면 ```https://퍼블릭ip:8888```로 연결이 잘 됐지만 daemon으로 항상 실행하도록 하려고 service파일을 만들어서 연결했을때는 ```http://localhost:8888```로 연결되는 오류 발생

* python3 버전을 보니 3.5였고 검색해보니 3.6이상으로 해야지 제대로 된다는 말이 있어서 3.6으로 바꿨고 이 과정에서 많은 에러 발생....그래도 바꿔서 실행하니  ```https://퍼블릭ip:8888```로 잘 돌아감

2.  ERROR: Package 'ipython' requires a different Python: 3.5.3 not in '>=3.6'

* ```python -V```를 하면 다운받은 3.6버전이 출력되지만 ```python3```을 하면 3.5버전이 출력되서 이런 에러 발생함
* [4번 심볼릭 링크 연결](https://eehoeskrap.tistory.com/316)로 해결했음.

>permission denied에러 발생시 ```ln -s ....```코드 앞에 sudo 붙여서 강제로 실행

3.  ModuleNotFoundError: No module named 'pip._internal.cli'

* pip이 없어서 발생하는 오류
* ```sudo python3 get-pip.py --force-reinstall```로 강제로 재설치

