React

	선언형, 컴포넌트기반, 범용성


	JSX = JavaScript XML
	JSX > Babel > JS > 브라우저



JSX 규칙

	여러 엘리먼트를 작성? -> 하나의 엘리먼트 안에 모든 엘리먼트를 넣기

	CSS class 속성? -> "className" (class 는 자바스크립트 클래스로 받음)

	JavaScript를 쓰고싶어? -> {JavaScript}

	React 엘리먼트가 JSX로 작성되면 "대문자"로 시작 (사용자 정의 컴포넌트)

	조건부 렌더링은 if문 X , 삼항연산자 O
		const isUnderstand = understand === ‘yes’
		const myAnswer = isUnderstand
			? ‘good_job’
			: ’study_harder’;

	React 에서 여러 개의 HTML 엘리먼트를 표시할 때는 "map()" 함수를 사용
		map 함수를 사용할 때는 반드시 "key" JSX 속성을 넣어야합 리액트 공식문서의 key





###
	Create React App 이 무엇인지 대략적으로나마 이해해라. 그리고 만들어진 프로젝트의 구조나 역할도 대략적으로라도 이해해봐라(Index.js, App.js …)


###
	npx create-react-app <앱이름> : 새로운 리액트 프로젝트를 시작
	npm run start : 