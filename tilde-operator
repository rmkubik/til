# JavaScript Bitwise Operators
## tags
#javascript #tilde #bitwise #operators

## explanation
The tilde (~) operator in JavaScript performs a bitwise not operation on its operand. Every number is represented by a series of 32 ones and zeroes called bits when bitwise operations are being performed. These numbers are represented in two's complement format. Two's complement format means that a number's negative counterpart (e.g. 5 vs. -5) is all the number's bits inverted plus one. The bitwise not operator `~` only inverts all of the bits in the operand without the final plus one. This causes the final number to be offset by one and have its sign inverted. This transformation can be represented by the formula: `y = -(x+1)`. 

```javascript
314 = 00000000000000000000000100111010
~314 = 11111111111111111111111011000101 = -315
-314 = 11111111111111111111111011000110
```

A property of the formula `y = -(x+1)` is that when `x` is `-1` y is `0`. This property becomes useful in conjunction with the array function `.indexOf()` that returns `-1` when it cannot find the element is searching for. Now you can use `~` in place of a `=== -1` check because `~-1 = 0`. 

```javascript
const array = [2,3,4];
const value = 1;
if (~array.indexOf(value)) {
  doWorkOnOnlyIndiciesThatExist(value);
}
```

All things considered, its probably more obvious to the developer following you (or your future self) just to compare to -1.

## sources
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators
https://stackoverflow.com/questions/5915789/how-to-replace-an-item-in-an-array-with-javascript
https://www.cs.cornell.edu/~tomf/notes/cps104/twoscomp.html
