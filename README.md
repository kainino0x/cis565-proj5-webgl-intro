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
* TODO
