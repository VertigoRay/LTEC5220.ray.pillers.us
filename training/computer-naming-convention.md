---
layout: post
title: Computer Naming Convention
img: //i.imgur.com/ien2uTu.png
author: Raymond Piller
comments: true
tags:
- Resources
---
All computer names cannot exceed a length of 15 characters, per NETBIOS compliance.
I realize NETBIOS is almost legacy, but exorbitantly long computers names are not conducive to good health.

**The naming conventions MUST be applied before binding any machines to the UNT domain.**
**If you have a name longer than 15 characters, Windows will give you a warning about the NETBIOS name being truncated.**
**Also, here's an example of what happens in AD when a hostname is set to something 16 characters or longer; such as `CAS-Gold-Win2016` (length: 16):**

![NETBIOS fail!](//i.imgur.com/pqfTLTX.png)

Any exceptions must be approved by the Infrastructure Team or Service Desk Manager.
Additional information can be found on [CAS’ Computer Naming Convention web page](https://itservices.cas.unt.edu/services/computers/articles/computer-naming-convention).