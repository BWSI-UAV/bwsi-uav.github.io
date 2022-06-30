---
title: "Tello Passport 3"
has_children: false
nav_order: 1
parent: "Module 3: Planning & Control"
---

# Tello Passport 3: Control
{: .no_toc }

We'll be using the knowledge we just acquired of PID and controls to write code to fly the drone semi-autonomously and incorporate autonomous components as we go.
{: .fs-6 .fw-300 }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

<div align="center"> 
    <img src="/assets/images/dji_tello.jpg" alt="DJI Tello" width="560" />
</div>

If you haven't already, please make sure to complete [Tello Passport 1](../module-1/passport-tello-1.md) and [Tello Passport 2](../module-2/passport-tello-2.md) before continuing with this unit.

## Fly in a Perfect Circle

Write a script similar to Unit 1 Challenge 3, except this time, use the `send_rc_control()` function and command your drone to fly in a perfect circle.

## Yaw ArUco Marker Tracker

Write an algorithm that commands the drone to takeoff, fly up to a certain height, and locate aruco markers. Then, adjusting only the yaw parameter of the `send_rc_control()` function, have the drone remain in the same position but autonomously adjust it’s orientation to face and track the aruco marker.

> **Hint**
> This may necessitate the implementation of a PID controller. Think of how you can utilize the code you wrote in Unit 2 to help you determine a way to calculate error to help with PID implementation. When completed, film a video of you walking around your drone with an aruco marker in hand while your drone autonomously tracks the marker and adjusts its yaw to face the marker.

## Stationary ArUco Marker Tracker

Tape your marker on the wall. Then write a script to have the drone take off, locate the marker, and autonomously adjust all four parameters of the `send_rc_control()` function to command the drone to be flying right in front of the marker at a predetermined distance. This distance is up to you to determine. The goal is to implement PID controls for all four parameters such that if the drone were to be nudged/pulled/pushed during flight, it would quickly correct and return to the set point.

> **Warning**
> This is a tough challenge so get as far as you can and reach out to your peers and instructors for help. Post a video of your final progress when complete.