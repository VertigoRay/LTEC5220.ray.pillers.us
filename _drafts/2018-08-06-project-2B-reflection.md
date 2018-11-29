---
layout: post
title: Project B Reflection
img: //i.imgur.com/2yO4ppW.jpg
author: Raymond Piller
comments: true
tags:
- Instructional Design
- ProjectA
---
After finishing [Project A](/2018/07/08/project-1a-reflection/), I had a great foundation for training our veteran colleagues.
I couldn't forget about our student employees though.
For my [next project](2018-07-04-project-2B-description), I decided to bring our level two and higher technicians up to speed.
I figured this would be pretty simple, right?
I already have the foundation for the original course.
All I had to do was create a lecture and demonstration phase and I would be done.
Turns out I was right and wrong.

I started by making a couple of PowerPoint presentations to keep the training on track.
The presentations were simple.
I didn't want to flood the learners with information.
I wanted to encourage discussion and thought so that they could come up with ideas and think about the resolution process.

I then re-worked Project A's job aid so that the instructor would have more information about how to work through the training.
Doing this was crucial for me to learn where my original thought had gone horribly wrong.
When I started thinking about what it would take to get the part-timers up to speed, I constantly reminded myself that they aren't as familiar with our processes.
As such, they needed the implementation phase to be a lot simpler.
This is why this training has two fewer servers.

For this training to be successful, we now have a fully functional Development UNT domain.
It's connected with real DNS, Office 365 with A5 licenses, MS Exchange Hybrid, SCCM, MFA, PKI, AADC, ADFS, SCOM, and web application proxy for ADFS.
It has everything we need to do this training and feel like we are on a real domain; because we are.
The learners only need to bring up a Windows 10 VM, to connect to the Dev Domain, and a Windows Server 2016 VM to act as a learner specific file and print server.
Those two VMs are created automatically with Vagrant and test scenarios generated from random user data.
This allows multiple learners to work on the excercises without actually colliding with each other.

With real dev email accounts, we're able to just send the requests/tickets to the learner's email address on the dev domain.
This is far superior to my original idea of just putting the requests in text files in a folder on the learner's desktop.
The only thing this is missing is the ability to communicate with the fake customers.
Luckily, MS's bot framework can make that happen, and we could make some basic question and answer responses look like they are happening with a real customer.

Overall, my experience with Project B has been far superior, and my desire to create a fantastic, streamlined learning experienced has not yet been quenched.
Even though I've turned in the project, I consider it to be in its introductory phase.
I look forward to expanding on it and sharing it with the other departmental areas on campus.