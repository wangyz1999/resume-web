---
title: Pathfinding Delivery Robot with Robotic Arm
summary: Simulating a Roomba robot traverse through a maze for delivery
tags:
- Academic
- Simulation
- Robotics
date: "2020-04-30T00:00:00Z"
lastmod: "2020-04-30T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: The Roomba robot is trying to deliver a cup in a maze
  focal_point: Smart

links:
# - icon: external-link-alt
#   icon_pack: fas
#   name: Website
#   url: https://csci527.wixsite.com/agentsmart
url_code: ""
url_pdf: ""
url_slides: ""
url_video: "https://www.youtube.com/watch?v=B_XmwHeK-N4"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

This is the final project of CSCI445 Introduction to Robotics in Spring 2020. In this project, we simulated a delivery robot (Roomba) holding up a cup to a robot arm. The delivery robot must first localize itself in the maze, and then plan a path to the robot arm. Then, motor commands are executed to drive the robot to the destination. Finally, a robot arm is responsible to pick up the cup and putting it onto a shelf. 

![Particle Filter](pf.jpg "Localization with Particle filter. Red arrows are particles of observation points representing possible Roomba location and the opaque Roomba is the approximated Roomba location by averaging particle coordinates. With more and more iterations, particless gradually converges to the actual location")

Several interesting topics are covered through this project. First, the Roomba needs to know its location at the maze. We use the particle filter method for this purpose. By randomly generating a large number of observation points inside the maze pretending they are the current location of Roomba (red arrows in the demo video) and then following Roomba to do random movements, the distribution of the sonar readings in all observation points or particles will gradually converge to that of the Roomba through resamplings. We can then approximate the Roomba's coordinate by averaging the coordinates of all observation points. 

![RRT Path](rrt_path.png "Planned path found by RRT*")

After localization, a path needs to be planned for Roomba to reach the robot arm, where we use the Rapidly-exploring Random Tree (RRT) algorithm. Starting from the localized coordinate, a tree-like search path gradually expands outwards until reaches the maximum iteration. Then, a search path can be traversed from the point closest to the destination back to the starting point and return the path as a sequence of coordinates. For a smoother and shorter trajectory, we upgrade the algorithm to RRT* which rewires the tree when a shorter path is possible. The robot then follows the planned path using PID control and odometry until reaches the robot arm. After that, the robot arm with 6 degrees of freedom pick up the cup and place it onto the shelf through a series of hard-coded motor commands.

{{< youtube B_XmwHeK-N4 >}}