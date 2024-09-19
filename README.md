# lab02-debugging

Team: Christina Qiu, Jason Liu
Link: https://www.shadertoy.com/view/43scWj
Bugs: 
* H *= len * iResolution.x / iResolution.y; // found because it was originally iResolution.x / iResolution.x which would have just been 1.0
* for(int i = 0; i < 640; ++i) { // found because the ground was dissapearing too soon, so know that the ray was ending after only a few iterations
* dir = reflect(dir, nor); // found because having it reflect by eye would be wrong, since reflect should take in incident direction and then normal direction
* vec2 uv2 = 2.0 * uv - vec2(1.0); // found because there was a red error sign that vec wasn't valid
* raycast(uv2, dir, eye, ref); // found because the rotation was off, which was due to the uv not being in the correct ranges

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
