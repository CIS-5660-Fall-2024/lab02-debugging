# lab02-debugging

Partner: Christina Qiu

Shadertoy: https://www.shadertoy.com/view/lXXcW2

## Bugs
The first bug we noticed was the syntax error:
```glsl
vec uv2 = 2.0 * uv - vec2(1.0);
```
which we corrected to:
```glsl
vec2 uv2 = 2.0 * uv - vec2(1.0);
```

---
The next bug we noticed was:
```glsl
 H *= len * iResolution.x / iResolution.x;
```
which should be:
```glsl
H *= len * iResolution.x / iResolution.y;
```
We found this by skimming the raytracing code for strange lines, since the original view was weird.

---
However, we noted that the camera position and raytracing was still incorrect, since the red sphere at (0, 0, 0) was not appearing in the center of view.
With the help of Adam, we noticed that the normalized UV coordinates were not being passed into raytracing:
```glsl
raycast(uv, dir, eye, ref);
```
which should be:
```glsl
raycast(uv2, dir, eye, ref);
```

---
Next we tackled the lack of specular reflection on the objects. We noted that the reflected direction was incorrect:
```glsl
dir = reflect(eye, nor);
```
The incident direction is given by `dir`, not `eye`, so we changed this to:
```glsl
dir = reflect(dir, nor);
```

---
Finally, we addressed the problem of the scene not being drawn to a far enough distance. With Rachel's help, we fixed this by increasing the iteration limit for the ray march from:
```glsl
for(int i = 0; i < 64; ++i) {
```
to:
```glsl
for(int i = 0; i < 1000; ++i) {
```
