# React

	선언형, 컴포넌트기반, 범용성

	상향식(bottom-up)으로 앱을 만들고
	데이터 흐름이 하향식(top-down) 임
	단방향 데이터 흐름(one-way data flow)

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
		const isUnderstand = understand === ‘yes’
		const myAnswer = isUnderstand
			? ‘good_job’
			: ’study_harder’;

	React 에서 여러 개의 HTML 엘리먼트를 표시할 때는 "map()" 함수를 사용
		map 함수를 사용할 때는 반드시 "key" JSX 속성을 넣어야합 리액트 공식문서의 key





###
	Create React App 이 무엇인지 대략적으로나마 이해해라. 그리고 만들어진 프로젝트의 구조나 역할도 대략적으로라도 이해해봐라(Index.js, App.js …)




### React Router DOM
	
	페이지를 새로고침하지 않고도 주소를 변경할 수 있게 해줌
	BrowserRouter가 상위에 작성되어 있어야 Route 컴포넌트를 사용할 수 있음

```javascript
Import { BrowserRouter, Switch, Route, Link } from “react-router-dom”;
```


##### BrowserRouter

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


##### Switch, Route

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



##### Link

	경로를 연결해주는 컴포넌트
	페이지를 새로 불러오지 않고 애플리케이션을 그대로 유지하여 HTML5 History API 를 이용해 페이지의 주소만 변경

```
<Link to='/'><i className="far fa-comment-dots"></i></Link>
```




### State & Props




#### Props

	부모 컴포넌트에서 자식 컴포넌트로 전달되어 자식컨포넌트에서 사용되는 것



#### State

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


setstate 로 상위 컴포넌트의 상태를 변경할 수 있다?


