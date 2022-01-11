# Linux


#### 터미널 기본적인 명령어
	바보
	멍청이
- pwd : 현재 위치를 확인하는 명령어
- mkdir : 새로운 폴더를 생성하는 명령어
- ls : 폴더나 파일의 목록을 출력하는 명령어
- ls -l : 모든 권한정보 함께 봄)
- ls -a
- ls -al
- nautilus (Ubuntu), open (macOS): 현재 폴더를 파일 탐색기로 여는 명령어
- cd: 폴더에 진입하는 명령어
- touch: 새로운 파일을 생성하는 명령어
- cat: 파일의 내용을 터미널에 출력하는 명령어 (다 출력하기 싫으면 head tail more less 사용)
- rm: 폴더나 파일을 삭제하는 명령어
- mv: 폴더나 파일의 위치를 이동하거나, 이름을 변경하는 명령어
- cp: 폴더나 파일을 복사하는 명령어
- sudo: 관리자 권한을 이해할 수 있다.
- open .  현재 위치를 Finder 로 열기

####
	mkdir hello world >> 폴더 ‘hello’ 와 폴더 ‘wolrd’ 가 각각 생성됨
	mkdir hello\ world >> 폴더 ‘hello world’ 하나 생성 

	[권한 정보 해석방법](https://tutonics.com/2012/12/linux-file-permissions-chmod-umask.html)
	whoami : 현재 로그인된 사용자를 확인

	명령어 옵션 ( 사용법 : 명령어 명령어옵션 ) rm -rf
    - -r : recursive의 약자로 특정 행동을 순환적으로 반복
    - -f : force의 약자로 어떤 행위를 강제 **주의
    - -h ,-help : 도움말 메뉴 (그냥 명령어만 입력해도 도움말 나오는 경우 대부분임)

	명령어를 사용할 때, 등장하는 키워드
    - / : 루트 디렉토리
    - ~ : 홈 디렉토리

	절대 경로와 상대 경로
    - 절대 경로의 시작이 루트 디렉토리(/)
    - 상대 경로의 시작이 현재 디렉토리(.)
    - 상위 폴더는 두 개의 점(..)

	nano <파일이름> : 텍스트 에디터 nano를 이용해 파일을 수정, 저장. (저장 : ^O)


#### nvm

- nvm --version : nvm 버전 확인
- nvm install --lts : node.js 설치
- node -v : node.js 버전확인
- nvm ls : nvm을 통해 설치한 node version들 확인
- nvm install 12.18.3 : 특정 버전 추가 설치
- nvm use 버전넘버  # 예를 들어, nvm use 12.18.3,  nvm use 14.15.5 : 버전 변경하여 사용하기

- node 파일명 : 파일을 node 환경에서 실행(node 를 런타임으로해서 실행)

#### nvm

- npm install : package.jason 에 적힌 의존성모듈을 모두 다운로드받아서 node_modules 에 저장
- npm install <모듈이름> --save-dev : 모듈을 다운받고 자동으로 devDependencies에 추가
- npm install --save <모듈이름> : 모듈을 다운받고 자동으로 dependencies에 추가, (--save 생략가능)
- npm run <스크립트이름> : package.jason 안에 scripts 항목에서 정의된 명령을 실행

