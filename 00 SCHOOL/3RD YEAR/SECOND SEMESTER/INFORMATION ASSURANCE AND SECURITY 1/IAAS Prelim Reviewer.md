---
subject: IAAS
term: prelim
week: "1"
Topic:
---
Tags:
Links:
Created: 2024-12-30
User: John Rogee Turqueza

---
# Information Security

---

## Week 1

>[!note] Overview of Security
> __Network security__ is a broad term that covers a multitude of technologies and processes.
> - A set of rules and configurations designed to protect the integrity, confidentiality and accessibility of computer networks and data using both software and hardware technologies.
> - Every organization requires a degree of network security solutions in place to protect it from the ever-growing landscape of cyber threats in the wild today.
> - The complexity of today's network architecture, coupled with a constantly evolving threat landscape and potential vulnerabilities in various areas such as devices, data, applications, users, and locations, necessitates the use of numerous network security management tools and applications to address specific threats, exploits, and regulatory non-compliance, crucial for preventing widespread disruption and significant damage to an organization's bottom line and reputation in the face of potential downtime.
> 
>> [!info] ##### CIA Triad
>> C.I.A. - __Confidentiality__, ___Integrity___ and _Availability_ 
>> A security model that has been developed to help people think about various parts of IT security.
>
>> [!info] ##### AAA of Security
>> _Authentication_, ___Authorization___, and __Accounting__ (AAA) is a method you can use in your network to control which administrators are allowed to connect to which devices (_Authentication_), what they can do on these devices (___Authorization___), and log what they actually did while they were logged in (__Accounting__).
>>
>>> [!abstract] Explanation of each process included in AAA:
>>> - __Authentication__ - process by which ___users prove that they are who they claim to be___, typically by having the user enter a valid `username` and `valid password` before access is granted.
>>>> [!example]
>>>> Authenticating an administrator's access to a router console port.
>>>> You can authenticate the administrator against the local router database or a remote RADIUS or TACACS+ server.
>>> - __Authorization__ - after the user has been authenticated, the authorization is used to ___determine which resources the user is allowed to access, and which operations he can perform___
>>>> [!example]
>>>> You can control what the user is allowed to modify or delete.
>>>
>>> - __Accounting__ - the process of recording (`logging`) the actions the user took while accessing the network resources.
>>> 	- This can include the amount of data a user has sent and received during a session, the amount of time spent in the network, the services accessed, etc.
>>> 	- Accounting is carried out by logging the session statistics and usage information and is used for trend analysis, capacity planning, billing auditing and cost allocation.
>>>>[!tip] The following options can be used to implement AAA on Cisco devices:
>>>> - __Cisco Secure ACS Solution Engine__ - a dedicated server that contains the usernames, passwords, and other information about what users are allowed to access and when.
>>>> - __Cisco Secure ACS for Windows Server__ - a software package installed on a Windows system that provide AAA services.
>>>> - __Cisco Secure ACS in a virtual machine__
>>>> - __Local database__ - aka local authentication and authorization, this option uses the local router database for AAA purposes.
>
>
>> [!info] ##### Security Threats
>> Defined as __a risk that which can potentially harm computer systems and organization__. The cause could be ___physical___ such as someone stealing a computer that contains vital data The cause could also be _non-physical_ such as a virus attack.
>>> [!example] Physical threat
>>> A potential cause of an incident that may result in loss or physical damage to the computer systems
>>>  - __Internal__ - Fire, unstable power supply, humidity in the rooms housing the hardware, etc.
>>>  - __External__ - Lightning, floods, earthquakes, etc.
>>>  - __Human__ - Theft, Vandalism of the infrastructure and/or hardware, disruption, accidental or intentional errors.
>>
>>>[!example] Non-Physical Threats
>>>also known as __Logical threats__
>>> a potential cause of an incident that may result in:
>>> - Loss or corruption of system data
>>> - Disrupt business operations that rely on computer systems
>>> - Loss of sensitive information
>>> - Illegal monitoring of activities on computer systems
>>> - Cyber Security Breaches
>>>>[!tip]- Others
>>>> - Virus
>>>> - Trojans
>>>> - Worms
>>>>- Spyware
>>>> - Keyloggers
>>>> - Adware
>>>> - Denial of Service Attacks
>>>> - Distributed Denial of Service Attacks
>>>> - Unauthorized access to computer systems 
>>>> - Phishing
>>>> - Other Computer Security Risks
>
>>[!info] ##### Hackers
>> Computer predators create computer threats to victimize other for their own gain.
>> __Hackers__ are unauthorized users who break into computer systems in order to `steal`, `change` or `destroy information`, often  ___by installing dangerous malware___ without your knowledge or consent.
>>> [!tip]- Hackers may be able to:
>>> - Hijack your usernames and passwords
>>> - Steal your money and open credit card and bank accounts in your name
>>> - Ruin your credit
>>> - Request new account Personal Identification Numbers (PINs) or additional credit cards
>>> - Make purchases
>>> - Add themselves or an alias that they control as an authorized user so it's easier to use your credit
>>> - Obtain cash advances
>>> - Use and abuse your Social Security Number
>>> - Sell your information to other parties who will use it for illicit or illegal purposes
>>
>>>[!abstract] Types of Hackers:
>>> - __Ethical Hacker (White Hat)__: A hacker who gains access to systems with __a view to fix__ the ___identified weaknesses___.
>>> 	- They may also perform penetration Testing and vulnerability assesments
>>> - __Cracker (Black Hat)__: A hacker who gains __unauthorized access__ to computer systems for ___personal gain___.
>>> 	- The intent usually to steal corporate data, violate privacy rights, transfer funds from bank accounts etc.
>>> - __Grey Hat__: A hacker who is in __between `ethical` and `black hat` hackers__. 
>>> 	- They break into computer systems without authority with a view to __identify weaknesses__ and ___reveal them to the system owner___.
>>> - __Script kiddies__: A non-skilled person who gains access to computer systems using already made tools.
>>> - __Hacktivist__:  A hacker who use hacking to send `social`, `religious` and `political`, etc. messages.
>>> 	- Usually __done by hijacking websites__ and leaving the message on the hijacked website.
>>> - __Phreaker__: A hacker who identifies and exploits weaknesses in telephones instead of computers.
>
>>[!info] ##### Threat Actors
>> A person or entity that has the ability or intent to impact the security of other individuals or companies
>> - Can be `internal` or `external` to the organization being targeted, and they may or may not posses the technical skillsets needed to infiltrate and compromise networks and corporate data.
>>> [!tip] Four types of Threat Actors
>>>  - __Cyber Criminals__ - Hackers and attackers that use techniques like ___phishing___ and ___ransomware___ when targeting individuals and corporations, typically in attempts to generate money from their cybercriminal activities.
>>>  - __Hacktivists__ - Typically motivated by ___political___ or ___social___ causes more than monetary gains in committing acts of "`hactivism" .
>>> 	 - More likely to take down websites and networks via __DDoS__ and similar attacks or commit other acts of ___cyber vandalism___ as opposed to extorting businesses or individuals for money.
>>>  - __State-Sponsored Attackers__ - Well-funded and well-organized cyber espionage entities that commit their activities with the backing of governments or similar large entities.
>>> 	 - Typically focus on __infiltrating larger organizations__ with the intent to steal massive amounts of mission-critical and other sensitive data.
>>>  - __Insider Threats__ - Intentionally or Unintentionally __provide sensitive corporate data to others__, either by mistake, by not following security policies and best practices, by being duped or deceived by a cybercriminal, or by criminally obtaining and sharing information with cyber criminals for money or revenge.
>>
>
>> [!info] ##### Malware
>> Been around __1970s__ when __Creeper virus__ first appeared.
>>>[!abstract] Types of Malware:
>>>> [!tip] Viruses
>>>> __Modifies__ other legitimate host files (or pointers to them) in such a way that __when a victim's file is executed__, ___the virus is also executed___.
>>>
>>>>[!tip] Worms
>>>> - Been around __longer than computer viruses__
>>>> - One person would open a __wormed email__ and the entire company would be infected in short order
>>>
>>>
>>>>[!tip] Trojans
>>>> - Replaced computer worms as the weapon of choice for hackers
>>>> - Masquerades legitimate programs but contains malicious instructions.
>>>
>>>
>>>>[!tip] Ransomware
>>>> - Encrypts data and hold as __hostage__ waiting for a cryptocurrency ___pay off___
>>>
>>>
>>>>[!tip] Spyware
>>>> - Most often used by people who want to check on the computer activities of loved ones.
>>>> 	- Criminals can use spyware to `log keystrokes` (__Keylogging__) of victims and gain access to ___passwords___ or ___intellectual property___.
>>>> - Easiest to remove
>>>> 	- Find the `malicious executable` and prevent it from being executed.
>>>
>>>
>>>>[!tip] Rootkits
>>>> - Designed to provide continued privileged access to a computer while ___actively hiding its presence___. 
>>>> - Collection of tools that enabled administrator-level access to a computer or network.
>>>> - Connection of two words: "__root__" and "__kit__"
>>>> 	- __root__: refers to Admin account on Unix and Linux systems
>>>> 	- __kit__: refers to the software components that implement the tool.
>>>> - Generally associated with __malware__ that conceal their existence and actions from users and other system processes.
>>>
>>>
>>>>[!tip] Spam
>>>> - Cyber-criminal sends messages intended to profit on fake or phony products.
>>>> 	- Much of it sent by botnets
>>>> 	- networks of virus-infected computers
>>>> 	Complicating the process of tracking down the spammers.
>>>> 	
>>>
>>>>[!tip] Phishing
>>>> - A method of trying to gather personal information using deceptive e-mails and websites
>>>> - Files sent with malicious embedded code.
>
>>[!info] Botnets and Zombies
>> Ro__bots__ are scripts or software apps that performs automated tasks on command.
>> - __Bad bots__ performs malicious tasks which allows attackers to take control over the infected computer.
>> - Infected machines are called ___Zombies___
>>> [!tip] Botnets
>>> - Most spam people receive is __also from other ordinary people's computers__, which have been infected but still functioning properly, except it might slow down the computer sometimes.
>>> - Botnets has extremely small footprint, and typically have the ability to mask themselves making it difficult to recognize and being able to perform large attacks without getting noticed.
>>> - They compromise open-source and unsecured devices
>
>
>>[!info] ##### Active Interception and Privilege
>> Attackers use IMSI-catcher, a part of Active GSM interception system to __interfere communications between mobile phones and base stations__.
>
>
>>[!info] ##### Backdoors and Logic bombs
>> - __Backdoor__ - when a programmer provides as a means to grant themselves or others future access to a system.
>> - __Logic Bomb__ - an attribute or a portion of code running within a program that remains inactive until a specific event or time occurs.
>
>
>> [!tip] ##### Preventing Malware
>> __Practice safe browsing__
>> 	- Use strong passwords and/or password managers
>> 	- Make sure you're on a secure connection
>> 	- Log out of websites after you're done
>> __Layer your security__
>> 	-Use firewall, anti-malware, anti-ransomware, and anti-exploit technology
>> __Protect vulnerabilities__
>> 	-Update your operating system, browsers, and plugins
>> 	- Enable click-to-play plugins
>> 	- Remove software you don't use (especially legacy programs)
>> __Watch out for social engineering__
>> 	-Read emails with an eagle eye
>> 	- Do not call fake tech support numbers
>> 	- Do not believe the cold callers




