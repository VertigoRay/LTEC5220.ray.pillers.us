---
layout: post
title: NS Permission Management
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

Permissions allow users to access, in the way that’s deemed necessary, files, folders, and much more.
Since we’re focused on network shares in this section, we’ll focus on that.
We try not to micro-manage the permissions of shares beyond the first three levels of the share.
Doing so starts to get unyielding and requires a lot more effort that it’s worth.

## Staff Member Needs Access

**Emailed Request:**

> My boss told me to get my colleague up to speed on what we do around here.
> I need her to have the same access as I do.
> What do we need to do?
> 
> Here’s her info: Malena Dex Ricci (mdr00001).
> 
> Thanks,<br />
> Randall A. Royce<br />
> Randall.Royce@donotreply.unt.edu

<span onClick="toggleReveal('nsp1')" class="fake-link">**Resolution ...**</span>

<div id="nsp1" class="startHidden">
You should first evaluate what AD groups Randall is a member of.
Upon doing so, you will discover there are two AD groups.
The requestor is not the manager of either group.
Both managers will need to grant permission.
Here are the groups and managers:

- <code>CASlab-S-ENGL-FacStaff</code>; Manager: Grace Wyatt (<code>gcw00001</code>)
- <code>CASlab-S-TWL-FacStaff</code>; Manager: Gwen Faulkner (<code>gcf00001</code>)

Only permission will be granted for the <code>CASlab-S-TWL-FacStaff</code> AD group.
The customer will be notified and told to take any concerns to the manager.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'NSP1'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

## Student Employee Needs Access

**Emailed Request:**

> Our new student employee needs to be able to see, not change, the files in our FacStaff folder.
> She will also need to be able to add files to our Incoming Faxes folder.
> Here are the specific details
> 
> - Trudy N. Cock (tnc00001)
> - S:\HIST\FacStaff
> - S:\HIST\Incoming Faxes
> 
> Thanks,<br />
> Gisella J. Falconer<br />
> Gisella.Falconer@donotreply.unt.edu

<span onClick="toggleReveal('nsp2')" class="fake-link">**Resolution ...**</span>

<div id="nsp2" class="startHidden">
You should first evaluate what AD groups manage those folders.
It turns out that Gisella is the manager of both AD groups.
Here are the groups:

- <code>CASlab-S-HIST-FacStaff</code>
- <code>CASlab-S-HIST-Incoming_Faxes</code>

You will add <code>tnc00001</code> to both AD groups.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'NSP2'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

## Staff Member No Longer Needs Access

**Emailed Request:**

> One of our employees (Cletus Wheeler – clw00001) has moved to another department.
> Can you please remove his access to the S:\WGS\FacStaff share?
> 
> Thanks,<br />
> Barthélémy Nannie Sessions<br />
> Barthelemy.Sessions@donotreply.unt.edu

<span onClick="toggleReveal('nsp3')" class="fake-link">**Resolution ...**</span>

<div id="nsp3" class="startHidden">
You should determine that Cletus is managed by Barthélémy.
After finding that he is, he should remove him from the AD group: <code>CASlab-S-WGS-FacStaff</code>.
Cletus is also a member of the following AD groups.
You should ask the customer about these as well:

- <code>CASlab-S-WGS-Academia</code>
- <code>CASlab-S-HIST-Incoming_Faxes</code>
- 
Cletus is moving to History, so he will need to be removed from the AD group: <code>CASlab-S-WGS-Academia</code>.
Cletus’ AD account should also be moved to the HIST OU.
You might also consider contacting the History department to proactively get Cletus put into the appropriate AD groups.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'NSP3'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

## New Department Needs All Things

**Emailed Request:**

> We have a new department getting formed: Non-Technical Writing Lab (NTWL)
> 
> Please make all of the things that all of our departments have:
>
> - OU
> - Faculty and Staff separate AD Groups
> - Space on the shared drive with a subfolder for FacStaffFacStaff
> 
> Anything else you think I’m missing…
> 
> Signed,<br />
> Timothy J Christianson<br />
> Timothy.Christianson@donotreply.unt.edu<br />
> Your Boss

<span onClick="toggleReveal('nsp4')" class="fake-link">**Resolution ...**</span>

<div id="nsp4" class="startHidden">
This is from your boss; as shown in the signature.
Do all of the things that were stated:

- Create an <code>NTWL</code> OU under <code>CAS Support</code>.
- Create the following AD Groups:
  - <code>CASlab-NTWL-Faculty</code>
  - <code>CASlab-NTWL-Staff</code>
  - <code>CASlab-S-NTWL-FacStaff</code>
- Additionally, discovery should show that all departments have a student employees AD group. So, the learner should also create the following AD group:
  - <code>CASlab-NTWL-StudentEmployees</code>

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'NSP4'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
</pre>
</div>

## Unable to Access Network Location

**Emailed Request:**

> I’m unable to access a location that I need.
> I think I used to be able to access it.
> Can you help?
> 
> S:\PSCI\Committees
> 
> Signed,<br />
> Jarvis P. Piper<br />
> Jarvis.Piper@donotreply.unt.edu

<span onClick="toggleReveal('nsp5')" class="fake-link">**Resolution ...**</span>

<div id="nsp5" class="startHidden">
The user is not a member of the <code>CAS-S-PSCI-Committees</code> AD group, but he is a member of the AD group that is listed as the manager.
You should add <code>jpp00001</code> to the <code>CAS-S-PSCI-Committees</code> AD group.

This can be evaluated automatically with this PowerShell script:

<pre class="highlight">
$section = 'NSP5'; iwr 'https://pastebin.com/raw/tQ95Q7Xh' -UseB | iex
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