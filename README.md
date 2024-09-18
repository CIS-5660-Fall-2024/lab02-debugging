# lab02-debugging

Team: Aaron Tian, Anthony Ge, Viraj Doshi
Shader: https://www.shadertoy.com/view/M3fcW2

Bugs:
- Transformed [-1, 1] range uv had wrong type definition
  - Found because shader did not compile
- raycast function needed that new uv2 variable instead of the old one
  - Raycast takes negative values in ray because we need that for proper SDF intersection
- Raycast function height H needed division factor to be iResolution.y to correct for aspect ratio
  - Found because image looked stretched
- Number of march iterations needed to be increased to fix artificating in spots near sphere and ground and to also increase render distance
  - Found because no pixels in space between sphere and ground
- Reflection vector for specular was calculated using wrong view vector. Should have been dir (initial view vector from camera)
 - Found because specular reflections were wrong

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
