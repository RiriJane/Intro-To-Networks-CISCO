**These notes are taken from courses in Cisco Networking Academy. No copyright intended.**

# Chapter 7 - Ethernet Switching
## 7.1 Ethernet Frames
### 7.1.1 Ethernet Encapsulation
![Ethernet and OSI Model](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/ethernet_osi_model.jpg)

- Ethernet operates in the data link layer (layer 2) and physical layer (layer 1)
- Ethernet support bandwidths of : 10 Mbps, 100 Mbps, 1000 Mbps (1 Gbps), 10'000 Mbps (10 Gbps), 40'000 Mbps (40 Gbps), 100'000 Mbps(100 Gbps)
-

### 7.1.2 Data Link Sublayes
#### Recall
- **Logical Link Control (LLC)** - IEEE 802.2 sublayer : communicates between the networking software at the upper layers and the device hardware at the lower layers.
  - Places information in the frame that identifies which network layer protocol is being used for the frame.
  - Allow Layer 3 protocols (IPv4 and IPv6) to use the same network interface and media.
- **Media Access Control (MAC)** - IEEE 802.3, 802.11, 802.15 sublayers in hardware :  responsible for data encapsulation and media access control. 
  - Provies data link layer addressing and integrates physical layer technologies.

### 7.1.3 MAC sublayer
- Responsible for data encapsulation and accessing the media

#### Data encapsulation - IEEE 802.3
- **Ethernet frame** : internal structure of the Ethernet frame.
- **Ethernet Addressing** : Ethernet frame includes both a source and destination MAC address.
  - Delivers the Ethernet Frame from Ethernet NIC to Ethernet NIC on the same LAN.
- **Ethernet Error Detection** : has a frame check sequence (FCS) trailer used for error detection.

### Accessing the Media
- legacy Ethernet uses bus topology or hubs, shared half-duplex medium.
  - Uses a contention-based access methods, carrier sens multiple access/collision detection. Only on device transmit at a time.

### 7.1.4 Ethernet Frame Fields
- Minimum Ethernet Frame size is 64 bytes, maximum is 1518 bytes.
- Any frame less than 64 bytes is considered "collision fragment" or "runt frame.
- More thant 1500 bytes are considered "jumbo" or "baby giant frames".
- If the size is less or greater then the receiving device drops the frame, considering it invalid.

#### Ethernet frame field
![Ethernet frame field](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/ethernet_frame_field.jpg)

## 7.2 Ethernet MAC Address
### 7.2.1 MAC address hexadecimal
![Equivalent table](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/equivalent_table.jpg)

- Uses 12 hexadecimal number system, consisting of 48-bit binary value.
- 0 are used to complete the 8-bit representation. For example, 0000 1010 is 0A hex.
- We use an x to distinguish hex and decimals. For example, 0**x**73.

### 7.2.2 Ethernet MAC Address
![MAC address representation](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/mac_address_representation.jpg)

- Used to identify physical source and destination devicces (NICs) on a local network.
- 48-bt address in 12 hexadecimal number.
- Must be unique to the Ethernet device or Ethernet interface. 
- Contains 6 hex vendor OUI (organizaionally Unique Identifier, registered with IEEE) and 6 hexa vendor-assigned value
- Also referred to as Burned-In Address (BIA) because the address is encoded into the ROM chip (NIC) premanently.

### 7.2.3 Frame Processing
![Sending a message to an Ethernet network](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/sending_message_ethernet_network.jpg)

- When the computer boots up, the NIC copies its MAC address from ROM into RAM.
- When a device is sending a message to an Ethernet network, the Ethernet header includes : **Source MAC address** and **Destination MAC Address**.

### 7.2.4 Unicast MAC Address
![unicast](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/unicast.jpg)

- A destination IP address must be in the IP packet header.
- A corresponding destination MAC address must be in the Ethernet frame header.
- **Address Resolution Protocol (ARP)** : the process that a source host uses to determine the destination MAC address associated with an IPv4 address.
- **Neighbor Discovery (ND)** : the process that a source host uses to determine the destination MAC address associated with an IPv6 address.

### 7.2.5 Broadcast MAC Address
![broadcast](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/broadcasr.jpg)

- The packet contains a destination IPv4 address that has all ones (1s) in the host portion (x.x.x.255 ou  x.x.x.FF-FF-FF-FF-FF-FF).
- Not forwarded by a router.

### 7.2.6 Multicast MAC Address
![multicast](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/multicast.jpg)

