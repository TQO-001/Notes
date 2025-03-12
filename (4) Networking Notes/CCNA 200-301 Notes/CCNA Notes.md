
# CCNA 200 – 301


![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image003.jpg)

# 1) Network Fundamentals (20%)
---
## 1.1) Explain the role and function of network components
---
---
### I)    Routers:

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image005.jpg)

Routers connect multiple networks together. They also connect computers on those networks to the Internet. Routers enable all networked computers to share a single Internet connection, which saves money. A router acts as a dispatcher. It analyses data being sent across a network, chooses the best route for data to travel, and sends it on its way. Routers connect your business to the world, protect information from security threats, and can even decide which computers receive priority over others. Beyond those basic networking functions, routers come with additional features to make networking easier or more secure. Depending on your needs, for example, you can choose a router with a firewall, a virtual private network (VPN), or an Internet Protocol (IP) communications system.

- Routers are networking devices that connect multiple networks together and route data packets between them.
- They operate at Layer 3 (the network layer) of the OSI model.
- Routers make decisions based on destination IP addresses to determine the best path for data packets to reach their destination.
- They also provide features such as network address translation (NAT), which allows multiple devices to share a single public IP address, and firewall capabilities for security.
---
### II)  Layer 2 and Layer 3 switches:

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image007.gif)

Switches are the foundation of most business networks. A switch acts as a controller, connecting computers, printers, and servers to a network in a building or a campus. Switches allow devices on your network to communicate with each other, as well as with other networks, creating a network of shared resources.

There are two basic types of switches to choose from as part of your networking basics: managed and unmanaged.
- An unmanaged switch works out of the box but can't be configured. Home-networking equipment typically offers unmanaged switches.
- A managed switch can be configured. You can monitor and adjust a managed switch.

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image008.gif)

o   Switches are devices used to connect multiple devices within a local area network (LAN).
o   Layer 2 switches operate at the data link layer (Layer 2) of the OSI model and make forwarding decisions based on MAC addresses.
o   Layer 3 switches, also known as multilayer switches, can perform routing functions in addition to switching at Layer 2.
o   Switches help to improve network performance by reducing the amount of traffic on a network segment and facilitating communication between devices.

--- 
### III) Next-generation firewalls and IPS (Intrusion Prevention Systems):

Next-generation firewalls: A traditional firewall provides stateful inspection of network traffic. It allows or blocks traffic based on state, port, and protocol, and filters traffic based on administrator-defined rules. In addition to access control, NGFWs can block modern threats such as advanced malware and application-layer attacks.

In summary, a next-generation firewall includes additional features like application awareness and control, integrated intrusion prevention, and cloud-delivered threat intelligence.

Here are the common features of most NGFWs:

1.    **Standard firewall features**: Include stateful port/protocol inspection, Network Address Translation (NAT), and Virtual Private Network (VPN).
2.    **Application identification and filtering**: Chief characteristic of NGFWs, identifying and filtering traffic based on specific applications to prevent malicious activity.
3.    **SSL and SSH inspection:** NGFWs decrypt SSL and SSH encrypted traffic, analyse it for authorized applications, policies, and then re-encrypt it for additional protection.
4.    **Intrusion prevention:** NGFWs offer deeper traffic inspection to detect and prevent intrusions, some integrating built-in IPS functionality.
5.    **Directory integration:** NGFWs include directory support (e.g., Active Directory) to manage authorized applications based on users and user groups.
6.    **Malware filtering:** NGFWs provide reputation-based filtering to block applications with a bad reputation, checking for phishing, viruses, and other malware sites and applications.
7.    **Intrusion Prevention System (IPS):** Cisco IOS Intrusion Prevention System (IPS) is an inline, deep-packet inspection feature that effectively mitigates a wide range of network attacks. IPS analyses network traffic can report and take corrective action on traffic that it deems malicious or harmful. This can be implemented as an appliance, as a blade, or as a module in an ASA or IOS router. The primary method for identifying problem traffic is through signature matching.

https://ipcisco.com/lesson/cisco-ngfw-and-cisco-ngips/

- Next-generation firewalls (NGFW) are advanced security devices that combine traditional firewall functionality with additional features such as intrusion prevention, application control, and advanced threat protection.
- NGFWs inspect network traffic at the application layer (Layer 7) of the OSI model and can block or allow traffic based on predefined rules and policies.
- Intrusion Prevention Systems (IPS) monitor network traffic for suspicious activity or known attack patterns and can take action to prevent intrusions in real-time.
---
### IV) Access points:

An access point allows devices to connect to the wireless network without cables. A wireless network makes it easy to bring new devices online and provides flexible support to mobile workers.

An access point acts like an amplifier for a network. While a router provides the bandwidth, an access point extends that bandwidth so that the network can support many devices, and those devices can access the network from farther away.

But an access point does more than simply extend Wi-Fi. It can also give useful data about the devices on the network, provide proactive security, and serve many other practical purposes.

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image010.jpg)

Access points support different IEEE standards. Each standard is an amendment that was ratified over time. The standards operate on varying frequencies, deliver different bandwidth, and support different number of channels.

o   Access points (APs) are devices used to connect wireless devices to a wired network.
o   They operate at Layer 2 of the OSI model and provide wireless connectivity using Wi-Fi standards such as 802.11ac or 802.11ax.
o   Access points allow devices such as laptops, smartphones, and tablets to connect to the network without the need for physical Ethernet cables. 

---
### IV) Controllers (Cisco DNA Center and WLC Wireless LAN Controller):

#### Controllers (Cisco DNA Center and WLC)

Cisco DNA Center is the network management and command center for Cisco DNA. With this platform, IT can respond to changes and challenges faster and more intelligently. The Cisco DNA Center is a complete network management platform with integrated tools for network management, automation, virtualization, analytics and assurance, security, and Internet of Things connectivity. The DNA Center dashboard provides an intuitive and simple overview of network health and clear drill-down menus for quickly identifying and remediating issues.

**Some important points on Cisco DNA center**

·         Cisco DNA Center is all about Automation
·         Cisco DNA Center is based on something called Intent-Based Networking
·         It is open and inclusive.
·         The Cisco DNA Center dashboard provides 360-degree visibility
·         We can vastly reduce deployment and provisioning times with Cisco DNA Center.
·         Cisco DNA Center takes the guesswork out of network performance capabilities
·         Cisco DNA Center detects and mitigates threats in real time.
·         Lower costs

**WLC(Wireless LAN Controller)**: Wireless networks have become a necessity today. Many corporate environments require deployment of wireless networks on a large scale. Cisco has come up with the concept of the Cisco Unified Wireless Network (CUWN) solution, which helps make it easier to manage such large scale deployments. WLC is a device that assumes a central role in the CUWN. Traditional roles of access points, such as association or authentication of wireless clients, are done by the WLC. Access points, called Lightweight Access Points (LAPs) in the unified environment, register themselves with a WLC and tunnel all the management and data packets to the WLCs, which then switch the packets between wireless clients and the wired portion of the network. All the configurations are done on the WLC. LAPs download the entire configuration from WLCs and act as a wireless interface to the clients.

**A wireless LAN (or WLAN) controller** is used in combination with the Lightweight Access Point Protocol (LWAPP) to manage light-weight access points in large quantities by the network administrator or network operations center. The wireless LAN controller is part of the Data Plane within the Cisco Wireless Model.

