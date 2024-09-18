# lab02-debugging

# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).

Let's practice debugging! We have a broken shader. It should produce output that looks like this:
[Unbelievably beautiful shader](https://user-images.githubusercontent.com/1758825/200729570-8e10a37a-345d-4aff-8eff-6baf54a32a40.webm)

It don't do that. Correct THREE of the FIVE bugs that are messing up the output. You are STRONGLY ENCOURAGED to work with a partner and pair program to force you to talk about your debugging thought process out loud.

Extra credit if you can find all FIVE bugs.

# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)

# Team Names
- Jeffrey Mostyn
- Matt Schwartz

# Shadertoy
https://www.shadertoy.com/view/lXfcW2

# Bugs 
1. uv2 was misdeclared as vec type. This was found from compiler error message
2. iResolution.x was being divided by itself, distorting the image horizontally. We traced this issue to this operation, which on inspection was clearly incorrect. Dividing by iResolution.y instead corrected the distortion
3. The center of the middle sphere was in the bottom left corner rather than the middle of the screen. This would have to be caused by an incorrect mapping of world to screen. We noticed that when we mapped the world to [-1, 1] space, that the resultant uv2 was not ever used. We passed this into the raycast function instead of uv, which is [0, 1] space
4. The rendering of the floor stopped shortly past the spheres, so we knew that we would need to either increase the step length or the number of steps to render things that were further into the scene. Changing the step length risks incorrect intersection calculations, so we increased the step count which fixed the problem.
5. Reflections did not render. In the intersection function, we noticed that the vector that was being reflected around the intersection normal was `eye` instead of the actual direciton of the raycast, `dir`. Switching the two fixed this bug
