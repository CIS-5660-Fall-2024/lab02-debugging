# lab02-debugging

I worked with Joyce Chen 

[Link to shader toy solution](https://www.shadertoy.com/view/l3fcD2)

# Bugs
1. vec uv2 = 2.0 * uv - vec2(1.0); – We found this bug because the bright red compiler errors "'vec' : undeclared identifier" "'uv2' : syntax error" were kind of hard to ignore haha. Changed vec to vec2.
2. raycast(uv, dir, eye, ref); – We saw that uv2 from bug 1 wasn't used, but should have been used by raycast, so changed uv to uv2.
3. H *= len * iResolution.x / iResolution.x; – After we fixed the first bug the shader looked stretched, so we fixed the aspect ratio here by changing it to iResolution.x / iResolution.y
4. dir = reflect(eye, nor); – We found this bug because the reflection was off, and it made more sense to do dir = reflect(dir, nor);
5. for(int i = 0; i < 64; ++i) { – We noticed you couldn't see as much of the background in our shader vs. the reference, so we increased the number of iterations from 64 to 200 in the march function (so the ray can search farther)

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
