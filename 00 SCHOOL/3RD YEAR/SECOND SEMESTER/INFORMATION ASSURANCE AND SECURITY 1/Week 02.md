---
subject: IAAS
term: prelim
week: "2"
Topic:
---
Tags:
Links:
Created: 2024-12-30

---
# Design

---

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







