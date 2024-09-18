# lab02-debugging

# Submission (Charles Wang)

Did not work with anyone.

Link to Shadertoy: [https://www.shadertoy.com/view/lXXyD2](https://www.shadertoy.com/view/lXXyD2)

1. When the page first loaded, Shadertoy pointed out an error it had while compiling. I corrected the type from vec to vec2.
2. I realized that even though we calculated the value of uv2, we never actually used it. That didn't feel right so I replaced uv with uv2 in the raycast() call, which fixed the viewport only rendering the first quadrant.
3. I noticed the ground was "cut off" early, which usually meant we weren't marching far enough. So I quadrupled the step size we took and it fixed it.
4. I went line by line through sdf3D(), and realized that the reflection we take about the intersection point was incorrect. `eye` is the position of the camera, not the direction that we're reflecting, so I changed that, and everything else worked.

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
