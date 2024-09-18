# lab02-debugging

Aaron Jiang and Lewis Ghrist  
Shader: https://www.shadertoy.com/view/X3syDj  
  
Bugs found:  
1) vec type not found in mainImage() causing a compliation error. I found this because there was big red text describing the error.  
2) uv2 was declared but not passed in. I figured that the 2 after uv2 was actually supposed to be with the vec to form vec2. This fixed a zoom in into the top left corner.   
3) The aspect ratio calculation was wrong as we divided by x/x instead of x/y. I found this because the image was stretched.  
4) The renderer had an insufficient number of steps - I found this because the floor disappeared early and there was warping around the edges of the spheres.  
5) The reflected ray was not using the correct input direction. It used eye, which was a vector from world origin to camera position, instead of dir, which is the direction the ray was traveling in. I noticed that specular reflections were not appearing.    
