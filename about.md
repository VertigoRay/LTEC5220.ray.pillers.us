---
layout: post
title: About This Training
author: Raymond Piller
comments: false
---
The training is designed to be asynchronous to mimic the way requests come into our office. When we get a request, there’s no a lecturer at the front of the office telling us how to address that request. If the request is for software we’ve never heard of before, we start by searching for that software on the internet and seeing if it’s well-documented. We then assert what the software is truly used for, and we assess what the customer is trying to accomplish. We then correlate the request to the software or other software we already support, and we present an alternative solution if it’s available. This requires searching our internal documentation and communicating with our colleagues to determine if we already support something that provides an identical or comparable service/solution. 

This course will be no different. The learner will assume the role of SME (the WSM) and will figure it out. Searching the internet, documentation, existing requests, and communicating with the customer and colleagues are all expected parts of this training.

This lesson will be designed as a one-week training session to allow colleagues and new employees familiarity with the roles and responsibilities of the WSM from a technological perspective. It will be an online asynchronous course that will discuss various problems encountered in the field, as well as explore effective methodologies to implement solutions to issues that arise for the WSM. There will be a final formative and summative assessment at the end of the term.

## Problem

When the WSM wants to take time off from work, most of his responsibilities wait for him to return. This fact remains in the back of his head for the duration of his vacation, and he cannot truly enjoy the time-off knowing he will face a heavy load when he returns to the office. More importantly, it is not okay for us to tell our customers that they must wait for him to return to get a seemingly simple request fulfilled.

There is no existing official training regimen established as part of onboarding or cross-training. We are expected to cover one another using past knowledge and experience to resolve issues and fulfill requests. Any knowledge currently received is “learn as you go.” The creation of this program will allow employees without any previous experience with Windows servers to temporarily field requests and resolve issues while the WSM is engaged elsewhere.

## Learning Expectations

### Lesson Goals and Objectives
1. **TLW will become proficient with basic management of VMware VMs.** This is the core of the work done by the WSM.
   1. **TLW be able to login to and navigate VCenter’s web interface from their lab computer over a period of a week 90% of the time that they attempt to do so.** After logging in, the learner should be able to easily find where the VMs are.
   2. **TLW create and delete VM Snapshot via VCenter’s web interface from their lab computer over a period of a week 90% of the time that they attempt to do so.** Creating a VM snapshot is crucial for testing a configuration and being able to easily and instantly revert those changes if something goes wrong. We create snapshots before touching a production server for any reason. Unfortunately, too many snapshots can also cause IOPs issues. As such, we must ensure we delete snapshots that are no longer needed.
   3. **TLW expand a VM’s storage via VCenter’s web interface from their lab computer over a period of a week 70% of the time that they attempt to do so.** To keep our systems running lean, we configure the servers with a minimum amount of local storage. When allocating storage to a server, we prefer fixed disk size, as opposed to dynamic. The performance hit for a dynamic disk is minimal when you’re running only a few servers. However, when there are have thousands of servers all running dynamic disks, the IOPS performance hit adds up. Occasionally, the size of the disk exceeds what we originally planned and needs to be expanded. This is usually a service outage event and not a change that can wait a week for the WMS to return for vacation.
2. **TLW become proficient with basic management of network printers.** The WSM manages the Windows Print Server (WPS) which allows centralized control of network accessible printers. We often get a need to set up new printers as our fleet is expanded by departmental growth. Sometimes, those printers are replacing older printers, but are a different brand and need different drivers associated with it; transferring the name of the replaced printer to the new printer.
   4. **TLW create a static IP address entry in the DHCP server for the printer from their lab computer over a period of a week 70% of the time that they attempt to do so.** Unlike most devices on the network, printers require a static IP address. This needs a specific configuration in our DHCP server. This process has been automated, but familiarity with this step is a must.
   5. **TLW add a network printer to the Windows print server from their lab computer over a period of a week 70% of the time that they attempt to do so.** In order for the WPS to control the new printer, it must have several things configured on the server: IP, port, driver, and the printer object. After that, it can be shared with computers that we manage, and the computers print to the server and the server hands the job off to the printer.
   6. **TLW audit and manage security, locking the printer down, on the Windows print server from their lab computer over a period of a week 70% of the time that they attempt to do so.** The printers themselves are typically wide open, and they need to be locked down. Locked down includes allowing the printer to only communicate on the network to the WPS and change the remote administrative password(s).
   7. **TLW audit and manage print codes on the Windows print server from their lab computer over a period of a week 70% of the time that they attempt to do so.** Some printers support the use of a print code that’s required for printing. This is an enterprise feature and allows print jobs to be associated to a print code, that’s assigned to a specific person. This is typically for accounting purposes and required by some departments for some printers.
   8. **TLW enable scan to email/network-share on the Windows print server from their lab computer over a period of a week 70% of the time that they attempt to do so.** Multi-Function Printers (MFPs) are capable of doing more than just printing; such as scanning, binding, stapling, and more. Since it’s a network printer, we typically need to configure an end-point for the scanned documents. This may be one or more email addresses or a network storage location that acts as a drop box. Either way, the options are typically controlled by the WPS and need to be configured by the WSM.
   9. **TLW evaluate printing functionality from Windows and OS X over a period of a week 70% of the time that they attempt to do so.** Now that everything is configured, test the work that you did. Simple print a test page from the two main desktop operating systems that we support: Windows 10 and OS X.
