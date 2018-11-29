---
layout: post
title: AD Access/Permission Issues
img: //i.imgur.com/ETQQMLQ.jpg
author: Raymond Piller
comments: true
tags:
- Cross-Training
- Active Directory
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

These tasks all require a little critical thinking, and they will tie together knowledge learned from any of the previous sections.
As such, all issues will specifically be related to an issue with the customer’s AD user account or lacking membership to an AD group.

## Network Access Denied

**Emailed Request:**

> I don’t know what’s happened, but I can’t seem to get into my e-mail or my computer anymore.
> It keeps telling me that my access is denied. I’m in a hurry and need this fixed immediately!!
> 
> PLEASE HELP!!!!!
> 
> Naldo B. Dorsey<br />
> Naldo.Dorsey@donotreply.unt.edu

<span onClick="toggleReveal('adh1')" class="fake-link">**Resolution ...**</span>

<div id="adh1" class="startHidden">
The account is disabled.
Notes on the accounts state this was requested by the user’s manager.
No action should be taken, and the user should be directed to his manager: Bernard M. Alesi (<code>bma02673</code>).

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADH1'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

## Cannot RDP to Desktop

**Emailed Request:**

> Dear IT Support,
> 
> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sapien diam, condimentum sit amet dolor nec, dignissim tristique lorem. Etiam ultrices ornare dolor, non volutpat risus convallis vitae. Praesent quis auctor urna. Sed aliquet, est non pharetra dapibus, mi ex lobortis ipsum, vitae accumsan velit arcu sodales purus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aenean ut dolor molestie, luctus est nec, ornare ligula. Nam lobortis ultrices lacus a dictum. Maecenas eleifend tincidunt eleifend. Phasellus varius imperdiet posuere.
> 
> Sed ac lacus fermentum nulla bibendum aliquam. Integer imperdiet leo nec massa porttitor, ut vulputate est tristique. Pellentesque in ante eu metus venenatis fermentum. Ut placerat nec elit vitae interdum. Nulla efficitur vel orci non tincidunt. Phasellus maximus odio quis aliquam blandit. Vestibulum nisl libero, porta vel nulla et, pulvinar luctus nisl. Nam dictum mauris eget libero porta, in varius urna rhoncus. Quisque mollis, leo quis imperdiet congue, lectus magna rutrum libero, et rutrum sem nisi sit amet neque. Morbi a mattis dui. Fusce cursus sem id ipsum tincidunt tincidunt. Mauris congue viverra risus, nec cursus turpis suscipit vel. Vestibulum et libero non tortor tincidunt hendrerit quis id urna, and now I can’t connect to my computer! Can you help?
> 
> Hopefully yours,<br />
> Wilfredo D. Zeni<br />
> Wilfredo.Zeni@donotreply.unt.edu

<span onClick="toggleReveal('adh2')" class="fake-link">**Resolution ...**</span>

<div id="adh2" class="startHidden">
The account is locked out; likely from all the craziness they were experiencing/explaining.
You should unlock it and offer further assistance.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADH2'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

## Cannot Print – Access Denied

**Emailed Request:**

> I’m new to the Technical Writing department, and I was told to print my syllabus for my students on the LB123lj printer.
> Unfortunately, I can’t seem to print to it, and I’ve been trying all morning.
> Any assistance would be appreciated.
> 
> Thanks!<br />
> Eustace A. Amador<br />
> Eustace.Amador@donotreply.unt.edu

<span onClick="toggleReveal('adh3')" class="fake-link">**Resolution ...**</span>

<div id="adh3" class="startHidden">
The printer is locked to a specific AD group: <code>CASlab-Printer-LB123lj</code>.
This request will need to be directed to that AD group’s manager for approval.
The manager is Everette D. Simmons (<code>eds00001</code>).
Once approval is given the user should be added to the AD group.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADH3'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

## Network Share Inaccessible

**Emailed Request:**

> My new employee needs to access the same files that I have access to.
> I’m not sure what needs to be done.
> 
> - Files: S:\PHYS\FacStaff
> - Employee: Panfilo Pound (ppp00001)
> 
> Thanks!<br />
> Reuben N. Pickering <br />
> Reuben.Pickering@donotreply.unt.edu

<span onClick="toggleReveal('adh4')" class="fake-link">**Resolution ...**</span>

<div id="adh4" class="startHidden">
That folder requires membership to an AD group: <code>CASlab-S-PHYS-FacStaff</code>.
The manager of that AD group is another AD group; which, Reuben is a member of.
No further information is required.
You should add Panfilo to that AD group.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADH4'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

##Cannot Log In to Website

**Emailed Request:**

> My new employee (sar00001) needs to be able to make changes to our website:
> 
> https://oralhistory.unt.edu
> 
> Thanks!<br />
> Christiane C. Hathway<br />
> Christiane.Hathway@donotreply.unt.edu

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