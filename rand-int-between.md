# Choose a Random Number Between Two Values
## tags
#javascript #random #between #range

## explanation
A simple, but useful utility function to randomly choose a float (whole number with decimal) in a range. The output includes the low number and excludes the high number.

```javascript
// range: [low, high)
function floatBetween(low, high) {
  return Math.random() * (high - low) + low;
}
```

From the basic random float in range function, its possible to make a few simple tweaks to guarantee the number is an integer (has no decimal values). Add `Math.floor()` to round the number down to a whole integer value. This function includes the low number and excludes the high number. By adding 1 to the max value calculation, you can include the high number in your range as well.

```javascript
// range: [low, high)
function intBetweenExclusive(low, high) {
  return Math.floor(Math.random() * (high - low)) + low;
}

// range: [low, high]
function intBetweenInclusive(low, high) {
  return Math.floor(Math.random() * (high - low + 1)) + low;
}
```

## sources
https://stackoverflow.com/questions/1527803/generating-random-whole-numbers-in-javascript-in-a-specific-range
