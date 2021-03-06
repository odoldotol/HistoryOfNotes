# node.js

Node.js는 "비동기 이벤트 기반 자바스크립트 런타임"  by Node.js 소개 문서

로컬 환경에서 자바스크립트를 실행할 수 있는 자바스크립트 런타임
브라우저에서 불가능한 몇 가지 일이 가능



#### nvm
    - nvm --version : nvm 버전 확인
    - nvm install --lts : node.js 설치
    - node -v : node.js 버전확인
    - nvm ls : nvm을 통해 설치한 node version들 확인
    - nvm install 12.18.3 : 특정 버전 추가 설치
    - nvm use 버전넘버  # 예를 들어, nvm use 12.18.3,  nvm use 14.15.5 : 버전 변경하여 사용하기

    - node 파일명 : 파일을 node 환경에서 실행(node 를 런타임으로해서 실행)

#### npm
    - npm install : package.jason 에 적힌 의존성모듈을 모두 다운로드받아서 node_modules 에 저장
    - npm install <모듈이름> --save-dev : 모듈을 다운받고 자동으로 devDependencies에 추가
    - npm install --save <모듈이름> : 모듈을 다운받고 자동으로 dependencies에 추가, (--save 생략가능)
    - npm run <스크립트이름> : package.jason 안에 scripts 항목에서 정의된 명령을 실행



###
	npx create-react-app <앱이름> : 새로운 리액트 프로젝트를 시작
	npm run start : 

	npm install react-router-dom@5.3.0 : React Router DOM을 설치 (@5.3.0 : 버전 , 생략하면 최신버전)




## Node.js 내장 모듈을 사용하는 방법

Node.js 내장 모듈 목록 : Node.js v14.17.0 Documentation

	모든 모듈은 '모듈을 사용하기 위해 불러오는 과정'이 필요

	const fs = require('fs'); // 파일 시스템 모듈을 불러옵니다
	// 이제 fs.readFile 메소드 등을 사용할 수 있습니다!

	구조분해임포트로하면 import { readFile } from “fs”; 하면
	fs. 없이 readFile 그냥 쓰면 됨

	( 메소드 fs.readFile 은 비동기적으로 파일 내용 전체를 읽습니다. )


### 3rd-party 모듈을 사용하는 방법

	npm install underscore

	node_modules에 underscore가 설치됨
	이제 Node.js 내장 모듈을 사용하듯 require구문을 통해 underscore 를 사용할 수 있음

	const _ = require('underscore');




#####
	Node.js 에서 경로를 다룰 때, __dirname과 path module은 매우 유용함
	__dirname의 사용 방법. How to use __dirname in Node.js