## Week 2


>[!abstract]  Security Applications and Devices
> __Application Security__ -  involves finding, fixing, and enhancing the security of apps, with a significant focus during the development phase. Even after deployment, applications continue to utilize tools and methods to ensure ongoing protection of their security.
> 
>> [!info]  Software Firewalls
>> - First line of defense in a network.
>> - Either stand-alone systems or included in routers or servers.
>>>[!example]
>>> - Cisco Adaptive Security Appliance (ASA)
>>> - FortiNet FortiGate
>>> - Cisco Meraki MX Firewalls
>>> - Palo Alto
>>> - pfSense
>
>
>>[!info]  IDS (Intrusion Detection System)
>> - Software that runs on either individual workstations or network devices to monitor and track network activity.
>> 
>> - Using __IDS__, a network administrator can configure the system to respond just like a burglar alarm.
>> - __IDS systems__ can be configured to:
>> 	- Evaluate systems logs
>> 	- Monitor suspicious network activity
>> 	- Disconnect sessions that appear to violate security settings
>>> [!tip] IDS with Firewall
>>> ___Firewalls___ themselves can prevent common attacks, but don't have the intelligence to report and monitor the entire network.
>>>  With __IDS__, allows both a reactive posture with the ___firewall___ and  preventative posture with the __IDS__
>
>
>> [!INFO] Pop-up Blockers
>> __Pop-ups__ - Eye-catching, attention-grabbing commonly advertisements of products contained in a secondary small window.
>>>[!tip] Blockers
>>>Browser manufacturers in the late 90's developed the ability to block pop-ups.
>>>- `Opera browser` was the first to offer this feature.
>
>
>>[!info] Data Loss Prevention (DLP)
>>> [!abstract]
>>> Is the practice of detecting and preventing breaches, exfiltration, or unwanted destruction of sensitive data.
>>> 
>>> Organizations use DLP to protect and secure their data and comply with regulations.
>>
>>
>> __Data Loss Prevention (DLP)__ has data leak prevention techniques __looking for unauthorized data transmissions__ by examining and inspecting data.
>> DLP system can be:
>>  - _Commonly_ __Network-based__ to inspect data in ___motion___,
>>  - __Storage-based__ to inspect data at ___rest___,
>>  - __Endpoint-based__ to inspect data ___in use__.
>
>>[!info] Securing Storage Devices
>> __Data storage security__ involves protecting storage resources and the data stored on them
>> - Both on-premises and in external data centers and the cloud
>> 	- from accidental or deliberate damage or destruction and from unauthorized users and uses.
>> - It's an area that is of critical importance to enterprises because most data breaches are ultimately cause by a failure in data storage security.
>>> [!tip] How to Secure USB Drives and Other Portable Storage Devices
>>> - Encrypt Your Data
>>> - Use BitLocker To Go for Windows 7 and 8
>>> - Use Encrypting File System (EFS) for Windows XP and Vista
>>> - Use 256-bit AES Encryption for MAC
>>> - Different Encryption Options With Third-Party Software
>>> - Mixing Encryption Hardware and Software May Be Best Medicine
>
>
>> [!info] Disc Encryption
>> Prevents a disk drive, such as a `hard drive in a laptop computer` or a `portable USB storage device`, from booting up __unless the user inputs a valid authentication data.__
>
>
>> [!info] Mobile Malware
>> Is malicious software that specifically __targets the operating systems on `mobile phones`__.
>> - There are many types of mobile malware variants and different methods of distribution and infection.
>
>
>> [!info] Sim Cloning and ID Theft
>>> [!example] Sim Cloning
>>> the process in which __a legitimate SIM card is duplicated__. 
>>> - When the cloning is completed, the `cloned SIM card’s` identifying information is transferred onto a `separate, secondary SIM card`. 
>>> - The secondary card can then be used in a different phone __while having all calls and associated charges attributed to the original SIM card__. 
>>> - The phrase SIM clone is often used to refer to the SIM card that has been __successfully duplicated__.
>>
>>
>>> [!example] ID Theft
>>> Identity (ID) theft happens __when someone steals your personal information `to commit fraud`__.
>>> - The identity thief may use your information to fraudulently apply for credit, file taxes, or get medical services. 
>>> - These acts can damage your credit status, and cost you time and money to restore your good name.
>
>
>> [!info] Bluetooth Attacks
>> - Bluetooth is best known as the wireless technology that powers hands-free earpieces and connects your phone to audio, navigation, and electronics through the Internet of Things (IoT). 
>> - __Bluetooth connections are encrypted__, but that has not stopped researchers finding vulnerabilities allowing them to eavesdrop on connections between phones and headsets. 
>> - Bluetooth can be used to transfer files from one device to another, so __if an attacker could access a device via the Bluetooth protocol they could also potentially access sensitive information on that device__.
>
>
>> [!info] Mobile Device Theft
>> With the rising use of electronic devices such as laptop computers, tablets, cellular phones, and other personal electronics, they have become a target of choice for thieves all over. Because these devices make it easier to store and access information for personal and professional use, they can also put your data at risk. Theft is a significant threat to users of these devices, especially when using them to access your personal information, bank accounts, or work on-the-go.
>
>
>> [!info] BYOD
>> __Bring your own device__ (BYOD) refers to the trend of employees using personal devices to connect to their organizational networks and access work-related systems and potentially sensitive or confidential data. 
>> Personal devices could include` smartphones, personal computers, tablets, or USB drives`.
>
>
>> [!info] Securing Mobile Devices
>> Smartphones have become such an integral part of our life that it is hard to imagine how people used to communicate, access and share information, and even pay bills without them. 
>> - Because of their size, we tend to forget that they are actually extremely powerful computers and that they should be secured as such.
>> - The below security tips will help you secure your phone and prevent malicious programs or people from accessing it. The more of these you implement, the safer your device will be.
>>> [!tip] Things to Consider:
>>> - Use a lock screen and enable auto-lock functionality
>>> - Do not “root” or “jailbreak” your device.
>>> - Avoid “rooting” your device if possible, as this can make it difficult to regularly pull down security updates and other patches for the device.
>>> - Ensure that any installed apps are regularly updated.
>>> - Avoid installing unrecognized apps or apps from unknown authors.
>>> - Install anti-malware software if available for your device.
>>> - If a mobile device supports encryption, use it.
>>> - Be careful when opening attachments and browsing.
>>> - Enable “remote wipe” functionality where available.
>>> - Enable “find my device” functionality if available.
>>> - Try not to store emails, text messages, or other content containing sensitive information (like credit card numbers, social security numbers, passwords, etc.) On mobile devices.
>>> - Be mindful when connecting to unrecognized or unsecured wireless networks.
>>> - Do not connect to wireless networks that are unrecognized.
>>> - Do not leave your phone/tablet unattended



