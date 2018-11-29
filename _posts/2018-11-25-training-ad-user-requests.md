---
layout: post
title: AD User Account Requests
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

To assist the WSM, we’re going to learn how to create a few AD objects.
First, confirm you can login using your EUID and the temporary password that you were given.
Then, ensure that you’ve been added to the `UNTDV\CAS-OU-Admins` AD group.
If you’re not, ask the WSM to add you, and you will need to logoff and login again.

To proceed through this section, the learner will need to install RSAT into the *Win10* VM.
The learner should know that, but they may need to be reminded that we don’t work directly on a domain controller (DC).

Each task in this set should be completed in order until the learner has mastery over the topic. Each task is the results of [a form on our website](https://itservices.cas.unt.edu/services/accounts-servers/request/get-account) is submitted; however, **these requests are fictitious and should only be created within the Virtual Lab**.
Additional information can be requested of the customer by whatever means is deemed appropriate by the instructor; I suggest they CC you on all correspondence.
For one reason or another, these requests failed the automated process’s pre-execution test.
You will have to do them all manually, resolving any issues that arise.
Also, describe why the automated processor likely failed.

## Account Request - lc00001

**Emailed Request; via Online Form:**

> The results of this submission may be viewed at:
> https://itservices.cas.unt.edu/node/11111111/submission/111111111
> 
> - Submitted on: Thursday, June 28, 2018 - 10:17am
> - Submitted by user: Visitor
> - Submitted from IP: 129.120.111.1
> 
> Submitted values are: 
> - First Name: ling
> - Last Name: cheng
> - EMPLID: 10000001
> - EUID: lc00001
> - Department: Biological Sciences
> - Employment Classification: Staff
> - Supervisor's EUID: Richard.Nixon@donotreply.unt.edu
> - Additional Information:
> - Contact Phone Number:
> - Contact Email Address: ling.cheng@mailinator.com

<span onClick="toggleReveal('lc00001')" class="fake-link">**Resolution ...**</span>

<div id="lc00001" class="startHidden">
Resolution of this task requires the creation of an AD user account. 
The account can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADU1'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

The automated process failed because the <i>Supervisor's EUID</i> field has an e-mail address and not an EUID.
</div>

## Account Request – sd00001

**Emailed Request; via Online Form:**

> The results of this submission may be viewed at:
> https://itservices.cas.unt.edu/node/11111111/submission/111111112
> 
> - Submitted on: Tuesday, June 26, 2018 - 6:02:35 PM
> - Submitted by user: mw00001
> - Submitted from IP: 129.120.111.2
> 
> Submitted values are:
> 
> - First Name: Sibonakaliso
> - Last Name: Damla
> - EMPLID: 10000002
> - EUID: sd00001
> - Department: Foreign Languages
> - Employment Classification: Staff
> - Supervisor's EUID: 10000011
> - Additional Information: Can you also please change my email address to be just Sam.Damla?
> - Contact Phone Number:
> - Contact Email Address: Sibonakaliso.Damla@ mailinator.com

<span onClick="toggleReveal('sd00001')" class="fake-link">**Resolution ...**</span>

<div id="sd00001" class="startHidden">
Resolution of this task requires the creation of an AD user account. 
The account can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADU2'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

The automated process failed because the Supervisor’s EUID field has an EMPLID and not an EUID.
Also, the space in the Contact Email Address could cause issues if not properly managed by automation.
</div>

## Account Request - wm00001

**Emailed Request; via Online Form:**

> The results of this submission may be viewed at:
> https://itservices.cas.unt.edu/node/11111111/submission/111111113
> 
> - Submitted on: Thursday, June 28, 2018 - 11:30:11 AM
> - Submitted by user: Visitor
> - Submitted from IP: 129.120.111.3
> 
> Submitted values are:
> 
> - First Name: Wybert
> - Last Name: Manoj
> - EMPLID: 10000003
> - EUID: wm000001
> - Department: Journalism 
> - Employment Classification: Faculty
> - Supervisor's EUID: sv00011
> - Additional Information: My computer keeps turning on with a blue screen and I cannot do anything with it. Please help!
> - Contact Phone Number:
> - Contact Email Address: wybert.manoj@mailinator.com

<span onClick="toggleReveal('wm00001')" class="fake-link">**Resolution ...**</span>

<div id="wm00001" class="startHidden">
Resolution of this task requires the creation of an AD user account. The account can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADU3'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

The automated process failed because the EUID field has too many digits.
</div>

## Account Request – nm00001

**Emailed Request; via Online Form:**

> The results of this submission may be viewed at:
> https://itservices.cas.unt.edu/node/11111111/submission/111111114
> 
> - Submitted on: Tuesday, June 26, 2018 - 11:22:34 PM
> - Submitted by user: Visitor
> - Submitted from IP: 129.120.111.4
> 
> Submitted values are:
> 
> - First Name: nikhil
> - Last Name: mikhailo
> - EMPLID: 1000-0004
> - EUID: nm00001
> - Department: Mathematics
> - Employment Classification: Staff
> - Supervisor's EUID: dp00011
> - Additional Information:
> - Contact Phone Number:
> - Contact Email Address: Nikhil.mikhailo@mailinator.com

<span onClick="toggleReveal('nm00001')" class="fake-link">**Resolution ...**</span>

<div id="nm00001" class="startHidden">
Resolution of this task requires the creation of an AD user account. The account can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADU4'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

The automated process failed because the EMPLID field has a dash in it; it should be just numbers.
</div>

## Account Request – pd00001

**Emailed Request; via Online Form:**

> The results of this submission may be viewed at:
> https://itservices.cas.unt.edu/node/11111111/submission/111111115
> 
> - Submitted on: Thursday, June 28, 2018 - 11:51:53 AM
> - Submitted by user: Visitor
> - Submitted from IP: 129.120.111.5
> 
> Submitted values are:
> 
> - First Name: Pauline
> - Last Name: Duygu
> - EMPLID: 10000005
> - EUID: pd00001
> - Department: Environmental Sciences
> - Employment Classification: Faculty
> - Supervisor's EUID: Secundinus.Ligeia@donotreply.unt.edu
> - Additional Information: How do I connect to WiFi?
> - Contact Phone Number:
> - Contact Email Address: Pauline.Duygu@mailinator,com

<span onClick="toggleReveal('pd00001')" class="fake-link">**Resolution ...**</span>

<div id="pd00001" class="startHidden">
Resolution of this task requires the creation of an AD user account. The account can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'ADU5'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>

The automated process failed because the Contact Email Address field has a comma in the domain name portion making it an invalid email address.
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