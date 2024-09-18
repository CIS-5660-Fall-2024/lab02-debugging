# lab02-debugging
# Lewis Ghrist : Aaron Jiang
Link: [text](https://www.shadertoy.com/view/XXlcWj)
# Bugs
Bug 1/2: Syntax error in the mainImage function (line 98) where uv was both defined twice and jankily: (vec uv2). 

Bug 3: Scale issue with the camera (line 10), causing horizontal stretching. This was due to the horizontal value being assigned an inccorect value: H = len * iResolution.x / iResolution.x; vs H = len * iResolution.x / iResolution.y;

Bug 4: The ray march distance was too short (line 17). After only 64 steps, the background grid was not getting rendered. This also caused the floor under the spheres to look deformed. The fix was to increase the number of steps in our march to 256. 

Bug 5: The specular reflections were not working (line 72). This was due to the eye vector being reflected about the normal. What we want is the vector from the eye to the intersection point to be reflected: dir = reflect(dir, nor);
