Team: Joyce Chen, Katherine Li

https://www.shadertoy.com/view/MXfcW2

1. “vec2 uv2 = 2.0 * uv - vec2(1.0);” changed vec to vec2 in mainImage, noticed syntax error noted by shader toy, 
2. “H *= len * iResolution.x / iResolution.y;” noticed H was calculated by len * iResolution.x / iResolution.x, which probably isn’t right
3. “raycast(uv2, dir, eye, ref);”reading comments, noticed that raycast function takes in uv [0,1] coords instead of uv2 [-1,1] coords
4. “dir = reflect(dir, nor);”changed argument taken in by reflect from eye to dir, found by reading through sdf3D function and finding that reflect needs incident ray direction, not camera position
5. “for(int i = 0; i < 200; ++i) {”increased march iterations from 64 to 200, noticed scene render difference between example and my scene
