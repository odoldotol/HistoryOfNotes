# JavaScript

ES6
http://junil-hwang.com/blog/javascript-es6-spec/

	Use namespacing and immediately invoked function expressions.
	Use the "use strict" directive.​
	Declare variables with const and let.​


## JavaScript types


* 원시 값(Primitive values) (언어의 최고 로우레벨에서 직접 표현되는 불변 데이터)
    * Boolean 타입
    * Null 타입 // 식별되지 않은 것 // 아무런 객체를 가리키지 않음을 표현 // 존재하지 않을 때 그 객체 대신 사용가능 ( typeof null // “object” )
    * Undefined 타입 // 전역 객체의 속성 // 선언한 후 할당하지 않은 곳에 자동으로 할당됨 ( typeof undefined // "undefined" )
    * Number 타입
    * BigInt 타입
    * String 타입
    * Symbol 타입
* 객체(Objects) (collections of properties)



#####
DOM과 JavaScript의 차이에 대해 이해할 수 있다. (Node vs element) (window)

#####
	console.log() : 출력
	console.dir() : DOM 을 객체의 모습으로 출력
	

#####
	doc[key] = value; // doc = {key : value}
	
	doc.key
	doc[index]
	
	object.key = value // key를 알떄
	object[key] = value // key를 동적으로 결정될떄
	
	배열은 index 를 key값으로 가지는 오브젝트다


#####
	Array.pop() // 맨 뒤 요소 삭제
	Array.push(ele) // 맨 뒤에 요소 삽입
	Array.unshift(ele) // 맨 앞에 요소 삽입
	Array.shift() // 맨 앞 요소 삭제
	Array.splice(index , deleteCount , item1 , item2 , …) // index 위치부터 deleteCount 만큼 요소 삭제하고 …item 삽입
	Array.slice(startIndex , endIndex) // startIndex 위치부터 endIndex 전까지를 요소로 갖는 새로운 배열을 shallow copy로 반환
	Array.concat(arr)	// Array의 요소와 arr 의 요소를 순서대로 갖는 새로운 하나의 배열 반환 = [...Array , …aar] ( spread syntax )
	Array.join(separator) // 모든 배열 요소가 문자열로 변환되고 연결한 하나의 문자열을 반환 // separator(optional) : 각 요소를 구분할 문자열 , 기본값 = “,”

#####
	String.split(separator, limit) // separator


#####
	for of
	for in


#####
	객체 구조분해





### 호이스팅

	인터프리터가 변수와 함수의 “메모리 공간을 선언 전에 미리 할당”

	선언
		var let const function  …
	초기화
		= *; …
	
	var : 호이스팅시 할당하고 초기화 -> 선언전에 접근시 undefined
	let const : 호이스팅시 할당만 하고 초기화는 하지 않음 -> 선언전에 접근시 레퍼런스 오류 발생






## CRUD

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



## Event


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



* onsubmit
* onchange
* onmouseover
* onkeyup
* event.preventDefault



return value.length >= 4 // boolean 이 리턴됨
Array.isArray(arr) // boolean






