# lab02-debugging - Annie Qiu
Shader toy Link: https://www.shadertoy.com/view/4XlyWj

# Results
![](Result.gif)

# Debug Process

### vec to vec2
- Bug: 'vec' : undeclared identifier 'uv2' : syntax error
- Solution: `vec2` should be used to represent the 2D vector `uv2`. Instead of `vec uv2 = 2.0 * uv - vec2(1.0);`, I use `vec2 uv2 = 2.0 * uv - vec2(1.0)`; to properly handle the 2D vector.

### H formula
- Bug:  H *= len * iResolution.x / iResolution.x;
- Solution: If I multiply and divide by the same value, the expression becomes unnecessary. The corrected formula is `H *= len * iResolution.x / iResolution.y;`, which ensures proper aspect ratio adjustment.

### Ray Cast Input
- Bug: `raycast(uv, dir, eye, ref);`
- Solution: The raycast function should use uv2 instead of uv, as uv2 is correctly normalized to the range [-1,1].

### March Steps
- Bug: ` for(int i = 0; i < 64; ++i)`
- Solution: Increase the number of marching steps to ensure a clearer rendering of the background. In this case, updating it to `for(int i = 0; i < 164; ++i)` yields better results.

### Reflect
- Bug: `dir = reflect(eye, nor);`
- Solution: The reflection should use the initial direction dir from the first march, updating the line to `dir = reflect(dir, nor);` for correct reflection behavior.


# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
