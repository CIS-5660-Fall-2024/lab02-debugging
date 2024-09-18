# lab02-debugging

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


# Final Result
[Correct Shadertoy Link](https://www.shadertoy.com/view/lXfyD2)

![image](https://github.com/user-attachments/assets/713999cf-661d-4e3d-88e9-ad71f65a406b)

# Bugs
## Bug1
Typo of vec2 and uv.

Found it thru shadertoy compiler error warning.

## Bug2

I fix Bug1 by changing 
```
vec uv2 = 2.0 * uv - vec2(1.0);
```

to

```
uv = 2.0 * uv - vec2(1.0);
```

So the Bug2 raycast(uv, dir, eye, ref); is resolved automatically.

## Bug3 
In function raycast, the H is computed like:
```
H *= len * iResolution.x / iResolution.x;
```

However, it should be computed as
```
H *= len * iResolution.x / iResolution.y;
```

How I found it:

1. The shperes' shape is scaled in the horizontatl direction.
2. The SDF of spheres is correct.
3. So there is something wrong with ray's direction.
4. Check the raycast function and each vector.
5. iResolution.x / iResolution.x looks suspicious.


## Bug4
Compared to the correct scene, current scene has reflected color from other surfaces. So I guess there is something wrong with the reflected color.

In line 75, the original shader get the dir to the reflect surface via ``` dir = reflect(eye, nor); ```

It is wrong because the direction should be the next marching ray direction instead of eye direction. 

```dir = reflect(dir, nor);```

## Bug5
The floor seems cut off in the scene compared to the correct one. It may because the rays stopped too early before reaching the floor.
In the marching function, add more iterations for rays to expand farther.


