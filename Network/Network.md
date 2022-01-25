# Network

2티어 아키텍쳐 , 3티어 아키텍쳐
	클라이언트 - 서버
	클라이언트 - 서버 - 데이터베이스


## 프로토콜 - 통신규약
https://developer.mozilla.org/ko/docs/Glossary/Protocol

tcp ip smtp http … etc


## API (Application Programming Interface)

‘응용프로그래밍간 의사소통 접점’

	https://ko.wikipedia.org/wiki/API
	
	사용자 인터페이스가 소프트웨어가 인간에게 서비스를 제공하는 접점이라면 API는 소프트웨어가 다른 소프트웨어에게 서비스를 제공하는 접점이다	
	
	HTTP 요청에는 메소드라는 것이 존재
	GET, POST, PUT, PATCH, DELETE, … 알맞게 사용하기
	

## URL & URI

### URL (Uniform Resource Locator)

	네트워크 상에서 웹 페이지, 이미지, 동영상 등의 파일이 위치한 정보

scheme, hosts, url-path

	scheme : 통신 방식(프로토콜)
	hosts : 웹 서버 이름 or 도메인 or IP
	url-path : 서버에서 지정한 루트 디렉토리부터 시작하여 웹 페이지, 이미지, 동영상 등이 위치한 경로와 파일명


### URI (Uniform Resource Identifier)

	URI는 URL을 포함하는 상위개념

scheme, hosts, url-path, query, bookmark

	query : 웹 서버에 보내는 추가적인 질문




## IP & PORT

	IP address(Internet Protocol address) : 네트워크에 연결된 특정 PC의 주소를 나타내는 체계
	PORT : 그 주소에 진입할 수 있는 정해진 통로

#####
	localhost, 127.0.0.1 : 현재 사용 중인 로컬 PC
	0.0.0.0, 255.255.255.255 : broadcast address, 로컬 네트워크에 접속된 모든 장치와 소통하는 주소. 서버에서 접근 가능 IP 주소를 broadcast address 로 지정하면, 모든 기기에서 서버에 접근할 수 있음

	이미 사용 중인 포트는 중복해서 사용할 수 없습니다
	포트 번호 확인하기
	이미 정해진 포트 번호라도, 필요에 따라 자유롭게 사용할 수 있음.
	잘 알려진 포트의 경우 URI 등에 명시하지 않지만, 그 외의 잘 알려지지 않은 포트(:3000과 같은 임시 포트)는 반드시 포함해야 함.




## Domain & DNS

### Domain name
ip 주소 대신 쓰는 이름

### DNS (Domain Name System)
ip 주소와 도매인이름을 필요에 따라 변환해주는 데이터베이스 시스템


#####
	크롬 브라우저 에러 읽기 : chrome://network-errors/




## HTTP Messages

클라이언트와 서버 사이에서 데이터가 교환되는 방식

	https://developer.mozilla.org/ko/docs/Web/HTTP/Messages

### HTTP (HyperText Transfer Protocol)
	HTML과 같은 문서를 전송하기 위한 Application Layer 프로토콜
	웹 브라우저와 웹 서버의 소통이 목적
	https://developer.mozilla.org/ko/docs/Web/HTTP/Overview

Stateless(무상태성)
	HTTP는 통신 규약일 뿐, 클라이언트나 서버의 상태를 확인,추적하지 않음.
	그러므로 필요에 따라 쿠키-세션, API 등을 통해 상태를 확인한다.
	이전 요청이나 다음 요청을 기억하지 않음


### HTTP messages

#### 요청(Requests)과 응답(Responses)의 구조
	start line : 요청이나 응답의 상태. 응답에서는 status line
	HTTP headers : 요청을 지정하거나, 메시지에 포함된 본문을 설명하는 헤더의 집합
	empty line : 헤더와 본문을 구분하는 빈 줄
	body : 요청과 관련된 데이터나 응답과 관련된 데이터 또는 문서를 포함. 요청과 응답의 유형에 따라 선택적으로 사용
	
	start line과 HTTP headers를 묶어 헤드(head), payload는 body라고 함


#####
	MDN: HTTP 요청 메서드
	MDN: HTTP 메시지
	MDN: HTTP 상태 코드

##### Adv
	MDN: MIME Type Content-Type에 대해서 설명합니다.
	브라우저는 어떻게 동작하는가









## AJAX

