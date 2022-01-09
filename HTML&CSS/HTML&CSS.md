HTML&CSS


HTML


* HTML을 CSS를 적용하고, JavaScript로 개발할 수 있게(Programmable) 작성할 수 있다.

* 동적인 웹 어플리케이션 개발을 위한 HTML 구조를 짤 수 있다.
    * 간단한 웹 페이지 기획안을 HTML 문서로 표현할 수 있다.
    * id와 class를 목적에 맞게 사용하여 사람과 컴퓨터가 읽기 쉬운, 의미있는(Sementic) HTML 문서를 작성할 수 있다.
    * HTML5 semantic tag를 적재적소에 사용하여 사람과 컴퓨터가 읽기 쉬운 시멘틱한 HTML 문서를 작성할 수 있다.

* CSS에서 쓰이는 단위의 두가지 구분을 이해할 수 있다.
    * 각 단위가 적합한 경우를 구분할 수 있다.
    * Rem vs em
* CSS 박스 모델을 이해할 수 있다
    * box model
        * width, height
        * Inline vs block
        * Margin border padding content
    * 박스 크기를 측정하는 두가지 기준의 차이를 이해할 수 있다.



div  section  header  p  등등 시맨틱 태그
반복되는 성향의 요소에’만’ class를 쓰자. 유일요소에는 id를 쓸것


template 태그
	이용해보기




와이어프레임
	뼈대, 레이아웃
	간단하지만 이것만 봐도 대강 어떤 목적을 가진 프로그램인지 유추가 가능해야한다
	이것만 보고도 html 코딩 가능해야한다. 

목업
	ex) 하드코딩








CSS


커맨드 + 쉬프트 + r  =  캐시까지 새로고침



a > b {} vs a b {}

CSS flexbox의 활용

CSS pseudo-class를 활용하여, interactive한 버튼을 만들 수 있습니다.




CSS Selector

셀렉터
	h1 { }
	div { }
전체 셀렉터
	* { }
Tag 셀렉터	section, h1 { }		( , 로 구분하여 추가)
ID 셀렉터	#only { }
class 셀렉터	.widget { }
	.center { }

(	.widget#only { } : 띄어쓰기 없이 ID와class셀렉터를 함께 쓰면 and 조건으로 셀렉	)
attribute 셀렉터 (암기할 필요는 없습니다)	a[href] { }
	p[id="only"] { }
	p[class~="out"] { }
	p[class|="out"] { }
	section[id^="sect"] { }
	div[class$="2"] { }
	div[class*="w"] { }
후손 셀렉터	header h1 { }		(띄어쓰기로 구분)
자식 셀렉터 (후손 셀렉터와의 차이를 반드시 알고 있어야 합니다)	header > p { }
인접 형제 셀렉터	section + p { }
형제 셀렉터	section ~ p { }
가상 클래스	a:link { }
	a:visited { }
	a:hover { }
	a:active { }
	a:focus { }
요소 상태 셀렉터	input:checked + span { }
	input:enabled + span { }
	input:disabled + span { }
구조 가상 클래스 셀렉터 (암기할 필요는 없습니다)	p:first-child { }
	ul > li:last-child { }
	ul > li:nth-child(2n) { }
	section > p:nth-child(2n+1) { }
	ul > li:first-child { }
	li:last-child { }
	div > div:nth-child(4) { }
	div:nth-last-child(2) { }
	section > p:nth-last-child(2n + 1) { }
	p:first-of-type { }
	div:last-of-type { }
	ul:nth-of-type(2) { }
	p:nth-last-of-type(1) { }
부정 셀렉터	input:not([type="password"]) { }
	div:not(:nth-of-type(2)) { }
정합성 확인 셀렉터	input[type="text"]:valid { }
	input[type="text"]:invalid { }




레이아웃 리셋
	때때로 HTML 문서가 갖는 기본 스타일이, 레이아웃을 잡는 데 방해가 되기도 함
	항상 필요한 것은 아니다. 필요할 떄만 쓰자.

기본 스타일링을 제거하는 CSS 코드의 예

* {
	box-sizing: border-box;
}

body {
	margin: 0;
	padding: 0;
}



flex

display: flex
	기본값으로, display: flex가 적용된 부모 박스의 자식 요소는 왼쪽부터 차례대로 가로 배치됨.

flex-direction: row (기본값)
flex-direction: column


자식요소 기본값
flex: 0 1 auto;
	flex: <grow> <shrink> <basis>

grow
	grow/grow총합 의 비율로 조정 (0 이면 기본크기)

shrink
	

basis
	자식 박스가 grow나 shrink에 의해 늘어나거나 줄어들기 전에 가지는 기본 크기
	grow가 0일 때, basis 크기를 지정하면 그 크기를 유지
	0% 를 주어 초기화 후, grow 속성으로 비율조정할 수 있음

따로 입력 가능
	flex-grow: 0;
	flex-shrink: 1;
	flex-basis: auto;





width와 flex-basis를 동시에 적용하는 경우, flex-basis가 우선
width(초과 가능) vs max-width(초과불가)



em rem
vh vw



main axis
	flex-direction 의 값을 따름
cross axis
	여러 개의 main axis와 수직을 이루는 방향

justify-content 속성
	main axis를 기준으로 정렬
	
	속성의 값
		flex-start
		flex-end
		center
		space-between
		space-evenly
		space-around
		

align-items 속성
	cross axis를 기준으로 정렬

	속성의 값
		flex-start
		flex-end
		center
		stretch


visibility: hidden // 엘리먼트가 차지하는 영역을 그대로 남겨놓음
display: none // 브라우저에서 아예 영역조차 사라짐