3. **TLW become proficient with creation and management of Active Directory (AD) Accounts and Groups.** CAS supports the largest number of faculty and staff in the UNT System (UNTS). As such, we get a new account and access permission requests daily. In today’s technological age, we must resolve these request within the working day, if not within the hour that they were requested. Not having access to work systems is a typically critical error for any of our faculty and staff.
   10. **TLW create a new AD accounts from their lab computer over a period of a week 70% of the time that they attempt to do so.** If we have a new faculty or staff member, we usually have their accounts create long before they get to campus. This is through years of process optimization and automation as we get notifications telling us about new hires. Occasionally, all the pieces to the puzzle don’t fall into place and manual intervention is required. In this event, the WSM needs to intimately familiar with the account creation script and how to troubleshoot it.
   11. **TLW assess access/permission issues from their lab computer over a period of a week 70% of the time that they attempt to do so.** Almost daily, we get a call or an email telling us that someone can’t access something. Our job isn’t to just grant those rights as they come in. Our job is to determine if the requestor is the has the authority to make the request and if not ensure the request is routed to the proper authority. After that, granting access is typically as easy as adding a user to a new AD group. If not, we need to ensure that it’s configured that way to uphold the standards that should have already been in place.
   12. **TLW create new AD groups from their lab computer over a period of a week 70% of the time that they attempt to do so.** Occasionally, requests come in for granting more specific permissions to a subset of customers to a more specific task, server, or service. These permission changes need to be granted using the standards that have been implemented for the relevant task, server, or service. Familiarity with where these standards are documented and how to apply these standards are required.
4. **TLW become proficient with creation and management of network shares.** Networks storage locations are a centralized and backed up file storage spaced. These locations are often used for shared documents and data repositories. Additionally, there are private locations available to every user that offers a limited amount of backed up storage.
   13. **TLW create and change storage quotas from their lab computer over a period of a week 70% of the time that they attempt to do so.** Quotas are designed to prevent users from filling up network storage by implementing a maximum usage size. This quota is often exceeded and if the user calls to request more storage, we audit usage and grant additional storage if usage seems justifiable. This political barrier just helps us ensure we’re not storing and backing up a customer’s entire music collection.
   14. **TLW audit and manage permissions from their lab computer over a period of a week 70% of the time that they attempt to do so.** Typically, users need proper permissions to either just see files in a location or make changes to those files. It’s important to grant permissions with the principle of least privilege in mind. As an educational institution, we fall under FERPA regulations, and must also be familiar with the types of data that is intended on being accessed.
5. **TLW become proficient at time management and will display proper communication techniques when working with customers.**
   15. **TLW be able to find, review, and resolve issues in a timely manner from their lab computer over a period of a week 80% of the time that they attempt to do so.** Just like work expectations, all tasks must be resolved in a timely fashion. Some tasks will be more complex, requiring more time. These tasks will have additional time afforded to the solution.
   16. **TLW will be able to communicate technical information and concepts in a clear, non-technical manner via e-mail or chat over a period of a week 80% of the time that they attempt to do so.** Just like with a real request, the solution must be communicated to the customer in a clear and concise manner; without the use of unnecessary technical jargon.

### Lesson Components

#### Learners

