Ubuntu

터미널 실행
* 단축키: Ctrl(컨트롤 키) + Alt(알트 키) + t(영문 t)




nautilus . : 현재 위치를 GUI 로 실행




* Linux Ubuntu 운영체제에서 사용하는 apt 패키지 매니저에 대해 알고, 명령어를 통해 패키지를 관리할 수 있다.
    * apt update: 패키지의 업데이트 여부 확인
    * apt list --upgradable: 업데이트 필요한 파일 조회
    * apt upgrade: 프로그램 업그레이드
    * apt show: 프로그램의 정보 확인
    * apt install: 프로그램 설치
    * apt list --installed: 설치된 프로그램 목록 보기
    * apt remove: 프로그램 삭제
    * apt search : 패키지 검색




* 패키지 목록 갱신: apt update(관리자 권한 필요)
    * 패키지를 다운로드받을 수 있는 여러 저장소의 최신 정보를 업데이트합니다. 새로운 저장소를 추가하거나, 패키지를 설치하기 전, 최신 정보를 갱신합니다.
    * 설치된 프로그램이 새로운 버전으로 변경되지 않습니다.
* 업그레이드 가능한 패키지 목록을 출력: apt list -—upgradable
* 전체 패키지 업그레이드(버전 업): apt upgrade (관리자 권한 필요)
* 특정 패키지만 업그레이드(버전 업): apt --only-upgrade install 패키지이름 (관리자 권한 필요)
* 패키지 설치: apt install 패키지이름 (관리자 권한 필요)
* 설치된 패키지 보기: apt list --installed
* 패키지 검색: apt search 검색어
* 패키지 정보 확인: apt show 패키지이름
* 패키지 삭제: apt remove 패키지이름(관리자 권한 필요)
