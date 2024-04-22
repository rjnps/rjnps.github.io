---
layout: page
title: Automated greenhouse robot on ROS
description: work done as part of eyantra competition
img: assets/img/projects/ghr.png
importance: 4
category: fun
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/projects/dazzle.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>

This project involved designing an agent that can navigate a greenhouse and pick ripe tomatoes. This work (part of <a href="https://portal.e-yantra.org/">eyantra competition</a>), challenged us to develop perception  system, to identify ripe tomatoes, a navigation system to navigate a greenhouse without a prebuilt map, and manipulate tomatoes (pick ripe tomatoes and place it in the basket). The entire system was built on <a href="https://www.ros.org/">ROS</a> and was simulated on <a href="https://gazebosim.org/home">GAZEBO</a> simulation engine.