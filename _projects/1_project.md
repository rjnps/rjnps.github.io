---
layout: page
title: RL-controller
description: quadruped robot
img: assets/img/projects/rl_qped.png
importance: 1
category: work
related_publications: true
---

Legged robots like quadruped robots and humanoids have supreme mobility when compared to its wheeled counterparts. Controlling a quadruped robot to walk on challenging terrain using conventional controllers results in a lot of edge cases that are impossible to take into account while designing one. Reinforcement learning is a powerful paradigm that allows us to train very complex systems to perform complex actions.

In this work I have used a custom implementation of proximal policy optimization to train a quadruped robot to traverse a challenging terrain by following the commands given by a high level entity. The robot was designed ergonomically to walk on different kinds of terrain; also keeping in mind the ease of manufacture of each of its parts. The robot was trained on Nvidia’s Isaacgym physics simulation engine with domain randomization (random mass for robot’s base, random values of friction,random external force to the base of the robot, noise to observations) to facilitate the sim to real transfer of policy. The robots were trained to walk on both flat and rugged terrains including stairs, slopes and gap terrains.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/projects/post.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>

The observation space (input to the policy) involves linear and angular velocity of the base, orientation of the base (euler angles), commands given by the high level entity (randomized periodically for training), the actuator positions and velocities (of all 12 actuators of the robot), height measurement around the base of the robot. A random noise was added to all the observations as part of domain randomization.

Actions (output of the policy) comprises the position targets for all the 12 actuators in the robot, scaled by a suitable parameter. The actions are then passed through a PD controller to calculate torques required for all the actuators. These torques are commanded to the actuators through the tensor interface in isaacgym. The policy is a multilayer perceptron network, with three hidden layers, that is trained with proximal policy optimization. Multiple robots were trained in parallel to speed up the training process. The training took around 40 minutes on an RTX 4070ti GPU.

This work was inspired from <https://leggedrobotics.github.io/legged_gym/>.
