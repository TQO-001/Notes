# CCNA 200-301 Complete Study Booklet

## Table of Contents
1. [Network Fundamentals (20%)](#1-network-fundamentals-20)
2. [Network Access (20%)](#2-network-access-20)
3. [IP Connectivity (25%)](#3-ip-connectivity-25)
4. [IP Services (10%)](#4-ip-services-10)
5. [Security Fundamentals (15%)](#5-security-fundamentals-15)
6. [Automation and Programmability (10%)](#6-automation-and-programmability-10)

---

# 1. Network Fundamentals (20%)

## 1.1 Network Components

### Routers
**Function**: Layer 3 devices that forward packets between different networks using IP addresses.

**Key Features**:
- Route packets based on routing tables
- Connect different network segments
- Make forwarding decisions using longest prefix match
- Support multiple routing protocols (OSPF, EIGRP, BGP)

**Real-world Example**: A home router connects your local network (192.168.1.0/24) to your ISP's network, enabling internet access.

### Layer 2 and Layer 3 Switches

| Feature          | Layer 2 Switch                       | Layer 3 Switch           |
| ---------------- | ------------------------------------ | ------------------------ |
| Primary Function | Frame forwarding using MAC addresses | Routing + Switching      |
| OSI Layer        | Data Link (Layer 2)                  | Network + Data Link      |
| Address Learning | MAC address table                    | MAC + Routing table      |
| VLAN Support     | Yes                                  | Yes + Inter-VLAN routing |
| Example Models   | Cisco 2960                           | Cisco 3850, 9300         |

**Layer 2 Switch Example**:
```
MAC Address Table:
VLAN    MAC Address      Port
1       00:1A:2B:3C:4D   Fa0/1
1       00:2B:3C:4D:5E   Fa0/2
```

### Next-Generation Firewalls (NGFW) and IPS

**NGFW Capabilities**:
- Deep packet inspection (DPI)
- Application awareness and control
- Intrusion prevention (IPS)
- URL filtering
- Advanced malware protection

**IPS vs IDS Comparison**:

| Feature | IPS (Intrusion Prevention) | IDS (Intrusion Detection) |
|---------|---------------------------|---------------------------|
| Position | Inline with traffic | Out-of-band monitoring |
| Action | Blocks malicious traffic | Alerts only |
| Performance Impact | Can introduce latency | Minimal impact |

### Access Points (APs)
**Types**:
- **Autonomous APs**: Standalone operation with built-in management
- **Lightweight APs**: Managed by Wireless LAN Controller (WLC)
- **Cloud-managed APs**: Managed through cloud platforms

**Real-world Deployment**: Corporate offices use lightweight APs (Cisco Aironet 2800/3800) managed by a centralized WLC for consistent policy enforcement.

### Controllers
**Wireless LAN Controller (WLC)**:
- Centralized management of multiple APs
- Configuration consistency
- Security policy enforcement
- Load balancing and failover

**Software-Defined Networking (SDN) Controllers**:
- Cisco DNA Center for intent-based networking
- Centralized policy management
- Automation and orchestration

### Endpoints
**Definition**: End-user devices that communicate on the network.

**Types**:
- Computers (desktops, laptops)
- Mobile devices (smartphones, tablets)
- IoT devices (sensors, cameras, printers)
- IP phones

### Servers
**Network Server Types**:
- **DHCP Server**: Assigns IP addresses automatically
- **DNS Server**: Resolves domain names to IP addresses
- **File Server**: Provides centralized file storage
- **Web Server**: Hosts websites and web applications

### Power over Ethernet (PoE)

| PoE Standard | Power Output | Typical Applications |
|--------------|--------------|---------------------|
| PoE (802.3af) | 15.4W | IP phones, basic cameras |
| PoE+ (802.3at) | 30W | Advanced cameras, small APs |
| PoE++ (802.3bt Type 3) | 60W | High-power APs, displays |
| PoE++ (802.3bt Type 4) | 100W | High-end equipment |

**Real-world Example**: A security camera requiring 25W can be powered using PoE+ through a single Ethernet cable, eliminating the need for separate power cables.

## 1.2 Network Topology Architectures

### Two-Tier Architecture
```
Core Layer (High-speed backbone)
    |
Access Layer (End-user connections)
```

**Characteristics**:
- Collapsed core/distribution layer
- Cost-effective for smaller networks
- Limited scalability

### Three-Tier Architecture
```
Core Layer (High-speed routing/switching)
    |
Distribution Layer (Policy enforcement, routing)
    |
Access Layer (End-user connections)
```

**Benefits**:
- High availability and redundancy
- Scalable design
- Clear separation of functions
- Fault isolation

**Real-world Example**: Large enterprise campus with core switches (Cisco 9500), distribution switches (Cisco 9300), and access switches (Cisco 9200).

### Spine-Leaf Architecture
```
    Spine 1    Spine 2    Spine 3
     |  \  X  /  |  \  X  /  |
     |   \ X /   |   \ X /   |
   Leaf1  Leaf2  Leaf3  Leaf4
```

**Characteristics**:
- Every leaf connects to every spine
- Predictable latency
- Easy horizontal scaling
- Common in data centers

**Use Case**: Modern data centers running virtualized workloads and requiring east-west traffic optimization.

### WAN Architectures

| WAN Type | Technology | Bandwidth | Cost | Use Case |
|----------|------------|-----------|------|----------|
| Leased Lines | T1/T3, Metro Ethernet | 1.5Mbps - 10Gbps | High | Mission-critical applications |
| MPLS | Label switching | Variable | Medium-High | Enterprise VPN |
| SD-WAN | Internet + overlay | Variable | Low-Medium | Branch connectivity |
| Satellite | VSAT | Up to 100Mbps | Medium | Remote locations |

### Small Office/Home Office (SOHO)
**Typical Components**:
- ISR router (Cisco 1100/4000 series)
- Layer 2 switch (8-24 ports)
- Wireless access point (integrated or standalone)
- Firewall (often integrated in router)

**Example Configuration**:
```
Internet → ISR Router (NAT/Firewall) → Switch → End devices
                ↓
           Wireless AP
```

### On-Premises vs Cloud

| Aspect | On-Premises | Cloud |
|--------|-------------|-------|
| Capital Expenditure | High (equipment purchase) | Low (subscription model) |
| Operational Control | Full control | Limited control |
| Scalability | Manual, time-consuming | Rapid, automated |
| Maintenance | Internal IT team | Cloud provider |
| Security | Organization responsibility | Shared responsibility |

**Hybrid Cloud Example**: Company keeps sensitive data on-premises while using AWS for development and testing environments.

## 1.3 Physical Interface and Cabling Types

### Fiber Optic Cables

| Type | Core Diameter | Transmission Distance | Bandwidth | Applications |
|------|---------------|----------------------|-----------|--------------|
| Single-mode | 9 μm | Up to 100+ km | Very High | Long-distance, ISP backbone |
| Multimode OM1 | 62.5 μm | Up to 550m | High | Legacy installations |
| Multimode OM3 | 50 μm | Up to 300m | Higher | 10Gbps applications |
| Multimode OM4 | 50 μm | Up to 400m | Highest | 40/100Gbps applications |

**Real-world Example**: Data center uses OM4 multimode fiber for 40Gbps connections between spine and leaf switches, while single-mode fiber connects to remote sites.

### Copper Cables

| Category | Bandwidth | Distance | Applications |
|----------|-----------|----------|--------------|
| Cat5e | 1 Gbps | 100m | Basic Ethernet |
| Cat6 | 1-10 Gbps | 55-100m | Modern installations |
| Cat6a | 10 Gbps | 100m | High-performance networks |
| Cat7 | 10 Gbps | 100m | Shielded applications |

### Connection Types

**Ethernet Shared Media (Legacy)**:
- Hub-based networks
- Collision domains
- Half-duplex communication
- CSMA/CD required

**Point-to-Point**:
- Switch-based networks
- Dedicated bandwidth per port
- Full-duplex communication
- No collisions

**Example Comparison**:
```
Shared Media (Hub):     Point-to-Point (Switch):
   [PC1]                     [PC1]
     |                         |
[PC2]-[HUB]-[PC3]         [PC2]-[SW]-[PC3]
     |                         |
   [PC4]                     [PC4]

Total bandwidth: 10Mbps   Per-port bandwidth: 100Mbps
Collision domain: All     Collision domain: None
```

## 1.4 Interface and Cable Issues

### Common Issues and Troubleshooting

| Issue | Symptoms | Causes | Solutions |
|-------|----------|--------|-----------|
| Collisions | High collision counter | Shared media, bad cable | Use switches, replace cables |
| CRC Errors | Frame check sequence errors | Bad cable, EMI | Replace cable, check environment |
| Duplex Mismatch | High collisions on one side | Auto-negotiation failure | Manually configure duplex |
| Speed Mismatch | Poor performance | Different speed settings | Configure matching speeds |

**Troubleshooting Commands**:
```
show interfaces ethernet0/0
show interfaces counters errors
show ip interface brief
```

**Real-world Scenario**: A user complains of slow network performance. Investigation shows duplex mismatch - PC configured for full-duplex while switch port auto-negotiated to half-duplex.

## 1.5 TCP vs UDP Comparison

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection Type | Connection-oriented | Connectionless |
| Reliability | Guaranteed delivery | Best effort |
| Ordering | Maintains sequence | No ordering guarantee |
| Error Checking | Extensive | Basic checksum |
| Overhead | Higher | Lower |
| Speed | Slower | Faster |
| Applications | HTTP, FTP, SSH, Telnet | DNS, DHCP, SNMP, streaming |

### TCP Three-Way Handshake
```
Client                    Server
  |                         |
  |-------- SYN ----------->|
  |<----- SYN-ACK ----------|
  |-------- ACK ----------->|
  |                         |
  |    Data Transfer        |
```

### UDP Communication
```
Client                    Server
  |                         |
  |------- UDP Data ------->|
  |<------ UDP Data --------|
  |                         |
  (No connection setup)
```

**Real-world Examples**:
- **TCP**: Web browsing requires reliable data transfer
- **UDP**: DNS queries need speed over reliability
- **Streaming**: Video uses UDP for real-time delivery

## 1.6 IPv4 Addressing and Subnetting

### IPv4 Address Classes

| Class | Range | Default Subnet Mask | Network Bits | Host Bits | Private Ranges |
|-------|-------|-------------------|--------------|-----------|----------------|
| A | 1-126 | 255.0.0.0 (/8) | 8 | 24 | 10.0.0.0/8 |
| B | 128-191 | 255.255.0.0 (/16) | 16 | 16 | 172.16.0.0/12 |
| C | 192-223 | 255.255.255.0 (/24) | 24 | 8 | 192.168.0.0/16 |

### Subnetting Examples

**Example 1: Subnetting 192.168.1.0/24**

Need 4 subnets:
- Borrow 2 bits from host portion
- New subnet mask: /26 (255.255.255.192)
- Each subnet has 62 usable hosts

| Subnet | Network | Broadcast | Host Range |
|--------|---------|-----------|------------|
| 1 | 192.168.1.0/26 | 192.168.1.63 | 192.168.1.1-62 |
| 2 | 192.168.1.64/26 | 192.168.1.127 | 192.168.1.65-126 |
| 3 | 192.168.1.128/26 | 192.168.1.191 | 192.168.1.129-190 |
| 4 | 192.168.1.192/26 | 192.168.1.255 | 192.168.1.193-254 |

**Example 2: Variable Length Subnet Masking (VLSM)**

Given 172.16.0.0/16, create subnets for:
- Sales: 120 hosts
- Engineering: 58 hosts
- Management: 28 hosts
- IT: 12 hosts

Solution:
1. Sales: 172.16.1.0/25 (126 hosts)
2. Engineering: 172.16.2.0/26 (62 hosts)
3. Management: 172.16.2.64/27 (30 hosts)
4. IT: 172.16.2.96/28 (14 hosts)

### Subnetting Formulas
- **Number of subnets**: 2^(borrowed bits)
- **Hosts per subnet**: 2^(host bits) - 2
- **Subnet increment**: 256 - subnet mask value

## 1.7 Private IPv4 Addressing

### RFC 1918 Private Address Ranges

| Class | Private Range | Subnet Mask | Total Addresses |
|-------|---------------|-------------|-----------------|
| A | 10.0.0.0/8 | 255.0.0.0 | 16,777,216 |
| B | 172.16.0.0/12 | 255.240.0.0 | 1,048,576 |
| C | 192.168.0.0/16 | 255.255.0.0 | 65,536 |

### Network Address Translation (NAT)
**Purpose**: Allows private addresses to access public networks

**Types**:
- **Static NAT**: One-to-one mapping
- **Dynamic NAT**: Pool of public addresses
- **PAT (Port Address Translation)**: Many-to-one using ports

**Real-world Example**:
```
Internal Network: 192.168.1.0/24
NAT Router: 203.0.113.1 (public IP)

Internal Host 192.168.1.10:3000 → 203.0.113.1:5001
Internal Host 192.168.1.20:3000 → 203.0.113.1:5002
```

## 1.8 IPv6 Addressing and Prefix

### IPv6 Address Format
- **Length**: 128 bits (32 hexadecimal digits)
- **Format**: 8 groups of 4 hex digits separated by colons
- **Example**: 2001:0db8:85a3:0000:0000:8a2e:0370:7334

### IPv6 Address Compression Rules
1. **Leading zeros**: Can be omitted
   - 2001:0db8:0000:0042 → 2001:db8:0:42

2. **Consecutive zeros**: Replace with "::" (once per address)
   - 2001:db8:0:0:0:0:0:1 → 2001:db8::1

### IPv6 Prefix Notation
- Similar to CIDR notation in IPv4
- Example: 2001:db8::/32
- Common prefix lengths: /48 (site), /64 (subnet), /128 (host)

**Subnetting Example**:
Given 2001:db8::/32, create subnets:
- 2001:db8:1::/48 (Site 1)
- 2001:db8:2::/48 (Site 2)
- 2001:db8:1:1::/64 (Site 1, Subnet 1)
- 2001:db8:1:2::/64 (Site 1, Subnet 2)

## 1.9 IPv6 Address Types

### Unicast Addresses

| Type | Prefix | Scope | Example |
|------|--------|-------|---------|
| Global Unicast | 2000::/3 | Internet | 2001:db8::1/64 |
| Unique Local | fc00::/7 | Organization | fd00:1234::1/64 |
| Link Local | fe80::/10 | Local segment | fe80::1/64 |

**Global Unicast Structure**:
```
| 48 bits |  16 bits  |    64 bits    |
|  Prefix | Subnet ID | Interface ID  |
```

**Link Local Characteristics**:
- Automatically configured
- Not routable beyond local segment
- Required on all IPv6 interfaces
- Used for neighbor discovery

### Anycast Addresses
- **Definition**: One address assigned to multiple interfaces
- **Behavior**: Packets delivered to nearest interface
- **Use Case**: Load balancing, redundancy

**Example**: DNS root servers use anycast addresses for global distribution.

### Multicast Addresses
- **Prefix**: ff00::/8
- **Scope**: Built into address structure

| Scope | Value | Meaning |
|-------|-------|---------|
| 1 | Interface-local | Single interface |
| 2 | Link-local | Local segment |
| 5 | Site-local | Organization |
| 8 | Organization-local | Multiple sites |
| e | Global | Internet |

**Common Multicast Addresses**:
- ff02::1 - All nodes on link
- ff02::2 - All routers on link
- ff02::1:2 - All DHCP servers/relays

### Modified EUI-64
**Process to create Interface ID from MAC address**:

1. Take MAC address: 00:1A:2B:3C:4D:5E
2. Insert FFFE in middle: 00:1A:2B:FF:FE:3C:4D:5E
3. Flip 7th bit: 02:1A:2B:FF:FE:3C:4D:5E
4. Result: 021a:2bff:fe3c:4d5e

**Complete IPv6 Address**:
Prefix: 2001:db8:1:1::/64
Interface ID: 021a:2bff:fe3c:4d5e
Final: 2001:db8:1:1:021a:2bff:fe3c:4d5e/64

## 1.10 IP Parameters for Client OS

### Windows IP Configuration
```cmd
ipconfig /all                    # Show all IP configuration
ipconfig /release               # Release DHCP lease
ipconfig /renew                 # Renew DHCP lease
ipconfig /flushdns             # Clear DNS cache
netsh interface ip show config # Detailed interface info
```

### macOS/Linux IP Configuration
```bash
ifconfig                       # Show interface configuration
ip addr show                   # Show IP addresses (Linux)
ip route show                  # Show routing table
dhclient -r eth0              # Release DHCP lease
dhclient eth0                 # Renew DHCP lease
```

### Common IP Parameters to Verify

| Parameter | Windows Command | macOS/Linux Command | Purpose |
|-----------|----------------|-------------------|---------|
| IP Address | ipconfig | ifconfig/ip addr | Host identification |
| Subnet Mask | ipconfig | ifconfig/ip addr | Network boundary |
| Default Gateway | ipconfig | route -n/ip route | Router to other networks |
| DNS Servers | ipconfig /all | cat /etc/resolv.conf | Name resolution |
| DHCP Status | ipconfig /all | dhclient -v | IP assignment method |

**Troubleshooting Scenario**:
User cannot access internet:
1. Check IP configuration (APIPA 169.254.x.x indicates DHCP failure)
2. Verify default gateway connectivity (ping gateway)
3. Test DNS resolution (nslookup google.com)
4. Check physical connectivity (cable, wireless association)

## 1.11 Wireless Principles

### Non-overlapping Wi-Fi Channels

**2.4 GHz Band**:
- 11 channels in North America (1-11)
- Only 3 non-overlapping channels: 1, 6, 11
- Channel width: 20 MHz
- Each channel overlaps with adjacent channels

**5 GHz Band**:
- More available channels (36, 40, 44, 48, 149, 153, 157, 161)
- Less congested
- Support for wider channels (40, 80, 160 MHz)

**Channel Planning Example**:
```
Floor 1: APs on channels 1, 6, 11 (2.4GHz)
         APs on channels 36, 44, 149, 157 (5GHz)
         
Adjacent APs should use different channels
to avoid interference
```

### Service Set Identifier (SSID)
- **Definition**: Network name broadcast by access points
- **Length**: Up to 32 characters
- **Case sensitive**: "Network" ≠ "network"
- **Hidden SSID**: Not broadcast but still visible to analyzers

**Enterprise SSID Strategy**:
- Corporate: Company-Secure (WPA3-Enterprise)
- Guest: Company-Guest (Captive portal)
- IoT: Company-IoT (WPA2-PSK, isolated VLAN)

### Radio Frequency (RF)
**Key Concepts**:
- **Frequency**: 2.4 GHz and 5 GHz bands
- **Wavelength**: Inversely related to frequency
- **Amplitude**: Signal strength
- **Phase**: Signal timing

**RF Propagation Factors**:
- **Distance**: Signal weakens with distance (free space path loss)
- **Obstacles**: Walls, furniture cause attenuation
- **Interference**: Other devices, microwaves, Bluetooth
- **Reflection**: Signals bounce off surfaces (multipath)

**Real-world Example**: 5 GHz signals have shorter range but higher throughput compared to 2.4 GHz. Use 5 GHz for high-density areas, 2.4 GHz for coverage.

### Encryption Standards

| Standard | Security Level | Key Length | Authentication | Use Case |
|----------|---------------|------------|----------------|----------|
| WEP | Weak | 64/128-bit | Shared key | Legacy (avoid) |
| WPA | Better | 256-bit | PSK/Enterprise | Transitional |
| WPA2 | Good | 256-bit | PSK/Enterprise | Current standard |
| WPA3 | Best | 256-bit | SAE/Enterprise | Modern networks |

**WPA3 Improvements**:
- Simultaneous Authentication of Equals (SAE)
- Forward secrecy
- Protection against offline dictionary attacks
- Enhanced Open for guest networks

## 1.12 Virtualization Fundamentals

### Server Virtualization

**Type 1 Hypervisor (Bare Metal)**:
- VMware vSphere ESXi
- Microsoft Hyper-V
- Citrix XenServer
- Direct hardware access
- Better performance

**Type 2 Hypervisor (Hosted)**:
- VMware Workstation
- Oracle VirtualBox
- Runs on host OS
- Easier to deploy

**Benefits**:
- Resource optimization
- Reduced hardware costs
- Faster deployment
- Improved disaster recovery
- Better testing environments

### Containers
**Comparison with VMs**:

| Feature | Virtual Machines | Containers |
|---------|------------------|------------|
| OS | Full guest OS | Shared host OS |
| Resource Usage | Higher | Lower |
| Boot Time | Minutes | Seconds |
| Isolation | Strong | Process-level |
| Portability | Good | Excellent |

**Container Technologies**:
- Docker (most popular)
- Kubernetes (orchestration)
- OpenShift (enterprise platform)

**Real-world Example**: Microservices architecture uses containers for each service, enabling independent scaling and deployment.

### Virtual Routing and Forwarding (VRF)
**Definition**: Creates multiple isolated routing tables on a single router.

**Benefits**:
- Network segmentation
- Multi-tenancy support
- Improved security
- Simplified management

**VRF Example**:
```
Router with two VRFs:
- VRF-A: Customer A traffic (10.1.0.0/16)
- VRF-B: Customer B traffic (10.2.0.0/16)

Each VRF has separate routing table,
preventing traffic mixing
```

**Configuration Example**:
```
ip vrf CUSTOMER-A
 rd 100:1
 route-target both 100:1

interface GigabitEthernet0/0
 ip vrf forwarding CUSTOMER-A
 ip address 10.1.1.1 255.255.255.0
```

## 1.13 Switching Concepts

### MAC Learning and Aging

**MAC Address Table Operations**:
1. **Learning**: Switch learns source MAC addresses from incoming frames
2. **Forwarding**: Switch forwards frames based on destination MAC
3. **Flooding**: Unknown unicast frames flooded to all ports
4. **Aging**: Unused entries removed after aging timer expires

**MAC Learning Process**:
```
Step 1: PC-A (MAC: aaaa.aaaa.aaaa) sends frame to PC-B
Step 2: Switch learns PC-A's MAC on port Fa0/1
Step 3: Destination MAC unknown, frame flooded
Step 4: PC-B responds, switch learns PC-B's MAC on port Fa0/2
Step 5: Future communication is unicast (no flooding)
```

### Frame Switching Methods

| Method | Description | Latency | Error Detection |
|--------|-------------|---------|-----------------|
| Store-and-Forward | Receives entire frame before forwarding | Higher | Full frame check |
| Cut-Through | Forwards after reading destination MAC | Lower | Destination check only |
| Fragment-Free | Forwards after 64 bytes received | Medium | Collision fragment check |

**Modern switches primarily use store-and-forward for reliability.**

### Frame Flooding Scenarios
1. **Unknown unicast**: Destination MAC not in table
2. **Broadcast**: Destination MAC is FF:FF:FF:FF:FF:FF
3. **Multicast**: Destination MAC starts with 01:00:5E (IPv4) or 33:33 (IPv6)

**Broadcast Domain**: All devices that receive broadcast frames
- Single VLAN = Single broadcast domain
- Router boundaries separate broadcast domains

### MAC Address Table Management
**Key Parameters**:
- **Aging Time**: Default 300 seconds (5 minutes)
- **Table Size**: Varies by switch model (8K-128K entries)
- **Learning**: Enabled by default on all ports

**Troubleshooting Commands**:
```
show mac address-table               # Show all entries
show mac address-table dynamic       # Show learned entries
show mac address-table aging-time    # Show aging timer
clear mac address-table dynamic      # Clear dynamic entries
```

**Security Consideration**: MAC address table overflow attacks can fill the table, causing the switch to flood all traffic like a hub.

---

# 2. Network Access (20%)

## 2.1 Configure and Verify VLANs

### VLAN Fundamentals
**Definition**: Virtual LANs logically separate broadcast domains on a single switch.

**Benefits**:
- Improved security through segmentation
- Reduced broadcast traffic
- Simplified management
- Flexible network design
- Cost reduction

### VLAN Types and Ranges

| VLAN Range | Type | Purpose | Configurable |
|------------|------|---------|--------------|
| 0, 4095 | Reserved | System use | No |
| 1 | Default | Default VLAN | Partially |
| 2-1001 | Normal Range | Standard VLANs | Yes |
| 1002-1005 | Default | Legacy (FDDI, Token Ring) | No |
| 1006-4094 | Extended Range | Enterprise VLANs | Yes |

### Access Ports Configuration

**Data VLAN Configuration**:
```
Switch(config)# vlan 10
Switch(config-vlan)# name SALES
Switch(config-vlan)# exit

Switch(config)# interface fastethernet0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
Switch(config-if)# no shutdown
```

**Voice VLAN Configuration**:
```
Switch(config)# vlan 20
Switch(config-vlan)# name VOICE
Switch(config-vlan)# exit

Switch(config)# interface fastethernet0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10        # Data VLAN
Switch(config-if)# switchport voice vlan 20         # Voice VLAN
Switch(config-if)# no shutdown
```

**Real-world Example**: IP phone connected to PC
```
[IP Phone] ← Voice VLAN 20
     |
[PC] ← Data VLAN 10
     |
[Switch Port] ← Configured for both VLANs
```

### Default VLAN
**Characteristics**:
- VLAN 1 by default
- Cannot be deleted or renamed
- All ports initially assigned to VLAN 1
- Carries control plane traffic (CDP, VTP, STP)

**Security Best Practice**: Move all user ports out of VLAN 1
```
Switch(config)# interface range fa0/1-24
Switch(config-if-range)# switchport access vlan 10
```

### Inter-VLAN Connectivity

**Router-on-a-Stick Configuration**:
```
Router Configuration:
interface GigabitEthernet0/0
 no shutdown
 
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
 
interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

Switch Configuration:
interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20
```

**Layer 3 Switch (SVI) Configuration**:
```
Switch(config)# ip routing

Switch(config)# interface vlan 10
Switch(config-if)# ip address 192.168.10.1 255.255.255.0
Switch(config-if)# no shutdown

Switch(config)# interface vlan 20
Switch(config-if)# ip address 192.168.20.1 255.255.255.0
Switch(config-if)# no shutdown
```

### VLAN Verification Commands
```
show vlan brief                      # Show VLAN summary
show vlan id 10                      # Show specific VLAN
show interfaces switchport           # Show port VLAN assignments
show running-config interface fa0/1  # Show port configuration
```

## 2.2 Configure and Verify Interswitch Connectivity

### Trunk Ports
**Purpose**: Carry traffic for multiple VLANs between switches

**Trunk Configuration**:
```
Switch(config)# interface gigabitethernet0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan all
Switch(config-if)# switchport trunk native vlan 99
Switch(config-if)# no shutdown
```

**Trunk Modes**:

| Mode | Description | Negotiation | Use Case |
|------|-------------|-------------|----------|
| trunk | Permanent trunk | Sends DTP | Force trunk mode |
| dynamic auto | Trunk if neighbor requests | Responds to DTP | Default mode |
| dynamic desirable | Actively negotiates trunk | Sends DTP | Auto-negotiate trunk |
| access | Permanent access | No DTP | Force access mode |

### 802.1Q Encapsulation
**Frame Structure**:
```
Original Ethernet Frame:
[Dest MAC][Src MAC][Type/Length][Data][FCS]

802.1Q Tagged Frame:
[Dest MAC][Src MAC][802.1Q Tag][Type/Length][Data][FCS]
                    |-- 4 bytes --|
```

**802.1Q Tag Fields**:
- **TPID (Tag Protocol Identifier)**: 0x8100 (2 bytes)
- **PCP (Priority Code Point)**: QoS priority (3 bits)
- **DEI (Drop Eligible Indicator)**: Frame can be dropped (1 bit)
- **VID (VLAN Identifier)**: VLAN ID (12 bits)

### Native VLAN
**Definition**: VLAN that sends untagged frames on trunk links

**Characteristics**:
- Default is VLAN 1
- Must match on both ends of trunk
- Security risk if not changed
- Used for management traffic

**Native VLAN Mismatch**:
```
Switch A: Native VLAN 1    Switch B: Native VLAN 99
    |                          |
    |------- Trunk Link -------|
    
Problem: Untagged frames from VLAN 1 on Switch A
         will be placed in VLAN 99 on Switch B
```

**Security Best Practice**:
```
# Change native VLAN to unused VLAN
interface gigabitethernet0/1
 switchport trunk native vlan 999
 
# Disable DTP negotiation
switchport nonegotiate
```

### Trunk Verification Commands
```
show interfaces trunk                # Show trunk status
show interfaces gi0/1 switchport     # Detailed port info
show vlan brief                      # VLAN assignments
```

## 2.3 Layer 2 Discovery Protocols

### Cisco Discovery Protocol (CDP)

**Features**:
- Cisco proprietary
- Layer 2 protocol
- Enabled by default
- 60-second hello timer
- 180-second holdtime

**CDP Configuration**:
```
# Global CDP
cdp run                              # Enable CDP globally
no cdp run                           # Disable CDP globally

# Interface CDP
interface gigabitethernet0/1
 cdp enable                          # Enable on interface
 no cdp enable                       # Disable on interface
```

**CDP Information Exchanged**:
- Device ID (hostname)
- Local port and remote port
- Holdtime
- Capabilities (Router, Switch, Bridge)
- Platform (device model)
- IP addresses

**CDP Commands**:
```
show cdp neighbors                   # Summary of neighbors
show cdp neighbors detail            # Detailed neighbor info
show cdp interface                   # CDP-enabled interfaces
show cdp traffic                     # CDP statistics
```

### Link Layer Discovery Protocol (LLDP)

**Features**:
- IEEE 802.1AB standard
- Vendor-neutral
- Similar to CDP
- 30-second hello timer
- 120-second holdtime

**LLDP Configuration**:
```
# Global LLDP
lldp run                             # Enable LLDP globally

# Interface LLDP
interface gigabitethernet0/1
 lldp transmit                       # Send LLDP frames
 lldp receive                        # Receive LLDP frames
```

**LLDP vs CDP Comparison**:

| Feature | CDP | LLDP |
|---------|-----|------|
| Standard | Cisco proprietary | IEEE 802.1AB |
| Default Status | Enabled | Disabled |
| Hello Timer | 60 seconds | 30 seconds |
| Holdtime | 180 seconds | 120 seconds |
| Vendor Support | Cisco only | Multi-vendor |

**LLDP Commands**:
```
show lldp neighbors                  # Summary of neighbors
show lldp neighbors detail           # Detailed neighbor info
show lldp interface                  # LLDP-enabled interfaces
```

**Real-world Use Cases**:
- Network topology discovery
- Troubleshooting connectivity
- IP phone power negotiation
- Network documentation
- Security (can be security risk if enabled)

## 2.4 Configure and Verify EtherChannel

### EtherChannel Overview
**Definition**: Technology that combines multiple physical links into a single logical link

**Benefits**:
- Increased bandwidth
- Load distribution
- Redundancy and failover
- Eliminates STP blocking

### EtherChannel Protocols

| Protocol | Type | Negotiation | Compatibility |
|----------|------|-------------|---------------|
| PAgP | Cisco proprietary | Auto/Desirable | Cisco devices only |
| LACP | IEEE 802.3ad | Active/Passive | Multi-vendor |
| Static | No protocol | On | Any device |

### Link Aggregation Control Protocol (LACP)

**LACP Modes**:
- **Active**: Actively negotiate LACP
- **Passive**: Respond to LACP requests
- **On**: Force channel without negotiation

**LACP Configuration**:
```
# Layer 2 EtherChannel
interface range gigabitethernet0/1-2
 switchport mode trunk
 switchport trunk allowed vlan all
 channel-group 1 mode active
 no shutdown

interface port-channel 1
 switchport mode trunk
 switchport trunk allowed vlan all
```

**Layer 3 EtherChannel Configuration**:
```
# Physical interfaces
interface range gigabitethernet0/1-2
 no switchport
 channel-group 1 mode active
 no shutdown

# Logical interface
interface port-channel 1
 ip address 192.168.1.1 255.255.255.0
 no shutdown
```

### EtherChannel Requirements
**All member links must match**:
- Speed and duplex
- VLAN configuration
- Spanning tree settings
- Access or trunk mode

**Load Balancing Methods**:
```
port-channel load-balance src-dst-ip    # Source and destination IP
port-channel load-balance src-dst-mac   # Source and destination MAC
port-channel load-balance src-ip        # Source IP only
port-channel load-balance dst-ip        # Destination IP only
```

### EtherChannel Verification
```
show etherchannel summary            # EtherChannel status
show etherchannel port-channel       # Port-channel information
show etherchannel load-balance       # Load balancing method
show interfaces port-channel 1       # Port-channel interface status
```

**EtherChannel States**:
- **P**: Port is bundled in port-channel
- **I**: Interface is standalone
- **S**: Interface is suspended
- **H**: Interface is hot-standby
- **D**: Interface is down

**Real-world Example**: Data center switches use LACP to bundle multiple 10Gbps links for 40Gbps total bandwidth between spine and leaf switches.

## 2.5 Rapid PVST+ Spanning Tree Protocol

### Spanning Tree Purpose
**Problem**: Layer 2 loops cause broadcast storms, MAC table instability, and duplicate frames

**Solution**: STP creates loop-free topology by blocking redundant paths

### STP Versions Comparison

| Version | Standard | Convergence | VLAN Support |
|---------|----------|-------------|--------------|
| STP | IEEE 802.1D | 30-50 seconds | Single instance |
| RSTP | IEEE 802.1w | 1-6 seconds | Single instance |
| PVST+ | Cisco | 30-50 seconds | Per-VLAN |
| Rapid PVST+ | Cisco | 1-6 seconds | Per-VLAN |

### Root Bridge Selection

**Root Bridge**: Switch with lowest Bridge ID becomes root

**Bridge ID Components**:
```
Bridge ID = Bridge Priority + MAC Address
           (2 bytes)      (6 bytes)

Example:
Priority: 32768 (default)
MAC: 0000.1111.2222
Bridge ID: 32768.0000.1111.2222
```

**Root Bridge Configuration**:
```
# Method 1: Set specific priority
spanning-tree vlan 1 priority 4096

# Method 2: Set as root primary
spanning-tree vlan 1 root primary

# Method 3: Set as root secondary
spanning-tree vlan 1 root secondary
```

### Port Roles and States

**Port Roles**:

| Role | Description | Forwards Data | Learns MAC |
|------|-------------|---------------|------------|
| Root Port | Best path to root bridge | Yes | Yes |
| Designated Port | Best path to segment | Yes | Yes |
| Non-Designated Port | Blocked alternate path | No | No |

**Port States (Rapid PVST+)**:

| State | Forwards Data | Learns MAC | Duration |
|-------|---------------|------------|----------|
| Discarding | No | No | 0 seconds |
| Learning | No | Yes | 15 seconds |
| Forwarding | Yes | Yes | Ongoing |

### STP Convergence Process

1. **Elect Root Bridge**: Lowest Bridge ID
2. **Elect Root Ports**: Best path to root on each non-root switch
3. **Elect Designated Ports**: Best path to each segment
4. **Block Alternate Ports**: Remaining ports are blocked

**Path Cost Values**:

| Link Speed | STP Cost | RSTP Cost |
|------------|----------|-----------|
| 10 Mbps | 100 | 2,000,000 |
| 100 Mbps | 19 | 200,000 |
| 1 Gbps | 4 | 20,000 |
| 10 Gbps | 2 | 2,000 |

### PortFast
**Purpose**: Immediately transition access ports to forwarding state

**Configuration**:
```
# Global configuration
spanning-tree portfast default

# Interface configuration
interface fastethernet0/1
 spanning-tree portfast

# Range configuration
interface range fa0/1-24
 spanning-tree portfast
```

**Important**: Only use PortFast on ports connected to end devices, never switches!

### STP Protection Features

**Root Guard**:
- Prevents superior BPDUs on designated ports
- Protects against rogue root bridges
```
interface gigabitethernet0/1
 spanning-tree guard root
```

**Loop Guard**:
- Prevents alternate ports from becoming designated
- Protects against unidirectional link failures
```
interface gigabitethernet0/2
 spanning-tree guard loop
```

**BPDU Guard**:
- Disables port if BPDU received
- Used with PortFast
```
interface fastethernet0/1
 spanning-tree portfast
 spanning-tree bpduguard enable
```

**BPDU Filter**:
- Prevents sending/receiving BPDUs
- Disables STP on port
```
interface fastethernet0/1
 spanning-tree bpdufilter enable
```

### STP Verification Commands
```
show spanning-tree                   # STP status all VLANs
show spanning-tree vlan 1            # Specific VLAN
show spanning-tree interface fa0/1   # Interface STP status
show spanning-tree root              # Root bridge information
show spanning-tree summary           # STP summary
```

**Real-world Example**: In a three-switch triangle topology, STP will block one link to prevent loops while maintaining redundancy for failover.

## 2.6 Cisco Wireless Architectures and AP modes

### Wireless Architecture Evolution

**Autonomous APs (Legacy)**:
- Self-contained wireless solution
- Individual configuration per AP
- Suitable for small deployments
- Limited scalability and management

**Lightweight APs (Current)**:
- Centrally managed by WLC
- CAPWAP tunnel to controller
- Consistent policy enforcement
- Scalable enterprise solution

### Access Point Modes

| Mode | Description | Use Case | Management |
|------|-------------|----------|------------|
| Local | Normal operation | Standard wireless access | WLC |
| Monitor | RF monitoring only | Wireless intrusion detection | WLC |
| FlexConnect | Local switching at branch | WAN failure survivability | WLC + Local |
| Sniffer | Packet capture | Troubleshooting | WLC |
| Bridge | Point-to-point link | Building interconnection | WLC |
| SE-Connect | Spectrum analysis | RF troubleshooting | WLC |

### FlexConnect (Hybrid Remote Edge AP - HREAP)
**Purpose**: Allows branch APs to switch traffic locally when WAN fails

**Operation Modes**:
- **Connected Mode**: CAPWAP tunnel to WLC active
- **Standalone Mode**: WAN failure, local switching active

**FlexConnect Configuration**:
```
# On WLC
AP > FlexConnect > Enable FlexConnect
AP > FlexConnect > VLAN Mappings
WLAN ID 1 → VLAN 10 (Data)
WLAN ID 2 → VLAN 20 (Voice)

# FlexConnect Group
FlexConnect Groups > New
Group Name: Branch-Office-1
Add APs to group
Configure VLAN mappings for group
```

### Centralized vs. Distributed Architectures

**Centralized (Traditional)**:
```
Lightweight AP ← CAPWAP → WLC → Distribution Switch
                 (All traffic tunneled to controller)
```

**Distributed (FlexConnect)**:
```
FlexConnect AP → Local Switch → Distribution Switch
                 (Data traffic switched locally)
                 
FlexConnect AP ← CAPWAP → WLC
                 (Control traffic only)
```

### Wireless LAN Controller (WLC) Functions
- **Radio Resource Management (RRM)**: Automatic channel and power optimization
- **Security Policy Enforcement**: Centralized authentication and encryption
- **Quality of Service (QoS)**: Traffic prioritization and bandwidth control
- **Guest Access**: Captive portal and guest network isolation
- **Mobility**: Seamless roaming between APs

**WLC Deployment Models**:
- **Appliance-based**: Dedicated hardware controllers
- **Integrated**: Built into switches (Catalyst 9800)
- **Virtual**: Software-based controllers
- **Cloud**: Cisco Meraki, DNA Center

## 2.7 Physical Infrastructure Connections

### Wireless Infrastructure Components

**Access Point (AP) Connections**:
```
Power Options:
1. PoE/PoE+ from switch
2. Local power adapter
3. Power injector

Network Connection:
AP → Switch Port (Access or Trunk)
```

**Lightweight AP Requirements**:
- IP connectivity to WLC
- DHCP for IP assignment (or static)
- DNS resolution for WLC discovery
- CAPWAP tunnel establishment

### Wireless LAN Controller (WLC) Connections

**WLC Interface Types**:

| Interface | Purpose | VLAN | Configuration |
|-----------|---------|------|---------------|
| Management | WLC management | Management VLAN | Static IP |
| AP Manager | CAPWAP communication | AP VLAN | Static IP |
| Virtual | DHCP relay, guest anchor | N/A | Static IP |
| Service Port | Out-of-band management | OOB VLAN | Static IP |
| Dynamic | Client data traffic | Client VLANs | Multiple |

**WLC Physical Connections**:
```
Distribution Switch
        |
    Trunk Port (Multiple VLANs)
        |
      WLC
        |
    LAG (Link Aggregation)
        |
Multiple Physical Ports for Redundancy
```

### Access and Trunk Port Configuration

**Access Port for Lightweight AP**:
```
interface fastethernet0/1
 description "Lightweight AP"
 switchport mode access
 switchport access vlan 100          # AP Management VLAN
 power inline auto                   # Enable PoE
 spanning-tree portfast
 spanning-tree bpduguard enable
```

**Trunk Port for WLC**:
```
interface gigabitethernet0/1
 description "WLC Connection"
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,100
 channel-group 1 mode active         # If using LAG
```

### Link Aggregation (LAG) for WLC
**Purpose**: Provide redundancy and increased bandwidth

**LAG Configuration on Switch**:
```
interface range gigabitethernet0/1-2
 description "WLC LAG"
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,100
 channel-group 1 mode active

interface port-channel 1
 description "WLC Port-Channel"
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,100
```

**WLC LAG Configuration**:
```
WLC GUI: Controller > Interfaces > LAG
- Enable LAG
- Configure distribution method
- Assign physical ports to LAG
```

### VLAN Design for Wireless

**Typical VLAN Structure**:
```
VLAN 10  - Corporate Data
VLAN 20  - Voice
VLAN 30  - Guest
VLAN 100 - AP Management
VLAN 200 - WLC Management
```

**WLAN to VLAN Mapping**:
```
WLAN "Corp-Secure" → VLAN 10
WLAN "Corp-Voice"  → VLAN 20
WLAN "Guest"       → VLAN 30
```

### Troubleshooting Wireless Infrastructure
**Common Issues**:
1. **AP not joining WLC**: Check CAPWAP connectivity, firewall rules
2. **Poor performance**: Verify PoE power levels, check for interference
3. **Authentication failures**: Verify RADIUS server connectivity
4. **Roaming issues**: Check mobility groups, subnet boundaries

**Diagnostic Commands**:
```
# On WLC
show ap summary                      # AP status
show capwap summary                  # CAPWAP tunnel status
show mobility summary                # Mobility group status

# On Switch
show power inline                    # PoE status
show mac address-table | include AP-MAC  # AP connectivity
```

## 2.8 Network Device Management Access

### Console Access
**Physical Connection**:
- RJ-45 to DB-9 serial cable
- USB to serial adapter (modern laptops)
- 9600 baud, 8 data bits, no parity, 1 stop bit (9600-8-N-1)

**Terminal Emulation Software**:
- PuTTY (Windows)
- SecureCRT (Multi-platform)
- Terminal (macOS/Linux)
- HyperTerminal (Legacy Windows)

**Console Configuration**:
```
line console 0
 password cisco
 login
 logging synchronous              # Prevent log messages from interrupting
 exec-timeout 30 0               # 30-minute timeout
```

### Telnet Access
**Characteristics**:
- Clear text transmission (insecure)
- TCP port 23
- Remote command-line access
- Legacy protocol

**Telnet Configuration**:
```
line vty 0 4
 password cisco
 login
 transport input telnet

# Enable secret required for privileged mode
enable secret cisco123
```

**Security Issues**:
- Passwords transmitted in clear text
- No encryption of session data
- Vulnerable to eavesdropping
- Should be replaced with SSH

### SSH Access
**Advantages over Telnet**:
- Encrypted authentication and session
- Strong cryptographic protection
- Industry standard for secure remote access
- Supports key-based authentication

**SSH Configuration**:
```
# Generate RSA key pair
crypto key generate rsa modulus 2048

# Configure domain name
ip domain-name company.com

# Configure SSH version
ip ssh version 2
ip ssh time-out 60
ip ssh authentication-retries 3

# Configure VTY lines
line vty 0 4
 login local
 transport input ssh

# Create local user account
username admin privilege 15 secret cisco123
```

**SSH Key-based Authentication**:
```
# Generate public key on client
ssh-keygen -t rsa -b 2048

# Copy public key to device
ip ssh pubkey-chain
 username admin
  key-string
   [paste public key here]
```

### HTTP/HTTPS Web Management
**HTTP Configuration (insecure)**:
```
ip http server
ip http authentication local
username admin privilege 15 secret cisco123
```

**HTTPS Configuration (secure)**:
```
ip http secure-server
ip http authentication local
crypto key generate rsa modulus 2048
```

**Web Management Capabilities**:
- GUI-based configuration
- Monitoring and diagnostics
- Software updates
- Certificate management

### TACACS+ Authentication
**Characteristics**:
- Cisco proprietary (TACACS+)
- TCP-based (port 49)
- Encrypts entire packet
- Separates authentication, authorization, accounting

**TACACS+ Configuration**:
```
# Configure TACACS+ server
tacacs-server host 192.168.1.100 key sharedkey123
tacacs-server timeout 5
tacacs-server directed-request

# Configure AAA
aaa new-model
aaa authentication login default group tacacs+ local
aaa authorization exec default group tacacs+ local
aaa accounting exec default start-stop group tacacs+

# Configure VTY lines
line vty 0 4
 login authentication default
 authorization exec default
 accounting exec default
```

### RADIUS Authentication
**Characteristics**:
- Industry standard (RFC 2865)
- UDP-based (ports 1812/1813)
- Encrypts only password
- Combines authentication and authorization

**RADIUS Configuration**:
```
# Configure RADIUS server
radius-server host 192.168.1.101 auth-port 1812 acct-port 1813 key sharedkey123
radius-server timeout 5
radius-server retransmit 3

# Configure AAA
aaa new-model
aaa authentication login default group radius local
aaa authorization exec default group radius local
aaa accounting exec default start-stop group radius
```

### Cloud-Managed Networks
**Cisco Meraki**:
- Cloud-based management platform
- Zero-touch provisioning
- Centralized policy management
- Real-time monitoring and analytics

**Cisco DNA Center**:
- On-premises management platform
- Intent-based networking
- Automation and assurance
- Integration with cloud services

**Benefits of Cloud Management**:
- Simplified deployment and management
- Automatic software updates
- Global visibility and control
- Reduced on-site expertise requirements

### Management Access Security Best Practices

| Practice | Implementation | Benefit |
|----------|----------------|---------|
| Disable Telnet | transport input ssh | Encrypted communication |
| Use SSH v2 | ip ssh version 2 | Strong encryption |
| Implement AAA | TACACS+/RADIUS | Centralized authentication |
| Use Local Fallback | local authentication | Backup access method |
| Set Timeouts | exec-timeout | Automatic session closure |
| Monitor Access | logging/SNMP | Audit trail |

## 2.9 Wireless LAN GUI Configuration

### WLAN Creation Process
**Basic WLAN Configuration Steps**:
1. Access WLC web interface (https://wlc-ip)
2. Navigate to WLANs tab
3. Create new WLAN
4. Configure SSID and basic parameters
5. Set security settings
6. Configure QoS profile
7. Apply advanced settings
8. Enable WLAN

### WLAN Security Settings

**Security Policies Available**:

| Security Type | Authentication | Encryption | Use Case |
|---------------|----------------|------------|----------|
| Open | None | None | Public hotspots (not recommended) |
| Enhanced Open | OWE | WPA3 | Secure public access |
| WPA2-PSK | Pre-shared key | AES | Small networks |
| WPA3-PSK | SAE | AES | Modern small networks |
| WPA2-Enterprise | 802.1X | AES | Corporate networks |
| WPA3-Enterprise | 802.1X | AES | Modern corporate networks |

**WPA2-Enterprise Configuration**:
```
WLAN Configuration:
- Security > Layer 2 Security: WPA+WPA2
- Authentication Method: 802.1X
- Encryption: AES
- RADIUS Servers:
  * Primary: 192.168.1.100:1812
  * Shared Secret: RadiusKey123
  * Accounting: 192.168.1.100:1813
```

### QoS Profiles
**Default QoS Profiles**:

| Profile | DSCP Marking | Queue | Typical Use |
|---------|--------------|-------|-------------|
| Platinum | 46 (EF) | Voice | VoIP traffic |
| Gold | 34 (AF41) | Video | Video conferencing |
| Silver | 18 (AF21) | Best Effort | Standard data |
| Bronze | 10 (AF11) | Background | File transfers |

**Custom QoS Profile Configuration**:
```
QoS Profile Settings:
- Average Data Rate: 50 Mbps
- Burst Data Rate: 100 Mbps
- Average Real-time Rate: 10 Mbps
- Burst Real-time Rate: 20 Mbps
- DSCP Marking: AF31 (26)
```

### Advanced WLAN Settings

**Band Selection**:
- **Dual Band Operation**: 2.4 GHz and 5 GHz
- **Band Steering**: Prefer 5 GHz for capable clients
- **Load Balancing**: Distribute clients across APs

**Client Load Balancing**:
```
Advanced Settings:
- Load Balancing: Enable
- Window Size: 5 clients
- Denial Threshold: 3 attempts
```

**Coverage Hole Detection**:
```
Advanced Settings:
- Coverage Hole Detection: Enable
- Data RSSI Threshold: -80 dBm
- Voice RSSI Threshold: -75 dBm
- Detection Threshold: 50%
```

### WLAN Mobility and Roaming
**Mobility Groups**:
- Enable seamless roaming between controllers
- Share client database between WLCs
- Maintain session state during roaming

**Fast Roaming Technologies**:
- **802.11r (Fast BSS Transition)**: Pre-authentication
- **802.11k (Radio Resource Management)**: Neighbor reports
- **802.11v (Wireless Network Management)**: BSS transition

### Guest Network Configuration
**Guest WLAN Design**:
```
WLAN Settings:
- SSID: Company-Guest
- Security: Open + Web Authentication
- VLAN: 30 (Guest VLAN)
- Interface: Dynamic (Guest)
- ACL: Guest-Access-Only

Web Authentication:
- Redirect URL: https://portal.company.com
- Session Timeout: 8 hours
- Idle Timeout: 30 minutes
```

**Guest Access Process**:
1. Client connects to open SSID
2. Web traffic redirected to captive portal
3. User accepts terms/provides credentials
4. Access granted with limitations
5. Session terminated after timeout

### Troubleshooting WLAN Issues
**Common Configuration Problems**:
- Incorrect VLAN mapping
- Missing RADIUS server configuration
- Improper security settings
- QoS profile mismatches

**Diagnostic Tools in WLC GUI**:
- **Monitor > Clients**: Client connection status
- **Monitor > Access Points**: AP status and statistics
- **Commands > Ping**: Network connectivity tests
- **Management > Tech Support**: Diagnostic information

**Client Connection Troubleshooting Steps**:
1. Verify SSID is enabled and broadcasting
2. Check security configuration matches client
3. Verify VLAN and interface configuration
4. Test RADIUS authentication (if applicable)
5. Check QoS profile assignments
6. Review client logs and statistics

---

# 3. IP Connectivity (25%)

## 3.1 Routing Table Components

### Routing Table Structure
**Definition**: Database containing network destinations and how to reach them.

**Routing Table Entry Components**:
```
R    192.168.2.0/24 [120/1] via 10.1.1.2, 00:00:23, FastEthernet0/0
|    |              |      |    |         |         |
|    |              |      |    |         |         └─ Outgoing Interface
|    |              |      |    |         └─ Age of route
|    |              |      |    └─ Next-hop IP address
|    |              |      └─ Metric/Hop count
|    |              └─ Administrative Distance
|    └─ Network/Subnet mask
└─ Routing Protocol Code
```

### Routing Protocol Codes

| Code | Protocol | Administrative Distance | Metric Type |
|------|----------|------------------------|-------------|
| C | Connected | 0 | N/A |
| S | Static | 1 | N/A |
| R | RIP | 120 | Hop count |
| D | EIGRP | 90 (internal), 170 (external) | Composite |
| O | OSPF | 110 | Cost |
| B | BGP | 20 (eBGP), 200 (iBGP) | Path attributes |
| i | IS-IS | 115 | Cost |

### Prefix and Network Mask
**CIDR Notation Examples**:
```
192.168.1.0/24    = 255.255.255.0    (Class C network)
10.0.0.0/8        = 255.0.0.0        (Class A network)
172.16.0.0/16     = 255.255.0.0      (Class B network)
192.168.1.0/25    = 255.255.255.128  (Subnet of /24)
```

**Subnet Mask Functions**:
- Defines network and host portions
- Determines network boundaries
- Used in longest prefix matching

### Next Hop
**Definition**: IP address of the next router in the path to destination.

**Next Hop Types**:
- **Directly Connected**: Exit interface only
- **Recursive**: Next-hop IP address
- **Fully Specified**: Next-hop IP + exit interface

**Examples**:
```
# Directly connected
ip route 192.168.2.0 255.255.255.0 FastEthernet0/1

# Next-hop IP
ip route 192.168.2.0 255.255.255.0 10.1.1.2

# Fully specified
ip route 192.168.2.0 255.255.255.0 FastEthernet0/0 10.1.1.2
```

### Administrative Distance
**Purpose**: Trustworthiness rating of routing information sources.

**Default Administrative Distances**:

| Route Source | AD Value | Trustworthiness |
|--------------|----------|----------------|
| Connected | 0 | Most trusted |
| Static | 1 | Very trusted |
| EIGRP Summary | 5 | High |
| External BGP | 20 | High |
| Internal EIGRP | 90 | Good |
| OSPF | 110 | Good |
| IS-IS | 115 | Good |
| RIP | 120 | Low |
| External EIGRP | 170 | Lower |
| Internal BGP | 200 | Lowest |

**Administrative Distance in Action**:
```
Router learns same network from multiple sources:
- EIGRP: 192.168.2.0/24 [90/156160]
- OSPF:  192.168.2.0/24 [110/65]
- RIP:   192.168.2.0/24 [120/2]

Router chooses EIGRP route (lowest AD = 90)
```

### Metric
**Definition**: Value used by routing protocols to determine best path.

**Metric Types by Protocol**:

| Protocol | Metric | Factors |
|----------|--------|---------|
| RIP | Hop count | Number of routers |
| OSPF | Cost | Bandwidth-based |
| EIGRP | Composite | Bandwidth, Delay, Load, Reliability |
| BGP | Path attributes | AS-path, Local Preference, etc. |

**OSPF Cost Calculation**:
```
Cost = Reference Bandwidth / Interface Bandwidth

Default Reference Bandwidth = 100 Mbps

Examples:
Fast Ethernet (100 Mbps): 100/100 = 1
Gigabit Ethernet (1000 Mbps): 100/1000 = 1
10 Gigabit Ethernet: 100/10000 = 1

# Modify reference bandwidth for modern networks
auto-cost reference-bandwidth 10000  # Sets to 10 Gbps
```

### Gateway of Last Resort
**Definition**: Default route used when no specific route exists for a destination.

**Default Route Configuration**:
```
# Static default route
ip route 0.0.0.0 0.0.0.0 192.168.1.1

# Default route via interface
ip route 0.0.0.0 0.0.0.0 GigabitEthernet0/0

# OSPF default route
router ospf 1
 default-information originate
```

**Gateway of Last Resort Display**:
```
Router# show ip route
Codes: L - local, C - connected, S - static, R - RIP...

Gateway of last resort is 192.168.1.1 to network 0.0.0.0

S*   0.0.0.0/0 [1/0] via 192.168.1.1
```

### Routing Table Lookup Process
1. **Exact Match**: Look for exact network match
2. **Longest Prefix Match**: Find most specific match
3. **Default Route**: Use if no specific match found
4. **Drop Packet**: If no route available

**Longest Prefix Match Example**:
```
Routing Table:
172.16.0.0/16    via 10.1.1.1
172.16.1.0/24    via 10.1.1.2
172.16.1.128/25  via 10.1.1.3
0.0.0.0/0        via 10.1.1.4

Destination: 172.16.1.150
Best Match: 172.16.1.128/25 (/25 is most specific)
Next Hop: 10.1.1.3
```

## 3.2 Router Forwarding Decision Process

### Forwarding Decision Hierarchy
**Decision Process Order**:
1. **Longest Prefix Match**: Most specific route wins
2. **Administrative Distance**: Lower AD preferred (if same prefix)
3. **Metric**: Lower metric preferred (if same AD and prefix)
4. **Load Balancing**: Equal cost paths

### Longest Prefix Match Examples

**Example 1: Multiple Route Matches**
```
Routing Table:
10.0.0.0/8       [1/0] via 192.168.1.1
10.1.0.0/16      [1/0] via 192.168.1.2
10.1.1.0/24      [1/0] via 192.168.1.3
10.1.1.128/25    [1/0] via 192.168.1.4

Packet to 10.1.1.200:
- Matches: /8, /16, /24
- Best match: 10.1.1.0/24 (longest prefix)
- Forward via 192.168.1.3
```

**Example 2: Administrative Distance Comparison**
```
Two routes to same network:
192.168.2.0/24 [90/156160] via 10.1.1.2  (EIGRP)
192.168.2.0/24 [110/65] via 10.1.1.3     (OSPF)

EIGRP chosen due to lower AD (90 < 110)
OSPF metric (65) is irrelevant
```

### Routing Protocol Metrics

**RIP Metric (Hop Count)**:
```
Network path: R1 → R2 → R3 → R4 → Destination
RIP Metric: 4 hops
Maximum: 15 hops (16 = unreachable)
```

**OSPF Cost Calculation**:
```
Path: R1 → R2 → R3 → Destination
R1-R2: GigE (cost 1)
R2-R3: FastE (cost 1)  
R3-Dest: Serial T1 (cost 64)
Total Cost: 1 + 1 + 64 = 66
```

**EIGRP Composite Metric**:
```
Default Formula:
Metric = 256 * (K1*Bandwidth + K2*Load + K3*Delay + K4*Reliability)

K values (default):
K1 = 1 (Bandwidth)
K2 = 0 (Load - disabled)
K3 = 1 (Delay)
K4 = 0 (Reliability - disabled)
K5 = 0 (MTU - disabled)

Simplified: Metric = 256 * (Bandwidth + Delay)
```

### Equal Cost Multi-Path (ECMP)
**Definition**: Load balancing across multiple equal-cost paths.

**ECMP Configuration**:
```
# Maximum paths (default is 4)
router ospf 1
 maximum-paths 6

router eigrp 100
 maximum-paths 8

# Verify load balancing
show ip route 192.168.2.0
```

**ECMP Example**:
```
R    192.168.2.0/24 [120/1] via 10.1.1.2, 00:00:15, FastEthernet0/0
                    [120/1] via 10.1.2.2, 00:00:15, FastEthernet0/1

Two equal-cost paths available
Traffic load-balanced between both
```

### Unequal Cost Load Balancing (EIGRP Only)
**Variance Configuration**:
```
router eigrp 100
 variance 2

# Allows paths up to 2x the best metric
# If best path = 100, paths up to 200 included
```

### Forwarding Process Summary
```
1. Receive packet on interface
2. Check destination IP address
3. Perform routing table lookup:
   a. Find longest prefix match
   b. If multiple matches, use lowest AD
   c. If same AD, use lowest metric
   d. If equal cost, load balance
4. Forward packet to next hop
5. Decrement TTL and update checksums
```

## 3.3 Configure and Verify Static Routing

### Static Route Types

**Network Route**:
```
# Routes to specific networks
ip route 192.168.2.0 255.255.255.0 10.1.1.2
ip route 172.16.0.0 255.255.0.0 GigabitEthernet0/1
```

**Host Route**:
```
# Routes to specific hosts (/32 subnet mask)
ip route 192.168.1.100 255.255.255.255 10.1.1.2
ip route 10.2.2.2 255.255.255.255 Serial0/0/0
```

**Default Route**:
```
# Gateway of last resort
ip route 0.0.0.0 0.0.0.0 203.0.113.1
ip route 0.0.0.0 0.0.0.0 GigabitEthernet0/0
```

### Static Route Configuration Methods

**Next-Hop IP Address**:
```
Router(config)# ip route 192.168.2.0 255.255.255.0 10.1.1.2

Advantages:
- Works with broadcast and point-to-point links
- Router performs recursive lookup

Disadvantages:
- Additional routing table lookup required
- Next-hop must be directly connected
```

**Exit Interface**:
```
Router(config)# ip route 192.168.2.0 255.255.255.0 Serial0/0/0

Advantages:
- No recursive lookup needed
- Faster forwarding

Disadvantages:
- Only works with point-to-point interfaces
- Broadcast interfaces need ARP resolution
```

**Fully Specified**:
```
Router(config)# ip route 192.168.2.0 255.255.255.0 GigE0/0 10.1.1.2

Advantages:
- Best of both methods
- Works with all interface types
- No recursive lookup for broadcast interfaces

Use Case:
- Broadcast interfaces (Ethernet)
- Backup routes
```

### IPv6 Static Routing

**IPv6 Static Route Syntax**:
```
ipv6 route destination/prefix-length next-hop-address [interface]

Examples:
ipv6 route 2001:db8:2::/64 2001:db8:1::2
ipv6 route ::/0 GigabitEthernet0/0 fe80::1
ipv6 route 2001:db8:3::/64 Serial0/0/0
```

**IPv6 Link-Local Next Hop**:
```
# Must specify exit interface with link-local next hop
ipv6 route 2001:db8:2::/64 GigE0/0 fe80::1

# Link-local addresses are not globally unique
# Interface specification resolves ambiguity
```

### Floating Static Routes
**Definition**: Backup static routes with higher administrative distance.

**Configuration Example**:
```
# Primary route (AD = 1)
ip route 192.168.2.0 255.255.255.0 10.1.1.2

# Backup route (AD = 5)
ip route 192.168.2.0 255.255.255.0 10.1.2.2 5

# If primary fails, backup activates
```

**Use Cases**:
- Dial-on-demand backup
- Load balancing with unequal costs
- Policy-based routing alternatives

**Advanced Floating Static Example**:
```
# Primary WAN link
ip route 0.0.0.0 0.0.0.0 203.0.113.1

# Backup satellite link (higher AD and cost)
ip route 0.0.0.0 0.0.0.0 198.51.100.1 10

# Only activates if primary fails
```

### Static Route Verification

**Show Commands**:
```
show ip route                        # All routes
show ip route static                 # Static routes only
show ip route 192.168.2.0            # Specific network
show running-config | include ip route  # Configuration
```

**IPv6 Verification**:
```
show ipv6 route                      # All IPv6 routes
show ipv6 route static               # Static IPv6 routes
show ipv6 route 2001:db8:2::/64     # Specific network
```

### Troubleshooting Static Routes

**Common Issues**:

| Problem | Symptoms | Solution |
|---------|----------|----------|
| Incorrect next hop | Route in table, no connectivity | Verify next-hop reachability |
| Wrong subnet mask | Partial connectivity | Check mask accuracy |
| Missing return route | One-way connectivity | Configure return path |
| Interface down | Route not in table | Check interface status |

**Troubleshooting Steps**:
1. Verify route in routing table
2. Check next-hop reachability
3. Verify interface status
4. Test with ping/traceroute
5. Check return path routing

**Debug Commands** (use carefully):
```
debug ip routing                     # Routing table changes
debug ip packet                      # Packet forwarding
```

### Static Routing Design Examples

**Hub-and-Spoke Network**:
```
Hub Router:
ip route 192.168.1.0 255.255.255.0 10.1.1.2  # To Spoke 1
ip route 192.168.2.0 255.255.255.0 10.1.2.2  # To Spoke 2

Spoke 1 Router:
ip route 0.0.0.0 0.0.0.0 10.1.1.1             # Default to Hub
ip route 192.168.2.0 255.255.255.0 10.1.1.1   # To Spoke 2 via Hub

Spoke 2 Router:
ip route 0.0.0.0 0.0.0.0 10.1.2.1             # Default to Hub
ip route 192.168.1.0 255.255.255.0 10.1.2.1   # To Spoke 1 via Hub
```

**Redundant Static Routes**:
```
# Primary path
ip route 192.168.100.0 255.255.255.0 10.1.1.2

# Secondary path (higher AD)
ip route 192.168.100.0 255.255.255.0 10.2.2.2 20

# Tertiary path (highest AD)
ip route 192.168.100.0 255.255.255.0 10.3.3.2 30
```

## 3.4 Configure and Verify Single Area OSPFv2

### OSPF Overview
**Open Shortest Path First (OSPF)**:
- Link-state routing protocol
- Uses Dijkstra's algorithm
- Hierarchical design with areas
- Fast convergence
- VLSM and CIDR support

### OSPF Areas
**Area Types**:
- **Backbone Area (Area 0)**: Central area, all other areas connect to it
- **Standard Area**: Normal OSPF area with full LSA database
- **Stub Area**: Blocks external LSAs (Type 5)
- **Totally Stubby Area**: Blocks external and summary LSAs
- **NSSA**: Not-So-Stubby Area, allows limited external routes

**Single Area Design**:
```
All routers in Area 0
Simple configuration
No area hierarchy
Suitable for small to medium networks
```

### OSPF Router Configuration

**Basic OSPF Configuration**:
```
Router(config)# router ospf 1
Router(config-router)# network 10.1.1.0 0.0.0.255 area 0
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router(config-router)# router-id 1.1.1.1
```

**Interface-Specific Configuration**:
```
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip ospf 1 area 0
Router(config-if)# ip ospf cost 10
Router(config-if)# ip ospf hello-interval 5
Router(config-if)# ip ospf dead-interval 20
```

### OSPF Network Types

| Network Type | Hello/Dead Timer | DR/BDR Election | Use Case |
|--------------|------------------|-----------------|----------|
| Broadcast | 10/40 seconds | Yes | Ethernet, LAN |
| Point-to-Point | 10/40 seconds | No | Serial, P2P links |
| Point-to-Multipoint | 30/120 seconds | No | Frame Relay |
| NBMA | 30/120 seconds | Yes | Frame Relay, ATM |

**Network Type Configuration**:
```
interface Serial0/0/0
 ip ospf network point-to-point

interface GigabitEthernet0/0
 ip ospf network broadcast
```

### Neighbor Adjacencies

**OSPF Neighbor States**:
1. **Down**: No hello packets received
2. **Init**: Hello received, but not bidirectional
3. **2-Way**: Bidirectional communication established
4. **ExStart**: Master/slave relationship established
5. **Exchange**: Database description packets exchanged
6. **Loading**: Link state request/update/acknowledgment
7. **Full**: Adjacency established, databases synchronized

**Neighbor Adjacency Requirements**:
- Same area ID
- Same subnet
- Same hello/dead timers
- Same network type
- Same authentication
- Same stub area flag

**Verification Commands**:
```
show ip ospf neighbor               # Neighbor status
show ip ospf neighbor detail        # Detailed neighbor info
show ip ospf interface              # OSPF interface status
show ip ospf database               # OSPF database
```

### Point-to-Point Networks

**Characteristics**:
- No DR/BDR election needed
- Direct adjacency between two routers
- Common on WAN links
- Hello timer: 10 seconds
- Dead timer: 40 seconds

**Point-to-Point Configuration**:
```
interface Serial0/0/0
 ip address 10.1.1.1 255.255.255.252
 ip ospf 1 area 0
 ip ospf network point-to-point
 ip ospf cost 64
```

### Broadcast Networks and DR/BDR Election

**Designated Router (DR) Purpose**:
- Reduces LSA flooding on multi-access networks
- Central point for LSA exchange
- Only DR and BDR maintain full adjacencies with all routers

**DR/BDR Election Process**:
1. Highest OSPF priority wins (0-255, default 1)
2. If priority tied, highest Router ID wins
3. Priority 0 = never DR/BDR
4. DR/BDR elections are not preemptive

**DR/BDR Configuration**:
```
interface GigabitEthernet0/0
 ip ospf priority 100              # High priority for DR
 
interface GigabitEthernet0/1
 ip ospf priority 50               # Medium priority for BDR
 
interface GigabitEthernet0/2
 ip ospf priority 0                # Never DR/BDR
```

**DR/BDR Verification**:
```
show ip ospf interface GigE0/0
Router ID 1.1.1.1, Network Type BROADCAST, Cost: 1
Designated Router (ID) 1.1.1.1, Interface address 192.168.1.1
Backup Designated router (ID) 2.2.2.2, Interface address 192.168.1.2
```

### Router ID

**Router ID Selection Order**:
1. Manually configured router-id
2. Highest IP address on loopback interface
3. Highest IP address on active physical interface

**Router ID Configuration**:
```
router ospf 1
 router-id 1.1.1.1

# Verify Router ID
show ip ospf

# Force Router ID change (requires OSPF restart)
clear ip ospf process
```

**Best Practice**: Use loopback interfaces for stable Router IDs
```
interface Loopback0
 ip address 1.1.1.1 255.255.255.255

router ospf 1
 router-id 1.1.1.1
```

### OSPF Cost Calculation

**Default Cost Formula**:
```
Cost = Reference Bandwidth / Interface Bandwidth

Default Reference Bandwidth = 100 Mbps (100,000,000 bps)
```

**Interface Costs**:

| Interface Type | Bandwidth | Default Cost |
|----------------|-----------|--------------|
| Serial (T1) | 1.544 Mbps | 64 |
| Ethernet | 10 Mbps | 10 |
| Fast Ethernet | 100 Mbps | 1 |
| Gigabit Ethernet | 1000 Mbps | 1 |
| 10 Gigabit Ethernet | 10000 Mbps | 1 |

**Cost Modification**:
```
# Change reference bandwidth globally
router ospf 1
 auto-cost reference-bandwidth 10000    # 10 Gbps reference

# Set interface cost manually
interface GigabitEthernet0/0
 ip ospf cost 50

# Modify interface bandwidth (affects cost)
interface Serial0/0/0
 bandwidth 256                          # 256 kbps
```

### OSPF Configuration Example

**Three-Router OSPF Network**:
```
R1 Configuration:
interface Loopback0
 ip address 1.1.1.1 255.255.255.255
 
interface GigabitEthernet0/0
 ip address 192.168.12.1 255.255.255.0
 
interface Serial0/0/0
 ip address 10.1.13.1 255.255.255.252
 
router ospf 1
 router-id 1.1.1.1
 network 192.168.12.0 0.0.0.255 area 0
 network 10.1.13.0 0.0.0.3 area 0
 network 1.1.1.1 0.0.0.0 area 0

R2 Configuration:
interface Loopback0
 ip address 2.2.2.2 255.255.255.255
 
interface GigabitEthernet0/0
 ip address 192.168.12.2 255.255.255.0
 
interface GigabitEthernet0/1
 ip address 192.168.23.2 255.255.255.0
 
router ospf 1
 router-id 2.2.2.2
 network 192.168.12.0 0.0.0.255 area 0
 network 192.168.23.0 0.0.0.255 area 0
 network 2.2.2.2 0.0.0.0 area 0

R3 Configuration:
interface Loopback0
 ip address 3.3.3.3 255.255.255.255
 
interface GigabitEthernet0/0
 ip address 192.168.23.3 255.255.255.0
 
interface Serial0/0/0
 ip address 10.1.13.3 255.255.255.252
 
router ospf 1
 router-id 3.3.3.3
 network 192.168.23.0 0.0.0.255 area 0
 network 10.1.13.0 0.0.0.3 area 0
 network 3.3.3.3 0.0.0.0 area 0
```

### OSPF Verification Commands

```
show ip ospf                         # OSPF process information
show ip ospf neighbor                # Neighbor relationships
show ip ospf interface               # OSPF-enabled interfaces
show ip ospf database                # Link state database
show ip route ospf                   # OSPF routes only
show ip ospf border-routers          # ABR and ASBR information
```

**Detailed Verification Example**:
```
R1# show ip ospf neighbor
Neighbor ID     Pri   State           Dead Time   Address         Interface
2.2.2.2           1   FULL/DR         00:00:35    192.168.12.2    GigE0/0
3.3.3.3           0   FULL/  -        00:00:31    10.1.13.3       Serial0/0/0

R1# show ip route ospf
     2.0.0.0/32 is subnetted, 1 subnets
O       2.2.2.2 [110/2] via 192.168.12.2, 00:10:15, GigE0/0
     3.0.0.0/32 is subnetted, 1 subnets
O       3.3.3.3 [110/65] via 10.1.13.3, 00:10:15, Serial0/0/0
O    192.168.23.0/24 [110/11] via 192.168.12.2, 00:10:15, GigE0/0
                      [110/74] via 10.1.13.3, 00:10:15, Serial0/0/0
```

### OSPF Troubleshooting

**Common Issues**:

| Problem | Symptoms | Troubleshooting |
|---------|----------|-----------------|
| No adjacency | Neighbor stuck in Init/2-Way | Check hello/dead timers, area ID |
| Partial adjacency | Neighbor in ExStart/Exchange | Check MTU, authentication |
| Missing routes | Adjacency full, no routes | Check LSA database, area configuration |
| Sub-optimal paths | Traffic taking wrong path | Verify OSPF costs, reference bandwidth |

**Troubleshooting Commands**:
```
debug ip ospf hello                  # Hello packet exchange
debug ip ospf adj                    # Adjacency formation
debug ip ospf lsa-generation         # LSA creation
show ip ospf database router         # Router LSAs
ping <neighbor-ip> source <interface>  # Connectivity test
```

## 3.5 First Hop Redundancy Protocols

### FHRP Overview
**Problem**: Single point of failure with single default gateway
- Host configured with static default gateway
- Gateway failure causes connectivity loss
- Manual reconfiguration required

**Solution**: Multiple routers provide gateway redundancy
- Virtual IP address as default gateway
- Active/standby router election
- Automatic failover
- Transparent to end hosts

### FHRP Types

| Protocol | Vendor | Virtual MAC | Priority Range | Preemption |
|----------|--------|-------------|----------------|------------|
| HSRP | Cisco | 0000.0c07.acXX | 0-255 | Configurable |
| VRRP | Standard | 0000.5e00.01XX | 1-254 | Automatic |
| GLBP | Cisco | 0007.b4XX.XXYY | 1-255 | Configurable |

### Hot Standby Router Protocol (HSRP)

**HSRP Roles**:
- **Active Router**: Forwards traffic for virtual IP
- **Standby Router**: Monitors active router, ready to take over
- **Virtual Router**: Logical router with virtual IP and MAC

**HSRP Configuration**:
```
R1 Configuration:
interface GigabitEthernet0/0
 ip address 192.168.1.2 255.255.255.0
 standby 1 ip 192.168.1.1              # Virtual IP
 standby 1 priority 110                # Higher priority (default 100)
 standby 1 preempt                     # Enable preemption
 standby 1 authentication text cisco123

R2 Configuration:
interface GigabitEthernet0/0
 ip address 192.168.1.3 255.255.255.0
 standby 1 ip 192.168.1.1              # Same virtual IP
 standby 1 priority 90                 # Lower priority
 standby 1 preempt delay minimum 60    # Preempt with delay
 standby 1 authentication text cisco123
```

**HSRP States**:
1. **Disabled**: HSRP not running
2. **Init**: HSRP enabled, learning configuration
3. **Listen**: Monitoring hello messages
4. **Speak**: Participating in active/standby election
5. **Standby**: Backup router ready to take over
6. **Active**: Currently forwarding traffic

### Virtual Router Redundancy Protocol (VRRP)

**VRRP Features**:
- IEEE standard (RFC 5798)
- Master/backup terminology
- Automatic preemption (cannot be disabled)
- Advertisement interval: 1 second

**VRRP Configuration**:
```
R1 Configuration:
interface GigabitEthernet0/0
 ip address 192.168.1.2 255.255.255.0
 vrrp 1 ip 192.168.1.1                 # Virtual IP
 vrrp 1 priority 120                   # Higher priority
 vrrp 1 authentication text cisco123

R2 Configuration:
interface GigabitEthernet0/0
 ip address 192.168.1.3 255.255.255.0
 vrrp 1 ip 192.168.1.1                 # Same virtual IP
 vrrp 1 priority 100                   # Lower priority (default)
 vrrp 1 authentication text cisco123
```

### Gateway Load Balancing Protocol (GLBP)

**GLBP Advantages**:
- Load balancing across multiple routers
- Utilizes all routers simultaneously
- Multiple virtual MAC addresses
- Automatic load distribution

**GLBP Roles**:
- **Active Virtual Gateway (AVG)**: Assigns virtual MAC addresses
- **Active Virtual Forwarder (AVF)**: Forwards traffic for specific virtual MAC
- **Standby Virtual Gateway**: Backup AVG
- **Virtual Forwarder**: Listens for specific virtual MAC

**GLBP Configuration**:
```
R1 Configuration:
interface GigabitEthernet0/0
 ip address 192.168.1.2 255.255.255.0
 glbp 1 ip 192.168.1.1                 # Virtual IP
 glbp 1 priority 120                   # Higher priority for AVG
 glbp 1 preempt
 glbp 1 load-balancing round-robin     # Load balancing method

R2 Configuration:
interface GigabitEthernet0/0
 ip address 192.168.1.3 255.255.255.0
 glbp 1 ip 192.168.1.1                 # Same virtual IP
 glbp 1 priority 100                   # Lower priority
 glbp 1 preempt
 glbp 1 load-balancing round-robin
```

**GLBP Load Balancing Methods**:
- **Round-robin**: Rotate through available forwarders
- **Weighted**: Based on configured weights
- **Host-dependent**: Same host always uses same forwarder

### FHRP Verification Commands

**HSRP Verification**:
```
show standby                         # HSRP status all interfaces
show standby brief                   # Summary view
show standby GigabitEthernet0/0      # Interface-specific
debug standby                        # HSRP messages (use carefully)
```

**VRRP Verification**:
```
show vrrp                           # VRRP status all interfaces
show vrrp brief                     # Summary view
show vrrp interface GigE0/0         # Interface-specific
```

**GLBP Verification**:
```
show glbp                           # GLBP status all interfaces
show glbp brief                     # Summary view
show glbp GigabitEthernet0/0        # Interface-specific
```

### FHRP Design Considerations

**Priority Planning**:
```
Production Network Example:
Router A: Priority 110 (Primary for VLAN 10)
Router B: Priority 100 (Standby for VLAN 10)

For load distribution:
VLAN 10: Router A = 110, Router B = 100
VLAN 20: Router A = 100, Router B = 110
```

**Tracking Interface States**:
```
# HSRP interface tracking
interface GigabitEthernet0/0
 standby 1 track Serial0/0/0 20        # Reduce priority by 20 if Serial down

# This ensures Router B becomes active if Router A loses WAN connection
```

**Authentication Security**:
```
# HSRP MD5 authentication
interface GigabitEthernet0/0
 standby 1 authentication md5 key-string cisco123

# VRRP authentication
vrrp 1 authentication text cisco123
```

### Real-World FHRP Implementation

**Enterprise Network Example**:
```
Core Switch A (Primary):
interface Vlan10
 ip address 192.168.10.2 255.255.255.0
 standby 10 ip 192.168.10.1
 standby 10 priority 110
 standby 10 preempt
 standby 10 track GigE1/0/1 20         # Track uplink

interface Vlan20
 ip address 192.168.20.2 255.255.255.0
 standby 20 ip 192.168.20.1
 standby 20 priority 100               # Standby for VLAN 20

Core Switch B (Secondary):
interface Vlan10
 ip address 192.168.10.3 255.255.255.0
 standby 10 ip 192.168.10.1
 standby 10 priority 100               # Standby for VLAN 10

interface Vlan20
 ip address 192.168.20.3 255.255.255.0
 standby 20 ip 192.168.20.1
 standby 20 priority 110               # Primary for VLAN 20
 standby 20 preempt
 standby 20 track GigE1/0/1 20         # Track uplink
```

**Benefits of FHRP Load Distribution**:
- Utilizes both routers/switches actively
- Prevents single router from handling all traffic
- Provides redundancy for both VLANs
- Automatic failover maintains availability

---

# 4. IP Services (10%)

## 4.1 Configure and Verify NAT

### Network Address Translation Overview
**Purpose**: Translate private IP addresses to public IP addresses for internet connectivity.

**NAT Benefits**:
- Conserves public IP addresses
- Provides security through address hiding
- Enables flexible internal addressing
- Supports network renumbering

### NAT Types

**Static NAT**:
- **One-to-one mapping**: Each private IP maps to specific public IP
- **Permanent translation**: Mapping remains constant
- **Bidirectional**: Connections can be initiated from either side

**Dynamic NAT**:
- **Pool-based mapping**: Private IPs map to available public IPs from pool
- **Temporary translation**: Mappings timeout when unused
- **Unidirectional**: Connections initiated from inside only

**Port Address Translation (PAT) / NAT Overload**:
- **Many-to-one mapping**: Multiple private IPs share single public IP
- **Port differentiation**: Uses source port numbers for uniqueness
- **Most common**: Typical home/small office implementation

### Static NAT Configuration

**Basic Static NAT**:
```
# Define inside and outside interfaces
interface GigabitEthernet0/0
 ip nat inside

interface GigabitEthernet0/1
 ip nat outside

# Create static NAT mappings
ip nat inside source static 192.168.1.10 203.0.113.10
ip nat inside source static 192.168.1.20 203.0.113.20
ip nat inside source static 192.168.1.30 203.0.113.30
```

**Static NAT with Port Specification**:
```
# Map specific ports
ip nat inside source static tcp 192.168.1.10 80 203.0.113.5 8080
ip nat inside source static tcp 192.168.1.10 443 203.0.113.5 8443

# Web server accessible on public IP:8080 and :8443
```

### Dynamic NAT with Pools

**NAT Pool Configuration**:
```
# Define NAT pool
ip nat pool PUBLIC_POOL 203.0.113.10 203.0.113.50 netmask 255.255.255.0

# Define ACL for inside networks
access-list 1 permit 192.168.1.0 0.0.0.255
access-list 1 permit 192.168.2.0 0.0.0.255

# Apply dynamic NAT
ip nat inside source list 1 pool PUBLIC_POOL

# Configure interfaces
interface GigabitEthernet0/0
 ip nat inside

interface Serial0/0/0
 ip nat outside
```

### PAT (NAT Overload) Configuration

**PAT with Interface**:
```
# Use outside interface IP for PAT
access-list 1 permit 192.168.0.0 0.0.255.255

ip nat inside source list 1 interface Serial0/0/0 overload

interface GigabitEthernet0/0
 ip nat inside

interface Serial0/0/0
 ip nat outside
```

**PAT with Pool**:
```
# Create small pool for PAT
ip nat pool PAT_POOL 203.0.113.1 203.0.113.5 netmask 255.255.255.0

access-list 1 permit 192.168.0.0 0.0.255.255

ip nat inside source list 1 pool PAT_POOL overload
```

### NAT Translation Process

**Outbound Translation (Inside to Outside)**:
```
1. Packet arrives from inside network
2. Check NAT translation table
3. If no entry exists, create new translation
4. Replace source IP (and port for PAT)
5. Update checksum
6. Forward packet to outside interface

Example:
Inside: 192.168.1.10:3000 → 8.8.8.8:53
Outside: 203.0.113.1:5001 → 8.8.8.8:53
```

**Inbound Translation (Outside to Inside)**:
```
1. Packet arrives from outside network
2. Check NAT translation table
3. If translation exists, replace destination IP/port
4. Update checksum  
5. Forward packet to inside interface

Example:
Outside: 8.8.8.8:53 → 203.0.113.1:5001
Inside: 8.8.8.8:53 → 192.168.1.10:3000
```

### NAT Verification Commands

```
show ip nat translations                # Active translations
show ip nat statistics                  # NAT statistics
show ip nat translations verbose        # Detailed translation info
clear ip nat translation *              # Clear all translations
debug ip nat                           # NAT translation process
```

**Translation Table Example**:
```
Router# show ip nat translations
Pro Inside global      Inside local       Outside local      Outside global
tcp 203.0.113.1:1024  192.168.1.10:1024  8.8.8.8:53        8.8.8.8:53
tcp 203.0.113.1:1025  192.168.1.20:1025  1.1.1.1:53        1.1.1.1:53
```

### NAT Troubleshooting

**Common Issues**:

| Problem | Symptoms | Solution |
|---------|----------|----------|
| No translation | Inside can't reach outside | Check ACL, interface config |
| Wrong interface | Translation not working | Verify inside/outside designation |
| Pool exhausted | Some hosts can't get online | Increase pool size or use PAT |
| Asymmetric routing | Partial connectivity | Ensure return path uses same NAT device |

**Troubleshooting Steps**:
1. Verify inside/outside interface configuration
2. Check ACL permits the inside networks
3. Confirm NAT pool has available addresses
4. Review translation table for active entries
5. Use debug commands to trace translation process

### NAT Design Examples

**Small Office NAT (PAT)**:
```
# Internal network: 192.168.1.0/24
# Public IP: 203.0.113.5

access-list 10 permit 192.168.1.0 0.0.0.255

ip nat inside source list 10 interface GigE0/1 overload

interface GigE0/0
 description LAN Interface
 ip address 192.168.1.1 255.255.255.0
 ip nat inside

interface GigE0/1
 description WAN Interface
 ip address 203.0.113.5 255.255.255.252
 ip nat outside
```

**DMZ with Static NAT**:
```
# DMZ server needs static public IP
ip nat inside source static 10.1.1.10 203.0.113.10

# Internal users use PAT
access-list 100 permit ip 192.168.1.0 0.0.0.255 any
access-list 100 deny ip 10.1.1.0 0.0.0.255 any

ip nat inside source list 100 interface Serial0/0/0 overload
```

## 4.2 Configure and Verify NTP

### Network Time Protocol Overview
**Purpose**: Synchronize clocks across network devices to ensure accurate timestamps.

**NTP Importance**:
- **Logging correlation**: Match events across devices
- **Security**: Certificate validity, Kerberos authentication
- **Troubleshooting**: Chronological event analysis
- **Compliance**: Regulatory requirements for accurate timestamps

### NTP Hierarchy

**Stratum Levels**:
- **Stratum 0**: Reference clocks (atomic, GPS)
- **Stratum 1**: Primary time servers (directly connected to Stratum 0)
- **Stratum 2**: Secondary servers (sync from Stratum 1)
- **Stratum 3-15**: Each level syncs from level above
- **Stratum 16**: Unsynchronized

**NTP Architecture Example**:
```
Stratum 0: GPS/Atomic Clock
    |
Stratum 1: pool.ntp.org (129.6.15.28)
    |
Stratum 2: Corporate NTP Server (192.168.1.100)
    |
Stratum 3: Network Infrastructure Devices
```

### NTP Client Configuration

**Basic NTP Client**:
```
# Configure NTP server
ntp server 129.6.15.28                 # Public NTP server
ntp server 192.168.1.100               # Internal NTP server

# Set timezone
clock timezone EST -5                  # Eastern Standard Time
clock summer-time EDT recurring        # Eastern Daylight Time

# Update hardware clock
ntp update-calendar
```

**Multiple NTP Servers for Redundancy**:
```
ntp server 129.6.15.28 prefer          # Primary server
ntp server 129.6.15.29                 # Backup server
ntp server 192.168.1.100               # Local server

# Prefer directive makes this the preferred server
```

### NTP Server Configuration

**Cisco Router as NTP Server**:
```
# Set local clock as authoritative (use with external reference)
ntp master 3                           # Stratum 3 server

# Synchronize with upstream servers
ntp server 129.6.15.28

# Allow NTP clients
ntp access-group peer 10               # Peer with ACL 10
ntp access-group serve 20              # Serve time to ACL 20

# Access control lists
access-list 10 permit 192.168.1.0 0.0.0.255
access-list 20 permit 192.168.0.0 0.0.255.255
```

**NTP Authentication**:
```
# Configure NTP authentication
ntp authenticate
ntp authentication-key 1 md5 MySecretKey123
ntp trusted-key 1

# Apply authentication to servers
ntp server 192.168.1.100 key 1
```

### NTP Verification Commands

```
show ntp status                        # NTP synchronization status
show ntp associations                  # NTP server relationships
show ntp associations detail           # Detailed association info
show clock                            # Current system time
show calendar                         # Hardware calendar time
```

**NTP Status Interpretation**:
```
Router# show ntp status
Clock is synchronized, stratum 4, reference is 129.6.15.28
nominal freq is 250.0000 Hz, actual freq is 249.9995 Hz, precision is 2**19
reference time is E4A2F4B2.D2F1A000 (15:23:46.824 EST Mon Nov 8 2021)
clock offset is -2.3523 msec, root delay is 145.17 msec
root dispersion is 203.91 msec, peer dispersion is 2.67 msec
```

**NTP Associations Output**:
```
Router# show ntp associations
      address         ref clock     st  when  poll reach  delay  offset    disp
*~129.6.15.28      .GPS.             1    61    64  377     5.5   -2.35     1.2
 ~129.6.15.29      .GPS.             1   120    64  377     8.2   -1.85     2.1
 
* = synchronized, ~ = configured
```

### NTP Security Configuration

**Access Control**:
```
# Restrict NTP access
ntp access-group peer 1                # Allow peering
ntp access-group serve-only 2          # Time service only
ntp access-group query-only 3          # Status queries only

access-list 1 permit 192.168.100.0 0.0.0.255
access-list 2 permit 192.168.0.0 0.0.255.255
access-list 3 permit 10.0.0.0 0.255.255.255
```

**Authentication Keys**:
```
# Multiple authentication keys for different servers
ntp authenticate
ntp authentication-key 1 md5 Key1ForServer1
ntp authentication-key 2 md5 Key2ForServer2
ntp trusted-key 1
ntp trusted-key 2

ntp server 192.168.1.100 key 1
ntp server 192.168.1.101 key 2
```

### NTP Troubleshooting

**Common Issues**:

| Problem | Symptoms | Troubleshooting |
|---------|----------|-----------------|
| Not synchronizing | Clock not accurate | Check network connectivity, firewall |
| High stratum | Poor time quality | Verify upstream server configuration |
| Authentication failure | No sync with auth | Verify keys match on both ends |
| Firewall blocking | NTP not working | Allow UDP port 123 |

**Troubleshooting Commands**:
```
debug ntp all                          # All NTP messages
debug ntp events                       # NTP events only
show ntp associations detail           # Detailed peer information
ping <ntp-server>                      # Basic connectivity
```

### NTP Design Best Practices

**Corporate NTP Design**:
```
Internet NTP Servers (Stratum 1)
    |
Corporate NTP Servers (Stratum 2)
    |
Network Infrastructure (Stratum 3)
    |
End Devices (Stratum 4)
```

**Redundant NTP Configuration**:
```
# Primary data center NTP server
ntp server 192.168.1.100 prefer
# Secondary data center NTP server  
ntp server 192.168.2.100
# Public NTP as backup
ntp server pool.ntp.org
```

## 4.3 DHCP and DNS in Networks

### Dynamic Host Configuration Protocol (DHCP)

**DHCP Purpose**:
- Automatic IP address assignment
- Centralized network configuration
- Reduced administrative overhead
- Supports mobility and dynamic environments

**DHCP Process (DORA)**:
```
1. DISCOVER: Client broadcasts request for IP
2. OFFER: Server offers IP address and parameters
3. REQUEST: Client requests specific offer
4. ACKNOWLEDGE: Server confirms assignment

Client              DHCP Server
  |                     |
  |------ DISCOVER ----->| (Broadcast)
  |<----- OFFER ---------|
  |------ REQUEST ------>|
  |<----- ACK -----------|
```

### DHCP Components

**DHCP Server Functions**:
- IP address pool management
- Lease time management
- Configuration parameter distribution
- Reservation management

**DHCP Information Provided**:
- IP address and subnet mask
- Default gateway
- DNS servers
- Domain name
- NTP servers
- TFTP server (for IP phones, network devices)

### DHCP Cisco Router Configuration

**Basic DHCP Pool**:
```
# Enable DHCP service
service dhcp

# Create DHCP pool
ip dhcp pool LAN_POOL
 network 192.168.1.0 255.255.255.0
 default-router 192.168.1.1
 dns-server 8.8.8.8 8.8.4.4
 domain-name company.local
 lease 7                               # 7 days

# Exclude addresses (gateway, servers)
ip dhcp excluded-address 192.168.1.1 192.168.1.10
```

**Advanced DHCP Configuration**:
```
ip dhcp pool VOICE_POOL
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 192.168.1.100
 option 150 ip 192.168.1.50           # TFTP server for IP phones
 lease 0 12                           # 12 hours

ip dhcp pool DATA_POOL
 network 192.168.20.0 255.255.255.0
 default-router 192.168.20.1
 dns-server 192.168.1.100 192.168.1.101
 netbios-name-server 192.168.1.102
 lease 1                              # 1 day
```

**DHCP Reservations**:
```
ip dhcp pool PRINTER_RESERVATION
 host 192.168.1.50 255.255.255.0
 client-identifier 0100.2345.6789.ab
 default-router 192.168.1.1
 dns-server 192.168.1.100

# Alternative using MAC address
ip dhcp pool SERVER_RESERVATION  
 hardware-address 0023.4567.89ab
 host 192.168.1.100 255.255.255.0
 default-router 192.168.1.1
```

### DHCP Verification Commands

```
show ip dhcp binding                   # Active DHCP leases
show ip dhcp pool                      # DHCP pool configuration
show ip dhcp conflict                  # IP address conflicts
show ip dhcp database                  # DHCP database information
debug ip dhcp server packet            # DHCP packet exchange
```

**DHCP Binding Example**:
```
Router# show ip dhcp binding
Bindings from all pools not associated with VRF:
IP address      Client-ID/        Lease expiration        Type
                Hardware address/
                User name
192.168.1.101   0100.1a2b.3c4d.5e   Nov 15 2021 03:30 PM    Automatic
192.168.1.102   0100.2b3c.4d5e.6f   Nov 15 2021 04:15 PM    Automatic
```

### Domain Name System (DNS)

**DNS Purpose**:
- Resolve hostnames to IP addresses
- Provide service discovery
- Enable user-friendly network access
- Support email routing (MX records)

**DNS Hierarchy**:
```
Root Servers (.)
    |
Top-Level Domains (.com, .org, .net)
    |
Second-Level Domains (example.com)
    |
Subdomains (www.example.com, mail.example.com)
```

### DNS Record Types

| Record Type | Purpose | Example |
|-------------|---------|---------|
| A | IPv4 address | www.example.com → 192.0.2.1 |
| AAAA | IPv6 address | www.example.com → 2001:db8::1 |
| CNAME | Canonical name (alias) | mail.example.com → server1.example.com |
| MX | Mail exchange | example.com → mail.example.com (priority 10) |
| PTR | Reverse lookup | 1.2.0.192.in-addr.arpa → www.example.com |
| NS | Name server | example.com → ns1.example.com |
| SOA | Start of authority | Domain authority information |

### DNS Configuration on Cisco Devices

**DNS Client Configuration**:
```
# Enable DNS lookup
ip domain-lookup

# Configure DNS servers
ip name-server 8.8.8.8
ip name-server 8.8.4.4
ip name-server 192.168.1.100

# Set domain name
ip domain-name company.local

# Domain search list
ip domain-list company.local
ip domain-list branch.company.local
```

**DNS Cache Configuration**:
```
# Enable DNS cache
ip dns server

# View DNS cache
show hosts
```

### DNS Troubleshooting

**DNS Resolution Process**:
```
1. Check local cache
2. Query configured DNS servers
3. DNS server performs recursive lookup
4. Return result to client
5. Cache result locally
```

**DNS Troubleshooting Commands**:
```
nslookup www.google.com                # Basic DNS lookup
ping www.google.com                    # Test resolution and connectivity
show hosts                            # Show DNS cache
debug ip dns                          # DNS resolution process
```

**Common DNS Issues**:
- Incorrect DNS server configuration
- Network connectivity to DNS servers
- DNS server not responding
- Firewall blocking DNS traffic (UDP/TCP port 53)

### DHCP and DNS Integration

**DHCP Option 6 (DNS Servers)**:
```
ip dhcp pool INTEGRATED_POOL
 network 192.168.1.0 255.255.255.0
 default-router 192.168.1.1
 dns-server 192.168.1.100 8.8.8.8     # Primary and secondary DNS
 domain-name company.local
```

**Dynamic DNS Updates**:
- DHCP server can update DNS records automatically
- Clients register their hostnames
- PTR records updated for reverse lookups
- Requires integration between DHCP and DNS servers

### Real-World DHCP/DNS Design

**Enterprise Network Example**:
```
# Management VLAN DHCP
ip dhcp pool MGMT_VLAN
 network 192.168.100.0 255.255.255.0
 default-router 192.168.100.1
 dns-server 192.168.100.10
 domain-name mgmt.company.local
 lease 30                             # Short lease for management

# User VLAN DHCP  
ip dhcp pool USER_VLAN
 network 192.168.200.0 255.255.255.0
 default-router 192.168.200.1
 dns-server 192.168.100.10 192.168.100.11
 domain-name company.local
 option 42 ip 192.168.100.50          # NTP server
 lease 8                              # 8-hour lease for users
```

## 4.4 SNMP in Network Operations

### Simple Network Management Protocol Overview

**SNMP Purpose**:
- Network device monitoring and management
- Performance data collection
- Fault detection and alerting
- Configuration management
- Capacity planning

**SNMP Components**:
- **SNMP Manager**: Network management station (NMS)
- **SNMP Agent**: Software on managed devices
- **Management Information Base (MIB)**: Database of manageable objects

### SNMP Versions

| Version | Security | Authentication | Encryption | Use Case |
|---------|----------|----------------|------------|----------|
| SNMPv1 | Community strings | None | None | Legacy, limited security |
| SNMPv2c | Community strings | None | None | Most common, backward compatible |
| SNMPv3 | User-based security | MD5/SHA | DES/AES | Modern, secure environments |

### SNMP Operations

**SNMP Message Types**:
- **GET**: Retrieve specific MIB object value
- **GET-NEXT**: Retrieve next MIB object in tree
- **GET-BULK**: Retrieve multiple objects (SNMPv2c+)
- **SET**: Modify MIB object value
- **TRAP**: Unsolicited notification from agent
- **INFORM**: Acknowledged notification (SNMPv2c+)

**SNMP Communication Flow**:
```
NMS (Manager)                  Network Device (Agent)
     |                              |
     |-------- GET Request -------->|
     |<------- GET Response --------|
     |                              |
     |<------- TRAP Notification ---|
```

### SNMP Configuration

**Basic SNMPv2c Configuration**:
```
# Enable SNMP agent
snmp-server community public RO        # Read-only community
snmp-server community private RW       # Read-write community
snmp-server location "Building A, Floor 2, Rack 15"
snmp-server contact "Network Admin: admin@company.com"

# Restrict SNMP access
snmp-server community public RO 10
access-list 10 permit 192.168.100.0 0.0.0.255
```

**SNMPv3 Configuration**:
```
# Create SNMP groups
snmp-server group READONLY v3 noauth read READVIEW
snmp-server group READWRITE v3 auth read READVIEW write WRITEVIEW

# Create SNMP users
snmp-server user monitor READONLY v3 auth md5 AuthPass123
snmp-server user admin READWRITE v3 auth md5 AuthPass123 priv aes 128 PrivPass123

# Define views
snmp-server view READVIEW iso included
snmp-server view WRITEVIEW iso included
```

### SNMP Trap Configuration

**Basic Trap Configuration**:
```
# Configure trap destination
snmp-server host 192.168.100.50 version 2c public

# Enable specific traps
snmp-server enable traps snmp linkdown linkup
snmp-server enable traps config
snmp-server enable traps ospf state-change
snmp-server enable traps eigrp
```

**Advanced Trap Configuration**:
```
# SNMPv3 traps with authentication
snmp-server host 192.168.100.50 version 3 auth admin

# Interface-specific traps
interface GigabitEthernet0/0
 snmp trap link-status                 # Enable link status traps

# CPU and memory thresholds
process cpu threshold type total rising 80 interval 30
snmp-server enable traps cpu threshold
```

### Management Information Base (MIB)

**MIB Structure**:
```
ISO (1)
 └── ORG (3)
     └── DOD (6)
         └── Internet (1)
             ├── Management (2)
             │   └── MIB-2 (1)
             │       ├── System (1)
             │       ├── Interfaces (2)
             │       ├── IP (4)
             │       └── SNMP (11)
             └── Private (4)
                 └── Enterprises (1)
                     └── Cisco (9)
```

**Common MIB Objects**:

| OID | Object | Description |
|-----|--------|-------------|
| 1.3.6.1.2.1.1.1.0 | sysDescr | System description |
| 1.3.6.1.2.1.1.3.0 | sysUpTime | System uptime |
| 1.3.6.1.2.1.1.5.0 | sysName | System name |
| 1.3.6.1.2.1.2.2.1.2 | ifDescr | Interface description |
| 1.3.6.1.2.1.2.2.1.8 | ifOperStatus | Interface operational status |

### SNMP Verification Commands

```
show snmp                              # SNMP agent status
show snmp community                    # Community strings
show snmp user                         # SNMPv3 users
show snmp group                        # SNMPv3 groups
show snmp host                         # Trap destinations
debug snmp packet                      # SNMP packet exchange
```

**SNMP Testing**:
```
# Test SNMP from router (if available)
snmp-server test oid 1.3.6.1.2.1.1.1.0

# External SNMP tools
snmpget -v2c -c public 192.168.1.1 1.3.6.1.2.1.1.5.0
snmpwalk -v2c -c public 192.168.1.1 1.3.6.1.2.1.2.2.1.2
```

### SNMP Security Considerations

**Community String Security**:
```
# Use complex community strings
snmp-server community Comp1ex!Read0nly RO
snmp-server community Comp1ex!ReadWr1te RW

# Restrict access by source IP
snmp-server community public RO SNMP_SERVERS
ip access-list standard SNMP_SERVERS
 permit 192.168.100.50
 permit 192.168.100.51
```

**SNMPv3 Security**:
```
# Strong authentication and encryption
snmp-server user secureuser SECUREGROUP v3 auth sha StrongAuthPass456 priv aes 256 StrongPrivPass789

# Limit SNMP access to management interfaces only
snmp-server source-interface traps Loopback0
snmp-server source-interface informs Loopback0
```

### SNMP Monitoring Use Cases

**Network Performance Monitoring**:
- Interface utilization (ifInOctets, ifOutOctets)
- Error rates (ifInErrors, ifOutErrors)
- CPU usage (cpmCPUTotal5minRev)
- Memory utilization (ciscoMemoryPoolUsed)

**Fault Management**:
- Link up/down traps
- Device unreachable alerts
- Configuration change notifications
- Environmental alarms (temperature, power)

**Capacity Planning**:
- Historical bandwidth trends
- Memory and CPU growth patterns
- Interface utilization forecasting
- Storage capacity monitoring

## 4.5 Syslog Features and Severity Levels

### Syslog Overview

**Purpose**:
- Centralized logging and event collection
- Real-time monitoring and alerting
- Historical analysis and forensics
- Compliance and audit requirements

**Syslog Components**:
- **Syslog Client**: Device generating log messages
- **Syslog Server**: Centralized log collection point
- **Syslog Protocol**: RFC 5424 standard

### Syslog Message Format

**Standard Syslog Message Structure**:
```
<Priority>Timestamp Hostname Process[PID]: Message

Example:
<189>Nov 8 15:23:45 Router1 %OSPF-5-ADJCHG: Process 1, Nbr 2.2.2.2 on GigE0/0 from FULL to DOWN
```

**Message Components**:
- **Priority**: Facility and severity encoded
- **Timestamp**: When event occurred
- **Hostname**: Source device identifier
- **Process**: Generating process/protocol
- **Message**: Actual event description

### Syslog Facilities

**Facility Codes**:

| Facility | Code | Description | Use Case |
|----------|------|-------------|----------|
| kern | 0 | Kernel messages | OS-level events |
| mail | 2 | Mail system | Email server logs |
| daemon | 3 | System daemons | Service processes |
| auth | 4 | Authorization | Authentication events |
| syslog | 5 | Syslog messages | Logging system itself |
| local0-local7 | 16-23 | Local use | Custom applications |

**Cisco Default Facilities**:
- **local7 (23)**: Default facility for Cisco devices
- Can be changed globally or per-message type

### Syslog Severity Levels

| Level | Name | Description | Example Use |
|-------|------|-------------|-------------|
| 0 | Emergency | System unusable | Complete system failure |
| 1 | Alert | Immediate action required | Hardware failure |
| 2 | Critical | Critical conditions | Software malfunction |
| 3 | Error | Error conditions | Protocol errors |
| 4 | Warning | Warning conditions | Configuration issues |
| 5 | Notice | Normal but significant | Interface state changes |
| 6 | Informational | Informational messages | Routine operations |
| 7 | Debug | Debug messages | Detailed troubleshooting |

### Syslog Configuration

**Basic Syslog Configuration**:
```
# Enable logging
logging on

# Set console logging level
logging console warnings               # Level 4 and above

# Set buffer logging
logging buffered 32768 informational  # 32KB buffer, level 6 and above

# Configure syslog server
logging host 192.168.100.50
logging host 192.168.100.51 transport udp port 514

# Set facility
logging facility local5
```

**Advanced Syslog Configuration**:
```
# Source interface for syslog
logging source-interface 