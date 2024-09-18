# lab02-debugging
group member：Yang Yu
links：https://www.shadertoy.com/view/4XfcDX
The compiler shows an error related to uv2. It should be uv(0,1) instead of uv2(-1,1), which is why the sphere appears in the lower-left corner instead of the center of the screen.
There's also a resolution issue, as the sphere isn't perfectly round.
The reflection direction is incorrect, causing the sphere not to reflect the floor properly.
Furthermore, the iteration count is too low, leading to voids around the edges of the sphere.

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
