---
layout: post
title: Network Shares - Introduction
img: //i.imgur.com/1flydtA.png
author: Raymond Piller
comments: true
tags:
- Cross-Training
- Network Shares
---
We encourage all faculty and staff to store their important, work-related files on the network shares instead of their computers.
This is because we have invested heavily in the backup of those network shares to protect the data stored on them, in the event of a failure.
However, backup of local computer data is left to the user of the computer to deal with.
As such, most computers are not backed up routinely.

In this lab, the only two shares available are both served from the same server, and should be mapped to a drive letter accordingly:

| Drive Letter | Lab UNC Path | Real UNC Path |
| --- | --- | --- |
| H: | \\cas-trainfile-0\Home | \\cas-home\Home |
| R: | -- | \\cas-research\Research |
| S: | \\cas-trainfile-0\Shared | \\cas-shared\Shared |

*Note: in the lab, we’re using a Windows Nano 2016 VM for the file share.*
*This is a very light-weight server and requires RSAT.*
*The “0” on the server name may vary for your training, but we will be posted to the BG Info of the Windows 10 VM.*