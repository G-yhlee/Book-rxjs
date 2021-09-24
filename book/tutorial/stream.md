## rxjs 다운로드
```html
<script src="https://unpkg.com/@reactivex/rxjs/dist/global/rxjs.umd.js"></script>
```


## 스트림 
```md
 배열 스트림: of, from, range, generate
 시간 스트림: interval, timer
 이벤트 스트림: fromEvent
 요청 스트림: ajax
 사용자 스트림: Observable

```
```js
const { 
    of, from, range, generate,
    interval, timer,
    fromEvent,
    Observable,
} = rxjs
const { ajax } = rxjs.ajax

const streams = {
 A_of$: of(1, 2, 3),
 A_from$: from([1, 2, 3]),
 A_range$: range(1, 3),
 A_generate$: generate( 1, x => x < 4, x => x + 1),
 T_interval$: interval(1000),
 T_timer$: timer(3000),
 E_fromEvent: fromEvent(document, 'click'),
 E_fromEvent2: fromEvent(document.getElementById('myInput'), 'keypress'),
 X_ajax: ajax(`http://127.0.0.1:3000/people/1`),
 C_Observable : new Observable(subscriber => {
  subscriber.next(1)
  subscriber.next(2)
  subscriber.next(3)
  // 값을 다 발행한 뒤에는 compelte를 실행하여 메모리 해제 
  subscriber.complete()
})

}

const subscriber = stream => stream.subscribe(s=>console.log(s))

Object.keys(streams).map(k=>subscriber(streams[k]))
```