- Controllers are network devices used to manage and control other network components, such as access points or switches.
- Cisco DNA Center is a network management platform that provides centralized management and automation for Cisco networks.
          ![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image012.jpg)  
Wireless LAN Controllers (WLCs) are used to manage and control access points in wireless networks, providing features such as centralized configuration, security policies, and roaming support.
---
### V) Endpoints:

Endpoints are remote computing devices that connect to a network and communicates back and forth with the other devices on the network.

Examples of endpoints include:

- Desktops
- Laptops
- Smartphones
- Tablets
- Servers
- Workstations

o   Endpoints are devices connected to a network, such as computers, smartphones, printers, or IoT devices.
o   They generate or consume data and communicate with other devices or servers on the network.
o   Endpoints can be both a source and destination of network traffic, and they often require security measures such as antivirus software and encryption to protect sensitive data.

---
### VII) Servers:

A server is a computer that provides data to other computers. It may serve data to systems on a local area network (LAN) or a wide area network (WAN) over the Internet. Many types of servers exist, including web servers, mail servers, and file servers. Each type runs software specific to the purpose of the server.

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image014.jpg)

- Servers are powerful computers or software applications that provide services or resources to other devices on the network.
- They can serve various purposes, such as hosting websites, storing files, running applications, or managing network services like email or databases.
- Servers typically have high reliability, availability, and performance requirements compared to regular desktop computers.

---
### VIII) PoE (Power over Ethernet):

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image015.jpg)

- PoE is a technology that allows network devices to receive power and data over a single Ethernet cable.
- It eliminates the need for separate power cables, simplifying installation and reducing costs.
- PoE is commonly used to power devices such as IP phones, wireless access points, and security cameras in enterprise networks.

---
---
## 1.2) Describe characteristics of network topology architectures
---
#### Ethernet and CSMA/CD

In Carrier Sense Multiple Access With Collision Detection (CSMA/CD), a node transmits only after listening to the media, and ensuring that no transmission is taking place. Further, sending nodes detect when a collision occurs and stop transmitting immediately, backing off for a random amount of time before trying again. This results in efficient use of the media since the bandwidth of transmitting the entire frame is not wasted.

---
### I) Two-tier:

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image017.gif)

Two-tier networks have an access layer connecting end-user devices and a distribution layer handling traffic aggregation. This architecture suits smaller to medium-sized networks, emphasizing scalability and simplicity.

---
### II) Three-tier:

Three-tier networks consist of access, distribution, and core layers. Access connects devices, distribution manages traffic, and the core provides high-speed connectivity. Common in larger enterprises for scalability and performance.

In 3-tier Cisco defines 3 layers of hierarchy, the core,distribution, and access each with specific function and it's referred to as a 3-tier network architecture.

#### Here is a description of each layer:

**Access:** Access layer controls user and workgroup access to the resources on the network. This layer usually incorporates Layer 2 switches and access points that provide connectivity between workstations and servers. You can manage access control and policy, create separate collision domains, and implement port security at this layer.

**Distribution:** Distribution layer serves as the communication point between the access layer and the core. Its primary functions are to provide routing, filtering, and WAN access and to determine how packets can access the core. This layer determines the fastest way that network service requests are accessed – for example, how a file request is forwarded to a server – and, if necessary, forwards the request to the core layer. This layer usually consists of routers and multilayer switches.

**Core:** Core layer also referred to as the network backbone, this layer is responsible for transporting large amounts of traffic quickly. The core layer provides inter-connectivity between distribution layer devices it usually consists of high speed devices, like high end routers and switches with redundant links.

---
### III) Spine-leaf:

̵   Spine-leaf networks feature spine (core) switches and leaf (access) switches forming a full mesh topology. Leaf switches connect devices, while spine switches provide high-speed connectivity. Ideal for modern data centers due to scalability and low latency.

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image019.gif)

With the increased focus on massive data transfers and instantaneous data travel in the network, the aging three-tier design within a data center is being replaced with what is being called the Leaf-Spine design. It is also referred to as leaf and spine topology, in this design there are switches found at the top of each rack that connect to the servers in the rack,with a server connecting into each switch for redundancy. People refer to this as a top-of-rack (ToR) design because the switches physically reside at the top of the rack.

The Leaf layer consists of access switches that connect to devices like servers, firewalls, load balancers, and edge routers. The Spine layer (made up of switches that perform routing) is the backbone of the network, where every Leaf switch is interconnected with each and every Spine switch.

o   With Leaf-Spine, the network uses Layer 2 and Layer 3 switching.
o   All routes are configured in an active state through the use of Equal-Cost Multipathing (ECMP). This allows all connections to be utilized at the same time while still remaining stable and avoiding loops within the network.
o   With traditional Layer 2 switching protocols like Spanning Tree on three-tiered networks, it must be configured on all devices correctly and all of the assumptions that Spanning Tree Protocol (STP) relies on must be taken into account.
o   The removal of STP between the Access and Aggregation layers using Layer 3 switching results in a much more stable environment.

---
### IV) WAN:

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image021.jpg)

WANs span large areas, connecting LANs and other networks. They use diverse technologies like leased lines and satellite links. WAN topology varies based on requirements, including point-to-point or mesh configurations.

---
### V) SOHO:

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image023.jpg)

SOHO networks cater to small offices or home offices, typically with basic devices like routers and access points. They may rely on wireless connectivity and feature star or bus configurations for simplicity.

o   SOHO means small office,home office, and is a small network connecting a user or small handful of users to the internet and office resources such as servers and printers. Usually just one router and a switch, or two, plus a firewall. Unlike large businesses, small businesses don’t need large networks to support themselves and/or any employees online. These businesses are often referred to as Small Offices/Home Offices, and they can set up small office networks that cater to their online needs. These networks are called “SOHO networks.”

o   In a small office/home office (SOHO) wireless LAN, the wireless AP acts autonomously, doing all the work required to create and control the wireless LAN (WLAN). (In most enterprise WLANs, the AP does not act autonomously.) In other words, the autonomous AP communicates with the various wireless devices using 802.11 protocols and radio waves. It uses Ethernet protocols on the wired side. It converts between the differences in header formats between 802.11 and 802.3 frames before forwarding to/from 802.3 Ethernet and 802.11 wireless frames. Beyond those basic forwarding actions, the autonomous AP must perform a variety of control and management functions. The AP authenticates new devices, defines the name of the WLAN (called a service set ID, or SSID), and other details.

![small office,home office](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image024.jpg)

---
### VI) On-premise and cloud:

On-premise networks are localized within an organization's premises, managed locally. Cloud networks leverage third-party cloud services. On-premise networks may use traditional topologies, while cloud networks employ virtualized architectures for scalability. Hybrid setups are common, combining on-premise and cloud resources for flexibility.

---
---
## 1.3) Compare physical interface and cabling types
---
### 1.3.1) Single-mode fiber, multimode fiber, copper

#### Cabling and Infrastructure: 

Media is the actual physical environment through which data travels as it moves from one component to another, and it connects network devices. The most common types of net-work media are twisted-pair cable, coaxial cable, fiber-optic cable, and wireless. Each media type has specific capabilities and serves specific purposes.
#### 1) Copper Cables

