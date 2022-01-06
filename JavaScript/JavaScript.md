JavaScript

Use namespacing and immediately invoked function expressions.
Use the "use strict" directive.​
Declare variables with const and let.​


<script src=“디렉토리”></script>
	HTML 내에서 위치에 따른 결과


DOM과 JavaScript의 차이에 대해 이해할 수 있다.
DOM 의 일부분은 일부 브라우저에서 지원하지 않을 수 있다


console.log()
	출력
console.dir()
	DOM 을 객체의 모습으로 출력

엘리먼트 vs 노드
	

속성
	dataset : data-* 속성에 담긴 값



CRUD
	createElement - CREATE
		document.createElement('div')
		const tweetDiv = document.createElement('div')

	querySelector, querySelectorAll - READ
		const oneTweet = document.querySelector('.tweet')
		const tweets = document.querySelectorAll('.tweet')
		
		 query라는 단어는 개발자 간에 "ㅇㅇㅇ를 조회한다"라는 의미를 "쿼리를 날리다"라는 jargon(특정 영역에서만 사용되는 단어)로 굳어짐

		querySelectorAll 을 사용아여 조회한 HTML 엘리먼트들은 배열처럼 for문을 사용하실 수 있다.
		조회한 HTML 엘리먼트들아 배열은 아님!
		이런 '배열 아닌 배열'을 유사 배열, 배열형 객체 등 다양한 이름으로 부름. 정식 명칭은 Array-like Object

		getElementByID/TagName/Class 등등은 querySelector와 비슷한 역할을 하는 옛날방식임 있다는것만 알고 넘어가자

		MDN에서 querySelector를 검색하여, 다음의 질문에 대해 학습합니다.
            * querySelector의 첫번째 인자에 'div'를 넣으면 어떻게 될까요?
            * querySelector를 통해서 더 복잡한 작업을 할 수 있을까요?
            * querySelector의 부모는 꼭 document 객체여야만 할까요?

	textContent, id, classList, setAttribute - UPDATE
		oneDiv.textContent = 'dev';
		oneDiv.classList.add('tweet')
		MDN에서 setAttribute 라는 메소드를 검색해보기

	remove, removeChild, innerHTML = "" , textContent = "" - DELETE
		tweetDiv.remove() // 이렇게 append 했던 엘리먼트를 삭제 (remove <-> add)
		document.querySelector('#container').innerHTML = ''; // 아주 간단하게 모든 자식 엘리먼트를 지울 수 있다.
			innerHTML 을 이용하는 방법은 분명 간편하고 편리한 방식이지만, innerHTML은 보안에서 몇 가지 문제를 가지고 있습니다. 
			innerHTML과 textContent의 차이 이해하기
		removeChild 는 자식 엘리먼트를 지정해서 삭제하는 메소드
			ex1) 자식 엘리먼트가 남아있지 않을 때까지, 첫 번째 자식 엘리먼트를 삭제
				while (container.firstChild) {
					container.removeChild(container.firstChild);
				}
			ex2) 자식 엘리먼트가 1개만 남을 때까지, 마지막 자식 엘리먼트를 제거
				while (container.children.length > 1) {
					 container.removeChild(container.lastChild);
				}
			ex3) 클래스 이름이 tweet인 엘리먼트만 찾아서 제거
				tweets.forEach(function(tweet){
					tweet.remove();
				})
				// or
				for (let tweet of tweets){
					tweet.remove()
				}

	appendChild - APPEND // 요소에 연결
		document.body.append(tweetDiv)
		container.append(tweetDiv)
		
		prepend() after() before() 도 있음



* element와 node의 차이 (difference between element and node in javascript dom)
* children과 childNodes의 차이 (difference between children and childNodes in javascript dom)
* removeChild와 remove의 차이 (difference between removeChild and remove in javascript dom)
* tweets에 forEach는 되는데, reduce는 안되는 이유 (why array method is not working on nodelist)
* tweets를 유사 배열에서 배열로 바꾸는 방법 (how to convert nodelist into javascript array)

Advanced Challenge
* DOM의 더 깊은 내용에 대해서 이해할 수 있다.
    * createDocumentFragment를 활용하여, 더 효율적으로 DOM을 제어할 수 있다.
    * HTML5 template tag 사용법을 이해할 수 있다.
    * element와 node의 차이를 이해할 수 있다.
    * children과 childNodes의 차이를 이해할 수 있다.
    * remove와 removeChild의 차이를 이해할 수 있다.
    * 같은 엘리먼트를 appendChild 하면, 기존 엘리먼트를 복사할까?
    * 좌표 정보 조회를 할 수 있다. - offsetTop...
    * 크기 정보 조회를 할 수 있다. - offsetWidth...





visibility: hidden // 엘리먼트가 차지하는 영역을 그대로 남겨놓음
display: none // 브라우저에서 아예 영역조차 사라짐



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





return value.length >= 4 // true or false 출력됨






* 함수의 선언과 호출, 그리고 결과값 리턴
    * 문제를 해결하기 위해 논리(알고리즘)을 컴퓨터가 이해할 수 있도록 코드로 작성할 수 있다.
    * 함수 표현식과 함수 선언식을 활용하여, 변수에 함수를 할당할 수 있다.
    * 함수가 담긴 변수에 괄호를 붙여 함수를 호출할 수 있다.
    * 함수가 결과를 리턴하는 경우와 그렇지 않은 경우를 구별할 수 있다.




Element.matches()
	var result = element.matches(selectorString);

모듈 사용하기
	require 함수 이용하여 모듈의 함수를 변수에 넣어 선언하고 변수를 호출하여 사용할 수 있음.