# Function




* 함수의 선언과 호출, 그리고 결과값 리턴
    * 문제를 해결하기 위해 논리(알고리즘)을 컴퓨터가 이해할 수 있도록 코드로 작성할 수 있다.
    * 함수 표현식과 함수 선언식을 활용하여, 변수에 함수를 할당할 수 있다.
    * 함수가 담긴 변수에 괄호를 붙여 함수를 호출할 수 있다.
    * 함수가 결과를 리턴하는 경우와 그렇지 않은 경우를 구별할 수 있다.






## 함수 선언(function declaration)

함수 선언(function declaration)은 지정된 매개변수(parameter)를 갖는 함수를 정의

	function name([param[, param,[..., param]]]) { [statements] }

#####
	선언을 둘러싼 함수의 최상부나 전역 범위(global scope)로 끌어올려짐




## 함수 표현식(function expression)

	var myFunction = function [name]([param1[, param2[, ..., paramN]]]) { statements };

#####
	익명 함수를 만들 경우 이름을 생략할 수 있음
	정의하자마자 실행되는  IIFE (즉시 호출되는 함수 표현식)로 사용될 수 있음
	함수 선언과는 달리 끌어올려지지 않음. 함수 표현식을 정의하기 전에는 사용할 수 없음



### 화살표 함수 표현(arrow function expression)
	
전통적인 함수표현(function)의 간편한 대안이지만 몇 가지 제한점이 있음
	
	this나 super에 대한 바인딩이 없고, methods 로 사용될 수 없다
	new.target 키워드가 없다
	일반적으로 스코프를 지정할 때 사용하는 call, apply, bind methods를 이용할 수 없다
	생성자(Constructor)로 사용할 수 없다
	yield를 화살표 함수 내부에서 사용할 수 없다

#####
	(param1, param2, …, paramN) => { statements }
	(param1, param2, …, paramN) => expression
	// 다음과 동일함:  => { return expression; }

	// 매개변수가 하나뿐인 경우 괄호는 선택사항:
	(singleParam) => { statements }
	singleParam => { statements }

	// 매개변수가 없는 함수는 괄호가 필요:
	() => { statements }



### 즉시 실행 함수 표현(IIFE, Immediately Invoked Function Expression)

정의되자마자 즉시 실행되는 Javascript Function

```javascript
	(function () {
   		statements
	})();
```




Element.matches()
	var result = element.matches(selectorString);


모듈 사용하기
	require 함수 이용하여 모듈의 함수를 변수에 넣어 선언하고 변수를 호출하여 사용할 수 있음.


arguments 객체는 모든 함수 내에서 이용 가능한 지역 변수






## 고차 함수 (higher order function)
	함수를 인자(argument)로 받을 수 있고, 함수의 형태로 리턴할 수 있는 함수




### 내장 고차함수

	
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









## 재귀(Recursion)

* 재귀적으로 사고하는 법
    * 잘게 쪼개어 사고하는 법
    * 재귀적 사고
    * 함수 자신의 재귀적 호출
    * 탈출 조건

* 재귀 함수의 활용 (트리 구조)
    * 트리 구조에 재귀 함수를 활용
    * JSON 구조에 재귀 함수를 활용
    * DOM 구조에 재귀 함수를 활용



### 재귀 함수

1. 재귀 함수의 입력값과 출력값 정의하기
2. 문제를 쪼개고 경우의 수를 나누기
3. 단순한 문제 해결하기 (base case)
4. 복잡한 문제 해결하기 (recursive case)
5. 코드 구현하기





#### JSON

JavaScript Object Notation

	데이터 교환을 위해 만들어진 객체 형태의 포맷

	JSON.stringify : Object type을 JSON으로 변환 (seriealize)
	JSON.parse : JSON을 Object type으로 변환 (deserialize)

JSON 공식 문서


자바스크립트의 객체와는 미묘하게 다른 JSON의 기본 규칙

	키 : 반드시 큰따옴표를 붙여야 함 (자바스크립트 객체의 키 : 따옴표 없이 쓸 수 있음)
	문자열 값 : 반드시 큰따옴표로 감싸야 함 (자바스크립트 객체의 문자열 값 : 어떠한 형태의 따옴표도 사용 가능)
	키와 값 사이, 그리고 키-값 쌍 사이에 공백이 있으면 안됨



Advanced contents
다음 키워드는 재귀 함수를 더 효율적이고 멋지게 쓸 수 있는 방법을 나타냅니다. 
* 재귀 함수와 메모리 사용량 간의 관계 (javascript recursion memory leak)
* 꼬리 재귀 (tail recursion in js)
* 하노이의 탑 재귀 (js tower of hanoi in recursion)
* 조합 재귀 함수 (js combination in recursion)

