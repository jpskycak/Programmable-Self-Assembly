<head>
    <style type="text/css">
       a:link {color: blue;}      /* unvisited link */
       a:visited {color: blue;}   /* visited link */
       a:hover {color: blue;}     /* mouse over link */
       a:active {color: blue;}    /* selected link */
    </style>
</head>

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

### Purpose

The goal of this project is to improve upon the self-assembly algorithm presented by Rubenstein, Cornejo, and Nagpal in the paper <i>Programmable self-assembly in a thousand-robot swarm</i>. Their algorithm "guarantees that a large group of robots, with limited capabilities and local communication, can cooperatively assemble into any 1-connected user-specified shape (with some restrictions)." Informally, this means it works on shapes having no "holes" or "cutouts". My goal in particular is to extend their algorithm to work on any 1-connected shape in general, including those having holes or cutouts.

### Original Algorithm

It is assumed that each agent has the ability to communicate with and estimate the distances to other agents within a given radius, "neighbors." Thus, each agent can
1. move along an edge (by maintaining fixed distance to the center of the nearest neighbor),
2. estimate its own coordinates (as those which minimize the discrepancy between the observed distances to neighbors and the distances calculated using neighbors' estimations of their own coordinates), and
3. estimate its distance from the source (the source has gradient value zero, and each agent generates a gradient value as one more than the minimum of the gradient values of its neighbors).

The shape-filling algorithm proceeds as follows:
1. A shape is chosen as a set of nonnegative coordinates.
2. A source agent is chosen, and its coordinates are assigned to be some point on the shape.
3. Each agent estimates its own coordinates and edge-follows clockwise (if able). It eventually enters the desired shape (as determined by its estimated coordinates) and continues to edge-follow until one of the following stop-conditions is true:
   a. another move would cause it to exit the shape, or
   b. it is next to a stationary agent with same gradient value, which has moved from its initial position.
   
The second stop condition is necessary because without it, the agents would line up along the perimeter of the shape, eventually closing off the interior of the shape before it is filled.

### Simulation

Build a computer simulation  -- pixels on a grid @ https://colab.research.google.com/drive/1Q0NYziPHotNOQMMr3hfI_unYi9muxIW9

### Problem with Holes

The original algorithm can fail on shapes which have holes or cutouts in them because _____

(do agents get trapped?)

### Modifications

Dilate the shape 4x

keep unit distance from nearest neighbors, to allow other agents to pass. Penalize holes in the shape -- agent cannot stop inside a hole, but it can stop on the exterior (may be needed if there are too many agents)

latex test: $$\int \zeta(x) dx$$