## Week 3

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



## Week 5

>[!abstract] The OSI Model 
>The __Open System Interconnection__ (OSI) model defines a networking framework to implement protocols in seven layers. 
>![[Pasted image 20240301092345.png]]
>> [!tip] Hardware Layers
>>> [!info] 1. __Physical Layer__ (`Layer 1`):
>>> - The __lowest layer of the OSI reference model__ is the physical layer. 
>>> - It is responsible for the __actual physical connection between the devices__. 
>>> - The physical layer contains information in the form of `bits`. 
>>> - It is ___responsible for transmitting individual bits from one node to the next___. 
>>> - When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together.
>>
>>> [!info] 2. __Data Link Layer__ (DLL) - (`Layer 2`):
>>> - The data link layer is responsible for the __node to node delivery of the message__. 
>>> - The main function of this layer is to make sure data transfer is __error-free__ from one node to another, over the physical layer.
>>> - When a ___packet___ arrives in a network, it is the responsibility of DLL to transmit it to the Host using its __MAC address__.
>> 
>>> [!info] 3. __Network Layer__ (`Layer 3`):
>>> - Network layer __works for the transmission of data from one host to the other located in different networks__. 
>>> - It also takes care of ___packet routing___ i.e. selection of the shortest path to transmit the packet, from the number of routes available. 
>>> - The sender & receiver’s IP address are placed in the header by the network layer.
>
>
>> [!tip] Heart of OSI
>>> [!info] 4. __Transport Layer__ (`Layer 4`):
>>> - Transport layer __provides services to application layer and takes services from network layer__. 
>>> - The data in the transport layer is referred to as ___Segments___. 
>>> - It is responsible for the __End to End Delivery__ of the complete message. 
>>> - The transport layer also provides the acknowledgement of the successful data transmission and re-transmits the data if an error is found.
>
>
>> [!tip] Software Layers
>>> [!info] 5. __Session Layer__ (`Layer 5`):
>>> This layer is responsible for `establishment of connection`, `maintenance of sessions`, `authentication` and also `ensures security`.
>>
>>> [!info] 6. __Presentation Layer__ (`Layer 6`):
>>> Presentation layer is also called the __Translation layer__. 
>>> The `data from the application layer` is __extracted here and manipulated__ as per the required format to transmit over the network.
>>
>>> [!info] 7. __Application Layer__ (`Layer 7`):
>>> - At the very top of the OSI Reference Model stack of layers, we find Application layer which is implemented by the network applications. 
>>> - These applications __produce the data__, which has to be transferred over the network. 
>>> - This layer also __serves as a window for the application services__ to access the network and for displaying the received information to the user.
>>
> ---
>> [!info] Switches
>>-  A switch in an Ethernet-based LAN `reads incoming TCP/IP data packets/frames` __containing destination information__ as they pass into one or more input ports. 
>> - The `destination information` in the packets is __used to determine which output ports will be used to send the data on to its intended destination__.
>
>
>> [!info] Routers
>> - A device that `connects two or more networks` and __allows packets to be transmitted and received between them__.
>> - A router __determines the best path__ for `data packets` ___from source to destination___.
>
>> [!info] Network Zones
>> - A security zone is an `area in a building` where __access is individually monitored and controlled__. 
>> - A `large network`, such as a large physical plant, can have many areas that require restricted access. 
>>- In a building, floors, sections of floors, and even offices can be broken down into smaller areas.
>> 	- These smaller zones are referred to as __security zones__. 
>> 	- In the physical environment, each floor is broken into separate zones. An alarm system that identifies a zone of intrusion can inform security personnel about an intruder’s location in the building; zone notification tells them where to begin looking when they enter the premises.
>
>>[!info] Network Access Control
>>- One of the basic security objectives set forth by most organizations is controlling access to the organization’s network. 
>>- Network access control (NAC) solutions help security professionals achieve two cybersecurity objectives: 
>>	- __limiting network access to authorized individuals__ and 
>>	- ensuring that `systems accessing the organization’s network` __meet basic security requirements__.
>
>
>> [!info] VLANS
>> - A __virtual local area network__ (VLAN) allows you to `create groups of users and systems` and ___segment them on the network___. 
>> - This ___segmentation___ lets you __hide segments of the network from other segments and thereby control access__. 
>> 	- You can also set up VLANs to control the paths that data takes to get from one point to another. 
>> - A VLAN is a good way to contain network traffic to a certain area in a network.
>
>
>> [!info] Subnetting
>> - Subnetting __divides a single range of IP addresses into several smaller ranges of IP addresses__. 
>> - This is often done to `isolate traffic and increase efficiency`. 
>> ![[Pasted image 20240301095453.png]]
>
>> [!info] Network Address Translation
>> - Network Address Translation (NAT) creates a unique opportunity to __assist in the security of a network__. 
>> - Originally, NAT `extended the number of usable Internet addresses`. 
>> - Now it __allows an organization to present a single address to the Internet for all computer connections__. 
>> - The NAT server provides IP addresses to the hosts or systems in the network and tracks inbound and outbound traffic
>
>>[!info] Telephony
>>IP or Internet telephony is the latest terminology related to __data/voice communication__. 
>>- It uses the Internet as a medium of communication. 
>>- IP telephony allows data communication in which voice, fax or digital information can be transmitted over the Internet.
>
>
>> [!info] Firewalls
>> Firewalls are one of the __first lines of defense in a network__. 
>> - There are different types of firewalls, and they can be either __stand-alone systems__ or ___included in other devices such as routers or servers___. 
>> - You can find firewall solutions that are marketed as hardware-only and others that are software-only. 
>> 	- Many firewalls, however, consist of add-in software that is available for servers or workstations.
>>> [!tip] Packet Filter Firewalls
>>> - A firewall operating as a packet filter __passes or blocks traffic to specific addresses__ based on the type of application. 
>>> - The packet filter `doesn’t analyze the contents of a packet`; it decides whether to pass it based on the packet’s addressing information.
>>
>>
>>> [!tip] Stateful Inspection Firewalls
>>>  Stateful inspection is also referred to as __stateful packet filtering__. 
>>>  - Most of the devices used in networks don’t keep track of how information is routed or used. 
>>> 	 - Once a packet is passed, the packet and path are forgotten. 
>>>  - In stateful inspection (or stateful packet filtering), __records are kept using a state table that tracks every communications channel__.
>
>> [!info] Proxy Servers
>> A proxy firewall can be thought of as an __intermediary between your network and any other network__. 
>> - Proxy firewalls are __used to process requests from an outside network__; 
>> 	- the proxy firewall examines the data and makes rules-based decisions about whether the request should be forwarded or refused. 
>> - The proxy `intercepts all the packages and reprocesses them for use internally`. This process includes hiding IP addresses.
>
>>[!info] Honeypots and Honeynets
>>A honeypot is a `decoy computer system` for __trapping hackers or tracking unconventional or new hacking methods__. 
>>- Honeypots are designed to purposely ___engage and deceive hackers___ and ___identify malicious activities___ performed over the Internet. 
>>	- While Honeynets purposely include system vulnerabilities and aid in better understanding hacker and cracker behavior (and the motivations behind their behaviors).
>
>> [!info] Data Loss Prevention
>> DLP is a method of __inspecting and keeping sensitive data__ from leaving the allowed perimeter. 
>> DLP systems are only concerned with the data passing over some kind of perimeter gateway device, such as through emails, instant messages and Web 2.0 applications.
>
>
>> [!info] NIDS and NIPS
>> - A __network-based intrusion detection system__ (NIDS) monitors activity on the network. 
>> 	- An administrator installs NIDSs sensors on network devices such as routers and firewalls. 
>> 	- These sensors gather information and report to a central monitoring server hosting a NIDS console.
>> - __Network-based intrusion prevention system__ (NIPS). 
>> 	- An IPS that `monitors the network`. 
>> 	- An IPS can `actively monitor data streams`, `detect malicious content`, and `stop attacks in progress`.
>
>> [!info] Unified Threat Management
>> The emergence of unified threat management is a relatively new phenomenon, because the various aspects that make up these products used to be sold separately. However, by selecting a UTM solution, businesses and organization can deal with just one vendor, which may be more efficient. Unified threat management solutions may also promote easier installation and updates for security systems, although others contend that a single point of access and security can be a liability in some cases.
>
>
>> [!info] Cloud Types
>> Cloud computing is `provided by cloud providers` and is __very useful for heavily utilized systems and networks__. 
>> - __Software as a Service__ (SaaS) is used for web-based applications. 
>> - __Infrastructure as a Service__ (IaaS) is also known as `Hardware as a Service`. 
>> - __Platform as a Service__ (PaaS) provides easy-to-configure operating systems.
>
>
> katamad na potek
>![[Pasted image 20240301101847.png]]
>![[Pasted image 20240301101903.png]]
>![[Pasted image 20240301101912.png]]
>![[Pasted image 20240301101920.png]]
>![[Pasted image 20240301101930.png]]