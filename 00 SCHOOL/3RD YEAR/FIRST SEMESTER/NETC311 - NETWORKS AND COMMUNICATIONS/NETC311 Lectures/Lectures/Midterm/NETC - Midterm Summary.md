# Module 6: Data Link Layer
### Data Link Layer
>[!INFO] Data Link Layer
> - Responsible for communications between end-device NIC (Network Interface Cards)
> - Allows __Upper layer__ protocols access Physical layer media
> 	- and Encapsulates Layer 3 packets (IPv4 and IPv6) into Layer 2 Frames
> - Performs _Error detection_ and __Rejects corrupt frames__
>> [!Abstract] 2 Sublayers of Data Link Layer
>>  - __Logical Link Control__ (LLC) - Communicates  between __Upper layers__ and device hardware at the ___Lower layers___ 
>>  - ___Media Access Control___ (MAC)
>>responsible for _data encapsulation_ and media access control
>>![[Pasted image 20231105130130.png | 400]]

>[!tip]-  A __router__ performs four basic Layer 2 functions:
>- Accepts a frame form the network medium.
>- De-encapsulates the packet into a new frame
>- Re-encapsulates the packet into a new frame
>- Forwards the new  frame on the medium of the next network segment.

### Topology
>[!INFO] Topology
>Arrangement and Relationship of the __network devices__ and the ___interconnections___ between them
>>[!abstract] 2 Types of topologies used when describing networks:
>>- __Physical topology__ - shows physical connections and how devices are interconnected.
>>![[Pasted image 20231105165605.png | 350]]
>>- ___Logical topology___ - identifies the virtual connections between devices using device interfaces and IP addressing schemes.
>>![[Pasted image 20231105165622.png | 350]]

>[!example] 3 Common physical WAN topologies:
>- __Point-to-point__:
>	- Simplest and most common WAN topology.
>	- Consists of a permanent link between two endpoints
>>[!tip] Point-to-point WAN topology
>>- Directly connect two nodes
>>- Nodes may not share the media with other hosts.
>>- Media can only travel to or from the two nodes
>>![[Pasted image 20231105141544.png]]
> - __Hub and spoke__:
> 	- Similar to star topology where:
> 		- A central site interconnects branch sites through point-to-point links.
> - __Mesh__
> 	- Provides high availability but requires every end system to be connected to every other end system.

>[!example] LAN topologies
>End devices are interconnected using a __star or extended star topology__.
>![[Pasted image 20231105142102.png | 400]]
> - __Bus__ - All end systems chained together and terminated on each end.
> - __Ring__ - Each end system is connected to its respective neighbors to form a ring.

>[!example] Half and Full Duplex Communication
> - __Half-duplex communication__ 
> 	- Only allows one device to send or receive at a time on a shared medium
> 	- Used on WLANs and legacy bus topologies with Ethernet hubs.
> - __Full-duplex communication__
> 	- Allows both devices to simultaneously transmit and receive on a shared medium
> 	- Ethernet switch operate in full-duplex mode

>[!Abstract] Access Control Methods
> ###### Contention-based access
> All nodes operating in half-duplex, competing for use of the medium.
>>[!Example]
>>- Carrier sense multiple access with collision detection (CSMA/CD) as used on legacy bus-topology Ethernet.
>>- Carrier sense multiple access with collision avoidance (CSMA/CA) as used on Wireless LANs.
>>>[!abstract] Contention-Based Access - CSMA/CD Process
>>> - Simultaneous transmission will result a signal collision on the shared media
>>> - Devices detect the collision
>>> - Devices wait a random period of time and retransmit data
>###### Controlled Access
>- Deterministic access where each node has its own time on the medium
>- Used on legacy networks such as Token Ring and ARCNET
### Data Link Frame
>[!Abstract] The frame
>Data link layer encapsulates data with a __header__ and a __trailer__ to form a ___frame___
>>[!example] 3 parts of data link frame:
>>- Header
>>- Data
>>- Trailer
>
>![[Pasted image 20231105171355.png]]
> 
| Field                | Description                              |
| -------------------- | ---------------------------------------- |
| Frame Start and Stop | Identifies beginning and end of frame    |
| Addressing           | Indicates source and destination nodes   |
| Type                 | Identifies encapsulated Layer 3 protocol |
| Control              | Identifies flow control services         |
| Data                 | Contains the frame payload               |
| Error Detection      | Used for determine transmission errors   |
>
>>[!INFO] Layer 2 Addresses
>> - aka "Physical Address"
>> - Contained in the frame __header__
>> - Used only for local delivery of a frame on the link.
>> - Updated by each device that forwards the frame.
>> ![[Pasted image 20231105174219.png | 350]]