#### 2) Twisted-pair cable: 
- Twisted-pair is a copper wire-based cable that can be either shielded or unshielded. Twistedpair is the most common media for network connectivity.
#### 3) Shielded Twisted Pair(STP): 
- STP stands for Shielded Twisted Pair and UTP stands for Unshielded Twisted Pair.
- STP cables reduce electrical noise and electromagnetic radiation. In other words, they help to keep the signal steady, and reduce interference with other devices. Given below is a diagram showing a typical shielded twisted pair cable

![Shielded Twisted Pair(STP)](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image025.jpg)

#### 4) Unshielded Twisted Pair(UTP): 
- UTP cables do not have shielding to reduce interference. They are designed to cancel electromagnetic interference with the way the pairs are twisted inside the cable. Unshielded twisted cables are most widely used for office LANs, though recently wireless LANs are more widely used. Unshielded cables are lightweight, thin and flexible. They are also versatile and inexpensive. A typical UTP cable cross section is shown in the figure below:

![Unshielded Twisted Pair(UTP)](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image026.jpg)
#### 5) Coaxial cable: 
- Coaxial cable consists of a hollow outer cylindrical conductor that surrounds a single inner wire conducting element. Coaxial cable offers several advantages for use in LANs. It can be run with fewer boosts from repeaters, which regenerate the signals in a network so that they can cover greater distances between network nodes than either STP or UTP cable. Coaxial cable is less expensive than fiber-optic cable, and the technology is well known. It has been used for many years for all types of data communication.
#### 6) Fiber-optic cable: 
- Fiber-optic cable is a networking medium capable of conducting modulated light trans-mission. Fiber-optic cable used for networking consists of two fibers encased in separate sheaths. That is each optical fiber is surrounded by layers of protective buffer material usually a plastic shield, then a plastic such as Kevlar, and finally, an outer jacket that provides protection for the entire cable. The plastic conforms to appropriate fire and building codes. The purpose of the Kevlar is to furnish additional cushioning and protection for the fragile, hair-thin glass fibers. Where buried fiber-optic cables are required by codes, a stainless steel wire is sometimes included for added strength. Several connectors can connect fiber to the networking device the most common is a SC connector, which has two optics, one connecting to transmit and the other connecting to receive.

![Fiber-optic cable](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image027.jpg)

---
- Fiber-optic cable does not carry electrical impulses as copper wire does. Instead, signals that represent bits are converted into pulses of light. Two types of fiber-optic cable exist:
##### Single-mode: 
- Single-mode fiber-optic cable allows only one mode (or wavelength) of light to propagate through the fiber. This type of cable is capable of higher band-width and greater distances than multimode and is often used for campus backbones. Single-mode cable uses lasers as the light-generating method and is more expensive than multimode cable. The maximum cable length of single-mode cable is 60+ km (37+ miles).

##### Multimode: 
- Multimode fiber-optic cable allows multiple modes of light to propagate through the fiber. Multimode cable is often used for workgroup applications, using Light Emitting Diodes (LEDs) as light-generating devices. The maximum length of multimode cable is 2 km (1.2 miles).
---
### 1.3.2) Connections (Ethernet shared media and point-to-point)

#### Point-to-point:
̵   Computers connected by communication channels that each connect Exactly two computers with access to full channel bandwidth.
̵   Forms a mesh or point-to-point network.
̵   Allows flexibility in communication hardware, packet formats, etc.
̵   Provides security and privacy because communication channel is not shared.
̵   Number of channels grows as square of number of computers

#### Shared or Broadcast Channel:
o   All computers connected to a shared broadcast-based communication channel and share the channel bandwidth.
o   Security issues as a result of broadcasting to all computers.
o   Cost effective due to reduced number of channels and interface hardware components.

#### Ethernet (IEEE 802.3):
̵   **10BASE-T: Standard Ethernet 10Mbps.**
̵   **100-BASE-T: Fast Ethernet 100Mbps.**
̵   **1000-BASE-T: Gigabit Ethernet 1000Mbps.**
̵   One Ethernet cable is sometimes called a segment.
̵   Limited to 500 meters in length for 10BASE-T.

#### Uses:
o   **Bus Topology:** Single coax, cable forming a segment the ether
o   **Star Topology:** Using hubs or switches (several segments).

---
---
## 1.3) Summary
---
### I) Single-mode fiber, multimode fiber, copper:

#### ![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image029.jpg)![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image030.jpg)
![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image032.jpg)

#### Single-mode fiber (SMF):
o   Single ray of light, high bandwidth, long distances.
o   Used in telecommunications and high-speed networks.

#### Multimode fiber (MMF):
̵   Multiple light modes, lower bandwidth, shorter distances.
̵   Common in LANs, data centers, and campus networks.

#### ![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image034.jpg)
#### Copper:
o   Uses electrical signals, cost-effective, easy to install.
o   Suitable for short to medium distance connections in buildings and LANs.

---
### II) Connections (Ethernet shared media and point-to-point):

#### Ethernet shared media:
̵   Multiple devices share the same medium, use CSMA/CD.
̵   Found in legacy Ethernet networks, with shared bandwidth.

#### Point-to-point:
o   Dedicated link between two devices, high reliability.
o   Used for connecting network devices, remote sites, and critical applications.

---
---
## 1.4) Identify interface and cable issues (collisions, errors, mismatch duplex, and/or speed)

#### 1. Collisions:
o   Collisions occur in Ethernet networks when two devices transmit data simultaneously on the same network segment.
o   This can happen in Ethernet shared media networks where devices compete for access to the network.
o   Collisions can lead to degraded network performance and increased packet loss.
o   Causes of collisions may include network congestion, improper cabling, or network interface card (NIC) issues.

#### 2. Errors:
̵   Errors in network interfaces can occur due to various reasons such as electrical interference, faulty cabling, or hardware issues.
̵   Errors can manifest as CRC (Cyclic Redundancy Check) errors, frame errors, or input/output errors.
̵   These errors can result in corrupted data transmission, packet loss, or network instability.
̵   Troubleshooting errors may involve checking cable connections, replacing faulty cables, or examining network equipment for hardware issues.

#### 3. Mismatch duplex:

o   Duplex mismatch occurs when two connected devices have different duplex settings for communication.
o   Duplex settings define how data is transmitted and received on a network link: half-duplex allows for bidirectional communication but not simultaneously, while full-duplex allows for simultaneous communication in both directions.
o   Mismatched duplex settings can lead to performance degradation, packet loss, and network instability.
o   To resolve duplex mismatches, ensure that both devices on the link are configured with the same duplex setting (either both set to full-duplex or both set to half-duplex).

#### 4. Mismatch speed:

- Speed mismatch occurs when two connected devices have different data transfer rates or link speeds.
- This can happen if one device is configured for a higher or lower data rate than the other device.
- Speed mismatches can lead to performance issues, data loss, and network congestion.
- To resolve speed mismatches, ensure that both devices on the link are configured to operate at the same data transfer rate (e.g., 100 Mbps, 1 Gbps, etc.).

Identifying and addressing these interface and cable issues promptly is essential to maintain network performance, reliability, and stability. Troubleshooting may involve inspecting physical connections, checking configuration settings, and replacing faulty cables or network equipment as necessary.

---
---
## 1.5) Compare TCP to UDP

