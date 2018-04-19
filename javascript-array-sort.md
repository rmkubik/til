# JavaScript's Array Sort Function
## tags
#javascript #array #sort #number

## explanation
Javascript's `array.sort()` function converts all objects in the array according to their Unicode code points. This means that by default, lowercase letters will be sorted before uppercase letters of the same value. 

This also means that numbers are not sorted numerically, but based on the value of each character's code point. For example, the number `1000` would be place before the number `2`. This is because, the Unicode code point of the character `1` is `49` while the Unicode code point of `2` is `50`. 

In order to sort in a different way than by Unicode code point value, sort provides the ability to pass in a comparator function. This function takes in parameters `a` & `b` referring to the two values being compared. 
- If the comparator function returns a negative value, then `a` is sorted first. 
- If it returns zero then `a` and `b` stay in order in respect to eachother. 
- If the function returns a positive value, then `b` is sorted first.

The function in the example below is one that works to correctly sort numbers numerically instead of by Unicode code point.

## examples
```javascript
const array = [1000, 3, 2];

array.sort(); // [1000, 2, 3]

array.sort((a, b) => a - b); // [2, 3, 1000]
```

## sources
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort
