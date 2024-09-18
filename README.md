# lab02-debugging

# Setup 

Team Yippee: Jill Rayca and Clara Nolan
https://www.shadertoy.com/view/MXXcD2
Bugs:
1) Changed rotateX to rotateY to get proper orientation in raycast()
   Found: Screen ratio was warped.
2) Added vec2 uv2 in mainImage()
   Found: Shader didn't compile correctly.
3) Changed uv->uv2 in main function so raycast has proper input and sdf. (this also fixed the position issue)
   Found: SDFs weren't interacting properly, needed to be negative.
5) I saw in other similar shadertoys that the raymarching iterations is 256 instead of 64 so I changed that. I think it also fixed the issue of pixeling.
   Found: Pixels were weird in sky and ground.
6) Changed reflection to dir,nor
  Found: Specular reflections were not correct/non-existent. Were calculated using incorrect view vector.
Extra credit if you can find all FIVE bugs.

# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
