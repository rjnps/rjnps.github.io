---
layout: page
title: Dual Arm Manipulator in ROS
description: Gazebo simulation
img: assets/img/projects/dac.png
importance: 2
category: fun
giscus_comments: false
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/projects/dac.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>

This work involved designing a dual arm controller to simultaneously manipulate an object without using the robot's grippers. The stack was built on <a href="https://www.ros.org/">ROS</a> and <a href="https://moveit.ros.org/">Moveit</a>. Trajectories for both the arms were planned simultaneously using Moveit (RRTStar as the planner), and was executed in a sequential manner.