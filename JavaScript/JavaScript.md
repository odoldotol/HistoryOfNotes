# JavaScript

ES6
http://junil-hwang.com/blog/javascript-es6-spec/

	Use namespacing and immediately invoked function expressions.
	Use the "use strict" directive.​
	Declare variables with const and let.​

	const : 재 선언 불가능 , 재 할당 불가능
	let : 재 선언 불가능 , 재 할당 가능


#####
DOM과 JavaScript의 차이에 대해 이해할 수 있다. (Node vs element) (window)


#####
	console.log() : 출력
	console.dir() : DOM 을 객체의 모습으로 출력


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
	return value.length >= 4 // boolean 이 리턴됨
	Array.isArray(arr) // boolean
	

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
	Array.sort(function(a,b){return ? }) // a, b 두개의 요소를 비교하여 리턴값이 양수면 b, a 순 정렬, 음수면  a, b 정렬, 0를 리턴하면 순서를 변경하지 않음

#####
	String.split(separator, limit) // separator


#####
	++i
	i++
	x+=y


#####
	문자열 생성시 따옴표 대신, 백틱(`)사용하기
	백틱(`)으로 템플릿 리터럴을 사용하면, 줄바꿈 등을 쉽게 표현
	${ } 사이에 변수나 연산 등을 삽입 (표현식 삽입(Expression interpolation))

```javascript
`${name}의 구매가는 ${price * num}원 입니다.`
```



## Loop

	for
	for of
	for in
	while
	do...while


#####
	break return continue


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
		oneDiv.className = ‘tweet'
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


1. 이벤트 핸들러 할당 (연이어 하면 덮어씀)
	btn.onclick = function() {
		console.log('버튼이 눌렸습니다!');
	}

2. 이벤트 리스너 생성 (다수의 리스너 추가 가능, 더 안전함, 지원안하는 구형브라우저가 있음)
	btn.addEventListener('click', function() {
		console.log('버튼이 눌렸습니다!');
	});

3. 함수 생성해서 1번 또는 2번 하기
	function handler() {
		console.log('버튼이 눌렸습니다!');
	}

	btn.onclick = handler;
	btn.addEventListener('click', handler);
	// 리스너 삭제 // btn.removeEventListener('click', handler);

Event reference https://developer.mozilla.org/ko/docs/Web/Events




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




