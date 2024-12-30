---
subject: 
term: ""
week: 
Topic:
---
Tags:
Links:
Created: 2024-12-30

---
# Design

---

> [!abstract] Securing System
> __Hardening__ is the practice of making a system or application more secure from its default installation.
> 
>> [!info] Unnecessary Applications
>> __How to find and uninstall programs you don't use__
>> - Regular uninstall
>> - Uninstall new or preinstalled Windows apps
>> - Uninstall apps you rarely use
>> - Avoid installing unrecognized apps or apps from unknown authors.
>> - Uninstalling apps from root folders and Program files folder
>> - Windows Defender detects applications and associated tag files as a potentially unwanted program.
>
>> [!info] Restricting Applications
>> You can control what software can be installed on a system and what software can run on a system to avoid malicious threats.
>
>
>> [!info] Unnecessary Services
>> The __more services__ that are running on your computer, the __more opportunities there are for others to use them__, break into or take control of your computer through them.
>
>
>> [!info] Trusted Operating System
>>  Trusted operating systems are __enhanced versions of everyday operating systems__ such as `Windows NT` or `Unix` that are made more secure.
>>> [!abstract]
>>>  - It was actually developed in the ___early 1980’s___ and received evaluation from the __National Security Agency in `1984`__.  
>>>  - A trusted operating system generally involves four components.  
>>> 	- They are __information compartmentalization__, __role compartmentalization__, __least privilege__ and __kernel level enforcement__.
>>>> [!example] Four components
>>>> - __Information compartmentalization__ restricts what information an application has access to.  
>>>> 	- If one application on the system is broken into, this prevents access to another unrelated application.  
>>>> 		- For instance, if the web server component is compromised, the attacker won’t be able to get at the database component.
>>>> - __Role compartmentalization__ restricts the control a user has.  
>>>> 	- There is no such thing as root access on a trusted operating system.  
>>>> 		- Even adding users and other routine administrative tasks requires the use of more than one account.  
>>>> 			- This would prevent an attacker from getting full control of the system.
>>>> - __Least privilege__ restricts what processes are able to perform. 
>>>> 	- Processes should only have enough rights to perform their duty.  
>>>> 		- For example, a web server process should not be able to modify an e-mail file or any other system files, just the web files that it uses.
>>>> - __Kernel level__ enforcement ensures that security decisions are made at a low level where users or applications cannot interfere with them.  
>>>> 	- This also reduces system overhead because the security decisions are close to the resources being protected.
>>
>> Basically a trusted operating system is about __separating elements from each other__ and __making access between areas more difficult__.  
>> It’s like having a firewall and access list to each application and process.
>
>
>> [!info] Updates and Patches
>> Patches are software and operating system (OS) updates that address security vulnerabilities within a program or product. Software vendors may choose to release updates to fix performance bugs, as well as to provide enhanced security features.
>> 
>> Users can install updates manually or elect for their software programs to update automatically. Manual updates require the user or administrator to visit the vendor’s website to download and install software files. Automatic updates require user or administrator consent when installing or configuring the software. Once you consent to automatic updates, software updates are “pushed” (or installed) to your system automatically.
>
>
>> [!info] Patch Management
>>is a hardening procedure that __ensures that systems and applications stay up to date with current patches__. 
>>This is one of the most efficient ways to reduce operating system and application vulnerabilities, since it protects systems from known vulnerabilities. 
>>Patch management includes a group of methodologies and includes the process of identifying, downloading, testing, deploying, and verifying patches.
>
>
>> [!info] Group Policies
>> `Windows domains` use Group Policy to __manage multiple users and computers in a domain__. 
>> Group Policy allows an administrator to configure a setting once in a Group Policy object (GPO) and apply this setting to many users and computers within the domain. 
>> Group Policy is implemented on a domain controller in a domain, but can also be applied to individual computers.
>
>
>> [!info] File Systems and Hard Drives
>> `Hard disks` and `Filesystems` are the __major sources of data storage__.
>> 
>> People usually delete their tracks after committing a crime with a computer in order to avoid being traced. 
>> That is why recovering the deleted files of hard disks and analyzing filesystems is important when investigating a computer-based crime.
>
>
>> [!info] Hypervisors
>> A hypervisor, also known as a __virtual machine monitor__, is a process that __creates and runs virtual machines (VMs)__. 
>> A hypervisor ___allows one host computer to support multiple guest VMs by virtually sharing its resources___, like memory and processing.
>>> [!example] 2 types of hypervisors
>>> Type 1: "__bare metal__"
>>> - run directly on the host's hardware.
>>> Type 2: "___hosted___"
>>> - run as a software layer on an operating system, like other computer programs.
>
>
>> [!info] Threats to VMs
>> - Virtual machine escape vulnerabilities are the most serious issue that may exist in a virtualized environment, particularly when a virtual host runs systems of differing security levels. 
>> - In an ___escape attack___, the attacker has access to a single virtual host and then manages to leverage that access to intrude on the resources assigned to a different virtual machine.
>>> [!tip] Hypervisor
>>> The __hypervisor__ is supposed to prevent this type of access by restricting a virtual machine’s access to only those resources assigned to that machine. 
>>> ___Escape attacks___ allow a process running on the virtual machine to “escape” those hypervisor restrictions.
>
>
>> [!info] Securing VMs
>> To secure your VMs, keep the guest operating systems patched and protect your environment just as you protect your physical machine.
>> Consider disabling unnecessary functionality, minimize the use of the VM console, and follow other best practices.