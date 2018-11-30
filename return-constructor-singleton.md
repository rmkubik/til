# Modifying the Return Value of a Constructor
## tags
#javascript #constructor #return #singleton #pool #new

## explanation
The `new` keyword [does a few of things behind the scenes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new#Description) to create a new instance of an object.

One of these things is to use the constructor of the object being newed. The constructor is a function responsible for building a new object to the specifications desired by its developer. When the constructor is actually called, it is bound with the context of the new object instance being created. This means that `this` inside of the constructor function refers to the new instance not the original object or class. By referencing `this` you can format the new object instance as desired.

Another less used feature of the constructor function is the usage of a `return` statement. This allows you to override the normal object creation process and return a different object as a result of the `new` expression. Among other things, you can use this to create a Singleton.

## examples
### Declaration
```javascript
let instance;

class Singleton {
  constructor() {
    if (instance) {
      return instance;
    }
    instance = new Object();
  }
}
```

### Usage:
```javascript
const a = new Singleton();
const b = new Singleton();
a === b // true
```

## sources
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new
- https://stackoverflow.com/questions/3350215/what-is-returned-from-a-constructor
