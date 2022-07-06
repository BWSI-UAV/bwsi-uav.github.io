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
> If you have a newer Mac with an M1 or M2 chip, you cannot install VMware Fusion Pro. One workaround is to install [VMware Fusion Tech Preview](https://customerconnect.vmware.com/downloads/get-download?downloadGroup=FUS-PUBTP-2021H1) instead. Way to check for chip type: `Apple Logo -> About This Mac -> Overview -> Processor`.

## Install VMware

MIT's IST Software page has numerous licensed software you can install, including VMware Pro. Scroll down [their page](https://ist.mit.edu/software-hardware) to find the link for VMware. Downloading software from this page will require you to authenticate with your MIT Kerberos account.

For Windows users, install [VMware Workstation Pro](https://ist.mit.edu/vmware/workstation). Depending on your Windows version, download the appropriate version of VMware. The download link should be called "Windows" under Workstation 16 Pro or Workstation 15.5.2 Pro (at the time these instructions were written).

For Mac users, install [VMWare Fusion Pro](https://ist.mit.edu/vmware/fusion) Depening on your MacOS version, download the appropriate version of VMware. The download link should be called "Software" under Fusion 12 Pro or Fusion 11.5.5 Pro (at the time these instructions were written). For visual instructions, view [these slides](https://docs.google.com/presentation/d/16RN_Lyg_VxJCYoO-hg_zKRYaw6xSa_2Tzl7m5DK3I-s/edit?usp=sharing).

Whether you have MacOS or Windows, you will need to copy the License Key from the same link you downloaded VMware (one of the above links. Click on the link called "License key" to get the key, and copy it to your clipboard with `Ctrl-C` or `Cmd-C`. When the setup wizard asks if you have a key, select "I have a license key" and paste it into the box below.

Continue through the setup wizard until you reach a Completed/thank you screen with Finish/Done.

## Download ISO

You can directly download the ISO file [here](https://releases.ubuntu.com/20.04.4/ubuntu-20.04.4-desktop-amd64.iso) for Ubuntu 20.04.4 from the official Ubuntu website. This may take a while.

<!-- TODO: Option for BitTorrent? Is it safe enough / worthwhile to menton? -->

## Upload ISO to VMWare

- For MacOS users, follow [this tutorial](https://graspingtech.com/vmware-fusion-ubuntu-20.04/) to set up your Ubuntu 20.04 Virtual Machine.
- For Windows users, follow [this tutorial](https://youtu.be/Q0Na0f1NtpA) to set up your Ubuntu 20.04 Virtual Machine.

<!-- TODO: Any specific settings we should highlight? -->