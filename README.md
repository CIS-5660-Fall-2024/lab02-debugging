### Results:
![](01.gif)
[Shadertoy](https://www.shadertoy.com/view/l3XcD2)
I fixed the following bugs in this lab02 project
- Syntax error:
  - vec uv should be vec2 uv
- Argument input error:
  - should put uv2 in the raycast function instead of uv, so that the camera can correctly see the entire scene
- iResolution error:
  - should change iResolution.x / iResolution.x to iResolution.x / iResolution.y so that the camera will not be distorted
- Ray march limit error:
  - should increase the maximum distance(i < 256 instead of i < 64) that ray can march the scene object so that the camera can see the further floor
- Reflection error:
  - this one is very tricky, should plug dir into the reflect function instead of eye




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
