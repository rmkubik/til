# Slice with a Negative Index
## tags
#javascript #array

## explanation
Slice can take in two parameters for the beginning and end index: `arr.slice([begin[, end]])`. The `array.slice()` function has some interesting logic when either of those parameters is a negative value. Positive index values start iterating from the beginning of the array while negative values iterate from the end of the array. 

[msdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) documentation for the slice function explains this:
> A negative index can be used, indicating an offset from the end of the sequence. slice(-2) extracts the last two elements in the sequence.

> A negative index can be used, indicating an offset from the end of the sequence. slice(2,-1) extracts the third element through the second-to-last element in the sequence.

This caused me some confusing issues when using the `array.findIndex()` function did not find the object I was looking for. It returns a value of `-1` and caused me to start slicing with negative indexes! 

## examples
```javascript
const arr = [1, 2, 3];
arr.slice(-2);
```
> [2, 3]

```javascript
const arr = [1, 2, 3];
arr.slice(1, -1);
```
> [2]
