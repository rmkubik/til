# The Atan2 Function
## tags
#javascript #atan2 #tan #tangent #trigonometry 

## explanation
The inverse tangent function, `Math.atan()`, is useful to calculate the angle of a provided ratio of a sides of a triangle (like a velocity vector's `x` and `y` values). This can be useful to find the angle an object should be rotated to face in the direction it's moving, `Math.atan(velocity.y/velocity.x)`. 

The normal arctangent function has a couple issues though for this use case:
  - In other programming languages, dividing by zero will cause an error if the x value of the vector (when moving horizontally). In JavaScript, this division returns the `Inifinity` number which `Math.atan()` can actually handle correctly.
  - The arctangent function's domain is -π/2 to π/2 radians (-90° to 90°). This means it cannot distinguish between `{x: 1, y: 1}` and `{x: -1, y: -1}`. `Math.atan(y/x)` both evalute to 0.785 radians (45°).

This is where the arctangent2 function comes in handy. `Math.atan2(y, x)` functions the same way as an `Math.atan(y/x)` function with some special exceptions. This function has a domain of -π to π radians (-180° to 180°). Revisiting the earlier example, `{x: 1, y: 1}` and `{x: -1, y: -1}` evaluate to 0.785 radians (45°) and -2.356 radians (-135°) respectively.

## examples
```javascript
function convertVelocityToAngle(velocity) {
  const { x, y } = velocity;
 
  return Math.atan2(y, x) * (180 / Math.PI);
}

```

## sources
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atan2
https://gamedev.stackexchange.com/questions/14602/what-are-atan-and-atan2-used-for-in-games
