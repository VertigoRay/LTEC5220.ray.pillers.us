---
layout: post
title: Preparing for Training
img: //i.imgur.com/JwAcelr.png
author: Raymond Piller
comments: true
tags:
- Cross-Training
---
Before you go any farther, you will want to start setting up your computer for the training.
The virtual lab that we’ll be using is free and easy to set up.
However, it can take an hour or more to automatically run through all the steps; the speed mostly depends on your internet speed and the speed of your computer.
Let’s get the lab creation process started so we can let it run while you read through this document.

# Definitions

I’ll attempt to define some common definitions for this document.
Definition details will be linked.

- CLI: Command-Line Interface
  - Any text/commands in orange code font should be typed into your CLI.

# Pre-Installation

We will need a few pieces of software to set up the training lab.
The lab will run in VirtualBox VMs.
The VMs are configured with Vagrant so setup is easy; even if it takes a while.
The Vagrant files are stored on [GitHub](https://github.com) so we might want a git client installed to make getting the files a breeze.
You’re expected to know how to run and walk through an installer on your own.
For the purposes of this lab, the default installation options are fine.

1. [VirtualBox](https://www.virtualbox.org) or [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/about/) (Windows 8+ Non-Home Editions):
   - [Ensure you have Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/about/#system-requirements) or Download and Install VirtualBox:
     - [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads). *The page isn’t the prettiest, but the download links are at the top.*
       - **Windows**: Click the *Windows hosts* link, near the top of that page.
       - **OS X**: Click the *OS X hosts* link, near the top of that page.
   - Install VirtualBox.
2. [Vagrant](https://www.vagrantup.com):
   - [Download Vagrant](https://www.vagrantup.com/downloads.html). *Choose the download appropriate for your OS.*
   - Install Vagrant.
3. **Optional**: [Git](https://git-scm.com):
   - Download [Git](https://git-scm.com/downloads). *Choose the download appropriate for your OS.*
     - **OS X**: OS X comes with Git, but it’s likely not the latest version. Feel free to take this time to upgrade it.
   - Install Git.

# Lab Preparation

You’re expected to already be familiar with using git, GitHub, and Vagrant.
If you’re not, you may want to find and run through the tutorials on those.
However, you don’t need to run through the tutorials to get this started, I’ll cover everything with enough detail to do it, even if you don’t understand how it’s working.
Understanding these pieces is beyond the scope of this document and the training.

1. Open your CLI. *We will work from `C:\Temp`. If you decide to change that path or you’re not using Windows, you will need to adapt future commands that reference the path that you’re using.*
   - Change into that folder: cd C:\Temp
2. Download the Vagrant files from GitHub: https://github.com/UNT-CAS/adfs2
   - **If you have git installed**:
     - `git clone https://github.com/UNT-CAS/adfs2.git`
   - **If you do not have git installed**:
     - Download the Zip with your web browser: https://github.com/UNT-CAS/adfs2/archive/master.zip
     - Save it to `C:\Temp`.
     - Extract the Zip file. *Make sure the extracted files are in a folder called `adfs2` and there’s a `Vagrantfile` file in that folder.*
3. Tell Vagrant to build your lab. *This can take an hour or more, so be patient.* 
   - Change into the adfs2 folder: cd adfs2
   - Tell vagrant to start the lab:
     ```
     vagrant up dc
     vagrant up web
     vagrant up ps
     vagrant up desktop
     ```
4. From the CLI on the Desktop VM, run this PowerShell command: `iwr 'https://pastebin.com/raw/mRvEc0hY' -UseB | iex`
   - *The virtual lab does not start out with many users in the domain. Generally, it’s a clean domain. So, we need to populate it with some fake user data. Run this script from the desktop VM to generate 2,000 mostly random AD objects.*