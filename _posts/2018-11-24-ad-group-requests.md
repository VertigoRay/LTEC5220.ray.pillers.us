---
layout: post
title: AD Group Requests
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

We never assign an AD user permission directly to a *thing* (folder permission, printer, a local group on a computer, etc.).
Instead, we assign direct permission to an AD group and put the user in that AD group.
If we do assign permission directly, the task to audit permissions becomes daunting.
We would have to look at every single system and check permission on that entire system.
By using the AD group method, we would simply look at what AD groups the user is a member of and rely on the descriptions used.

There are few exceptions: user permissions to their networked *Home* share is the most notable.
Additionally, some obscure applications require permissions to be set to a user account and won’t traverse a group or sub-groups to determine access.
These applications aren’t common, but they do exist.
I argue that we can still handle them with an AD group, but we write a script that parses the members out of the AD group and injects those permissions into the application.
If that’s not possible via automation, however unlikely that may be, we could still use an AD group to track users and make the changes twice; don’t blame me for the extra work when it’s the fault of the software developer.

## Share Access

**Emailed Request:**

> Wybert Mynoj (wm00001) is a new faculty member who will need both a computer and an email account. He will also need access to all files and folders in the following folder on the "S" drive:
> 
> S/JOUR/FACSTAFF/FACULTY & STAFF
> 
> Sincerely,<br />
> Cybill Terry Smythe<br />
> Cybill.Smythe@donotreply.unt.edu

<span onClick="toggleReveal('adg1')" class="fake-link">**Resolution ...**</span>

<div id="adg1" class="startHidden">
Ensure the user is added to the AD group: <code>CASlab-S-JOUR-FACSTAFF</code>.
This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADG1'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

You should have evaluated if the requestor is the manager of that AD group; which she is.
</div>

## RDP Request – Add User

**Emailed Request:**

> I currently have a computer in my research lab, that I can RDP into.
> I would like to allow my research assistance the same ability.
> Can you please give Shirley McTemple access to RDP into that computer?
> 
> Computer: CASlab-56D72H43<br />
> Shirley’s EUID: sm00001
> 
> Thank you!<br />
> Sincerely,<br />
> Ramiro R. Harlow<br />
> Ramiro.Harlow@donotreply.unt.edu

<span onClick="toggleReveal('adg2')" class="fake-link">**Resolution ...**</span>

<div id="adg2" class="startHidden">
Ensure the user is added to the AD group: <code>CASlab-GPO-RDPAllow-CASlab-56D72H43</code>.
This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADG2'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

You should have evaluated if the requestor is the manager of that AD group; which he is.
</div>

## Technician Leaving – Chucky Dobi

**Emailed Request:**

> I must report that the time of Chucky Dobi has come to an end.
> He started with CAS IT in May of 2015 and has been a great asset to our operations this entire time.
> We’ll miss him as he moves on having graduated from UNT.
> 
> Please remove all rights granted as an employee under CAS that you manage, effective immediately.
> 
> Thanks!<br />
> Chas G. Abbatangelo<br />
> Chas.Abbatangelo@donotreply.unt.edu

<span onClick="toggleReveal('adg3')" class="fake-link">**Resolution ...**</span>

<div id="adg3" class="startHidden">
You should discuss with the customer to determine if they know if Chucky will still be at UNT.
They will find out that they should not be at UNT, and the account should also be disabled, manager removed, CAS home drive archived and removed, and AD user moved to the <code>Lost Users</code> OU.

Ensure the user is removed from all AD groups.
This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADG3'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

You should have evaluated if the requestor is the manager of that AD group; which he is.

*Bonus:* You should also evaluate all AD objects and determine if Chucky was listed as the manager of anything.
</div>

## New Technician – KVM Access

**Emailed Request:**

> My new tech is ready for his KVM training.
> Please grant him access accordingly.
> 
> Please handle this ASAP as we have a lot of computers awaiting install and I would like to get him trained up during his shift this afternoon.
> 
> Yours rushedly,<br />
> Dorris C. Newton<br />
> Dorris.Newton@donotreply.unt.edu

<span onClick="toggleReveal('adg4')" class="fake-link">**Resolution ...**</span>

<div id="adg4" class="startHidden">
You should discuss with the customer to determine which new tech.
The new Tech is Isaure H. Sargent (<code>ihs00001</code>).

Ensure the user is added to the AD group: <code>CAS-KVM-TechAccess</code>.
This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADG4'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

You should have evaluated if the requestor is the manager of that AD group; which she is.
</div>

## Restricted Printer Access

**Emailed Request:**

> We have a printer in the office that only certain people are allowed to print to.
> Can you please add Maria Martinez permission to print to this printer?
> 
> Thanks!<br />
> Jackie B. Howse<br />
> Jackalyn.Howse@donotreply.unt.edu

<span onClick="toggleReveal('adg5')" class="fake-link">**Resolution ...**</span>

<div id="adg5" class="startHidden">
You should have confirmed the exact printer name with the requester. Doing so would confirm that this is a request for access to print to <code>ABC123lj</code>.

You should have evaluated if the requestor is the manager of that printer; which she is NOT.
The request needs to be confirmed with the manager: Gessica E. Blanc (<code>geb00001</code>).

You need Maria’s EUID since there are multiple Maria Martinez’s in the domain; her EUID is <code>mbm29125</code>.

Ensure the user is added to the AD group: <code>CAS-Print-ABC123lj</code>.
This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADG5'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
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