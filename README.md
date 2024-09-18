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
- - Matt Schwartz and Jeff Mostyn
- In the README, create a link to your shader toy solution with the bugs corrected
- - https://www.shadertoy.com/view/M3fyD2
- In the README, describe each bug you found and include a sentence about HOW you found it:

vec2 uv in `mainImage` was declared mistakenly as vec (easy to find, the compiler called it out)

H was mistakenly computed by dividing iResolution.x by itself (just by visual inspection and talking it out loud. We noticed the image was distorted).

uv2 was unused - uv was passed into raycast instead (just by luck lol)

Specular reflection march direction was incorrect, instead of reflect(eye, nor), it should be reflect(eye, dir) (we knew the reflection wasn't working, so we started talking through the specular reflection code. "Is this the right direction to march in for reflections?" etc.)

Not stepping enough times in the march code (changed from 64 to 128) (this one was easy, it was clear the floor wasn't extending far enough, and this is pretty much the only thing that controls the far-clip distance)
