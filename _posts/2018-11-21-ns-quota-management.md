---
layout: post
title: NS Quota Management
img: //i.imgur.com/ETQQMLQ.jpg
author: Raymond Piller
comments: true
tags:
- Cross-Training
- Network Shares
- Tasks
---
<style>
span.fake-link {
    color: blue;
    text-decoration: underline;
    cursor: pointer;
}

div.startHidden {
    display: none;
}
</style>

Quotas allow limiting how much space a user or group (department, research lab, etc) can use.
By default, all home directories start with 1 GB.
That’s not a lot, but 90% of our home drives are below that, and those that aren’t have been expanded after a simple audit of the types of files that are being stored.
We have no limit on the amount of space allowed, but we restrict thing to keep everything manageable.

If we do get a request for more space, the files must be audited, and if they all seem legit, the user can have his quota expanded by 10% or 1 GB; whichever is larger.
We prefer increases of 1 GB at a time.

We use tools like [WinDirStat](https://windirstat.net) to audit the types of files in a folder and all sub-folders.

##Home Drive is Out of Space

**Emailed Request:**

> I’m not able to save any more documents to my home drive.
> Can you help?
> 
> Thanks,<br />
> Praise C. Orsini<br />
> Praise.Orsini@donotreply.unt.edu

<span onClick="toggleReveal('adh5')" class="fake-link">**Resolution ...**</span>

<div id="adh5" class="startHidden">
In order to edit that website, the user requires membership in an AD group: <code>CASlab-WWW-Editors-oralhistory.unt.edu</code>.
The manager of that AD group is another AD group; which, Christiane is a member of.
No further information is required.
You should add <code>sar00001</code> to that AD group.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADH5'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

Resolution:
The user has 1 GB quota and a lot of Office docs. Request Approved.
This can be evaluated automatically with this PowerShell script:
$section = 'NSQ1'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex




Departmental Share Full – Chemistry 
Emailed Request:
We’re not able to save to chemistry’s departmental share anymore. I know I was able to about an hour ago. Can you take a look, please?
Thanks,
Delicia P. Leblanc
Delicia.Leblanc@donotreply.unt.edu
Resolution:
The department share should immediately be bumped by 1 GB to keep work flowing. The files should be audited to be sure nothing out of the normal appeared recently. All looks good. Request approved with an additional 9 GB.
This can be evaluated automatically with this PowerShell script:
$section = 'NSQ2'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
Departmental Share Full – Psychology
Emailed Request:
We’re not able to save to psychology’s departmental share anymore. One of the faculty members came in to ask if we knew what was going on. I tried to save something small and I was able. He tried something small and was able to. However, he’s having issues with a recording he’s trying to save. I told him I would contact you all, so I am.
Thanks,
Hai Lia Guo
Hai.Guo@donotreply.unt.edu
Resolution:
The department share should immediately be bumped by 1 GB to keep work flowing. The files should be audited to be sure nothing out of the normal appeared recently. Found a folder with a lot of videos. Owner of videos should be questioned about the videos. Leave that up to the department to decide. The request will be evaluated further when management makes gets an answer and makes a decision.
This can be evaluated automatically with this PowerShell script:
$section = 'NSQ3'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
Need More Space
Emailed Request:
I keep my life’s research on the H drive. It’s telling me now that I there’s insufficient space available on the drive. How do I go about requesting more?
Thanks,
Waldo P. Martelli
Waldo.Martelli@donotreply.unt.edu
Resolution:
The user has 44 GB quota; all files appear to be legitimate. Request Approved and no more than 4.4 GB additional space granted.
This can be evaluated automatically with this PowerShell script:
$section = 'NSQ4'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
Need More Space on Home Drive
Emailed Request:
I’ve out of space and trying to get work done for my chair. It won’t let me save my word document to my H: drive. For now, I’ve saved it to my desktop. Can you help me fix my H: drive, please?
Thanks,
Mariabella E. Denis
Mariabella.Denis@donotreply.unt.edu
Resolution:
Personal MP3 collection taking up 10 GB, and the user already has 11 GB quota. Request denied, and the user is informed that our expensive backups are for university use. The customer is informed that he has a week to clear off the MP3 collection. After which, it will be deleted.
This can be evaluated automatically with this PowerShell script:
$section = 'NSQ5'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex







<script>
function toggleReveal(id) {
    var x = document.getElementById(id);
    if (x.style.display === "block") {
        x.style.display = "none";
    } else {
        x.style.display = "block";
    }
}
</script>