---
title: "Practical: Feedback & PID Control"
has_children: false
nav_order: 1
parent: "Module 3: Planning & Control"
---

# Explore Feedback & PID Control
{: .no_toc }

Practice incorporating feedback, then coding and tuning a PID controller.
{: .fs-6 .fw-300 }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Feedback  

1. From the `laboratoy` repo you previously cloned, open the notebook `laboratory/control/simple_feedback_control.ipynb` in VS Code.  
2. Complete the `TODO` code in the **Controller** section to return a **proportional** command.  
3. Complete the `TODO` code in the **Simulation Script** section to assign a value for the proportional gain (`kp`).  
4. Answer the questions in the notebook.  
5. Upload your completed code (with question answers) to your student repo.  

*NOTE: Be sure to comment out the `raise NotImplementedError()` lines in steps 2 & 3 above after adding your code.*  

## PID Controller  

1. Clone the `simple_pid` repo:
  ```
  cd ~
  git clone git@github.com:BWSI-UAV/simple_pid.git
  ```
2. Implement the PID controller: open `simple_pid.py` and edit lines 53, 54, and 57 to calculate your P, I, and D terms (look for `TODO` in the code).  
3. Tune your PID controller: open the notebook `Implementing PID in Python.ipynb` and tune the "gain" values kP, kI, and kD to generate a reasonable system response (again, look for `TODO` in the code).
4. Try to beat the response shown at the bottom of the notebook and answer the question about what makes your response "better".  
5. Upload your completed code (with question answer) to your student repo.  
