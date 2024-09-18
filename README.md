# lab02-debugging

Team: Viraj + Aaron Tian

Solution: [https://www.shadertoy.com/view/M3XyD2](https://www.shadertoy.com/view/M3XyD2)

# Bug fixes
- First fixed line 97, correcting the syntax error
- Second fixed line 100 to use correct [-1,1] space for camera calculations; found because only a quarter of the full picture was rendering
- Third fixed line 11 to have the correct aspect ratio; found because the picture was squished
- Fourth fixed the ray march number of steps to extend the ray search distance; noticed this because the tiles farther away weren't appearing + weird warping near the spheres
- Fifth fixed line 75 to have proper reflections -- noticed that there weren't any and figured that the reflection direction wasn't right
  - (I initially thought I fixed this by replacing eye with isect and that led me down an incorrect path as I was trying to fix nor later... but in reality, my first fix was wrong and deceived me.)

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