Two types of Internet Protocol (IP) are Transmission Control Protocol (TCP) and User Datagram Protocol (UDP). TCP is connection oriented and data can be sent bidirectional after establishment of a connection. UDP is a simpler, connectionless Internet protocol. Multiple messages are sent as packets in chunks using UDP. TCP uses sequence numbers for tracking the receipt of the packets at the destination. UDP is more like a telegram, and any packets that does not arrive at the destination can not be determined. This function has to be done by the application layer (or higher level protocols). Hence, it (UDP) is also known as connectionless protocol. A detailed comparison of both TCP and UDP protocols is given below

|   |   |   |
|---|---|---|
|Aspect|TCP|UDP|
|**Suitability**|Suitable for applications that require high reliability, and not very critical of transmission delays.|Suitable for applications that need fast, efficient transmission, such as games. UDP's stateless nature is also useful for servers that answer small queries from a large numbers of clients.|
|**Use by protocols**|HTTP, HTTPs, FTP, SMTP, Telnet|DNS, DHCP, TFTP, SNMP, RIP, VOIP.|
|**Ordering of data packets**|TCP rearranges data packets in the order specified.|UDP has no inherent order as all packets are independent of each other. If ordering is required, it has to be managed by the application layer.|
|**Speed and reliability**|The speed for TCP is slower than UDP. When using TCP, any missing packets are retransmitted. TCP guarantees packet delivery and hence more reliable.|UDP is faster because error recovery is not attempted. It is a "best effort" protocol. There is no guarantee that a packet is received at the destination and hence less reliable than TCP.|
|**Header Size**|TCP header size is 20 bytes|UDP Header size is 8 bytes.|
|**Common Header Fields**|Source port, Destination port, Check Sum|Source port, Destination port, Check Sum|
|**Streaming of data**|Data is read as a byte stream, no distinguishing indications are transmitted to signal message (segment) boundaries.|Packets are sent individually and are checked for integrity only if they arrive. Packets have definite boundaries which are honored upon receipt, meaning a read operation at the receiver socket will yield an entire message as it was originally sent.|
|**Connection Setup**|TCP requires three packets to set up a socket connection, before any user data can be sent.|UDP is lightweight. There is no ordering of messages, no tracking connections, etc. It is a small transport layer designed on top of IP.|
|**Data Flow Control**|TCP does Flow Control. TCP requires three packets to set up a socket connection, before any user data can be sent. TCP handles reliability and congestion control.|UDP does not have an option for flow control|
|**Error Checking**|TCP does error checking and error recovery. Erroneous packets are retransmitted from the source to the destination.|UDP does error checking but simply discards erroneous packets. Error recovery is not attempted.|
|**Fields**|1. Sequence Number, 2. AcK number, 3. Data offset, 4. Reserved, 5. Control bit, 6. Window, 7. Urgent Pointer 8. Options, 9. Padding, 10. Check Sum, 11. Source port, 12. Destination port|1. Length, 2. Source port, 3. Destination port, 4. Check Sum|
|**Acknowledgement**|Acknowledges segments|No Acknowledgment|
|**Handshake**|SYN, SYN-ACK, ACK|No handshake (connectionless protocol)|

### TCP and UDP Frames

**TCP Frame:** TCP frame fields: Total 20 bytes long.
1)    Sequence Number
2)    AcK number
3)    Data offset
4)    Reserved
5)    Control bit
6)    Window
7)    Urgent Pointer
8)    Options
9)    Padding
10) Check Sum
11) Source port
12) Destination port

**UDP Frame:** UDP frame fields: Total 8 bytes long.
1)    Length
2)    Source port
3)    Destination port
4)    Check Sum

---
---
## 1.6) Configure and verify IPv4 addressing and subnetting
---
### 1. Define the Network Requirements:
o   Determine the number of hosts required in each subnet.
o   Identify the number of subnets needed for your network.

---
### 2. Choose a Subnet Mask:
̵   Select an appropriate subnet mask based on the number of hosts and subnets required.
̵   Common subnet masks include /24 (255.255.255.0), /25 (255.255.255.128), /26 (255.255.255.192), etc.

---
### 3. Subnetting:
o   Divide the IPv4 address space into smaller subnets according to the selected subnet mask.
o   Assign subnet addresses to each subnet.

---
### 4. Assign IP Addresses:
̵   Allocate IP addresses to devices within each subnet.
̵   Ensure that each device is assigned a unique IP address within its subnet.

---
### 5. Verify IP Addressing:

o   Use command-line tools such as ipconfig (Windows) or ifconfig (Linux) to verify the IP address configuration on devices.
o   Ensure that each device has the correct IP address, subnet mask, default gateway, and DNS server settings configured.

---
### 6. Test Connectivity:

̵   Verify connectivity between devices within the same subnet.
̵   Test connectivity between devices in different subnets to ensure that routing is functioning correctly.
̵   Troubleshoot and resolve any connectivity issues as needed.

---
### 7. Document the Configuration:

o   Document the assigned IP addresses, subnet masks, and network topology for future reference.
o   Keep the documentation updated as network changes occur.

---
#### Here's an example of IPv4 addressing and subnetting:

**Network Requirements:** You have a network with 100 hosts divided into 4 subnets.
**Subnet Mask:** Based on the requirements, a subnet mask of /25 (255.255.255.128) is chosen.
**Subnetting:**
o   _Subnet 1:_ 192.168.1.0/25 (Network Address: 192.168.1.0, Broadcast Address: 192.168.1.127)
o   _Subnet 2:_ 192.168.1.128/25 (Network Address: 192.168.1.128, Broadcast Address: 192.168.1.255)
o   _Subnet 3_: 192.168.2.0/25
o   _Subnet 4:_ 192.168.2.128/25

**Assign IP Addresses:** Allocate IP addresses within each subnet to devices.
**Verify IP Addressing:** Use ipconfig (Windows) or ifconfig (Linux) to verify IP address configurations.
**Test Connectivity:** Ensure devices can communicate within the same subnet and across different subnets.
**Document the Configuration:** Document the assigned IP addresses, subnet masks, and network topology.

#### Subnetting

Subnetting is nothing but creating networks within a network. Subnetting allows an organization with a single IP address (Class A /Class B /Class C) to have multiple subnetworks, thus allowing several physical networks with in the organization.

Addresses are written using decimal numbers separated by decimal points. This is called dotted decimal notation of expressing IP addresses.

|       |             |                     |                       |                  |                    |
| ----- | ----------- | ------------------- | --------------------- | ---------------- | ------------------ |
| Class | Format      | Leading Bit Pattern | Network address Range | Maximum networks | Maximum host/nodes |
| **A** | N.H.H.H     | 0                   | 0 126                 | 127              | 16,777,214         |
| **B** | N.N.H.H     | 10                  | 128 191               | 16,384           | 65,534             |
| **C** | N.N.N.H     | 110                 | 192 223               | 2,097,152        | 254                |
| **D** | Not defined | 1110                | 224 255               | Not defined      | Not defined        |
| **E** | Not defined | 1111                | 240 255               | Not defined      | Not defined        |

