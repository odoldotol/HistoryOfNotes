# Linux


#### 터미널 기본적인 명령어

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

######
	mkdir hello world >> 폴더 ‘hello’ 와 폴더 ‘wolrd’ 가 각각 생성됨
	mkdir hello\ world >> 폴더 ‘hello world’ 하나 생성 

	[권한 정보 해석방법](https://tutonics.com/2012/12/linux-file-permissions-chmod-umask.html)
	whoami : 현재 로그인된 사용자를 확인

	명령어 옵션 ( 사용법 : 명령어 명령어옵션 ) rm -rf
    - <명령어> -r : recursive의 약자로 특정 행동을 순환적으로 반복
    - <명령어> -f : force의 약자로 어떤 행위를 강제 **주의
    - <명령어> -h ,-help : 도움말 메뉴 (그냥 명령어만 입력해도 도움말 나오는 경우 대부분임)

	디렉토리
    - / : 루트 디렉토리
    - ~ : 홈 디렉토리
    - 절대 경로의 시작이 루트 디렉토리(/)
    - 상대 경로의 시작이 현재 디렉토리(./)
    - 상위 폴더(../)

	nano <파일이름> : 텍스트 에디터 nano를 이용해 파일을 수정, 저장. (저장 : ^O)


