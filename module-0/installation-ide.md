---
title: "Installation: IDE"
has_children: false
nav_order: 4
parent: "Module 0: Introduction & Setup"
---

# Integrated Development Environment
{: .no_toc }

Set up your IDE/workspace with helpful extensions.
{: .fs-6 .fw-300 }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Download IDE

Visual Studio Code is a great IDE where you can develop your code and edit many kinds of files. Download VS Code from [here](https://code.visualstudio.com) for Debian/Ubuntu (.deb).

## Important Extensions

We recommend you get the Python extension for VS code with [this link](https://marketplace.visualstudio.com/items?itemName=ms-python.python). You can also search for the extension with the id: `ms-python.python` in VS Code's extension search bar.

There is also an extension for the Robot Operating System (ROS), a tool we will using often in this course. You can get it with [this link](https://marketplace.visualstudio.com/items?itemName=ms-iot.vscode-ros).

This isn't an extension but while you're writing code, it's helpful to enable auto save by going to `File -> Auto Save`.

### Fun Extensions
{: .no_toc }

If you want to customize your IDE, check out the [Material Theme](https://material-theme.site/). In VS Code, use this [link](https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme) to install the extension. Alternatively, you can search for the extension ID `Equinusocio.vsc-material-theme`. Once installed, type `Ctrl + Shift + P` and search for “Preferences: Color Theme”. You will then be able to choose from all the Material themes.

Another nice extension is the [VS Code Icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons). The extension ID is `vscode-icons-team.vscode-icons`.

## Important Packages

Don't worry about installing Python 3. It should already be installed along with Ubuntu 20.04. You can check the version in Terminal with:
```bash
python3 --version
```

However, we do need to install pip, which is a package installer for Python:
```bash
sudo apt install python3-pip
```

Using pip, we will install a python library for the Tello:
```bash
pip install djitellopy
```