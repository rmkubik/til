# The Atan2 Function
## tags
#javascript #atan2 #tan #tangent #trigonometry 

## explanation
The inverse tangent function, `atan()`, is useful to calculate the angle of a provided ratio of a sides of a triangle (like a velocity vector's `x` and `y` values). This can be useful to find the angle an object should be rotated to face in the direction of it's moving. An issue that can occur with the standard arctangent function is that if the x value of the vector (when moving horizontally), a divide by zero error will occur. 

`atan2(y, x)` functions the same way as an `atan(y/x)` function with some special exceptions. 

This function is useful when you've got the `x` and `y` components of a velocity and want 

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
