---
title: "Tello Passport 2"
has_children: false
nav_order: 1
parent: "Module 2: Computer Vision & Machine Learning"
---

# Tello Passport 2: Computer Vision
{: .no_toc }

We will write code that allows us to stream video being taken by our Tello camera drone via python’s open source computer vision library (Open CV).
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

If you haven't already, please make sure to complete [Tello Passport 1](../module-1/passport-tello-1.md) before continuing with this unit.

## Detect ArUco Markers

Write a simple script in your IDE of choice to stream video from your Tello’s camera and display via OpenCV. 

> **Hint**
> Don’t forget to use the `streamon()` and `get_frame_read()` functions from the `djitellopy` package! When done, take a screenshot of the opencv window with the Tello camera pointing at your face with your face shields on and paste the screenshot on the next slide to show us that you’ve completed the challenge!

Generate your own ArUco Markers via this [link](https://chev.me/arucogen/).

Standard Parameters: Dictionary - 5 x 5 Marker size, mm - 150

Feel free to modify the Marker ID. You might need multiple ArUco tags for future project work!

Now use the aruco module from the opencv-contrib-python package to detect aruco markers from your Tello’s live camera feed. The goal is to detect ID numbers and be able to return the pixel locations of the four corners of the aruco markers that appear in your video stream.

> **Note**
> You may need to do a significant amount of research on your own for this challenge but do not be afraid to reach out to your peers and instructors for help. When done, take a screenshot of the opencv window that pops up with the aruco marker detected by the script your wrote.

## Why do we use ArUco Tags?

AR tags, or more specifically, aruco markers are helpful features that we can utilize when attempting autonomous flight because they are easily recognizable by computer vision algorithms that we write, can convey information based on their ID numbers, and can tell us about our drone’s relative distance and orientation from the markers

When flying autonomously, your drone will need to know it’s relative distance and orientation to the aruco marker that it detects. To know this information, you will need to extract properties of the aruco marker that that are not given to you by default by the function used in the previous section.

## Finding Center of Tags

Since you are given corners, you can create a function that finds the average side length of the aruco marker and another that sets a target for the drone to follow at the center (centroid) of the aruco marker. Write a python class called Marker with a constructor that takes in the ID and the four corner values of the aruco marker. When the constructor is called to create an object, call functions (that you will write as well) to calculate the marker’s average side length and centroid and store these values as object attributes that can be referenced when scanning markers in your autonomous flight scripts.

## Calculating Distance & Orientation

Now we have information about how far our drone is from the aruco marker. (average slide length, more pixels = closer, less pixels = farther) We also know which direction the drone is pointing relative to the marker based on the location of the centroid to the middle of the video stream output (a little to the left, a little above, etc.). This is great information, but how do we know where exactly our drone is relative to the marker?

This requires us to look at the shape of the marker.

**Brainstorm a method for determining orientation and position relative to the markers.**

Create another attribute in the Marker class that gives an indication of orientation and position relative to the markers.

> **Hint**
> This has to do with the camera’s perceived shape of the marker. You may also need to write one or more helper functions in the Marker class for determining this value. When done, write an explanation of what you came up with and provide supporting images/videos.