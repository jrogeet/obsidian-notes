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