# Module 7: Ethernet Switching
### Ethernet Frames
>[!abstract] 
> - Ethernet operates in the __data link layer__ and ___physical layer___
> ![[Pasted image 20231105180915.png| 350]]
>
>>[!question]- What are the __2__ separate __sublayers of the Data Link Layer__ used by __802 LAN/MAN__ standards (including Ethernet)?
>> - __LLC Sublayer__ (IEEE 802.3) Places information in the frame to identify which network layer protocol is used for the frame
>> - __MAC Sublayer__ (IEE 802.3, 802.11 or 802.15) Responsible for data encapsulation and media access control, and provides data link layer addressing
>> ![[Pasted image 20231105203048.png | 350]]
>
>###### Ethernet Frame Fields
>> [!tip]- What are the Minimum and Maximum Ethernet frame size?
>> - Minimum:
>> 	- __64 bytes__
>> 	- Frames less than __64 bytes__ in length are considered a "___collision fragment___" or "___runt frame___" and is automatically discarded
>> - Maximum:
>> 	- __1518 bytes__
>> 	- Considered as "___jumbo___" or "___baby giant frames___"
>> ![[Pasted image 20231105204631.png | 350]]
>>>[!Question]- What would happen to frames less or greater than the minimum and maximum?
>>>- Receiving device drops the frame.
>>>- They are considered invalid
>>


### Ethernet MAC Address
>[!Abstract] 
>-  Ethernet LAN: All devices share the same network medium. 
>- MAC addressing: Identifies devices at the OSI data link layer.
>- Ethernet MAC address: Expressed in __12__ hexadecimal digits (48-bit address).
>- MAC address length: 6 bytes (each byte is 8 bits).
>- Uniqueness: All MAC addresses must be unique.
>- Vendor registration: Vendors obtain an OUI (organizationally unique identifier) from IEEE.
>- Structure: MAC address consists of 6 hex digits for OUI and 6 hex digits for vendor-assigned value.
>![[Pasted image 20231105211157.png | 400]]

#### Frame Processing
>[!TIP] Frame Processing
> - When forwarding message to an Ethernet network, the __Header__ include a ___Source MAC address___ and a ___Destination Mac address___
>>[!question]- What would NIC do once received an Ethernet frame?
>> - Examines the __Destination MAC Address__ if it matches the __Physical MAC Address__ stored in RAM
>> 	- ___No Match___: Device _discards_ the frame
>> 	- a __Match__: passes frame up to _OSI Layers_, where de-encapsulation process takes place

#### Unicast MAC Address
>[!tip] Unicast MAC Address
> the unique address used when a frame is sent from a single __Transmitting__ device to a single __Destination__ device.
> - __Address Resolution Protocol__ (__ARP__) - Process used by source host to determine the destination MAC address associated with an ___IPv4___ address
> - __Neighbor Discovery__ (__ND__) - Process used by source host to determine the destination MAC Address associated with an ___IPv6___ address
> ![[Pasted image 20231105232854.png | 350]]

#### Broadcast MAC Address
>[!tip] Broadcast MAC Address
> Received and processed by every device on the Ethernet LAN
> - It has a destination MAC address of FF-FF-FF-FF-FF-FF in hexadecimal (48 ones in binary).
> - It is flooded out all Ethernet switch ports except the incoming port. It is not forwarded by a router.
> - If the encapsulated data is an IPv4 broadcast packet, this means the packet contains a destination IPv4 address that has all ones (1s) in the host portion. This numbering in the address means that all hosts on that local network (broadcast domain) will receive and process the packet.
> ![[Pasted image 20231105233038.png | 350]]

>[!tip] Multicast MAC Address
> Received and processed by a group of devices that belong to the same multicast group
> - Because multicast addresses represent a group of addresses (sometimes called a host group), they can only be used as the destination of a packet. The source will always be a unicast address.
> - As with the unicast and broadcast addresses, the multicast IP address requires a corresponding multicast MAC address.
> ![[Pasted image 20231105234206.png | 350]]


