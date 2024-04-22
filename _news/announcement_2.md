---
layout: post
title: Won the NeurIPS 2023, HomeRobot Open Vocabulary Mobile Manipulation (OVMM) Challenge
date: 2023-12-16 16:11:00-0400
inline: false
related_posts: false
---

<!-- Announcements and news can be much longer than just quick inline posts. In fact, they can have all the features available for the standard blog posts. See below. -->

---

The HomeRobot Open Vocabulary Mobile Manipulation (OVMM) Challenge involved designing an embodied AI agent that is capable of navigating unfamiliar environments, recognizing open vocabulary classes and manipulating novel objects.

<a href="https://aihabitat.org/challenge/2023_homerobot_ovmm/">**Challenge website**</a>

<a href="https://arxiv.org/pdf/2312.08611.pdf">**Our solution**</a>

I was part of the team that worked on the perception pipeline for this work. The baseline agent provided in the challenge used <a href="https://github.com/facebookresearch/Detic">DETIC</a> for open vocabulary segmentation. As an alternative, we tried using <a href="https://github.com/IDEA-Research/GroundingDINO">GroundingDINO</a> with <a href="https://github.com/facebookresearch/segment-anything">SAM</a>, <a href="https://github.com/CASIA-IVA-Lab/FastSAM">FastSAM</a>, <a href="https://github.com/yformer/EfficientSAM">EfficientSAM</a>. We observed that  DETIC performed much better than GroundingDINO in this environment, especially when it came to identifying objects that are partially visible. To reduce the false positives, we tried using an object tagging model Recognize Anything Model (<a href="https://github.com/xinyu1205/recognize-anything">RAM</a>), to identify all the objects in the scene, and use it as text prompts to DETIC and GroundingDINO. We also experimented by giving the task specific objects (start receptacle name, end receptacle name, object) explicitly to DETIC and GroundingDINO, along with the tags that RAM predicted, to prime the open vocabulary segmentation module. 
