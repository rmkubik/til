# Generate Array of Increasing Indices
## tags
#javascript #array #generate #increasing

## explanation
This is a fairly simple function to allow the easy creation of an array of an increasing order of indicies. This was useful for me to set certain indicies of a tilesheet of sprites as collidable while leaving others untouched. 

`new Array(length)` lets you create an empty array of the specified length. 

`Array.from(array, mapFunction)` creates a shallow copy of a given array and maps it with the provided function.

Combining the two, you can create an empty of array of the desired length and the populate a copy of that array with an increasing count of indices.

## examples
```javascript
function generateArrayOfLength(length) {
  return Array.from(new Array(length), (value, index) => index);
}

generateArrayFromExclusive(5, 8);
// -> [0, 1, 2]
```

```javascript
function generateArrayFromExclusive(low, high) {
  return Array.from(new Array(high - low), (value, index) => low + index);
}

generateArrayFromExclusive(5, 8);
// -> [5, 6, 7]
```

```javascript
function generateArrayFromInclusive(low, high) {
  return Array.from(new Array((high - low) + 1), (value, index) => low + index);
}

generateArrayFromInclusive(5, 8);
// -> [5, 6, 7, 8]
```

## sources
https://www.jstips.co/en/javascript/create-range-0...n-easily-using-one-line/
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from

