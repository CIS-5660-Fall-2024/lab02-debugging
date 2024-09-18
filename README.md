# lab02-debugging
1. In the line 97, there was a compile error:
    
    ```cpp
    vec uv2 = 2.0 * uv - vec2(1.0);
    ```
    
    which should be:
    
    ```cpp
    vec2 uv2 = 2.0 * uv - vec2(1.0);
    ```
    
2. After fixing bug 1, the shader compiles successfully and it looks like this:
    
    ![Screenshot 2024-09-18 at 10.28.47 AM.png]
    
    It seems that the SDF is not at the right place. And it does not look like a sphere. So, I assume there will be a bug in the x and y. And I found out that in the line 11.
    
    ```cpp
    textH *= len * iResolution.x / iResolution.x;
    ```
    
    which should be:
    
    ```cpp
    textH *= len * iResolution.x / iResolution.y;
    ```
    
    The aspect ratio calculation is incorrect, which can lead to distortion in the image.
    
3. Now, the shader looks like this:
    
    ![image.png](CIS%20566%20lab02%201051b7c33bd480e5b938df07fabe2d95/image.png)
    
    I found out that the screen is only outputting 1/4 of what we expected. I assume that there is some uv issue since ray march seems fine after all. Then I found out that uv2 is declared but never used. So I changed line 100 from
    
    ```cpp
    raycast(uv, dir, eye, ref);
    ```
    
    to
    
    ```cpp
    raycast(uv2, dir, eye, ref);
    ```
    
4. The scenes transform seems fine now:
    
    ![image.png](CIS%20566%20lab02%201051b7c33bd480e5b938df07fabe2d95/image%201.png)
    
    However, there are still some issue. Like the material of the sphere is not ray marching. I also noticed that there are some strange warp around the sphere:
    
    ![image.png](CIS%20566%20lab02%201051b7c33bd480e5b938df07fabe2d95/image%202.png)
    
    I think this should be some ray marching precision problem. In the line 22, I changed the m:
    
    ```cpp
    if(m < 0.01)
    ```
    
    to
    
    ```cpp
    if(m < 0.001)
    ```
    
    Then, the floor turns out to be cutoff more, but the warp seems better:
    
    ![image.png](CIS%20566%20lab02%201051b7c33bd480e5b938df07fabe2d95/image%203.png)
    
    This appears to be a cutoff issue if the distance is too far, so I adjust the iteration cutoff distance in line 18:
    
    ```cpp
    for(int i = 0; i < 64; ++i)
    ```
    
    into
    
    ```cpp
    for(int i = 0; i < 256; ++i)
    ```
    
5. The only problem left here is that there is no reflection:
    
    ![image.png](CIS%20566%20lab02%201051b7c33bd480e5b938df07fabe2d95/image%204.png)
    
    So, I went to the ray marching logic and, thanks to my friend Crystal, I found out that in line 75 the ray should be:
    
    ```cpp
    dir = reflect(dir, nor);
    ```
    
    Everything seems fine now!
    
    ![image.png](CIS%20566%20lab02%201051b7c33bd480e5b938df07fabe2d95/image%205.png)


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
