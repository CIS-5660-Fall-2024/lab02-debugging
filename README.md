# lab02-debugging

# Submission
<img width="626" alt="image" src="https://github.com/user-attachments/assets/e996c0a8-7e26-4762-b1fd-880436a588cd">

*Shadertoy Link:* https://www.shadertoy.com/view/l3XyD2 

*Team Members:* Michael Mason

*Bugs Found:*

1. Passing remapped `uv2` to the `raycast` function. 
2. Fixed aspect ratio multiplication within `raycast` function. 
3. Increased iterations in `march` from 64 to 256. 
4. in `sdf3D`, reflect `dir` about the `nor` (instead of the `eye`). 
5. Compiler error `vec` to `vec2`. 




# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).

Let's practice debugging! We have a broken shader. It should produce output that looks like this:
[Unbelievably beautiful shader](https://user-images.githubusercontent.com/1758825/200729570-8e10a37a-345d-4aff-8eff-6baf54a32a40.webm)

It don't do that. Correct THREE of the FIVE bugs that are messing up the output. You are STRONGLY ENCOURAGED to work with a partner and pair program to force you to talk about your debugging thought process out loud.

Extra credit if you can find all FIVE bugs.

# Submission Instructions
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
