---
title: "Tello Passport 1"
has_children: false
nav_order: 1
parent: "Module 1: Quadcopter Basics"
---

# Tello Passport 1: Connection & Position Control
{: .no_toc }

We'll write code to connect to, receive telemetry from, and send commands to our Tello drone to allow us to fly in position control.
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

## Overview

This and future set of practicals utilize the DJI Tello Drone and its Python SDK. All the challenges should be completed using Python >= 3.6.

SDK documentation for the `djitellopy` library is available [here](https://github.com/damiafuentes/DJITelloPy). As of December 2021, this repository is more actively maintained than DJI’s official [repository](https://github.com/dji-sdk/Tello-Python). There are also lots of great YouTube tutorials if you get stuck.

The content on Tello passports is adapted from the [slide deck](https://docs.google.com/presentation/d/1Ims2b5a_DzUD3b-be4ckeH0wZR0W3Hx9ogS0RFHURTo/edit?usp=sharing) used to track student progress.

### This Unit
{: .no_toc }

This unit's challenges include:

* Connect to your drone
* Display drone telemetry
* Fly your drone in position control
* Fly around objects in your house

If you get stuck, refer to the resources page and reach out to other students and your instructors for help!

## Connect to Drone

Write a simple script in your IDE of choice to initialize your Tello, connect to it over Wi-Fi, and display some basic information about the drone (e.g. battery percentage) to confirm that you have successfully connected. When done, take a screenshot of your python output where you printed your drone information and show it to your instructors. You may run into seem errors establishing a socket connection through the SDK. Make sure you read the documentation FAQs before asking for help.

## Take Off & Hover

Write a script to connect to your Tello the same way you did in the previous challenge, but now, have the drone takeoff, hover for a certain period of time (e.g. 3 seconds), then land. 

> **Hint**
> Use the `sleep()` function from the `time` package to have the drone hover before it lands. When done, take a picture of your Tello with your phone while it’s hovering.

### Controlled Flight

Write a script to fly around your room via commands that tell the drone to move a specific distance. (e.g. make your drone fly in a square)

> **Hint**
> The `move()` and `rotate_clockwise()` functions will help a lot! Take a video on your phone and embed the link on the next slide. YouTube unlisted might be a good way to do this if you have an account.

## Fly Around an Object

Write a script to fly around a specific object in your room via commands that tell the drone to move a specific distance. (e.g. fly around a chair) Get creative!!

Take a video on your phone and upload to an unlisted YouTube video. Think - where is programming a predefined series of instructions like this likely to be useful, and where will it fail?