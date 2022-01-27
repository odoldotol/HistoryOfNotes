# React

선언형, 컴포넌트기반, 범용성

	상향식(bottom-up)으로 앱을 만들고
	데이터 흐름이 하향식(top-down) 임
	단방향 데이터 흐름(one-way data flow)

##### 데이터는 아래로 흐른다 https://ko.reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down (복붙해서 보기)
##### React 로 생각하기 https://ko.reactjs.org/docs/thinking-in-react.html


	JSX = JavaScript XML
	JSX > Babel > JS > 브라우저

```javascript
import React from 'react';

function Name(props) {
	return(
		<tag>
		…
		</tag>
	)
}
```

JSX 규칙

	여러 엘리먼트를 작성? -> 하나의 엘리먼트 안에 모든 엘리먼트를 넣기

	CSS class 속성? -> "className" (class 는 자바스크립트 클래스로 받음)

	JavaScript를 쓰고싶어? -> {JavaScript}

	React 엘리먼트가 JSX로 작성되면 "대문자"로 시작 (사용자 정의 컴포넌트) -> <Sidebar /> (<sidebar /> 는 html 태그로 인식)

	조건부 렌더링은 if문 X , 삼항연산자 O

	React 에서 여러 개의 HTML 엘리먼트를 표시할 때는 "map()" 함수를 사용
		map 함수를 사용할 때는 반드시 "key" JSX 속성을 넣어야합 리액트 공식문서의 key


##### 삼항연산자 예

```javascript
{isLoading ? <LoadingIndicator /> : <FlightList list={flightList} />}
```

```javascript
		const isUnderstand = understand === ‘yes’
		const myAnswer = isUnderstand
			? ‘good_job’
			: ’study_harder’;
```




##### export

파일 밖에서 이용하고자 내보낼떄 사용

```javascript
export function getFlight( filterBy = {} ) {};
```



#####
	Create React App 이 무엇인지 대략적으로나마 이해해라. 그리고 만들어진 프로젝트의 구조나 역할도 대략적으로라도 이해해봐라(Index.js, App.js …)




# React Router DOM
	
	페이지를 새로고침하지 않고도 주소를 변경할 수 있게 해줌
	BrowserRouter가 상위에 작성되어 있어야 Route 컴포넌트를 사용할 수 있음

```javascript
Import { BrowserRouter, Switch, Route, Link } from “react-router-dom”;
```


## BrowserRouter

index.js

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(<BrowserRouter><App/></BrowserRouter>,document.querySelector('#root'));
```
Or, App.js 의 App 함수에서

```javascript
return (
	<BrowserRouter>
		…
	</BrowserRouter>
);
```


## Switch, Route

	경로를 매칭해주는 역할을 하는 컴포넌트

```javascript
<Switch>
	<Route exact path="/">
		<Home />
	</Route>
	<Route path="/about">
		<MyPage />
	</Route>
	<Route path="/dashboard">
		<Dashboard />
	</Route>
</Switch>
```

	exact : 주어진 경로와 정확히 일치해야만 설정한 <Route> 컴포넌트를 보여줌



## Link

	경로를 연결해주는 컴포넌트
	페이지를 새로 불러오지 않고 애플리케이션을 그대로 유지하여 HTML5 History API 를 이용해 페이지의 주소만 변경

```
<Link to='/'><i className="far fa-comment-dots"></i></Link>
```




## State & Props




### Props

	부모 컴포넌트에서 자식 컴포넌트로 전달되어 자식컨포넌트에서 사용되는 것
	어떤 타입의 값도 넣어 전달할 수 있도록 props는 객체의 형태임
	읽기 전용

```javascript
function Parent() {
	return (
	…
		<Child attribute={value} />
	…
	);
};

function Child(props) {
	return (
		…
			{props.attribute}
		…
	);
};
```


### State

	useState 를 호출한다는 것은 "state" 라는 변수를 선언하는 것과 같고 이 변수의 이름은 아무 이름으로 지어도 됨
	일반적인 변수는 함수가 끝날 때 사라지지만, state 변수는 React에 의해 함수가 끝나도 사라지지 않음
	React 컴포넌트는 state가 변경되면 새롭게 호출되고, 리렌더링됨

```javascript
import { useState } from "react";

