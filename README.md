
- In the README, describe each bug you found and include a sentence about HOW you found it.

- Team Member: Sirui Zhu and Crystal Jin
- Link: https://www.shadertoy.com/view/43lyW2
- Bugs:
- 1. Line 97: Change from vec to vec2. Initially, it shows that there is a syntax issue caused by uv2 with a type vec. uv2 should be vec2 as it is calculated from uv which is a vec2 and by definition uv2 should be vec2 to indicate a position in a 2D coordinate.
- 2. Line 100: Change from uv to uv2. Previously we adjusted uv from [0,1] to uv2 [-1,1] to make the center lie on the origin (0,0), and we should use it here.
- 3. Line 11: Change the second iResolution.x to iResolution.y. Objects are weirdly stretched in the x-axis. After taking a deep look at the raycast function, I found that on line 11 we should time the aspect ratio (iResolution.x / iResolution.y) instead.
- 4. Line 75: Change from eye to dir. Specular reflection does not work, and to achieve it we need to make a recursive call.
- 5. Line 18: Change the iteration from 64 to 100. The ground grid is not rendered as much compared to it in the example demo. So we need more iterations in the march function to explore further distance. 
