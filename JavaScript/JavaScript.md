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


CRUD

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





Function


* 함수의 선언과 호출, 그리고 결과값 리턴
    * 문제를 해결하기 위해 논리(알고리즘)을 컴퓨터가 이해할 수 있도록 코드로 작성할 수 있다.
    * 함수 표현식과 함수 선언식을 활용하여, 변수에 함수를 할당할 수 있다.
    * 함수가 담긴 변수에 괄호를 붙여 함수를 호출할 수 있다.
    * 함수가 결과를 리턴하는 경우와 그렇지 않은 경우를 구별할 수 있다.




Element.matches()
	var result = element.matches(selectorString);

모듈 사용하기
	require 함수 이용하여 모듈의 함수를 변수에 넣어 선언하고 변수를 호출하여 사용할 수 있음.



호이스팅
	인터프리터가 변수와 함수의 “메모리 공간을 선언 전에 미리 할당”

	선언
		var let const function  …
	초기화
		= *; …
	
	var : 호이스팅시 할당하고 초기화 -> 선언전에 접근시 undefined
	let const : 호이스팅시 할당만 하고 초기화는 하지 않음 -> 선언전에 접근시 레퍼런스 오류 발생




고차 함수 (higher order function)
	함수를 인자(argument)로 받을 수 있고, 함수의 형태로 리턴할 수 있는 함수


1. 다른 함수를 인자로 받는 경우

	function double(num) {
		return num * 2;
	}

	function doubleNum(func, num) {
		return func(num);
	}

	let output = doubleNum(double, 4);
	console.log(output); // -> 8


2. 함수를 리턴하는 경우

	function adder(added) {
		return function (num) {
			return num + added;
		};
	}

	let output = adder(5)(3); // -> 8
	console.log(output); // -> 8

	const add3 = adder(3);
	output = add3(2);
	console.log(output); // -> 5

3. 함수를 인자로 받고, 함수를 리턴하는 경우

	function double(num) {
		return num * 2;
	}

	function doubleAdder(added, func) {
		const doubled = func(added);
		return function (num) {
			return num + doubled;
		};
	}

	doubleAdder(5, double)(3); // -> 13

	const addTwice3 = doubleAdder(3, double);
	addTwice3(2); // --> 8





arguments 객체는 모든 함수 내에서 이용 가능한 지역 변수





내장 고차함수

	
	slice


	forEach


	find


	filter
		배열의 각 요소를 인자로 쓸수있는 함수가 리턴하는 값이 true 면 남기고 false면 버리고 새로운 배열을 만들어서 리턴한다.

		Array.filter(function(el){
			~~
			return boolean
		})

		filter 메소드에 들어가는 콜백 함수는 truthy 또는 falsy를 리턴할 수 있습니다.
		그러나 filter 메소드에 들어가는 콜백 함수는 Deep equality를 통해 조건을 명확하게 밝히는 걸 권장합니다.
		따라서 이 콘텐츠에서도 콜백 함수가 내부 조건에 따라 참(true) 또는 거짓(false)을 리턴하도록 구현하길 권장합니다.

	map
		배열의 각 요소를 인자로 쓸수있는 함수가 리턴하는 값이 각 요소를 대체하는 새로운 배열을 리턴한다.
	
		Array.map(function(el){
			~~
			return *
		})


	reduce
		배열의 각 요소를 cur 로 받고 acc = initialValue 로 시작한다. 리턴하는 값을 acc 로 하고 반복하여 배열을 하나의 값으로 만들어 리턴한다.
		initialValue 가 없으면 첫번째 요소는 그냥 리턴된다.

		Array.reduce(function(acc, cur){
			~~
			return *
		},initialValue)


	sort


	some


	every




추상화
	일반적으로 우리가 구현하고 싶은 서비스는 매우 추상적인것에서 출발한다.
	우리는 구체화를 통해 서비스를 실현 가능하도록 만든다.
	이에 반해 너무 구체적이고 사소한 것들의 집합은 추상화를 통해 처리해버릴 수 있다.
	이렇게 하면 우리는 추상화된 것의 아래단에 있는 사소한 것들은 잊어도 된다.
	마치 컴퓨터가 0101 로 보는것을 우리가 0101로 볼 필요가 없어졌듯이
	추상화가 잘 될 수록 우리는 더 높은 추상적인 개념에 빨리 도달할 수 있고,
	결국 우리가 일반적으로 구현하고 싶은 매우 높은 수준의 추상적인 결과물에 가까워 지는것이다.






Advanced
* MapReduce 학습하기 (MapReduce Model)
* 자바스크립트에서 커링(currying)과 클로저(closure)의 차이 이해하기 (js closure vs curry)
* 선언형 프로그래밍(declarative programming)과 절차형 프로그래밍(imperative programming)의 차이를 배열 메소드를 통해 이해하기 (js imperative vs declarative)
* 함수의 조합(function composition)에 대해 학습하기 (javascript function composition)