const [state 저장 변수, state 갱신 함수] = useState(상태 초기 값);
```

	부모로부터 props를 통해 전달되지 않음
	시간이 지나거나 상호작용하면서 값이 변함
	컴포넌트 안의 다른 state나 props를 가지고 계산이 불가능


```html
<button onclick="handleEvent()">Event</button>
```

```javascript
<button onClick={handleEvent}>Event</button>
```



#### State 끌어올리기(Lifting state up)

setstate 로 상위 컴포넌트의 상태를 변경할 수 있다?

	상태를 변경시키는 함수(handler)를 하위 컴포넌트에 props로 전달해서 해결
	콜백 함수를 사용하는 방법과 비슷

	부모컴포넌트가 상태병변경함수를 자식컴포넌트에 전달한다.
	자식컴포넌트는 프롭스로 부모컴포넌트의 상태를 변경하는 함수를 받았다.
	자식 컴포넌트의 어떤 이벤트 핸들러함수는 부모컴포넌트의 상태를 변경하는 함수를 실행시킬수 있다,

https://ko.reactjs.org/docs/lifting-state-up.html 




# Effect Hook

React 의 함수 컴포넌트에서 Side Effect를 다루기 위한 Hook


### Side Effect (부수 효과)

	함수 내에서 어떤 구현이 함수 외부에 끼치는 영향

### Pure Function (순수 함수)

	오직 함수의 입력만이 함수의 결과에 영향을 주는 함수
	함수의 입력이 아닌 다른 값이 함수의 결과에 영향을 미치지 않음
	입력으로 전달된 값을 수정하지 않음
	어떠한 전달 인자가 주어질 경우, 항상 똑같은 값이 리턴됨을 보장하는 예측 가능한 함수

### React 의 함수 컴포넌트

	props가 입력으로, JSX Element가 출력으로 나감. Side Effect 없는 순수 함수.
	
	하지만 AJAX 요청이 필요하거나, LocalStorage 또는 타이머(fetch API, localStorage, setTimeout…)와 같은 React와 상관없는 API를 사용하는 경우 React의 입장에서는 전부 Side Effect
	이때, Side Effect를 다루기 위한 Hook인 Effect Hook 을 사용.




## useEffect

useEffect(함수, [종속성1, 종속성2, ...])

	첫번째 인자는 함수, 두 번째 인자는 배열(dependency array 종속성 배열)
	첫번쨰 인자인 함수 내에서 side effect를 실행
	어떤 값이 변경되면 이 함수가 실행되도록 조건을 걸 수 있다.
	두번쨰 인자의 배열에는 그 값들이 요소로 들어간다.
	즉, 종속성 배열의 각 요소의 값이 변할 때, 첫 번째 인자의 함수가 실행.



#### 종속성 배열을 주지 않을 경우 useEffect의 첫번쨰 인자인 함수가 실행되는 기본적인 조건

useEffect(함수)

	컴포넌트 생성 후 처음 화면에 렌더링(표시)
	컴포넌트에 새로운 props가 전달되며 렌더링
	컴포넌트에 상태(state)가 바뀌며 렌더링
	
	새롭게 컴포넌트가 렌더링될 때 Effect Hook도 실행
	



#### 단 한번만 실행되는 Effect 함수

useEffect(함수, [])

	컴포넌트가 처음 생성될때 한번만 effect 함수가 실행됨
	처음 단 한 번, 외부 API를 통해 리소스를 받아오고 더이상 API 호출이 필요하지 않을 때에 사용함




#### Hook을 쓸 때 주의할 점
	
	최상위에서만 Hook을 호출합니다.
	React 함수 내에서 Hook을 호출합니다.

https://ko.reactjs.org/docs/hooks-rules.html#only-call-hooks-at-the-top-level










# AJAX 요청 로딩화면

외부 API 접속이 느릴 경우를 고려하여, 로딩 화면(loading indicator)의 구현은 필수적이다.
기본적으로, Loading indicator의 구현은 상태 처리를 통함

```javascript
const [isLoading, setIsLoading] = useState(true);

// 생략, LoadingIndicator 컴포넌트는 별도로 구현했음을 가정
return {isLoading ? <LoadingIndicator /> : <div>로딩 완료 화면</div>}
```

fetch 요청의 전후로 setIsLoading을 설정해주어 보다 나은 UX를 구현할 수 있다

```javascript
useEffect(() => {
	setIsLoading(true);
	fetch(`http://서버주소/proverbs?q=${filter}`)
		.then(resp => resp.json())
		.then(result => {
			setProverbs(result);
			setIsLoading(false);
		});
}, [filter]);
```








## 클라이언트가 서버에 요청을 덜 보내는 방법

#### Throttle a series of fetch requests in JavaScript

#### throttle과 debounce




## 서버가 클라이언트에게 돌려줄 응답을 캐싱하는 방법

HTTP 및 서버 구현에 대한 이해가 필요합니다.

####  HTTP caching