- IPv4 multicast packet : the destination MAC address is 01-00-5E
- IPv6 multicast packet : the destination MAC is 33-33
- There are other multicast destination MAP address for Spanning Tree Protocol (STP) and Link Layer Discovery Protocol (LLDP)
- Not forwarded by a router, unless its configured to do so.
- If an IP belongs to a multicast group, it's assigned a multicast group IP address.
- Range of IPv4 multicast addressses : 224.0.0.0 to 239.255.255.255.
- Range for IPv6 begins with ff00::/8.
- The source will always be a unicast address.
- The multicast IP address requires a corresponding Multicast MAC address to deliver the frame across the local network.

## 7.3 The MAC Address Table
- Layer 2 Ethernet switch uses Layer 2 MAC Address to make forwarding decisions. 
- Unaware of the date (protocol) being carried in the data portion of the frame.
- When powering on port switches, the MAC address table are still empty. It has not learned the MAC addresses of the devices attached.
- It dynamically builds the table when it examines the source MAC address of the frames received on a port.

#### Learning
1. Every frame entering a switch, the information is being learned.
2. It verifies the source MAC address and the port number where the frame entered.
3. If the MAC address doesn't exist, it's added to the table with the port number.
4. If it does exist, it updates the refresh timer for that entry in the table. by default, most switches keep an entry in the table for 5 minutes.

#### Forwarding
- If the destination MAC address is a unicast address, it will look for a match in the table.
- If it's in the table, it will forward the frale to the specified port.
- If it's not in the table, it will forward to all ports except the incoming port. Called the unknown cast.

### 7.3.4 Filtering Frames
![Filtering frames](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/filtering_frames.jpg)

When there are two switches connect, if the switch receive a packet from a device and doesn't know the destination MAC address, it will transmit to other ports connected and goes on to other devices connected until it reaches it's destination. The non corresponding device doesn't accept the packet if the MAC address doesn't match.

### 7.3.5 Sending the Frame to the Default Gateway
![Sending frame to router](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/sending_frame_to_router.jpg)

If the destination isn't on the table. It continues to send to other ports connected until the destination is reached. The non corresponding device doesn't accept the packet if the MAC address doesn't match.

## 7.4 Switch Speeds and Forwarding Methods
### 7.4.1 Frame forwarding methods on Cisco switches
- **Store-and-forward switching** : receives the entire frame and computes the CRC (Cyclic Redundancy Check). If the CRC is valid, the switch examines the destination addres and outgoing interface. The frame is then forwarded to the correct port.
  - Advantages : detects if the frame has errors before forwarding and it will be discarded. Discarding reduces the amount of bandwidth used.
  - Required for QoS analysis where traffic priorization is ncessary. 
- **Cut-through switching** : forwards the frame before it's entirely received. At the minimum, the destination address of the frame must be read before the frame can be forwarded.

### 7.4.2 Cut -through switching
- **Fast-forwarding switching** : offers the lowest level of latency. Immediately forwards the packet after reading the destination address. 
  - Packets can be relayed with errors. Occurs infrequently. The NIC discards faulty packets when received.
- **Fragment-free switching** : the switch stores the first 64 bytes of the frame before forwarding because most errors or collision occur during the first 64 bytes. 
  - Enhances fast-forwarding switching by performing a small error check. 

### 7.4.3 Memory Buffering on Switches
- Buffering may be used when the destination port is busy because of congestion. The switch stores the frame until it can be forwarded. 

#### 2 methods of memory buffering
1. **Port-based memor** 
- frames are stored in queues linked to specific incoming and outgoing ports.
- a frame is forwarded only if it's turn.
- it's possible that a frame can delay transmission due to a busy destination port.
- it can occur even if the other frames in queue could be transmitted to open destination ports.

2. **Shared Memory**
- put frames into a common memory buffer shared by all switch ports
- the amount of buffer memory is dynamically allocated to each port
- the frames in the buffer are dynamically linked to the destination port

### 7.4.4 Duplex and Speed settings
![duplex and speed settings](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/duplex_speed_setting.jpg)

- It's important that the duplex and bandwidth settings match between the switch port and the connected devices.
- Autonegotiation : optional function on switches and NICs. Enables two devices to negotiate the best speed and duplex capabilities.
- if the settings are not set up properly, having a duplex and half-duplex communicating can occur collisions for the half-duplex device.

### 7.4.5 Auto-MDIX
**Cables used to connect devices**
![Cables used to connect devices](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap7/cable_connect_devices.jpg)

Some devices support the automatic medium-dependent interface crossover (Auto-MDIX) feature meaning that the switch automatically detects the type of cable attached to the port and configures the interfaces accordingly. 


























