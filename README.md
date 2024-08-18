# Polar Coordinates (w/ Logarithmic Scaling)

A simple repo, which includes a custom node + example of logarithmic scaling using polar coordinates.

*Polar coordinates* -> calculated from (centered [(uv * 2.0) - 1.0]) Cartesian UV coordinates.

---

**[Radial] Distance** = 'length' of the centered UV vector, representing how far a point is from the center. 

**Angle** = 'arctan2', which calculates the angle (in radians) between the positive x-axis and the point (x, y) in the Cartesian plane.
> Returns a value in range [-π, π].

Logarithmic scaling is simply applying 'log' to length, altering space in a way that compresses distances moving outward from the center.

---

```
uv = centeredUV;

polar.x = length(uv);          // Length of centered UVs = radial gradient (signed distance).
polar.y = arctan2(uv.y, uv.x); // Angle.

// For log scale, we simply use the log function on polar.x:

polar.x = log(polar.x); // AKA, polar.x = log(length(uv));
```

![Polar Coordinate Scaling](https://github.com/user-attachments/assets/3e955f9d-5523-4ed8-9068-40c89eef5094)
