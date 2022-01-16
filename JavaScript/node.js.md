# node.js

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



