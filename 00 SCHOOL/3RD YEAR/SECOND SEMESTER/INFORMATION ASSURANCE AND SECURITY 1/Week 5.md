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
>