CIS 565 Project 5: WebGL
========================

* Kai Ninomiya (Arch Linux, Intel i5-2410M)

Part 1
------

Given code:

* Drawing a VBO through WebGL
* Javascript code for interfacing with WebGL
* Functions for generating simplex noise

Implemented:

* Sine-wave-based vertex shader
* A parametric surface (mobius band) vertex shader
    * Interprets input (x, y) position as (s, t) of a parametric surface and
      moves the vertices to the (x, y, z) calculated parametrically from (s, t).

![](images/mobius.png)
