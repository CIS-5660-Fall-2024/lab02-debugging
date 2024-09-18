# lab02-debugging

Team: Anthony Ge

Shader: https://www.shadertoy.com/view/MXXcW2

Bugs:
- Bad perspective: We see the balls from above and really close up. Anthony helped point this problem out.
    - I fixed this by inputting the correct uv into the raycast function
- Bad aspect ratio: The screen appeared to be stretched. I read the raycast code and saw that the H was making the screen a square by diving x by itself.
    - I fixed this by diving the resolution's x by y instead of itself
- Small floor: The ground appeared to be really small. I tried to increase the raycast distance and that worked well.
    - I increased the raymarch distance
- Folding floor: The floor appeared to fold up between the spheres. I saw that the threshold to return might not be precise enough, so I reduced it.
    - I decreased the value m is compared to in the raymarch code (I think?)
- No reflections: The balls and floor weren't reflecting anything. Adam asked me what the proper inputs to reflect were, and I saw the problem.
    - I changed the reflect function to input dir instead of eye
