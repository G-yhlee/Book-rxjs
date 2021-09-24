## rx 패턴 
```js
observable$.subscribe(observer)
```

## 예시 1
```js
const observer = {
  next: console.log,
  error: err => console.error('발행중 오류', err),
  complete: () => console.log('발행물 완결'),
}
observable$.subscribe(observer)

```
## 예시 2
```js
observable$.subscribe(
  console.log,
  err => console.error('발행중 오류', err),
  _ => console.log('발행물 완결')
)
```

## 예시 3
```js
observable$.subscribe(
  console.log
)
```

