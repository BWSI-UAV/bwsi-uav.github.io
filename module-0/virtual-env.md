---
title: "Installation: Virtual Environment"
has_children: false
nav_order: 1
parent: "Module 0: Introduction & Setup"
---

# Installation: Virtual Environment
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

For this course, you will need to have a Linux machine. We can easily achieve this by installing a Linux virtual machine on our current computers. A virtual machine is software that you run on your computer that emulates a whole new, different computer. If you have a Windows or MacOS computer, follow the instructions below to install a Linux virtual machine with [VMware](https://www.vmware.com/).

> **Note**
> If you have a newer Mac with an M1 or M2 chip, please let us know. Way to check: `Apple Logo -> About This Mac -> Overview -> Processor`.

## Install VMware

MIT's IST Software page has numerous licensed software you can install, including VMware Pro. Scroll down [their page](https://ist.mit.edu/software-hardware) to find the link for VMware. Downloading software from this page will require you to authenticate with your MIT Kerberos account.

For Windows users, install [VMware Workstation Pro](https://ist.mit.edu/vmware/workstation). Depending on your Windows version, download the appropriate version of VMware. The download link should be called "Windows" under Workstation 16 Pro or Workstation 15.5.2 Pro (at the time these instructions were written).

For Mac users, install [VMWare Fusion Pro](https://ist.mit.edu/vmware/fusion) Depening on your MacOS version, download the appropriate version of VMware. The download link should be called "Software" under Fusion 12 Pro or Fusion 11.5.5 Pro (at the time these instructions were written). For visual instructions, view [these slides](https://docs.google.com/presentation/d/16RN_Lyg_VxJCYoO-hg_zKRYaw6xSa_2Tzl7m5DK3I-s/edit?usp=sharing).

Whether you have MacOS or Windows, you will need to copy the License Key from the same link you downloaded VMware (one of the above links. Click on the link called "License key" to get the key, and copy it to your clipboard with `CTRL-C`. When the setup wizard asks if you have a key, select "I have a license key" and paste it into the box below.

Continue through the setup wizard until you reach a Completed/thank you screen with Finish/Done.

## Download ISO

You can directly download the ISO file [here](https://releases.ubuntu.com/20.04.4/ubuntu-20.04.4-desktop-amd64.iso) for Ubuntu 20.04.4 from the official Ubuntu website. This may take a while.

<!-- TODO: Option for BitTorrent? -->

## Upload ISO to VMWare

- For MacOS users, follow [this tutorial](https://graspingtech.com/vmware-fusion-ubuntu-20.04/) to set up your Ubuntu 20.04 Virtual Machine.
- For Windows users, follow [this tutorial](https://youtu.be/Q0Na0f1NtpA) to set up your Ubuntu 20.04 Virtual Machine.

<!-- TODO: Any specific settings we should highlight? -->

## Git

For any instructions from this point forward, you should be on your virtual machine, not Windows or MacOS.

We need Git to manage the history of changes to repositories that we create. We will use Terminal (the command line) to install Git.

> **Note**
> To find Terminal, click on the waffle at the bottom left corner of the screen, search for "Terminal", and click on the app. We will be using it quite often so we recommend you add it to the left vertical menu by right-clicking the app icon and selecting "Add to Favorites".

To [install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), enter the following into Terminal:

```bash
sudo apt install git-all
```

You also need to set your [identity on Git](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup), which includes your user name and email address:

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

Now is the also the time to set up the virtual machine with any apps you need. We recommend you stick with the bare minimum (covered in the next steps), as our virtual machine is limited in size.

## GitHub

You will submit all individual code through Github.

1. Make a [GitHub account](https://github.com/) if you haven’t already done so.
2. FORK this repository linked [here](https://github.com/BWSI-UAV/BWSI_Student_Code). The repo is empty to start, but you will fill it out in time
3. Make sure your repository is set to PRIVATE
4. Add the Instructors and TAs as members (viewers):
  - nhanson2
  - arykledet
  - TODO: add Matthew Boyd's username
  - rumaisaabduhai
  - TODO: add Matthew Schofield's username