## Mac Address Table
>[!quote] 
>- A Layer 2 Ethernet switch uses Layer 2 MAC addresses to make forwarding decisions. It is completely unaware of the data (protocol) being carried in the data portion of the frame, such as an IPv4 packet, an ARP message, or an IPv6 ND packet. The switch makes its forwarding decisions based solely on the Layer 2 Ethernet MAC addresses.
>- An Ethernet switch examines its MAC address table to make a forwarding decision for each frame, unlike legacy Ethernet hubs that repeat bits out all ports except the incoming port.
>- When a switch is turned on, the MAC address table is empty
>
>#### Switch Learning and Forwarding
>Examine the Source MAC Address (Learn)
>- Every frame that enters a switch is checked for new information to learn. It does this by examining the source MAC address of the frame and the port number where the frame entered the switch. If the source MAC address does not exist, it is added to the table along with the incoming port number. If the source MAC address does exist, the switch updates the refresh timer for that entry. By default, most Ethernet switches keep an entry in the table for 5 minutes.
>  
>  Find the Destination MAC Address (Forward)
>  If the destination MAC address is a unicast address, the switch will look for a match between the destination MAC address of the frame and an entry in its MAC address table. If the destination MAC address is in the table, it will forward the frame out the specified port. If the destination MAC address is not in the table, the switch will forward the frame out all ports except the incoming port. This is called an unknown unicast.
>  Note: If the destination MAC address is a broadcast or a multicast, the frame is also flooded out all ports except the incoming port.

>[!question] How does a network switch populate its MAC address table, and what role does this table play in the frame forwarding process?
>###### Filtering Frames
>- As a switch receives frames from different devices, it is able to populate its MAC address table by examining the source MAC address of every frame. 
>- When the MAC address table of the switch contains the destination MAC address, it is able to filter the frame and forward out a single port.
>![[Pasted image 20231106003601.png | 350]]

### Switch Speeds and Forwarding Methods

>[!abstract] Frame forwarding Methods on Cisco Switches
> - __Store and Forward switching__ - Receives entire frame and computes CRC
> - __Cut-through switching__ - Forwards the frame before it's entirely received.

>[!abstract] Duplex and Speed Settings
> - 2 most basic switch settings: __bandwidth ("speed")__ and __duplex settings__ 
> - Those __2__ should match between the switch port and the connected devices.
>> [!example] 2 Types of __Duplex settings__
>> - ___Full-duplex___ - Both ends of the connection can send and receive simultaneously
>> - ___Half-duplex___ - Only one end of the connection can send at a time.
>> 
>>> [!caution] Duplex Mismatch
>>> - One of the most common causes of  performance issues
>>> - Happens when 1 port is __Full-duplex__ and the other is ___Half-Duplex___
>>   ![[Pasted image 20231106173431.png | 450]]
>>   

# Module 8: Network Layer

## The network layer
>[!INFO] Network Layer
>- Provides services to allow end devices to exchange data
>- IPv4 and IPv6 are principle network layer communication protocols
>> [!example] 4 Basic operations of Network Layer
>> -  Addressing end devices
>> - Encapsulation
>> - Routing
>> - De-encapsulation
>
>> [!TIP] Characteristics of IP
>> - __Connectionless__
>> 	- Does not establish a connection with the destination before sending the packet
>> 	- No control information needed
>> 	![[Pasted image 20231106181054.png | 350]]
>> - __Best Effort__
>> 	- delivery of packet is not guaranteed
>> 	- doesn't know if the other device is operational or if it received the packet
>> - __Media Independent__
>>

## IPv4 Packet
>[!Abstract] IPv4 Packet Header
> __IPv4__ : primary communication protocol for the network layer.
> 
>> [!example] IPv4 network header characteristics:
>> - in Binary
>> - Contains several fields of information
>> - Diagram read from left to right, 4 bytes per line
>> - Source and Destination (most important fields)
>> ![[Pasted image 20231106182154.png | 350]]

