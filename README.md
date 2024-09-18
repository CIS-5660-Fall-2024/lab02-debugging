# lab02-debugging

# Link
[Link](https://www.shadertoy.com/view/lXXcD2)

# Team Member
Annie Qiu

# Bugs
- 1. vec -> vec2 : This is a reported error.
  2. raycast(uv, dir, eye, ref); -> raycast(uv2, dir, eye, ref); : Unused variable.
  3. dir = reflect(eye, nor); -> dir = reflect(dir, nor); : Using eye does not make any sense.
  4. H *= len * iResolution.x / iResolution.x; -> H *= len * iResolution.x / iResolution.y; : Why use iResolution.x / iResolution.x, which is 1?
  5. for(int i = 0; i < 64; ++i) -> for(int i = 0; i < 160; ++i) : Not enough grids are shown in the far distance.

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