o   Network address of all zeros means "This network or segment.
o   Network address of all 1s means "all networks", same as hexadecimal of all Fs.
o   Network number 127 is reserved for loopback tests.
o   Host(Node) address of all zeros mean "This Host (Node)".
o   Host (Node) address of all 1s mean "all Hosts (Nodes) " on the specified network.

1) The address range and the corresponding binary values for the first octet of IP classes are as given below:

|                                                                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Class A**<br><br>**0. 0. 0. 0 = 00000000.00000000.00000000.00000000**<br><br>**127.255.255.255 = 01111111.11111111.11111111.11111111**<br><br>**0nnnnnnn.HHHHHHHH.HHHHHHHH.HHHHHHHH**   |
| **Class B**<br><br>**128. 0. 0. 0 = 10000000.00000000.00000000.00000000**<br><br>**191.255.255.255 = 10111111.11111111.11111111.11111111**<br><br>**10nnnnnn.nnnnnnnn.HHHHHHHH.HHHHHHHH** |
| **Class C**<br><br>**192. 0. 0. 0 = 11000000.00000000.00000000.00000000**<br><br>**223.255.255.255 = 11011111.11111111.11111111.11111111**<br><br>**110nnnnn.nnnnnnnn.nnnnnnnn.HHHHHHHH** |
| **Class D**<br><br>**224. 0. 0. 0 = 11100000.00000000.00000000.00000000**<br><br>**239.255.255.255 = 11101111.11111111.11111111.11111111**<br><br>**1110XXXX.XXXXXXXX.XXXXXXXX.XXXXXXXX** |
| **Class E**<br><br>**240. 0. 0. 0 = 11110000.00000000.00000000.00000000**<br><br>**255.255.255.255 = 11111111.11111111.11111111.11111111**<br><br>**1111XXXX.XXXXXXXX.XXXXXXXX.XXXXXXXX** |

2) The range of numbers from 224.0.0.0 to 239.255.255.255 are used for multicast packets. This is known as Class D address range.