#####
	[onClick이벤트에 event객체 외 다른 인자 전달하기](https://velog.io/@haribo/onClick%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-event%EA%B0%9D%EC%B2%B4-%EC%99%B8-	%EB%8B%A4%EB%A5%B8-%EC%9D%B8%EC%9E%90-%EC%A0%84%EB%8B%AC%ED%95%98%EA%B8%B0)

## 비동기

#### 동기
	처리되면 다음주문받음 // blocking
		(처리의끝=새로운주문) // 동기적(synchronous)

#### 비동기
	언제든 주문받고 // non-blocking
		주문과 처리가 따로 수행될수 있음 // 비동기적(asynchronous)

	Node.js // non-blocking하고 비동기적(asynchronous)으로 작동하는 런타임
	Node.js는 "비동기 이벤트 기반 자바스크립트 런타임"  by Node.js 소개 문서
	JavaScript의 비동기적 실행(Asynchonous execution)이라는 개념은 웹 개발에서 특히 유용


어떤 경우에 중첩된 callback이 발생하는지 이해해보기



#####
	비동기적으로 처리하고싶은일이 있다면,
	이후의 일은 콜백함수로 만들어서 인자에 넣어서 보내버리고
	나는 다음 요청을 또 받을 수 있다. // 비동기적 실행

	이벤트 처리되는 모습이 대표적인 예시이다.
	우리는 핸들러를 콜백함수로 만들고 인자로 넣어 보내버린다.
	그래서 계속 이벤트를 받을 수 있는것


request animation frame 찾아보기

https://developer.mozilla.org/ko/docs/Web/JavaScript/EventLoop 이벤트루프






### 프로미스

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise


#### Promise의 세 가지 상태
	프로미스의 핵심!! (대기 이행 거부)  아무것도 안하거나 아직 리솔브가 호출되지 않은경우는 대기(pending)

####
	Promise 실행함수는 두 개의 파라미터 resolve 와 reject 를 가짐
	resolve, reject함수에는 인자를 넘길 수 있음
	리솔브는 문제없을때 넘기는 인자를 담음
	리젝트는 실패했을때 넘기는 인자를 담음

	프로미스의 매쏘드인 덴과 캐치
	둘다 다시 프로미스를 리턴함

	덴은 두개의 콜백함수를 인자로 가질수 있음
	첫번째는 리솔브했을떄 실행될 콜백함수이고 두번쨰는 리젝트 했을때 실행될놈
	각각은 리솔브함수와 리젝트함수의 인자를 쓸수있다
	하지만 실재 개발시에는 then에서 2단 핸들러보다는 캐치를 사용해 처리함
	덴의 콜백함수에서 리솔브함수에서 넘긴 인자를 쓰고
	캐치의 콜백함수에서 리젝트함수에서 넘긴 인자를 씀

	캐치는 하나의 콜백함수를 인자로 가짐. 그 함수는 reason 을 인자로 가짐 reason은 리젝트 이유임. 리젝트함수에서 넘겨준 인자.

	덴은 프로미스를 리턴하므로
	덴의 콜백함수의 리턴값을 다음 덴의 파라미터로 쓸수있다


프로미스체인



### async

	fulfil Promise가 반환
	때문에 반환된 값을 사용하기 위해선 .then() 블럭을 사용해야 합

#####
	async 를 함수와 같이 사용하면 결과를 직접 반환하는게 아니라 Promise를 반환
	또한 동기식 함수는 await 사용을 위한 지원과 함께 실행되는 잠재적인 오버헤드를 피할 수 있다
	함수가 async 라고 선언될 때 필요한 핸들링만 추가하면 JavaScript엔진이 우리가 만든 프로그램을 최적화 할 수 있는것!

#### async 및 await

	await는 async function 안에서만 쓸 수 있음
	.then()블럭을 사용하여 작업을 이어가는 대신 메서드 호출 전에 await 키워드를 사용하여 반환된 결과를 변수에 할당
	await 키워드는 JavaScript 런타임이 이 라인에서 비동기 코드를 일시 중지하여 비동기 함수 호출이 결과를 반환할 때 까지 기다리게 함
	그러나 외부의 다른 동기 코드는 실행될 수 있도록 한다
	작업이 완료되면 코드는 계속 이어져서 실행

async/await와 함께 다시 쓰는 promise code

#####
	await 키워드 다음에 등장하는 함수 실행은 어떤 타입을 리턴할 경우에만 의미가 있나요?
	await 키워드를 사용할 경우, 어떤 값이 리턴되나요?


### Reference
A. MDN
* Promise
* Promise 생성자
* Promise Prototype
B. Google developer web fundamentals
* 웹의 최신 기술을 전반적으로 학습할 때, 지속적으로 읽을 수 있는 좋은 자료가 있습니다.
* JavaScript Promises: An introduction
* Async functions - making promises friendly
C. The Modern JavaScript Tutorial
* async/await
D. 그밖에...
* What is a Promise
* 캡틴판교, 자바스크립트 Promise 쉽게 이해하기
* [Advanced] Understanding Asynchronous JavaScript


#### Promise.all

Promise.all 의 인자 프로미스를 요소로하는 배열 
	Promise.all([promise1, promise2, promise3])

* Promise.all 을 사용할 경우에 then 메소드의 파라미터는 어떠한 형태인가요?
* Promise.all 에 두 개의 Promise 요청이 전달되고, 만일 그 중 하나가 rejected 상태가 되는 경우, then메소드를 따라가나요, 아니면 catch 메소드를 따라가나요?
