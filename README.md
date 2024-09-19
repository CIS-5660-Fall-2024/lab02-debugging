link to shadertoy: https://www.shadertoy.com/view/4XlyDj
# lab02-debugging
Name: Jinxiang Wang
Bugs found: 
1. Compiler error vec uv2;
2. Change vec uv2 to uv;
3. Change vec2 uv = fragCoord.xy/iResolution.xy to uv = fragCoord.xy/iResolution.y; 
4. In march() change iteration from 64 to 256;
5. In sdf3D() change reflect(eye, nor) to reflect(dir, nor);

