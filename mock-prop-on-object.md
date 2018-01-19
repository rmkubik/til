# [UNFINISHED] Mocking a property using getters and setters
## tags
#javascript #property #mock #test

## explanation


This is the [getter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get)/[setter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set) pattern explained on MDN.
```javascript
const test = {
  set val(val) {
    console.log('setting');
    this._val = val;
  },
  get val() {
    console.log('getting');
    return this._val;
  },
  _val: 0
}
```

## examples
```javascript
inputElement._val = '';

Object.defineProperty(inputElement, 'value', {
  get() {
    console.log('getting: ' + this._val);
	return this._val;
  },
  set(val) {
   	console.log('setting: ' + val);
    this._val = val;
  },
  configurable: true
});
```

Creating a property called `val` on object `test`
```javascript
const original = {
  val: 1,
  unchangedProp: false
}

const mockedOriginal = Object.assign({}, original, { 
  set val(val) {
    console.log('setting');
    this._val = val;
  },
  get val() {
    console.log('getting');
    return this._val;
  },
  _val: 0
});
```
