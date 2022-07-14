---
title: "Challenge 1: ROS Wrapper For Tello"
has_children: false
nav_order: 4
parent: "Module 1: Quadcopter Basics"
---

# Challenge 1: ROS Wrapper For Tello
{: .no_toc }

Detailed instructions for Challenge 1 of the BWSI UAV Racing Course.
{: .fs-6 .fw-300 }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Overview

This week's challenge is to write your own ROS Wrapper for the [DJI/Ryze Tello EDU](https://www.ryzerobotics.com/tello-edu) Drone. In other words, we will develop an interface that allows us to communicate with our Tello through the Robot Operating System (ROS).

In real life, software isn't going to be readily compatible with each other. So we have to write code to be able to use two (or more) pieces of software/hardware simultaneously. The goal of this challenge is to understand how to use ROS by creating your own package, nodes, topics, and messages and see it all come to life. And of course, you'll need this code to complete later challenges. We hope you find this fun and challenging!!

In order to work through this challenge, you will need to have completed [Module 0](https://bwsi-uav.github.io/module-0). We recommend that you:

1. Complete the simple [Publisher and Subscriber](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29) tutorial first before working on this challenge. You should have already created your own publisher and subscriber nodes in the recent ROS practical.
2. Use the [DJITelloPy](https://github.com/damiafuentes/DJITelloPy/) package to interact with the Tello. You should already be familiar with using DJITelloPy through the Tello Passport 1.

You can work together in groups of 3 or 4, but we encourage everyone to write their own copy of the code so that we can all test code on the Tello. You will have Thursday and Friday afternoon to work on the challenge. The instructors will be visiting breakout rooms to make sure everything is running smoothly. Do not worry about time. If we find that most students need more time, we will allocate more time for the challenge.

> **Note**
> We kindly ask that you refrain from searching up anything online except on the [ROS Tutorials](http://wiki.ros.org/ROS/Tutorials) page. This is an important learning experience for everyone. If you get stuck, please do not hesitate to contact the instructors or TAs on Discord. You are welcome to review lecture content.

## Instructions

1. Create a catkin package for your ROS wrapper.

2. Organization in package (create these folders):

    * `src` folder for python code (nodes)
    * `launch` folder for launch files
    * `msg` folder for custom msgs
    * `rviz` (optional) folder for rviz files
    * `config` (optional) folder for config files

3. You will need to have these topics and these messages:

    * `/tello/cam_forward`: [sensor_msgs/Image](http://docs.ros.org/api/sensor_msgs/html/msg/Image.html)
    * `/tello/cam_downward`: [sensor_msgs/Image](http://docs.ros.org/api/sensor_msgs/html/msg/Image.html)
    * `/tello/state`: tello/State
    * `/tello/flip`: tello/Flip
    * `/tello/cmd_vel`: [geometry_msgs/Twist](http://docs.ros.org/api/geometry_msgs/html/msg/Twist.html)
    * `/tello/takeoff`: [std_msgs/Empty](http://docs.ros.org/api/std_msgs/html/msg/Empty.html)
    * `/tello/land`: [std_msgs/Empty](http://docs.ros.org/api/std_msgs/html/msg/Empty.html)
    * `/clock`: [rosgraph_msgs/Clock](http://docs.ros.org/en/api/rosgraph_msgs/html/msg/Clock.html) (optional)
    * `/tello/cam_forward_info`: [sensor_msgs/CameraInfo](http://docs.ros.org/en/api/sensor_msgs/html/msg/CameraInfo.html) (optional)
    * `/tello/cam_downward_info`: [sensor_msgs/CameraInfo](http://docs.ros.org/en/api/sensor_msgs/html/msg/CameraInfo.html) (optional)

    Don't do anything with these yet, but take some time to discuss these topics with your team and review all of the above message links.

4. You will need to create custom messages called **State** and **Flip** to store the drone’s state and desired type of flip. How you design these messages is up to you. Refer to this [post](https://answers.ros.org/question/271620/importerror-no-module-named-xxxxmsg/?answer=320343#post-id-320343) to understand how to create your own messages.

5. You need to create two nodes. The first node, called `driver`, will **publish** the cameras and state information from the Tello. It will **subscribe** to flip, velocity, takeoff, and land commands and directly send those commands to the drone. The second node, called `teleop` (short for teleoperation or manual control) will be listening to keyboard input from the user and **publishing** flip, velocity, takeoff, and land commands.

6. For the `teleop` node, there are two packages you could use: `pynput` or `pygame`. There could be other python packages for reading keyboard input but we recommend you stick to one of the above so that the instructors can easily help.

7. In order to run your nodes, we use launch files. For our use, these will seem really simple but they're actually super useful if you want to run multiple nodes at the same time. Create two launch files for each node. For more information on what `roslaunch` is and how to use it visit [this page](http://wiki.ros.org/roslaunch). To understand how to create them visit [this page](http://wiki.ros.org/roslaunch/XML#Example_.launch_XML_Config_Files), specifically the minimal example.

8. Use `rqt_image_view <topic_name>` to see the forward and downward camera. First try visualing the camera stream only using `djitellopy` and `cv2.imshow()` (without ROS), and then use `rqt_image_view`. To visualize the images in ROS, you will need to convert the image/frame (which is a numpy array) into a [ROS Image](http://docs.ros.org/api/sensor_msgs/html/msg/Image.html). To learn more about how to encode the images into ROS messages and vice versa, visit [this tutorial](http://wiki.ros.org/cv_bridge/Tutorials/ConvertingBetweenROSImagesAndOpenCVImagesPython).

    > **Note**
    > You can only view one camera at a time, so do not worry about trying to view both the forward and downward camera streams. Consider creating a boolean variable to alternate between the two.

9. Please notify the instructors/TAs that you would like a checkoff and an available instructor/TA will come to your breakout room. In a checkoff, you and your teammates should walk us through your code. Then, show us the code running on the Tello. This should take about 5-10 minutes.

## Helpful Reminders/Tips

* Tip 1: Every time you open a new terminal tab, always make sure to enter:

  ```
  source ~/catkin/devel/setup.bash
  ```

  You can also copy & paste it into your `.bashrc` file. What this does is it allows you to access your ROS packages from anywhere (whether you are inside your `catkin_ws` or not!). Whenever you add a new package, launch, or rviz file, you should enter it manually.

* Tip 2: You don't have to remember the exact name of your package or launch file. For example, if you want to run something like `roslaunch package_name file.launch`, You can enter half of the package name and just press tab to autocomplete or see all packages (that you've installed or exist in your `catkin_ws`) that start with that prefix. You can also do the same with the launch file name.

## Challenges with WiFi

Given the drone has it’s own WiFi, you will often have to disconnect from the WiFi to connect to the drone and use it. We will allow you to join zoom with your phones in your breakout rooms (still use your Kerberos accounts to sign in). If you have a separate laptop/school iPad that you can join Zoom with (we acknowledge that not everyone has access to this) that’s even better.

## Extra Challenge

Please only work on the extra challenge once you have worked through steps 1-9. The first extra challenge is a sneak peek of what we will learn in Week 3.

1. Using the driver node (or both nodes), we want you to write instructions that will allow the drone to draw/trace a specific shape in the air. Maybe a star, square, or even a beaver!!
2. Use RViz (short for ROS Visualization) to view the image stream from the Tello. This is similar to `rqt_image_view` but it is more useful when you want to visualize more topics (ie. multiple camera streams or laser scans from a LiDAR). Once you create an RViz file and set the topics for the forward and downward camera stream, we want you to save it and then open the saved file again. Learn more about using RViz [here](https://www.theconstructsim.com/ros-qa-125-save-and-load-rviz-configuration/).