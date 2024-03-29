---
layout: page
title: MR-OMPL
description: An extension of the revered Open Motion Planning Library (OMPL) to account for multi-robot motion planning.
img: assets/img/mr-ompl-project-display.png
importance: 1
category: Work
---

The [Multi-Robot Open Motion Planning Library](https://github.com/aria-systems-group/Multi-Robot-OMPL) (MR-OMPL) is one of my newest, yet most open-sourced projects. The concept originated when I recognized my desire to employ OMPL for my multi-robot planning research, only to discover that several procedures within it were not functional without additional adjustments. This is especially true for decoupled planners, which treat every robot as its own individual and manage system-level (i.e. robot-robot) collisions seperately. To this end, MR-OMPL extends the single-robot capabilities of OMPL to account for decoupled multi-robot motion planning.     

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MR-OMPL-API.png" title="MR-OMPL API" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    MR-OMPL main classes and how they relate to the existing capabilities inside of OMPL.
</div>

MR-OMPL serves as a wrapper for OMPL by expanding the single-robot classes and functions into the multi-robot planning space. For example, an MR-OMPL *StateSpace* is a collection of single-robot OMPL *StateSpace's*. All of the required extensions are implemented inside a *new* namespace called __ompl::multirobot__. The classes shown in green in the figure above represent classes that are already implemented in MR-OMPL. The classes shown in yellow represent future-progress. Despite the simplicity of the idea, these simple extensions allow us to do mighty things like implement many decoupled multi-robot motion planning algorithms in a concise and consistent way without losing the generality and effectiveness of OMPL. So far, only a few multi-robot planners exist in MR-OMPL:

1. Geometric Prioritized Planner (ompl::multirobot::geometric::PP)
2. Control Prioritized Planner (ompl::multirobot::control::PP)
3. Geometric Knodynamic-Conflict Based Search (ompl::multirobot::control::KCBS)

It is hoped that researchers help utilize this library to implement many other multi-robot motion planning algorithms. Together, we can possibly grow MR-OMPL to become an excellent resource for researcher and industry partners alike. 


