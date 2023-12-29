---
layout: page
title: XG-CBS
description: Explanation-Guided Conflict-Based Search (XG-CBS) extends CBS for MAPF to account for interpretability and thus producing more easily validated plans.
img: assets/img/xgcbs-project-display.png
importance: 5
category: Work
---

The goal of the Multi-Agent Path Finding (MAPF) problem is to find non-colliding paths for agents in an environment, such that each agent reaches its goal from its initial location. In safety-critical applications, a human supervisor may want to verify that the plan is indeed collision-free. To this end, a recent work introduces a notion of explainability for MAPF based on a visualization of the plan as a short sequence of images representing time segments, where in each time segment the trajectories of the agents are disjoint. Then, the problem of \emph{Explainable MAPF via Segmentation} asks for a set of non-colliding paths that admit a short-enough explanation. Explainable MAPF adds a new difficulty to MAPF, in that it is \NP-hard with respect to the size of the environment, and not just the number of agents. Thus, traditional MAPF algorithms are not equipped to directly handle Explainable MAPF. In this work, we adapt Conflict Based Search (CBS), a well-studied algorithm for MAPF, to handle Explainable MAPF. We show how to add explainability constraints on top of the standard CBS tree and its underlying \\(A^*\\) search. We examine the usefulness of this approach and, in particular, the trade-off between planning time and explainability.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/XG-CBS-illustration-Full.png" title="xg-cbs-full-plan" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/XG-CBS-illustration-1.png" title="xg-cbs-1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/XG-CBS-illustration-2.png" title="xg-cbs-2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/XG-CBS-illustration-3.png" title="xg-cbs-3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A plan for three agents (left), and a corresponding explanation via disjoint decomposition (right three). The circles and stars mark the start and goal vertices, respectively.
</div>

In this work, we consider a decoupled approach to the Explainable MAPF problem.  Specifically, we adapt CBS, a two-level algorithm that, in its low-level, plans individually for each agent, and in its high-level, identifies collisions between the agents and places constraints to resolve them in the next low-level iteration. Our *main contribution* is how we can use similar constraints as those used by CBS to capture *segmentation conflicts*, namely plans whose plan decomposition is too long (w.r.t. the end-user). We then discuss how to adapt CBS to compute and place these constraints during its search, thus obtaining our new algorithm, dubbed *Explanation-Guided CBS* (XG-CBS). XG-CBS is capable of returning MAPF plans that can be satisfiably presented to the human end-user. Some example plans from XG-CBS are shown below:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/cbs_full_plan.png" title="xg-cbs-full-plan" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/cbs_seg1.png" title="xg-cbs-1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/cbs_seg2.png" title="xg-cbs-2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/xgcbs_opt_full_plan.png" title="xg-cbs-3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Road crossing example: solutions via CBS (left three) and XG-CBS (right) that can be more easily validated by a human end-user. 
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/HT3_cbs_full.png" title="cbs-full-plan" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/HT3_cbs_seg1.png" title="cbs-1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/HT3_cbs_seg2.png" title="cbs-2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/HT3_cbs_seg3.png" title="cbs-3" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/HT3_cbs_seg4.png" title="cbs-4" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/HT3_xgcbs_opt_full.png" title="xg-cbs-opt" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Apparent collision from CBS solution (left five) vs. a more easily validated plan from XG-CBS (right). 
</div>

I invite you to investigate any of these great resources to learn more about K-CBS:

1. The original XG-CBS [ICAPS 2022 Conference Paper](https://ojs.aaai.org/index.php/ICAPS/article/view/19859)
2. The most-current implementation of [XG-CBS](https://github.com/aria-systems-group/Explanation-Guided-CBS) (to my knowledge)




