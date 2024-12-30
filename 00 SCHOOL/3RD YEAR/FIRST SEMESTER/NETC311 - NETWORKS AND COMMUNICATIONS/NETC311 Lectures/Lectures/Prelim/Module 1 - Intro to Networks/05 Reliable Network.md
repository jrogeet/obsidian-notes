---
subject: Network and Communications
term: prelim
week: "1"
Topic: Reliable Network
---
Tags: #netc
Links:
Created: 2023-10-01

---
# 05 Reliable Networks

---

## Network Architecture
![[Pasted image 20231001165609.png]]

Network Architecture refers to the technologies that support the infrastructure that moves data across the network.

There are four basic characteristics that the underlying architectures need to address to meet user expectations:

- Fault Tolerance
- Scalability
- Quality of Service (QoS)
- Security

## Fault Tolerance

A fault tolerant network _limits the impact of a failure by limiting the number of affected devices_. __Multiple paths__ are required for fault tolerance.

Reliable networks provide redundancy by implementing a packet switched network:

- Packet switching splits traffic into packets that are routed over a network.
- Each packet could theoretically take a different path to the destination.

This is not possible with circuit-switched networks which establish dedicated circuits.

![[Pasted image 20231001165738.png]]

## Scalability
![[Pasted image 20231001165851.png]]

A scalable network can expand quickly and easily to support new users and applications without impacting the performance of services to existing users.

Network designers follow accepted standards and protocols in order to make the networks scalable.


## Quality of Service
Voice and live video transmissions require higher expectations for those services being delivered. 

Have you ever watched a live video with constant breaks and pauses? This is caused when there is a higher demand for bandwidth than available – and QoS isn’t configured.

•Quality of Service (QoS) is the primary mechanism used to ensure reliable delivery of content for all users.

•With a QoS policy in place, the router can more easily manage the flow of data and voice traffic.

![[Pasted image 20231001170004.png]]

## Network Security
![[Pasted image 20231001170019.png]]
There are two main types of network security that must be addressed: 

- Network infrastructure security

- Physical security of network devices

- Preventing unauthorized access to the devices

- Information Security

- Protection of the information or data transmitted over the network

Three goals of network security:

- Confidentiality – only intended recipients can read the data

- Integrity – assurance that the data has not be altered with during transmission

- Availability – assurance of timely and reliable access to data for authorized users