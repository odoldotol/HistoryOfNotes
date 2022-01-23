# etc


# 타이머 관련 API

## setTimeout(callback, millisecond)

일정 시간 후에 함수를 실행

* arguments: 실행할 callback 함수, callback 함수 실행 전 기다려야 할 시간 (밀리초)
* return value: 임의의 타이머 ID

* setTimeout에 대응하는 clearTimeout도 있음




## setInterval(callback, millisecond)

일정 시간의 간격을 가지고 함수를 반복적으로 실행

* arguments: 실행할 callback 함수, 반복적으로 함수를 실행시키기 위한 시간 간격 (밀리초)
* return value: 임의의 타이머 ID


## clearInterval(timerId)

반복 실행중인 타이머를 종료

* arguments: 타이머 ID
* return value: 없음








# fetch API 사용법

```javascript
let url =
	"https://v1.nocodeapi.com/codestates/google_sheets/YbFMAAgOPgIwEXUU?tabId=최신뉴스";
fetch(url)
	.then((response) => response.json()) // 자체적으로 json() 메소드가 있어, 응답을 JSON 형태로 변환시켜서 다음 Promise로 전달합니다
	.then((json) => console.log(json)) // 콘솔에 json을 출력합니다
	.catch((error) => console.log(error)); // 에러가 발생한 경우, 에러를 띄웁니다
```

더욱 자세한 내용은 MDN에서 찾아볼 수 있다