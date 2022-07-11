---
title: "Setup: Git & GitHub"
has_children: false
nav_order: 2
parent: "Module 0: Introduction & Setup"
---

# Setup: Git & GitHub
{: .no_toc }

Configure Git and learn to stage, commit, and push your code to GitHub.
{: .fs-6 .fw-300 }

> **Note**
> For any instructions from this point forward, you should be on your virtual machine, not Windows or MacOS.

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Install Git

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

> **Note**
> If you're copying the above command on your virtual machine, use `Ctrl-C`. To paste into your terminal, use `Ctrl-Shift-V`. To copy from Terminal, use `Ctrl-Shift-C`.

Now is the also the time to set up the virtual machine with any apps you need (maybe Google Chrome if you use it over Firefox). We recommend you stick with the bare minimum (covered in the next steps), as our virtual machine is limited in size. Note you don't need to connect through WiFi on the virtual machine.

## GitHub Code

You will submit all individual code through GitHub.

1. Make a [GitHub account](https://github.com/) if you haven’t already done so.
2. Create a new repository called `BWSI_Student_Code`. The repo is empty to start, but you will fill it out in time.
3. Make sure your repository is set to PRIVATE.
4. You can initialize the repo with a README.
5. Add the Instructors and TAs as members (viewers):
  * nhanson2
  * arykledet
  * ifueko
  * mcboyd-bu
  * mschof
  * rumaisaabdulhai

## Creating/Adding a SSH Key

Because support for password authentication was removed in 2021, we can no longer push code to GitHub with our username and password. There are 2 ways to get around this. 

1. If you would like to use HTTPS as your preferred protocol, you can look into [GitHub CLI or Git Credential Manager (GCM)](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git) to remember your credentials.

2. If you would like to use SSH as your preferred protocol, continue reading this section. This has been tested to work by the instructors.

The first step is to generate a new SSH key. We will be following [this tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to make one. Make sure you are on the **Linux** sub-tab of the page. Follow all the steps in ["Generating a new SSH key"](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key). For your email address, use the email associated with your GitHub account. Next, add your SSH key to the ssh-agent following steps 1 and 2 in ["Adding your SSH key to the ssh-agent"](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent).

The second step is to add the public SSH key to our GitHub account. Follow the instructions on [this page](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) to configure our GitHub account to use our new SSH key. Make sure you are on the **Linux / Web browser** sub-tab of the page. Make sure when you are copying the public key to paste, you use the output from entering `cat ~/.ssh/id_ed25519.pub` in the terminal.

## Pushing to GitHub

We will test making changes to the student code to make sure you can push changes to your remote repository on GitHub. We will need Terminal for this.

First, `cd` to the directory where you want to add this repository. One option is to add the repo to the home directory, indicated by the `~` (tilde) sign. You should already be at the home directory, but to make sure enter `cd` in the terminal.

To add the repository, we have to clone it:
```bash
# This is using SSH protocol
git clone git@github.com:<your username>/BWSI_Student_Code.git
```

Next, navigate to the repository/directory we just cloned:
```bash
cd BWSI_Student_Code
```

Next, we will try making changes to the README file. Open the file in a text editor/IDE of your choice, and insert a line of text (can be your name, for example). One way to open this in the terminal is using `nano`. Assuming you are already in the repository directory:
```bash
nano README.md
```

Once the file is opened, make whatever changes you would like to make. Use the arrow keys to move around the file. When you are ready, enter `CTRL-X` to Exit, `y` to save, and `Enter`/`Return` to write changes to the file.

Next, we have to [stage our file](https://github.com/git-guides/git-add) to be ready for committing:
```bash
git add README.md
```

You can also use `git add -A`, where the `-A` flag stands for all files in the entire working tree. This is useful if you made changes to multiple files and you want to stage them all at once.

Now we want to [commit](https://github.com/git-guides/git-commit) this change. To commit, we need to write a brief message describing what kind of changes we made:
```bash
git commit -m "add name to README.md"
```

Next, we can use `git status` to tell us the current state of your Git working directory and staging area. For more information, [see here](https://github.com/git-guides/git-status). This should tell us that our local branch is ahead of the remote `origin/main` branch by 1 commit, which is what we expected. It should also tell you the name of the branch you are currently on. In this case, it should be `main`.

Finally, let's [push](https://github.com/git-guides/git-push) our changes to the remote branch:
```bash
git push origin main
```

You should see the changes reflected on your online GitHub repository.