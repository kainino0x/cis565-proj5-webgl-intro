CIS 565 Project 5: WebGL
========================

* Kai Ninomiya (Arch Linux, Intel i5-2410M)


Part 1
------

![](images/mobius.png)

Given code:

* Drawing a VBO through WebGL
* Javascript code for interfacing with WebGL
* Functions for generating simplex noise

Implemented:

* Sine-wave-based vertex shader
* A parametric surface (mobius band) vertex shader
  * Interprets input (x, y) position as (s, t) of a parametric surface and
    moves the vertices to the (x, y, z) calculated parametrically from (s, t).


Part 2
------

![](images/globe.png)

Given code:

* Reading and loading textures
* Rendering a sphere with textures mapped on
* Basic passthrough fragment and vertex shaders 
* A basic globe with Earth terrain color mapping
* Gamma correcting textures
* Javascript to interact with the mouse
  * Left-click and drag moves the camera around
  * Right-click and drag moves the camera in and out

Implemented:

* Bump mapped terrain (using a height-map input)
* Rim lighting to simulate atmospheric scattering (on lit parts of the globe)
* Night-time lights on the dark side of the globe (smoothly blended)
* Specular mapping (showing specularity on the water)
* Moving clouds (using a cloud layer)
* Procedural water rendering and animation using noise
  * Noise library (c) Ashima Arts. Used under MIT License. [1]

### Performance

I found that I was unable to capture any meaningful data on the actual
rendering time of each frame, due to lack of granularity and asynchronous GPU
process offloading (Stats.js [2] always showed 0 or 1 ms per frame).
However, using Ben Vanik's WebGL Inspector, I was able to find and make a few
optimizations.

![](images/globe_trace.png)

* Only compute the light position and camera matrix when the camera is moved
* Factored out the first two rotations of the model matrix calculation
* Only set the earth texture uniforms once

Afterward:

![](images/globe_trace_after.png)


References/Libraries
--------------------

[1] webgl-noise. Copyright 2011 Ashima Arts. Used under MIT License.
    https://github.com/ashima/webgl-noise
[2] stats.js. Copyright 2009-2012 Mr.doob. Used under MIT License.
    https://github.com/mrdoob/stats.js
