# Lab02- Debugging Shader
- Name: Catherine Cheng
- [Shader Link](https://www.shadertoy.com/view/lXlcWj)

## Bugs
- **Line 97**: `vec uv2 = 2.0 * uv - vec2(1.0);`
    - `vec` should be `vec2`.
    - Found it by directly compile the shader.
- **Line 100**: `raycast(uv, dir, eye, ref);`
    - `uv` should be `uv2`.
    - Found it by first seeing that 3/4 of the screen is cut off. 
- **Line 11**: `H *= len * iResolution.x / iResolution.x;`
    - Should be `iResolution.x / iResolution.y`
    - Found it by seeing the spheres being oval.
- **Line 18**: `for(int i = 0; i < 64; ++i)`
    - 64 should be some larger number, such as 128
    - This causes too few iterations during ray marching so that floor would not expand far enough
- **Line 75**: `dir = reflect(eye, nor);`
    - `eye` should be `dir`
    - Found it by seeing incorrect reflection. Correct reflection should take view direction and normal as inputs.