# lab02-debugging

Yi Liu 

# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).


# Shader Link 
https://www.shadertoy.com/view/M3fcD2


<p align="center">
  <img src="https://github.com/yiliu1237/lab02-debugging/blob/main/shader_result.gif?raw=true"/>
</p>



## Bug1: Syntax Error 
- Issue: The variable uv2 was declared as vec instead of vec2.
- Fix: Change the type of uv2 to vec2.
- How It Was Found: The Shadertoy editor highlighted this as a syntax error upon running the shader.

## Bug2 Incorrect Input to raycast Function
- Issue: The uv variable was incorrectly used when calling the raycast function.
- Fix: Use uv2 instead of uv when calling raycast to ensure proper coordinates are passed.
- How It Was Found: The rendered output was distorted, leading to inspection of how coordinates were handled.

## Bug3: Reflection Calculation Error
- Issue: The reflection was not computed correctly due to the misuse of the reflect function.
- Fix: Update the reflect function call to use the correct vector inputs:

```
dir = reflect(dir, nor);
```

- How It Was Found: The reflection on objects appeared incorrect, leading a deeper look into the reflection calculation. 

## Bug4: Scene Aspect Ratio Distortion
- Issue: The rendered scene was stretched along the x-axis, showing ellipsoids instead of spheres.
- Fix: Adjust the scene's aspect ratio to prevent distortion.

```
uv2.x *= iResolution.x; 
uv2.x /= iResolution.y;
```

- How It Was Found: Comparing the reference Shadertoy to the current output revealed the ratio issue.


## Bug5: Insufficient Iterations in march Function
- Issue: The march function was not iterating through enough steps, causing the scene to render incorrectly.
- Fix: Increase the number of iterations in the march function to allow sufficient steps for ray marching:

```
for (int i = 0; i < 300; ++i) { ... }
```

- How It Was Found: Visual artifacts and incomplete rendering prompted the inspection of the march funtion.