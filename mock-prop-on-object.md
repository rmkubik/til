# Mocking a property using getters and setters
## tags
#javascript #property #mock #test

## explanation
This is the [getter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get)/[setter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set) pattern explained on MDN that I only recently learned existed. 
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
Leveraging this pattern its possible to detect when a variable has been set or gotten. By passing in a mocked function as the getter or setter of a property you're interested in, its possible to test for assignment of the property by checking if the mocked function was called.

## examples
```javascript
it('mocks the value property on originalObject', () => {
    const originalObject = {
    	value: ''
    }

    // add new property to hold the value of the property
    originalObject._val = '';

    // create a mocked function in jest
    const mockedSetter = jest.fn()

    // implement setter behavior on the mock
    mockedSetter.mockImplementation((val) => {
        originalObject._val = val
    });

    // override the value property definition with our mocked setter
    Object.defineProperty(originalObject, 'value', {
      set: mockedSetter,
      configurable: true
    });

    // assign to the newly mocked proprty
    originalObject.value = 'test';

    // expect our value property was set exactly once
    expect(mockedSetter.mock.calls.length).toBe(1);
});
```

## sources
https://j11y.io/snippets/fun-with-getters-setters/
https://github.com/jquery/jquery/blob/master/src/attributes/val.js#L46
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty
