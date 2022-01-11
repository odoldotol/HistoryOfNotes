# Git&Github

[마크다운](https://gist.github.com/ihoneymon/652be052a0727ad59601)

######SSH key 이용하기
    1. ssh-keygen : ssh 키를 생성
    2. cat ~/.ssh/id_rsa.pub : ssh 공개키(Public Key)를 출력
    3. 복사하여 GitHub > settings > SSH and GPG keys 에 새로운 키 추가





* git 명령어
    * clone <Repository 주소>
    * status : staging area와 untracked files 목록에 어떤 것들이 있는지 확인 / merge conflicts 확인
    * restore : commit되지 않은 Local Repository의 변경 사항을 폐기/취소
    * add <파일명> / add . : Local 의 untracked file 을 staging area 로 추가
    * commit (-m “”) : staging area 에 add 된 변경사항을 Local Repository 에 저장 (Merge commit은 자동으로 Commit 메시지가 생성됨)
    * reset (HEAD^ , --hard , --soft) : Remote Repository에 업로드 되지 않은 Local Repository의 commit 을 취소
    * log : 현재까지 commit 된 로그들을 터미널 창에서 확인
    * pull <shortname> <branch> : Remote Repository의 해당 branch 내용을 Local Repository로 가져옴
    * push <origin> <branch> : Local Repository에 저장되어 있는 commit 기록들을 내 Remote Repository 에 업로드
    * init : 기존 디렉토리를 Git Repository(Local)로 변환하거나 새로운 Repository를 초기화
    * remote add <shortname> <Repository 주소> : Local Repository를 Remote Repository와 연결
    * remote -v : 현재의 Local Repository와 연결된 모든 Remote Repository 목록을 확인


* Git Repository의 commit되지 않은 변경 사항을 취소할 수 있다.
    * reset HEAD <file>
    * checkout -- <file>
* 협업을 위한 git 개념을 이해할 수 있다.
    * branch, merge의 개념
    * remote repository에서 origin과 upstream의 차이점


