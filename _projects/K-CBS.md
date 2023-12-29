---
layout: page
title: K-CBS
description: Kinodynamic Conflict-Based Search (K-CBS) is a complete and scalable MRMP algorithm.
img: assets/img/kcbs-project-display.png
importance: 2
category: Work
---

*Multi-robot motion planning* (MRMP) is the fundamental problem of finding non-colliding trajectories for multiple robots acting in an environment, under kinodynamic constraints. Due to its complexity, existing algorithms utilize simplifying assumptions, are incomplete, or both. To this end, this work introduces a decoupled, scalable, and (proabilistically) complete MRMP algorithm that treats the kinodynamic constraints of the robots natively. Unlike related works that directly adopt MAPF algorithms on a discretized version of the problem, we incorporate the ideas that make CBS successful into the continuous domain using a sampling-based method. Our algorithm, dubbed **Kinodynamic CBS** (K-CBS), like CBS, uses a low-level search and maintains a constraint tree.  The low-level search can be any (kinodynamic) sampling-based tree planner (e.g., RRT or KPIECE).  

<div class="row">
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-demo-1.png" title="demo1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-demo-2.png" title="demo2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-demo-3.png" title="demo3" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-demo-4.png" title="demo4" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Many conflicts occur during a single collision between the orange and blue robots within the collision time-interval. The set of conflicts creates one constraint for each robot, which are reasoned about separately. Constraint on orange agent is not shown.
</div>

In each iteration of K-CBS, a trajectory is computed for an individual robot given a set of constraints (time-dependent obstacles). Then, collisions between the robot trajectories are checked. If one exists, constraints are defined in the constraint tree, and a new planning query is specified accordingly. To ensure probabilistic completeness, we introduce a \emph{merge and restart} method, by which we merge robots whose plans often conflict, into a single meta-robot.

The main contribution of this work is a decoupled, probabilistically-complete MRMP algorithm that is capable of generating kinodynamically feasible plans efficiently. Our algorithm, K-CBS, naturally adapts CBS from MAPF to MRMP. This lifts every off-the-shelf (kinodynamic) random tree-based planner to the multi-robot setting and removes all the limitations (assumptions) of state-of-the-art MRMP planners. Specifically, K-CBS operates completely in the continuous state space of the agents, hence, it does not require discretization nor a feedback-control design. It easily works with arbitrary, possibly heterogeneous, nonlinear dynamical models, and is capable of solving very complex MRMP instances efficiently. Some example solutions are shown below. 

<div class="row">
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-empty-space-example.png" title="empty" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-coridoor-space-example.png" title="coridoor" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-maze-space-example.png" title="maze" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/KCBS-large-space-example.png" title="large" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Solved MRMP instances using K-CBS. The initial states are shown with small circles and goal regions with large circles. K-CBS calculates plans in all of these spaces with great success without any limiting assumptions on the MRMP problem. 
</div>

I invite you to investigate any of these great resources to learn more about K-CBS:

1. The original K-CBS [IROS 2022 Conference Paper](https://ieeexplore.ieee.org/abstract/document/9982018)
2. The most-current implementation of K-CBS (to my knowledge) located inside The [Multi-Robot OMPL Repository](https://github.com/aria-systems-group/Multi-Robot-OMPL)
3. The extended [K-CBS Demos Repository](https://github.com/aria-systems-group/K-CBS-Demos) that pairs with the MR-OMPL implementation