[https://www.examguides.com/CCNA/cisco-ccna-19.htm](https://www.examguides.com/CCNA/cisco-ccna-19.htm)

---
---
## 1.7) Describe the need for private IPv4 addressing

Private IPv4 addressing is essential for conserving public IP addresses, enhancing security, and simplifying network design. It allows organizations to create isolated internal networks, reducing exposure to cyber threats. Private addresses, such as those defined in RFC 1918, can be reused across different networks without conflict, saving costs and administrative overhead. By providing a scalable and secure foundation for internal communications, private addressing facilitates efficient network management and operation.

---
---
## 1.8) Configure and verify IPv6 addressing and prefix

The IPv6 protocol defines a set of headers, including the basic IPv6 header and the IPv6 extension headers. The following figure shows the fields that appear in the IPv6 header and the order in which the fields appear.

![](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image036.jpg)

#### The following list describes the function of each header field.
o   Version – 4-bit version number of Internet Protocol = 6.
o   Traffic class – 8-bit traffic class field.
o   Flow label – 20-bit field. Flow label is a new field in the IPv6 header.
o   Payload length – 16-bit unsigned integer, which is the rest of the packet that follows the IPv6 header, in octets.
o   Next header – 8-bit selector. Identifies the type of header that immediately follows the IPv6 header.
o   Hop limit – 8-bit unsigned integer.
o   Source address – 128 bits. The address of the initial sender of the packet.
o   Destination address – 128 bits. The address of the intended recipient of the packet.

#### The extension header may include the following:
̵   Hop-by-Hop options
̵   Destination options
̵   Routing (specifies intermediate routers that the route must include forcing an administratively defined path)
̵   Fragment (Used to divide packets that are too large for the maximum unit (MTU) )
̵   Authentication and Encapsulating Security Payload (ESP)

#### IPv6 hosts should support the following addresses:
o   Assigned global unicast and anycast addresses (2000::/3)
o   Loopback address (::1/128)
o   Link-local address (FE80::/10), autoconfigured
o   All-nodes multicast addresses (FF01::1 and FF02::1)
o   Solicited-nodes multicast addresses (FF02::1:FF00:/104 and appending the last 24 bits of the corresponding unicast or anycast address of the device
o   Any other assigned multicast addresses (in the range FF00::/8)

#### Routers should additionally support at least the following:
̵   Subnet-router anycast address
̵   All-routers multicast addresses (FF01::2, FF02::2, and FF05::2)

#### To enable routing of IPv6 packets, we need to enable IPv6 on a router by using the command :
- `Router(config)# ipv6 unicast-routing`

#### To enable IPv6 on an interface, use the command :
- `Router(config-if)#ipv6 enable`

#### To add an IPv6 address to an interface :

`ipv6 address <address>/<prefix> [link-local] [eui-64]`

Example: `ipv6 address 2001:100:1::1/64`

To leave the interface unnumbered : `ipv6 unnumbered eth 0/0`

#### Typical commands that enable ipv6 routing are:
```
RouterA>enable

RouterA#configure terminal

RouterA(config)#ipv6 unicast-routing
```
#### IPv6 Multicast Addresses used by different routing protocols:

RIPv6 : FF02::9

OSPF speaker: FF02::5

OSPF DR and BDR: FF02::6

Multicast Address Node Local::

FF01:0:0:0:0:0:0:1 or FF01::1 All Nodes Address

FF01:0:0:0:0:0:0:2 or FF01::2 All Routers Address

Link Local:

FF02:0:0:0:0:0:0:1 or FF02::1 All Nodes Address

FF02:0:0:0:0:0:0:2 or FF02::2 All Routers Address

FF02:0:0:0:0:0:0:D or FF02::D All PIM Routers

---
---
## 1.9) Describe IPv6 address types

#### The following are true about IPv6 address format
I) The total length of IPv6 address is 128 bits`
II) The first 48 bits of the IPv6 global unicast address are used for global routing at the Internet Service Provider (ISP) level.
III) 16 bits (after the first 48-bit global unicast address) are used for subnetting, allowing organizations to subdivide their network
IV) Multicast addresses are in the range FF00::/8.
V) In an IPv6 network, a host can auto configure its IP address without the help of a DHCP server.

#### Basic rules:
  I)        ":" in every 2 bytes.
  II)        heading 0s in each block can be omitted
  III)        "0: all zeros in between :0" can be written as "::"

**IPv6 Packet Types:** IPv6 uses three types of communication: Unicast (one-to-one), Multicast (one-to-many), and Anycast (one-to-closest). The concept of Broadcast messaging is tied with the IPv4 protocol and is no longer valid in IPv6. There is no such thing as Cryptocast messaging. Figure below shows the these three types of communications

![IPv6 Packet Types](file:///C:/Users/Thulani/AppData/Local/Temp/msohtmlclip1/01/clip_image038.jpg)

Unicast 6to4 addresses (2002::/16) are used to communicate between two IPv6/IPv4 nodes over the IPv4 Internet. A 6to4 address combines the prefix 2002::/16 with the 32 bits of the public IPv4 address of the node to create a 48-bit prefix - 2002:WWXX:YYZZ::/48, where WWXX:YYZZ is the colon-hexadecimal representation of w.x.y.z, a public IPv4 address.

**The Maximum Transmission Unit (MTU)** is the largest number of bytes an individual datagram can have on a particular data communications link.

**Tunneling** is used when two hosts using IPv6 want to communicate through a region of IPv4.

o   When a packet enters and passes through the IPv4 region, IPv6 packet is encapsulated in IPv4 packet.
o   The IPv6 packet leaves the capsule when it exits the region of IPv4.
o   The source and destination fields are set to IPv4 addresses of tunnel endpoints.
o   The IPv4 Protocol field within the IPv4 header is set to 41 to indicate an encapsulated IPv6 packet.
o   When using the tunnel, firewalls and/or routers using packet filtering must be configured to allow IPv4 Protocol 41 packets to be received and forwarded.

###  Unicast (global, unique local, and link local)

Unicast addresses are used for one-to-one communication in IPv6. This means that a packet sent from a source address to a unicast address is delivered to a single, specific interface.

o  **Functionality:** Unicast addresses allow for direct communication between two devices. Each device has a unique unicast address, ensuring that data packets are accurately routed to their intended destination.
o  **Types of Unicast Addresses:** There are several types of unicast addresses, including global unicast addresses, link-local addresses, and unique local addresses.
o   **Global Unicast Addresses:** These are globally unique and routable on the IPv6 internet. They are similar to IPv4 public addresses.
o   **Link-Local Addresses:** These addresses are used for communication within a single network segment or link. They are automatically configured on all IPv6-enabled interfaces and are not routable beyond the link.
o   **Unique Local Addresses (ULA):** These addresses are used for local communications within a site or between a limited set of sites. They are not intended to be routable on the global IPv6 internet but can be used within an organization.

###  Anycast

Anycast addresses in IPv6 are used for one-to-nearest communication. A packet sent to an anycast address is delivered to the nearest interface (in terms of routing distance) identified by that address.

o  **Device Usage:** Anycast addresses can be used only by devices, not individual hosts.
o  **Source Address Restriction:** Anycast addresses must not be used as the source address of an IPv6 packet. They are designed for destination addressing only.
o  **Address Identification:** An anycast address is identified by a prefix concatenated with a series of zeros to form the interface ID. For example, 2002:db7:c058::/128 is an IPv6 anycast address.

**Example:** While 2001:db7:A00:1::1/64 is an IPv6 unicast address, 2002:db7:c058::/128 is an example of an IPv6 anycast address. In anycast addresses, the prefix is concatenated by a series of zeros.

###  Multicast

Multicast addresses are used for one-to-many communication in IPv6. A packet sent to a multicast address is delivered to all interfaces identified by that address.
o  **Scope:** Multicast addresses have defined scopes, which determine how far the multicast traffic can travel. These scopes include interface-local, link-local, site-local, and global.
o   **Prefix:** All IPv6 multicast addresses begin with the prefix FF00::/8.
o  **Groups:** Devices interested in receiving multicast traffic join specific multicast groups identified by the multicast address.
o   **Applications:** Multicast addresses are commonly used in applications like video conferencing, streaming media, and real-time data feeds, where data needs to be delivered to multiple recipients simultaneously.

###  Modified EUI-64

The Modified EUI-64 method is used to create a unique IPv6 address based on the MAC address of a network interface card (NIC).

o  **Process:** The process involves taking the 48-bit MAC address, inserting the hexadecimal value FFFE in the middle, and inverting the seventh bit of the first byte.
	**Example:** If the MAC address is 00:1A:2B:3C:4D:5E, the Modified EUI-64 address would be 021A:2BFF:FE3C:4D5E.
o  **Purpose:** This method ensures that each interface on a network has a unique IPv6 address without requiring manual configuration or the use of DHCP.
o  **Usage:** Modified EUI-64 addresses are typically used for link-local addresses but can also be used for global unicast addresses.

Each of these IPv6 address types serves a specific purpose and ensures efficient and accurate routing of data in an IPv6 network, addressing the limitations of IPv4 and supporting the growing number of devices connected to the internet.

---
---
---
## Summary

**Unicast:** One-to-one communication.
**Anycast:** One-to-nearest communication.
**Multicast:** One-to-many communication.
**Modified EUI 64:** Method to create a unique IPv6 address.

## Extra Information

Multicast addresses from FF01:: through FF0F:: are reserved, well-known addresses. To identify all nodes for the node-local and link-local scopes, the following multicast addresses are defined

_FF01::1 (node-local scope all-nodes address)_
_FF02::1 (link-local scope all-nodes address)_

To identify all routers for the node-local, link-local, and site-local scopes, the following multicast addresses are defined:

_FF01::2 (node-local scope all-routers address)_
_FF02::2 (link-local scope all-routers address)_
_FF05::2 (site-local scope all-routers address)_

#### Mapping IP Multicast address to MAC address

o   The high order 25 bits of the 48-bit MAC addresses are fixed and the low order 23 bits are variable. The high order 9 bits (out of total of 32 bits) of the IP address are not used for mapping into the MAC address. The lower 23 bits are mapped to lower 23 bits of MAC address.

o   So the multicast address 224.252.6.24 becomes 01-00-5E-7c-06-18. To use the 23 low order bits, the first octet is not used, and only the last 7 bits of the second octet is used. The third and fourth octets are converted directly to hexadecimal numbers. The second octet, 252 in binary is 11111100. If you drop the high order bit, it becomes 1111100 or 124 (in decimal), or 7c (in hexadecimal). For the next octet, 6 in hexadecimal is 06. For the last octet, 24 in hexadecimal is 18. Therefore, the MAC address corresponding to 224.252.6.24 becomes 01-00-5E-7c-06-18.

o   A dual-stack router can receive requests from both IPv4 and IPv6 clients on the same interface. This provides a smoother transition between the two protocols.

1)    Automatic 6to4 is a point-to-multi point tunneling method, where the tunnel destination is determined from the border router IPv4 address facing the IPv4 network.
2)    The border routers that delimit the 6to4 tunnel must support IPv4 and IPv6 and are not configured in pair.

3)    Automatic 6to4 can be used to connect two IPv6 networks as well an IPv6 host to an IPv6 network.

4)    IPv6 network is treated as NBMA link.

5)    The IPv4 embedded in IPv6 is used to find the other end of the tunnel.

6)    Border routers create a tunnel on a per packet basis to other IPv6 Border router.

### 1. Configure and verify IPv6 addressing and prefix:

The IPv6 protocol introduces a set of headers, including the basic IPv6 header and extension headers. The IPv6 header comprises several fields:

-          Version: A 4-bit version number indicating IPv6 (version 6).

-          Traffic class: An 8-bit field for specifying the traffic class.

-          Flow label: A 20-bit field used to label packets belonging to a particular flow.

-          Payload length: A 16-bit field indicating the length of the packet payload.

-          Next header: An 8-bit selector identifying the type of header following the IPv6 header.

-          Hop limit: An 8-bit field decremented by each node forwarding the packet; discarded if it reaches zero.

-          Source address: A 128-bit field containing the sender's address.

-          Destination address: A 128-bit field containing the intended recipient's address.

IPv6 extension headers may include Hop-by-Hop options, Destination options, Routing (specifying intermediate routers), Fragmentation (for packet division), Authentication, and Encapsulating Security Payload (ESP).

IPv6 hosts should support assigned global unicast and anycast addresses (2000::/3), loopback (::1/128), link-local (FE80::/10) addresses, all-nodes multicast (FF01::1 and FF02::1), and solicited-nodes multicast addresses (FF02::1:FF00:/104).

To configure IPv6 on routers, use the commands ipv6 unicast-routing to enable routing, ipv6 enable on interfaces to enable IPv6, and ipv6 address <address>/<prefix> to assign addresses. For example, ipv6 address 2001:100:1::1/64.

### 2. Describe IPv6 address types:

IPv6 addresses have several types and characteristics:

-          Global unicast addresses: Used for end-to-end communication over the internet; first 48 bits are for global routing.

-          Loopback address (::1/128): Represents the local host.

-          Link-local addresses (FE80::/10): Autoconfigured addresses for communication on a single link.

-          Multicast addresses (FF00::/8): Used to communicate with multiple destinations simultaneously.

-          Anycast addresses: Assigned to a group of devices, with packets sent to the nearest member.

-          6to4 addresses (2002::/16): Used to communicate between IPv6/IPv4 nodes over the IPv4 internet.

-          Maximum Transmission Unit (MTU): Must be 1280 bytes or greater for all IPv6 networks.

-          Tunneling: Used to transmit IPv6 packets over IPv4 networks, enabling communication between different protocol versions.

-          Transition mechanisms: Include Manual, Teredo, 6to4, ISATAP Tunneling, and NAT-PT for facilitating interoperability between IPv4 and IPv6 networks.

## 1.10) Verify IP parameters for Client OS (Windows, Mac OS, Linux)

To verify IP parameters on client operating systems (Windows, Mac OS, Linux), you need to use specific commands and graphical interfaces provided by each OS. Below are the steps and commands for each:

###  Windows

#### Using Command Prompt:

    1)        Open Command Prompt:

-       Press “Win + R”, type “cmd”, and press Enter.

    2)        Check IP Configuration:

-       Type “ipconfig” and press Enter.

-       Look for entries like IPv4 Address, Subnet Mask, Default Gateway, and DNS Servers.

    3)        Check Detailed IP Configuration:

-       Type “ipconfig /all” and press Enter.

-       This command provides more detailed information, including the MAC address, DHCP status, and more.

#### Using GUI:

    1)        Open Network & Internet Settings:

-       Click on the network icon in the system tray and select "Network & Internet settings".

    2)        View Network Properties:

-       Click on "Change adapter options".

-       Right-click on the network connection and select "Status".

-       Click on "Details" to view IP parameters.

###  Mac OS

#### Using Terminal:

    1)        Open Terminal:

-       Press “Command + Space”, type “Terminal”, and press Enter.

    2)        Check IP Configuration:

-       Type “ifconfig” and press Enter.

-       Look for entries under the network interface you're interested in (e.g., en0 for Ethernet, en1 for Wi-Fi).

    3)        Check Route and DNS Information:

-       Type “netstat -nr” for routing information.

-       Type “scutil --dns” for DNS server information.

#### Using GUI:

    1)        Open System Preferences:

-       Click on the Apple menu and select "System Preferences".

    2)        View Network Settings:

-       Click on "Network".

-       Select the active network connection (e.g., Wi-Fi or Ethernet) on the left.

-       Click on "Advanced" and go to the "TCP/IP" tab to view IP address, subnet mask, router, and DNS server information.

###  Linux

#### Using Terminal:

    1)        Open Terminal:

-       Depending on the distribution, find the Terminal application in the system menu or press “Ctrl + Alt + T”.

    2)        Check IP Configuration:

-       Type “ifconfig” (older method) or “ip a” (newer method) and press Enter.

-       Look for the network interface (e.g., eth0, wlan0) and corresponding IP information.

    3)        Check Route Information:

-       Type “route -n” to view the routing table.

-       Alternatively, use “ip route”.

    4)        Check DNS Information:

-       Check the contents of “/etc/resolv.conf” by typing “cat /etc/resolv.conf”.

#### Using GUI (GNOME Network Manager Example):

    1)        Open Network Settings:

-       Click on the network icon in the system tray and select "Settings" or "Network Settings".

    2)        View Connection Details:

-       Select the active network connection (e.g., Wired or Wireless).

-       Click on the settings icon or "Details" to view IP parameters like IP address, subnet mask, default gateway, and DNS servers.

These methods allow you to verify the IP parameters of client operating systems, ensuring proper network configuration and connectivity.

## 1.11) Describe wireless principles

### 1.11.1) Non overlapping Wi-Fi channels

Wireless communication usually involves a data exchange between two devices. A wireless LAN goes even further, many devices can participate in sharing the medium for data exchanges. Wireless LANs must transmit a signal over radio frequencies (RF) to move data from one device to another. Transmitters and receivers can be fixed in consistent locations, or they can be mobile and free to move around. A WiFi channel is the medium through which our wireless networks can send and receive data. The 2.4 GHz band has 11 channels and the 5 GHz band has 45 channels. Selecting the proper WiFi channel can significantly improve your WiFi coverage and performance. In the 2.4 GHz band, 1, 6, and 11 are the only non-overlapping channels. Selecting one or more of these channels is an important part of setting up your network correctly.

### 1.11.2) SSID

SSID is short for "Service Set Identifier." SSID is the name for a Wi-Fi network. An SSID is a unique ID that consists of 32 characters and is used for naming wireless networks. When multiple wireless networks overlap in a certain location, SSIDs make sure that data gets sent to the correct destination. On the AP, the network is associated with a MAC address. This network or workgroup that your clients connect to is called a Service Set Identifier (SSID). So on an AP, the SSID is a combination of MAC address and network name. This MAC address can be that of the wireless radio or another MAC address generated on the AP. When an AP offers service for only one network, it is called a Basic Service Set Identifier (BSSID). APs offer the ability to use more than one SSID. This would let you offer a Guest Network and a Corporate Network and still use the same AP. When the AP has more than one network, it is called a Multiple Basic Service Set Identifier (MBSSID). It offers service for multiple networks, but it’s the same hardware. Because it’s the same hardware and the same frequency range, users on one network share with users on another and can collide if they send at the same time.

### 1.11.3) RF

Radio transmissions use radio frequencies (RF) to transmit information. There are many different radio frequency ranges in the electromagnetic spectrum that are assigned to different services. From 800 MHz to 2.5 GHz , range of the electromagnetic spectrum, is used for various services such as digital cordless phones, pagers, personal digital assistants, laptops and personal computer memory card international association (PCMCIA) , and so on. Wireless communication takes place over free space through the use of radio frequency (RF) signals, that one device, the transmitter, sends RF signals to another device, the receiver. The transmitter can contact the receiver at any and all times, as long as both devices are tuned to the same frequency (or channel) and use the same scheme to carry the data between them. To send data across a wired link, an electrical signal is applied at one end and carried to the other end. The wire itself is continuous and conductive, so the signal can propagate rather easily. A wireless link has no physical strands of anything to carry the signal along.

### 1.11.4) Encryption

Applying a specific algorithm to data to alter the appearance of the data, making it incomprehensible to those who are not authorized to see the information. When data encryption is enabled for an AP, packets are protected with Datagram Transport Layer Security DTLS).The identification process is performed through various authentication schemes. Protecting wireless data involves security functions like encryption and frame authentication. To protect data privacy on a wireless network, the data should be encrypted. This is accomplished by encrypting the data payload in each wireless frame just prior to being transmitted, then decrypting it as it is received. The idea is to use an encryption method that the transmitter and receiver share, so the data can be encrypted and decrypted successfully. In wireless networks, each WLAN may support only one authentication and encryption scheme, so all clients must use the same encryption method when they associate. Ideally, the AP and a client are the only two devices that have the encryption keys in common so that they can understand each other’s data. No other device should know about or be able to use the same keys to eavesdrop and decrypt the data.

## 1.12) Explain virtualization fundamentals (server virtualization, containers, and VRFs)

###  Virtualization Fundamentals

Virtualization is a technology that allows the creation of multiple simulated environments or dedicated resources from a single physical hardware system. It enhances resource utilization, scalability, and flexibility in IT environments. There are various types of virtualization, each serving different purposes and offering unique benefits. Key types include server virtualization, containers, and Virtual Routing and Forwarding (VRFs).

### Server Virtualization

Server virtualization involves partitioning a physical server into multiple virtual servers, each running its own operating system and applications, independently of the others. This is achieved using a hypervisor, a software layer that manages the virtual machines (VMs).

### Hypervisor Types:

1)    **Type 1 (Bare-Metal):** Runs directly on the physical hardware, providing better performance and efficiency. Examples include **VMware ESXi, Microsoft Hyper-V, and Xen.**

2)    **Type 2 (Hosted):** Runs on top of a host operating system, which then manages the virtual machines. Examples include **VMware Workstation and Oracle VM VirtualBox.**

#### Benefits:

o   **Resource Utilization:** Improves the utilization of physical server resources by running multiple VMs on a single physical server.

o   **Isolation:** Each VM operates independently, providing strong isolation between applications.

o   **Flexibility and Scalability:** Easily create, modify, and delete virtual servers as needed, allowing for dynamic scaling of resources.

o   **Disaster Recovery:** Simplifies backup and recovery processes by allowing entire VMs to be backed up and restored.

### Containers

Containers are a lightweight form of virtualization that packages an application and its dependencies into a single unit that can run consistently across multiple environments. Unlike VMs, containers share the host system's kernel and resources, making them more efficient.

#### Container Platforms:

**Docker:** The most popular platform for containerization, offering tools to create, deploy, and manage containers.

**Kubernetes:** An orchestration platform for managing containerized applications across clusters of hosts, providing automation, scaling, and management.

#### Benefits:

**Lightweight:** Containers have minimal overhead compared to VMs because they share the host OS kernel and do not require a full OS for each instance.

**Portability:** Containers encapsulate all necessary components, ensuring applications run consistently across different environments.

**Speed:** Containers can be started, stopped, and replicated quickly, facilitating rapid development and deployment cycles.

**Microservices Architecture:** Ideal for developing and deploying microservices, allowing each service to run in its own container and be managed independently.

### Virtual Routing and Forwarding (VRF)

Virtual Routing and Forwarding (VRF) is a technology used in network virtualization that allows multiple instances of a routing table to coexist on the same router or switch. This enables the segmentation of network traffic and the isolation of different network segments.

#### Functionality:

**Segmentation:** Each VRF instance operates independently, with its own set of routing tables and interfaces. This segmentation is akin to having multiple virtual routers within a single physical device.

**Isolation:** VRFs provide traffic isolation between different users, departments, or tenants, ensuring that traffic from one VRF does not interfere with another.

**Overlapping IP Addresses:** VRFs allow the use of overlapping IP address spaces across different VRFs, which is particularly useful in multi-tenant environments.

#### Benefits:

**Security:** Enhances network security by isolating traffic and providing separate routing domains.

**Flexibility:** Simplifies network management by allowing logical segmentation without the need for additional hardware.

**Efficiency:** Reduces costs by maximizing the use of existing network infrastructure to serve multiple purposes or clients.

Understanding these virtualization fundamentals enables IT professionals to design and implement more efficient, scalable, and flexible IT infrastructures, meeting the demands of modern applications and services.

## 1.13) Describe switching concepts

Switching is a fundamental concept in network communication, enabling devices within the same network to communicate efficiently. This involves various mechanisms and protocols to manage and route data frames between devices.

### 1.13.1 MAC Learning and Aging

#### MAC Learning:

**Definition:** MAC (Media Access Control) learning is the process by which a network switch dynamically learns the MAC addresses of devices connected to its ports.

**Mechanism:** When a frame arrives at a switch port, the switch inspects the frame's source MAC address and stores it in the MAC address table, associating it with the specific port.

**Purpose:** This allows the switch to make intelligent forwarding decisions, sending frames only to the relevant port rather than broadcasting to all ports.

#### MAC Aging:

**Definition:** MAC aging refers to the process of removing MAC addresses from the MAC address table after a certain period of inactivity.

**Mechanism:** Each MAC address entry in the table has an associated timer. If a MAC address is not seen on the network within the aging time, the entry is deleted.

**Purpose:** This prevents the MAC address table from becoming stale and filled with outdated entries, ensuring efficient memory use and accurate forwarding.

### 1.13.2 Frame Switching

#### Frame Switching:

**Definition:** Frame switching is the process by which a switch receives a frame on one port and forwards it to another port based on the destination MAC address.

**Mechanism:** Upon receiving a frame, the switch checks the destination MAC address in its MAC address table:

If the destination MAC address is found, the switch forwards the frame to the corresponding port.

If the destination MAC address is not found, the frame is flooded to all ports except the one it was received on.

#### Types:

-          **Store-and-Forward:** The switch stores the entire frame, checks it for errors, and then forwards it.

-          **Cut-Through:** The switch starts forwarding the frame as soon as it reads the destination MAC address, reducing latency.

-          **Fragment-Free**: A compromise between store-and-forward and cut-through, the switch checks the first 64 bytes for errors before forwarding.

### 1.13.3 Frame Flooding

#### Frame Flooding:

**Definition:** Frame flooding occurs when a switch sends a frame out on all ports except the port it was received on.

**Conditions for Flooding:**

o   **Unknown Destination:** When the destination MAC address is not in the MAC address table.

o   **Broadcast Frames:** Frames destined for the broadcast MAC address (FF:FF:FF:FF:FF:FF) are always flooded.

o   **Multicast Frames:** Frames sent to a multicast MAC address are flooded unless IGMP snooping is used.

**Purpose:** Ensures that frames reach their intended destination when the switch does not have the necessary forwarding information.

### 1.13.4 MAC Address Table

#### MAC Address Table:

**Definition:** The MAC address table, also known as the Content Addressable Memory (CAM) table, is a database used by switches to store MAC address-to-port mappings.

**Structure:** Each entry in the table includes a MAC address, the corresponding port number, and a timer for aging.

**Function:** The table enables the switch to make forwarding decisions by mapping incoming frames to the correct output port based on the destination MAC address.

**Maintenance:** The table is dynamically updated through MAC learning and aging processes, ensuring accurate and efficient frame forwarding.

**Size and Limitations:** The size of the MAC address table can vary based on the switch model. Exceeding the table's capacity can lead to performance issues, such as increased flooding.

Understanding these switching concepts is crucial for network administrators to design, manage, and troubleshoot network infrastructures effectively. Proper utilization of MAC learning, aging, frame switching, and flooding ensures efficient data transmission and optimal network performance.

https://www.examguides.com/CCNA/cisco-ccna-41.htm