>[!aBSTRACT] IPv6 Packets
> - Based on __128 bits__, not 32 bits
> - Simplified header with fewe
> - Eliminates the need for NAT
>  ![[Pasted image 20231106182624.png | 350]]
>
>> [!example] IPv6 Header
>> - Fixed at __40 bytes__ or octets long
>> ![[Pasted image 20231106182731.png | 350]]
>> 
>> | Function                 | Description                                                                              |
>> | ------------------------ | ---------------------------------------------------------------------------------------- |
>> | Version                  | This will be for v6, as opposed to v4, a 4 bit field= 0110                               |
>> | Traffic Class            | Used for QoS: Equivalent to DiffServ – DS field                                          |
>> | Flow Label               | Informs device to handle identical flow labels the same way, 20 bit field                |
>> | Payload Length           | This 16-bit field indicates the length of the data portion or payload of the IPv6 packet |
>> | Next Header              | I.D.s next level protocol: ICMP, TCP, UDP, etc.                                          |
>> | Hop Limit                | Replaces TTL field Layer 3 hop count                                                     |
>> | Source IPv4 Address      | 128 bit source address                                                                   |
>> | Destination IPV4 Address | 128 bit destination address                                                              |
 
### Introduction to Routing
>[!INFO] Router Packet Forwarding Decision
>![[Pasted image 20231106183518.png | 450]]
>
>![[Pasted image 20231106183508.png | 350]]
>
>>[!abstract] 3 Types of Routes in a router's routing table:
>>- __Directly Connected__ - Automatically added by the router, provided the interface is active and has addressing
>>- __Remote__ - Doesn't have a direct connection and may be learned:
>>	- Manually - with a static route
>>	- Dynamically 
>>- __Default Route__ - Forwards all traffic to specific direction if no match in the routing table
>  
>>[!abstract] Static Routing:
>>Characteristics:
>>- Configured __manually__
>>- Good for small non-redundant networks
>>- used in conjunction with a dynamic routing protocol for configuring a default route
>
>>[!abstract] Dynamic Routing
>>Automatically:
>>	- Discover remote networks
>>	- Up-to-date
>>	- choose best path to destination
>>	- find new best paths when topology changes

>[!Tip] IPv4 Routing commands
>__show ip route__ command shows:
>- ___L___ - Directly connected local interface IP Address
>- ___C___ - Directly connected network
>- ___S___ - Static route was manually configured by an administrator
>- ___O___ - OSPF
>- ___D___ - EIGRP
> This command shows types of routes:
> - Directly Connected – C and L
> - Remote Routes – O, D, etc.
> - Default Routes – S*
> ![[Pasted image 20231106184738.png | 350]]

>[!dONE] SUMMARY:
> - IP is connectionless, best effort, and media independent.
> - IP does not guarantee packet delivery.
> - IPv4 packet header consists of fields containing information about the packet.
> - IPv6 overcomes IPv4 lack of end-to-end connectivity and increased network complexity.
> - A device will determine if a destination is itself, another local host, and a remote host.
> - A default gateway is router that is part of the LAN and will be used as a door to other networks
> - The routing table contains a list of all known network addresses (prefixes) and where to forward the packet.
> - The router uses longest subnet mask or prefix match.
> - The routing table has three types of route entries: directly connected networks, remote networks, and a default route.


## Address Resolution
>[!abstract] 2 primary addresses assigned to a device on an Ethernet LAN:
> - __Layer 2 physical address (MAC address)__ - Used for NIC to NIC communications on the same Ethernet network
> - __Layer 3 logical address (IP address)__ - Used to send the packet from the source device to destination device.


### ARP
>[!abstract] ARP
>Used to determine the destination MAC address of a local device when it knows its IPv4 address
>
>>[!example] 2 basic functions of ARP
>> - Resolving IPv4 addresses to MAC addresses
>> - Maintaining an ARP table of IPv4 to MAC address mappings
>>   ![[Pasted image 20231107005458.png | 350]]
>
>>[!question]- are entries in ARP permanent?
>> - Entries in the ARP table are not permanent and are removed when an ARP cache timer expires after a specified period of time.
>> - The duration of the ARP cache timer differs depending on the operating system.
>> - ARP table entries can also be removed manually by the administrator.
>
>- The `show ip arp` command displays the ARP table on a Cisco router.
>- The `arp –a` command displays the ARP table on a Windows 10 PC.

## IPv6 Neighbor Discovery

>[!abstract] IPv6 Neighbor Discovery (ND) protocol provides:
>- Address resolution
>- Router discovery
>- Redirection services


## Basic Router Configuration
>[!example] Basic Router Configuration
>![[Pasted image 20231107013538.png]]
>![[Pasted image 20231107013600.png]]
>![[Pasted image 20231107013713.png]]


>[!example] Configure Interfaces
>| Command | Description |
>| ---------------|-----------------|
>|