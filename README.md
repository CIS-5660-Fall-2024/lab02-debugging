# lab02-debugging

## Name: Christine Kneer

[My Shadertoy Link](https://www.shadertoy.com/view/X3scWj)

![sdf](https://github.com/user-attachments/assets/92dc2cc3-7005-4dbc-8069-d6b2a0c1c5a1)

- **Bug 1**: Line 97, vec uv2 = 2.0 * uv - vec2(1.0); Code did not compile, so this bug was fairly easy to find.
- **Bug 2**: Line 100, raycast(uv, dir, eye, ref); Sphere position was off, so I decided to double check my ray cast inputs, where I found the bug.
- **Bug 3**: Line 11, H *= len * iResolution.x / iResolution.x; The scene's aspect ratio was obviously off (not unit spheres), so I naturally looked for where iResolution was used,
since iResolution is usually related to aspect ratio.
- **Bug 4**: Line 75, dir = reflect(eye, nor); I noticed that there was absolutely no reflection. In order to see what was going on better, I changed the reflection color to black, and I realized that I could indeed see the black color on these objects. This means that “reflection” was happening, just with the wrong color - this most likely means that our reflected rays were not hitting the correct object. Then I went to look for where we were calculating the reflection color, and I immediately noticed that dir = reflect(eye, nor) is off, because we would want to reflect our rayCast ray instead of the eye in the other direction.
- **Bug 5**: Line 18, for(int i = 0; i < 64; ++i). Plane was abruptly cut off, but the rest of the plane all looked correct. It seems that ray march did reach far enough, i.e. not enough steps, so I went to check the ray cast for loop.

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
