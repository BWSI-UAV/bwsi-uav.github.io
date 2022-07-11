---
title: "Installation: ROS"
has_children: false
nav_order: 3
parent: "Module 0: Introduction & Setup"
---

# Installation: Robot Operating System
{: .no_toc }

Install ROS Noetic and set up a catkin_ws where you can develop your robotics applications.
{: .fs-6 .fw-300 }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## ROS Noetic

The Robot Operating System (ROS) provides the infrastructure for developing autonomous robots. It is a powerful tool in autonomous robotics as it is open source and applies to multiple programming languages including Python, Java, Lisp, and C++. For this course, we will be using a version of ROS called Noetic that is compatible with Ubuntu 20.04 and Python 3.

Follow [this page](http://wiki.ros.org/noetic/Installation/Ubuntu) to install ROS Noetic. Complete steps 1.2 - 1.4 in terminal. For the ROS install, we recommend you do the Desktop-Full Install or the Desktop Install.

Next, we will add this line to our `.bashrc` file, so that every time we open a new Terminal tab, this setup script is sourced so we can use ROS. If we don't do this, we would have to run `source /opt/ros/noetic/setup.bash` for every Terminal tab where we want to use ROS.

```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

Finally, follow step 1.6 from the above linked page. We have now successfully installed ROS.

## Create a ROS Workspace

Follow the steps [here](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment#Create_a_ROS_Workspace) to create a ROS workspace with `catkin_make`. This workspace is where we will write our code. Instead of creating the workspace in the home directory like `mkdir -p ~/catkin_ws/src`, create the workspace inside the `BWSI_Student_Code` repo that we created earlier.

Commit and push this workspace to your repo.

## ROS Tutorials

More ROS tutorials can be found [here](http://wiki.ros.org/ROS/Tutorials).