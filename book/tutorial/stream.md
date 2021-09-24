## rxjs 다운로드
```html
<script src="https://unpkg.com/@reactivex/rxjs/dist/global/rxjs.umd.js"></script>
```


## 배열된 스트림
```js
const { of, from, range, generate } = rxjs

const obs1$ = of(1, 2, 3, 4, 5)
const obs2$ = from([6, 7, 8, 9, 10])
const obs3$ = range(11, 5)
const obs4$ = generate(
  15, x => x < 30, x => x + 2
)

//obs1$.subscribe(item => console.log(`of: ${item}`))
//obs2$.subscribe(item => console.log(`from: ${item}`))
//obs3$.subscribe(item => console.log(`range: ${item}`))
//obs4$.subscribe(item => console.log(`generate: ${item}`))
```

## 시간 스트림
```js
const { interval, timer } = rxjs

const obs1$ = interval(1000)
const obs2$ = timer(3000)

//obs1$.subscribe(item => console.log(`interval: ${item}`))
//obs2$.subscribe(item => console.log(`timer: ${item}`))
```

## 이벤트 스트림
```html
<input id="myInput" type="text"/>
```
```js
const { fromEvent } = rxjs

const obs1$ = fromEvent(document, 'click')
const obs2$ = fromEvent(document.getElementById('myInput'), 'keypress')

obs1$.subscribe(item => console.log(item))
obs2$.subscribe(item => console.log(item))
```

## ajax 스트림
```js
const { ajax } = rxjs.ajax

const obs$ = ajax(`http://127.0.0.1:3000/people/1`)
obs$.subscribe(result => console.log(result.response))
```

## custom 스트림
```js
const { Observable } = rxjs

const obs$ = new Observable(subscriber => {
  subscriber.next(1)
  subscriber.next(2)
  subscriber.next(3)

  // 값을 다 발행한 뒤에는 compelte를 실행하여 메모리 해제 
  subscriber.complete()
})

obs$.subscribe(item => console.log(item))
```