- Performance computer system access.
  - The learner will need to run a virtual lab on their computer. The lab will be configured with Vagrant.
    - Multiple VMs (at least two) acting as VMware ESX Hypervisors
    - 60-Day VSphere/VCenter will be installed for lab
- Network/internet access.
  - Searching the internet (aka googling) for assistance is encouraged, but the learner should start with internal documentation.
- Proficient knowledge of:
  - AD objects. These acronyms should be second nature: DN, FQDN, GPO, GPP, DC, etc.
  - Network design and communication protocols. These acronyms should be second nature: DNS, DHCP, TCP, UDP, IPSEC, TCP/IP, VLAN, MAC, etc.
- Familiarity with:
  - OTRS Ticketing System
  - VMware Web Management Console
  - Principle of Least Privilege
  - Coding: PowerShell, VBScript, and AutoIt
  - Vagrant and basic usage
  - GitHub.com and downloading repositories
- Troubleshoot their own computer issues.

#### Instructors

In addition to the expectations of the learners, the instructors are expected to have the following qualifications:

- Expert knowledge of:
  - VMware VM configuration.
  - Windows Servers.
  - Active Directory.
  - Group Policy Objects and Group Policy Preferences.
  - Printer Management.
  - Network Share Management.
- Proficient knowledge of:
  - PowerShell, PowerShell Best Practices, and PowerShell Coding Standards.

## Learning Activities

Each task will have a basic request that will require the learner to communicate with the customer to get clarification.
Proper communication skills must always be exhibited.

Each task has a scriptable solution equivalent.
At least 50% of all work done must be done using PowerShell.
The learner will earn a free custom pizza, courtesy of the instructor, if 100% of all work is done using PowerShell.

Learner will submit screen recording to the instructor for each task completed.
The screen must be recorded from the time the learner reads the request until the time moment before linking the recording into the email submitted to the instructor.
All internet searches should be done within view of the screen recorder.
The learner will submit a compressed archive (such as ZIP or 7zip) of any code written to complete the task.
The training environment will be saved in its state and review of the completed task will be done before the learner is allowed to proceed to the next task.

- TLW use the Vagrantfiles to create their learning and testing environment. (1.1.1)
  - Download and install Vagrant.
  - Download and execute the Vagrantfiles for this course.
  - Download and install a Screen Recorder for use when working on a task.
- TLW be given a new infrastructure (Windows Server) request to look over. (1)
  - Clarification questions can be asked of the customer (the instructor) via e-mail.
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (1, 6)
- TLW be given a new printer request to look over. (2)
  - Clarification questions can be asked of the customer (the instructor) via e-mail.
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (2, 6)
- TLW be given a new AD Learner account and group request to look over. (3)
  - Clarification questions can be asked of the customer (the instructor) via e-mail.
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (3, 6)
- TLW be given a new network share request to look over. (4)
  - Clarification questions can be asked of the customer (the instructor) via e-mail.
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (4, 6)
- TLW be given several real examples of simple and complex requests that dive deeper into the skills learned throughout this training. (4, 6)
  - Clarification questions can be asked of the customer (the instructor) via e-mail.
  - Will resolve (if applicable) the request/issue and communicate technical information back to the customer in a clear, non-technical manner.

## Assessment

- Assessment 1.1: Instructor confirms, via the turned in screen recordings, the learner can navigate VCenter’s web interface.
- Assessment 1.2: Instructor confirms, via the turned in screen recordings, proper usage of VMware’s snapshots before every time the learner begins working on a server.
- Assessment 1.3: Instructor confirms, via the turned in screen recordings, the learner properly expanding storage, upon request.
- Assessment 2.1: Instructor confirms, via the turned in screen recordings and the automation logs, the learner properly submitted a static IP address of the new printer.
- Assessment 2.2: Instructor confirms, via the turned in screen recordings and lab environment, the learner properly creates a network printer on the Windows print server.
- Assessment 2.3: Instructor confirms, via the turned in screen recordings and penetration testing against the printer, the learner could secure the printer. 
- Assessment 2.4: Instructor confirms, via the turned in screen recordings and confirmation on the printer, the learner could manage print codes on the printer.
- Assessment 2.5: Instructor confirms, via the turned in screen recordings and lab environment, that scan to email/network-share function as intended.
- Assessment 2.6: Instructor confirms, via the turned in screen recordings and lab environment, that printers can be printed to through the Windows print server. 
- Assessment 3.1: Instructor confirms, via the turned in screen recordings and lab environment, the learner created AD accounts.
- Assessment 3.2: Instructor confirms, via the turned in screen recordings and lab environment, the learner properly resolved permissions without causing security issues.
- Assessment 3.3: Instructor confirms, via the turned in screen recordings and lab environment, the learner created AD groups.
- Assessment 4.1: Instructor confirms, via the turned in screen recordings and lab environment, was able to create storage quotas, change storage quotas, and that the quotas function as expected.
- Assessment 4.2: Instructor confirms, via the turned in screen recordings and lab environment, the learner could audit permissions of networks storage and ensure permissions are correct.
- Assessment 5.1: Instructor confirms, via the turned in screen recordings and lab environment, the learner could evaluate and resolve issues in an thorough and efficient manner.
- Assessment 5.2: Instructor confirms, via the turned in screen recordings and emailed consultations, the learner could communicate effectively with non-technical users.