Asynchronous JavaScript And XMLHttpRequest

	비동기적으로 데이터를 서버에서 받아와 브라우저에 렌더링을 하는 웹 개발 기법
	JavaScript, DOM, Fetch, XMLHttpReqest, HTML 등의 다양한 기술 사용
	https://developer.mozilla.org/ko/docs/Web/Guide/AJAX

AJAX를 구성하는 두가지 핵심기술 : JavaScript와 DOM & Fetch

	Fetch : 비동기적인 방식 으로 사용자가 현재 페이지에서 작업을 하는 동안 서버와 통신가능. 필요한 데이터만 가져
	JavaScript와 DOM : Fetch를 통해 필요한 데이터만 가져와 DOM을 사용해 기존 페이지에서 필요한 부분만 변경



### AJAX의 장점
	서버에서 HTML을 완성하여 보내주지 않아도 웹페이지를 만들 수 있다
	표준화 되면서 브라우저에 상관 없이 AJAX를 사용할 수 있다
	필요한 일부분만 렌더링하기 때문에 빠르고 더 많은 상호작용이 가능한 서비스 가능
	서버로부터 완성된 HTML 파일을 받아오는것 대비, AJAX에서는 필요한 데이터를 텍스트 형태(JSON, XML 등)로 보내면 되기 때문에 더 작은 대역폭 가능



### AJAX의 단점
	Search Engine Optimization(SEO)에 불리
	AJAX에서는 이전 상태를 기억하지 않기 때문에 브라우저의 뒤로가기 버튼 이슈있다. (별도로 History API를 사용해야함)




## SSR과 CSR

### SSR (Server Side Rendering)
웹 페이지를 서버에서 렌더링


###CSR (Client Side Rendering)
웹 페이지를 클라이언트(브라우저)에서 렌더링


### USE

Use SSR
* SEO(Search Engine Optimization) 가 우선순위인 경우
* 웹 페이지의 첫 화면 렌더링이 빠르게 필요한 경우
* 웹 페이지가 사용자와 상호작용이 적은 경우

Use CSR
* SEO 가 우선순위가 아닌 경우
* 사이트에 풍부한 상호 작용이 있는 경우
* 웹 애플리케이션



## CORS

	Simple Requests 가 아닌경우
	브라우저가 자발적으로 서버에 Pre Flighted Requests 를 보내서 허락을 구하함
	응답으로 하락을 받고나면 원래의 진짜 요청을 보내고 응답을 받아옴.
	https://developer.mozilla.org/ko/docs/Web/HTTP/CORS








# REST API

#### REST (Representational State Transfer) https://ko.wikipedia.org/wiki/REST https://developer.mozilla.org/ko/docs/Glossary/REST

#### REST API : 웹에서 사용되는 데이터나 자원(Resource)을 HTTP URI로 표현하고, HTTP 프로토콜을 통해 요청과 응답을 정의하는 방식


## REST API를 잘 적용하기 위한 4단계 REST 성숙도 모델

	0123단계 중 2단계까지만 지켜도 좋은 API 디자인 (HTTP API 라고도 부름)
	
	(이 원칙은 좋은 API 디자인을 하기위해 존재한다. 원칙을 우선시하지 말길)


### 0단계
	단순히 HTTP 프로토콜을 사용하기만 해도 됩



### 1단계
	모든 자원은 개별 리소스에 맞는 엔드포인트(Endpoint)를 사용해야 함
	요청하고 받은 자원에 대한 정보를 응답으로 전달해야함
	(HTTP URI)



### 2단계
	CRUD에 맞게 적절한 HTTP 메소드를 사용
	응답도 그에 맞게 달라져서(응답코드 등) 클라이언트가 확인할 수 있어야함
	MDN HTTP request methods

#### 멱등성을 가지는 메소드 PUT과 그렇지 않은 POST // PUT 과 PATCH
	POST : 요청마다 새로운 리소스를 생성
	PUT : 요청마다 같은 리소스를 반환 (멱등(idempotent)하다 : 매 요청마다 같은 리소스를 반환)	
	PUT(교체) 과 PATCH(수정) 도 구분하여 사용해야 함



### 3단계
하이퍼미디어 컨트롤 적용 // HATEOAS(Hypertext As The Engine Of Application State)
	
	요청은 2단계와 동일
	응답에는 리소스의 URI를 포함한 링크 요소를 삽입하여 작성



Reference
* 5가지의 기본적인 REST API 디자인 가이드
* 호주 정부 API 작성 가이드
* 구글 API 작성 가이드
* MS의 REST API 가이드라인





## Chrome Network Tab
https://www.youtube.com/watch?v=e1gAyQuIFQo
