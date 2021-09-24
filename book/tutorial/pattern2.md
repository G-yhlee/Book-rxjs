## 패턴 
```js

observable$.pipe( 
 operator(x => x + 1 ),
 operator2(x => x + 1 ),
 ...
).subscribe(observer)

```
