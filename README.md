# lab02-debugging

Team member: Crystal Jin, Sirui Zhu

Link: https://www.shadertoy.com/view/M3XcD2

Bug1: line 97

syntax error appears first

replacing vec with vec2 to compile


Bug2: line 100

looks like a camera bug occurred since the view isn't centered in the middle

replacing uv with uv2 since we want a centered view


Bug3: line 11

The camera is still horizontally stretched

Change the second iResolution.x to iResolution.y to resolve the stretching


Bug4: line 75

The specular reflection is not working. 

The wrong light source is passed into the recursive call, replace eye with dir to enable the reflection


Bug5: line 18

The background floor is not detailed enough compared to the reference video.

Increase the i value in the for loop of the march function from 64 to 300 to provide an extension on the floor

