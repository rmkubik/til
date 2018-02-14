# [WIP] JavaScript Void Keyword
## tags
#javascript #void #keyword

## explanation
The `void` keyword is an operator that evalutes the expression following it as `undefined` every time. The most common usage of this keyword seems to be as a way to access the JavaScript primitive value `undefined` as `void(0)` (it could be any expression, but `(0)` is convention). In most current development environments it would be equivalent to use `undefined` instead. This seems like it would only come up when targeting older browsers, which is why `void(0)` can be found in Babel transpiled code.


## examples
```javascript
void true // undefined
void false // undefined
void(0) // undefined
```

## sources
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/void
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined
