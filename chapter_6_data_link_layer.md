**These notes are taken from courses in Cisco Networking Academy. No copyright intended.**

# Chapter 6 - Data Link Layer

## 6.1 Purpose of the Data Link Layer
### 6.1.1 The Data Link Layer

![Data Link Layer](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/data_link_layer.jpg)

- The data link layer responsible for controlling the transfer of frames across the media.
- Responsible for the NIC to NIC comunications.
- Enables upper layers to access the media. The upper layers are unaware of the media being used to forward the data.
- Accepts data (layer 3 packets : IPv4 or IPv6) and encapsulates them into Layer 2 frames.
- Controls how data is placed and received on the media.
- Exchanges frames between endpoints over the network media.
- Receives encapsulated data (Layer 3 packets) and directs them to the proper upper-mayer protocol.
- Performs error detection and rejects any corrupt frame.

![Data Link Layer adds Layer 2 information to Layer 3 packet](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/data_link_layer_adding_layer2_layer3_packet.jpg)

- **Node** : device that receive, create, store or forward data on communications path.
  - It can be an end device(Laptop, computer, etc.) or an intermediary device (Ethernet Switch).
- Without data link layer, network layer would have to have many existing path options. Data Link Layer provides this path. 
- Data Link Layer adds Layer 2 Ethernet destination and source NIC information to a Layer 3 packet. Then converts information to a format supported by the physical layer.

### 6.1.2 IEEE 802 LAN/MAN Data Link Sublayers
IEEE 802 LAN/MAN standards are specific to Ethernet LANs, WLAN, WPAN and other local and metropolitan area networks.

2 sublayers:
- **Logical Link Control (LLC)** - IEEE 802.2 sublayer : communicates between the networking software at the upper layers and the device hardware at the lower layers.
  - Places information in the frame that identifies which network layer protocol is being used for the frame.
  - Allow Layer 3 protocols (IPv4 and IPv6) to use the same network interface and media.
- **Media Access Control (MAC)** - IEEE 802.3, 802.11, 802.15 sublayers in hardware :  responsible for data encapsulation and media access control. 
  - Provies data link layer addressing and integrates physical layer technologies.

![Two sublayers of data link layer - table](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/two_sublayers_dll_table.jpg)

- LLC sublayer takes the network protocol data (IPv4 or Ipv6) and adds Layer 2 control information to help deliver the packet to the destination node.
- MAC sublayer controls the NIC and other hardware that is responsible for sending and receiving data on the wired or wireless LAN/MAN medium.

The Mac Sublayer provides data encapsulation :
- **Frame delimiting** : to identify fields within a frame. Provides synchronization between the transmitting and receiving nodes.
- **Addressing** : provides sources and destination addressing for transport layer 2 frame between devices.
- **Error detection** : detects transmission errors

Mac sublayers provide media access acontrol, allowing devices to communicate over a shared medium.

### 6.1.3 Providing Access to Media
- A router interfaces encapsulate packets into the appropriate frame. MAC is used to access each link.
- At each hop, a router performs layer 2 functions :
1. Accepts a frame from a medium.
2. De-encapsulates the frame.
3. Re-encapsulates the packet into a new frame.
4. Forwards new appropriate frame to the medium.


![Example pc to router encapsulation](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/pc_router_encapsulation.jpg)
![Example router to router encapsulation](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/router_router_encapsulation.jpg)
1. First router has an Ethernet interface to connect to LAN and a serial interface to connect to the WAN.
2. The router processes frames and uses data link layer services to receive the frame from one medium.
3. de-encapsulate it to the layer 3 PD.
4. re-encapsulate the PDU int a new frame.
5. Place the frame on the medium of the next link of the network.


## 6.2 Topologies

**Physical topology** : physical connections betweend end devices and intermediary devices. May specify device location (Room number, etc.). 
- Point-to-point or star diagram

![Physical topology](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/physical_topology.jpg)

**Logical topology** : identifies virtual connections using device interfaces and layer IP adressing schemes.

The data link layer sees the logical topology.

![Logical topology](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/logical_topology.jpg)

### 6.2.2 WAN topologies

#### Point-to-point
![Point-to-point](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/point-topoint_topologie.jpg)

- Simplest and most used
- Permanent link between two endpoints

#### Hub and Spoke
![Hub and spoke](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/hub_and_spoke_topology.jpg)

- WAn version of star topology
- Central site connects branch sites through the use of point-to-point links
- Branche sites cannot exhcange data with another branch site without going through the central site

#### Mesh
![Mesh](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/mesh_topology.jpg)

- Provides high availabilty
- Requires every system to be connected with other system
- Cost can be signficant
- Each link is a point-to-point link to another node


A hybrid can exist. 

### 6.2.3 Point-to-point WAN topology
![Point-to-point WAN topology](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/ppp_WAN_topology.jpg)

- PP connects two nodes
- Two nodes don't have to share media with other host.
- **Point-to-point protocol (PPP)** : serial communication protocol, a node doesn't have to determine about whether an incoming frame is destined for it or anothr node.
  - Logical data link protocols are simple since the frames travel from one node to another.
  - Adding intermediary device may not affect the logical topology since the connection is the same.


### 6.2.4 LAN topologies
![LAN topologies](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/LAN_topology.jpg)

- Star or extended star topologies.
- End decices are connected to a central intermediary device.
- **Extended star** : extends the topology by connecting other Ethernet switches.
- Scalable, easy to install, and easy to troubleshoot

**Bus** : All end systems are chained to each other and terminated in some form on each end. Needs to be terminated.
**Ring** : Devices are connected to their respective neighbors. The ring doesn't need to be terminated.

### 6.2.5 Half and Full Duplex Communication
**Half-duplex communication** : two devices can send and receive on the media but not simultaneously.

![Half-duplex communication](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/half_duplex_comm.jpg)

**Full-duplex communication** : Both can send and receive on media simultaneously.

![Full-duplex communication](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/full_duplex_comm.jpg)

### 6.2.6 Access Control Methods
- **Multiaccess network** : has 2 or more devices accessing the network simultaneously.

#### Contention-based access
![Contention-based access](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/contention-based_access.jpg)

- All nodes are operating half-duplex.
- One device can send at a time.
- Methods :
  - Carrier sense multiple access with collision detection (CSMA/CD) : used on legacy bus topology Ethernet LANs
   - Operates in half-duplx mode, one device can send or receive at a time.
   - If two devices send at the same time, a collision will occur.
  - Carrier Sense multiple access with collision avoidance (CSMA:CA) : used on wireless LANs
   - May not be possible to detect collision in wireless environments
   - Doesn't detect collision but avoids them by waiting before transmiting
   - Each device that transmits includes time duration and it's receive by other devices and would know how long to wait.

#### Controlled access
![Controlled access](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap6/controlled_access.jpg)

- Each node has its own time to use the medium.
- Inefficient because must wait for its turn
















