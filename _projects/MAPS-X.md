---
layout: page
title: MAPS-X
description: Sampling-based random-tree algorithms for MRMP are extended to consider plan interpretability and thus producing more easily validated plans. 
img: assets/img/mapsx-project-display.png
importance: 6
category: Work
---

Traditional *Multi-Robot Motion Planning* (MRMP) focuses on computing trajectories for multiple robots acting in an environment, such that the robots do not collide when the trajectories are taken simultaneously. In *safety-critical* applications, a human supervisor may want to verify that the plan is indeed collision-free. In this work, we propose a notion of explanation for a plan of MRMP, based on visualization of the plan as a short sequence of images representing time segments, where in each time segment the trajectories of the agents are disjoint, clearly illustrating the safety of the plan. We show that standard notions of optimality (e.g., makespan) may create conflict with short explanations. Thus, we propose meta-algorithms, namely *Multi-Agent Plan Segmenting*-\\(X\\) (MAPS-\\(X\\)) and its lazy variant, that can be plugged onto existing coupled sampling-based tree planners \\(X\\) to produce plans with good explanations using a desirable number of images. We demonstrate the efficacy of this explanation-planning scheme and extensively evaluate the performance of MAPS-\\(X\\). An example of MAPS-X is shown below. 

<div class="row">
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/maps-x-example-full.png" title="empty" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/maps-x-example-seg1.png" title="coridoor" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/maps-x-example-seg2.png" title="maze" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/maps-x-example-seg3.png" title="large" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An example of a solved MRMP instance from MAPS-X with its minimal disjoint decomposition. 
</div>

I invite you to investigate any of these great resources to learn more about K-CBS:

1. The original [MAPS-\\(X\\) ICRA 2021 Conference Paper](https://ieeexplore.ieee.org/abstract/document/9561893)
2. The implementation of [MAPS-\\(X\\)](https://github.com/aria-systems-group/MAPS-X)

