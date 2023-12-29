---
layout: page
title: Online Fault ID
description: We use M-ary Bayesian Hypothesis Testing to verify nominal system performance (or lack thereof) in real-time. 
img: assets/img/fault-ID-project-display.png
importance: 4
category: Work
---

We developed a Model-Based Fault Identification (MBFID) algorithm that utilizes a technique called M-ary Bayesian Hypothesis Testing. Our MBFID framework requires telemetry data from a digital-twin capable of accurately simulating the real autonomous vehicle's nominal telemetry and the effects of known faults. Given this, our MBFID framework can detect many different faults with over 95% success rate. Since this project was funded by the [Air Force Research Laboratory](https://www.afrl.af.mil/) (AFRL) in collaboration with [Verus Research](https://verusresearch.net/), the experiments and project evolution were spacecraft-specific. However, our methodologies remain generalizable to any dynamical system.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Fault-ID-framework.png" title="fault-ID" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/fault-ID-project-display.png" title="fault-id-distributions" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The MBFID framework.
</div>

Intuitively, we run multiple estimators (e.g. a Kalman Filter) simultaneously, each one assuming (via the state and measurement equations) a particular operation mode/fault. Then, given a measurement from the real system, the M-ary Bayesian Hypothesis Testing framework creates an M-partition of the entire observation space and fits a posterior distribtuion given the measurement. Then, the tester can select the mode that the system is *most likely* in. We also can effectively identify unknown anomalies this way by recognizing when the system is most likely **not** in any modeled mode. 

We have shown that that this method is very effective at identifying both known and unknown faults. Some examples are shown below. 

<div class="row">
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/Fault-ID-example1.png" title="fault-ID-ex1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/Fault-ID-example3.png" title="fault-ID-ex2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/Fault-ID-example3.png" title="fault-ID-ex3" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-4 mt-md-0">
        {% include figure.html path="assets/img/Fault-ID-example4.png" title="fault-ID-ex4" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A number of correctly identified spacecraft faults using our M-ary Bayesian Hypothesis Framework. 
</div>

I invite you to investigate any of these great resources to learn more about our work on this project:

1. The implementation of the [M-ary Bayesian Hypothesis Tester](https://github.com/aria-systems-group/Fault-Identification-via-Bayesian-Inference)