The learner will have the opportunity to e-mail back and forth with the customer (instructor) to clarify anything; ensuring a firm understanding of the requirements.
The instructor will review the screen recordings made by the learner for each task to see how the task was completed and ensuring the task was fully completed.
During the tasks, the internet is available for assistance.
All searching should be done within view of the screen recorder; we want to understand how the solution was obtained as well as if the solution is correct.

Since this training is for seasoned veterans to become proficient in the common tasks of their colleagues, we have high standards.
If a request comes in while the WSM is out of the office, it must be completed to standard without having to be revisited by the WSM.
Due to our high expectations, learners in this training are expected to complete 100% of the tasks successfully.
We will use the TOTE (test, operate, test, exit) method to ensure that our expectations are being met.
We will have at least five versions of each task.
If we run out of versions of a task, we will be forced to abandon the task for that learner.
If we get to the point where we abandon the TOTE method, remedial training will be recommended for the learner.

## Evaluation

- TLW navigate VMware VMs with ease.
- TLW be able to manage printers on the Windows print server.
- TLW be proficient in managing AD objects.
- TLW be proficient in managing network shares, their permissions, and their quotas.
- TLW be able to repeat tasks on demand without notes.
- TLW be able to communicate naturally with customers about technical matters.
- 
If most learners can complete the assigned tasks, then I know my instructional design was successful.
If there is a task that cannot be completed, then I know will have an area for improvement.
The SME will determine if the tasks are done to completion, but the Team Manager will be the final judge on whether the learner is fully cross-trained.

My assessment directly relates to my evaluation.
All the tasks require a specific solution.
If that solution works without security vulnerabilities, then the task was successful.
If the task works, but with security vulnerabilities, we need to address that with the learners.
All learners are seasoned I.T.
Administrators, so they should be able to think about the security implications of their decisions without being walked through the thought process in this training.

The training is task-based and the goals/objectives can be measured by the completeness of tasks.
The learners will have completed the task successfully if the outcome of all tasks are satisfactory and result in the proper and secure implementation of the requested service.
If a completed evaluation is not considered satisfactory, remedial training will be suggested for the learner.

## Timeline

The training will be asynchronous, but it is expected to take no longer than a week.
The average amount of time should be 15 hours; three hours per day.
After the first day, a basic understanding of all goals is expected.
The second day will start with a one-hour session with the instructor; the instructor is also the SME.
This will confirm a firm understanding of all training goals.
After day two’s introduction, the rest of the training will occur asynchronously; at the learner’s pace.

- TLW use the Vagrantfiles to create their learning and testing environment. (1.1.1) (30 minutes; Task is automated and might take several hours to complete.)
- TLW be given a new infrastructure (Windows Server) request to look over. (1) (30 minutes)
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (1, 6) (2 hours)
- TLW be given a new printer request to look over. (2) (30 minutes)
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (2, 6) (1 hour)
- TLW be given a new AD account and group request to look over. (3) (30 minutes)
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (3, 6) (1 hours)
- TLW be given a new network share request to look over. (4) (30 minutes)
- TLW fulfill the request and provide customer with usage information in a formal e-mail. (4, 6) (2 hours)
- TLW be given several real examples of simple and complex requests that dive deeper into the skills learned throughout this training. (4, 6) (3 hours)
