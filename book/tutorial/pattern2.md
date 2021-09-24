## 패턴 
```js

observable$.pipe(
  tap(console.log),
  filter(x => x % 2 === 0),
  map(x => x * x)
).subscribe(observer)

```

