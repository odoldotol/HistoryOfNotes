# JavaScript

ES6
http://junil-hwang.com/blog/javascript-es6-spec/

	Use namespacing and immediately invoked function expressions.
	Use the "use strict" directive.​
	Declare variables with const and let.​

###
DOM과 JavaScript의 차이에 대해 이해할 수 있다. (Node vs element) (window)

###
	console.log() : 출력
	console.dir() : DOM 을 객체의 모습으로 출력
	

###
	doc[key] = value; // doc = {key : value}
	
	doc.key
	doc[index]
	
	object.key = value // key를 알떄
	object[key] = value // key를 동적으로 결정될떄
	
	배열은 index 를 key값으로 가지는 오브젝트다


###
	Array.split()
	Array.join()



###
	for of
	for in


###
	객체 구조분해





### 호이스팅

	인터프리터가 변수와 함수의 “메모리 공간을 선언 전에 미리 할당”

	선언
		var let const function  …
	초기화
		= *; …
	
	var : 호이스팅시 할당하고 초기화 -> 선언전에 접근시 undefined
	let const : 호이스팅시 할당만 하고 초기화는 하지 않음 -> 선언전에 접근시 레퍼런스 오류 발생






### CRUD

	createElement - CREATE
		document.createElement('div')
		const tweetDiv = document.createElement('div')

	querySelector, querySelectorAll - READ
		const oneTweet = document.querySelector('.tweet')
		const tweets = document.querySelectorAll('.tweet')
		
		querySelectorAll 을 사용아여 조회한 HTML 엘리먼트들은 유사배열로 for문을 사용할수 있다. Array-like Object

	textContent, id, classList, setAttribute - UPDATE
		oneDiv.textContent = 'dev';
		oneDiv.classList.add('tweet')
		setAttribute(name, value)

	remove, removeChild, innerHTML = "" , textContent = "" - DELETE
		remove() vs removeChild()

	appendChild - APPEND // 요소에 연결
		document.body.append(tweetDiv)
		container.append(tweetDiv)
		
		appendChild() prepend() after() before() 도 있음


* children과 childNodes의 차이 (difference between children and childNodes in javascript dom
* tweets에 forEach는 되는데, reduce는 안되는 이유 (why array method is not working on nodelist)
* tweets를 유사 배열에서 배열로 바꾸는 방법 (how to convert nodelist into javascript array)

Advanced Challenge
* DOM의 더 깊은 내용에 대해서 이해할 수 있다.
    * createDocumentFragment를 활용하여, 더 효율적으로 DOM을 제어할 수 있다.
    * HTML5 template tag 사용법을 이해할 수 있다.
    * children과 childNodes의 차이를 이해할 수 있다.
    * 같은 엘리먼트를 appendChild 하면, 기존 엘리먼트를 복사할까?
    * 좌표 정보 조회를 할 수 있다. - offsetTop...
    * 크기 정보 조회를 할 수 있다. - offsetWidth...


visibility: hidden // 엘리먼트가 차지하는 영역을 그대로 남겨놓음
display: none // 브라우저에서 아예 영역조차 사라짐



Event


1. 이벤트 핸들러 생성
	btn.onclick = function() {
		console.log('버튼이 눌렸습니다!');
	}

2. 이벤트 리스너 생성
	btn.addEventListener('click', function() {
		console.log('버튼이 눌렸습니다!');
	});

3. 함수 생성해서 1번 하기
	function handler() {
		console.log('버튼이 눌렸습니다!');
	}

	btn.onclick = handler;



onclick 에 직접 할당하는 것과 addEventListener의 차이



인자 사용
	function handleClick(event) {
		console.log(event.target.textContent);
	}

	btnAmericano.onclick = handleClick;
	btnCaffelatte.onclick = handleClick;



이벤트 핸들러 함수에서 이벤트가 발생한 곳의 정보를 확인해보기
유효성 검사에서 활용할 수 있는 정규표현식 사용법 기초 익히기 
관심사 분리를 적용하거나, 유효성 검사 함수를 따로 분리해서 설계해보기



이벤트 객체에 대해서 더 자세히 알고 싶다면, 아래 키워드를 검색해서 학습하세요
* onsubmit
* onchange
* onmouseover
* onkeyup
* event.preventDefault



return value.length >= 4 // boolean 이 리턴됨
Array.isArray(arr) // boolean
Array.concat(arr)	// Array의 요소와 arr 의 요소를 순서대로 갖는 새로운 하나의 배열
	= [...Array , …aar] // spread syntax





