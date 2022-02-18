**These notes are taken from courses in Cisco Networking Academy. No copyright intended.**

# Chapter 8 - Network Layer
## 8.1 Network Layer Characteristics
### 8.1.1 The network layer
![Layer 3 - Network](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap8/layer_3_network.jpg)

- OSI layer 3.
- provides services that allow devices to exchange data ovr a network.
- IPv4 and IPv6 are the main protocols for communication in layer 3.
  - Other protocols : Open Shortest Path First (OSPF), Internet Control Message Protocols (ICMP).

#### Four operations of protocols
1. **Addressing end devices** : end devices are configured with IP address for identification on a network.
2. **Encapsulation** : encapsulates protocol data unit (PDU) from the transport layer into a packet.
   - The encapsulation process adds IP header information such as IP address source and destination hosts. 
   - Encapsulation is performed bw the source of the IP packet.
3. **Routing** : provides services to direct packets to the destination host. 
   - Packets are processed by routers.
   - Router's role is to select the best path.
   - Hop : when a packet crosses a router when going to the destination.
4. **De-encapsulation** : When the packet arrives at the destination host, it checks the IP header of the packert. If the destination IP address in the header matches its own, the header is removes from the packet. After the de-encapsulation, the resulting Layer 4 PDU is passed up to the appropriate service at the transport layer. 
   - Performed by the destination host of the IP packet.

#### Steps when two end devices exchanges data.

1. PC sends data to a laptop.
2. Data is encapsulated in the layer 4 (Transport). It becomes a segment.
3. Segment is passed on to layer 3 (network). The segment is encapsulated. It becomes a packet.
4. Packet is passed on to layer 2 (data link).The packet is encapsulated. It becoles a frame.
5. The frame is passed on to layer 1 (Physical). It's converted to binary numbers. 
6. Routing. Finding path to the destination host (laptop).
7. It arrives to the laptops layer 1 (Physical). It's converted to a frame and passed on to layer 2 (data link).
8. Layer 2 de-encapsulates the frame and becomes a packet. It's passed on to layer 3 (network).
9. Layer 3 de'encapsulates the the packet and becomes a segment. It's passed on to layer 4 (transport).
10. Layer 4 de-encapsulates the segment and becomes a data. And passed on to the upper layers.

### 8.1.2 IP encpasulation
**Transport Layer pDU encapulsated by the network layer to create an IP packet**
![Transport layer PDU encapsulated by the network layer](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap8/transport_layer_encapsulated_by_network_layer.jpg)

- IP encapsulates the transport layer segment or adding an IP header to the data. 
- The IP header is used to deliver the packet to the destination host.
- When the packet leaves the source host, the IP addressing information stays the same until it arrives at the destination host.

### 8.1.3 Characteristics of IP
1. **Connectionless** : no connection with the destination established before sending data packets.
- destination host is unaware of receiving packets.
2. **Best effort** : unreliable because packet delivery is not guaranteed.
- Packets can arrive corrupted, out of sequence or not at all.
- Other protocols manage the process of tracking packets and ensuring their delivery.
3. **Media Independent** : independent of the medium
- IP packts can be transmitted as electronic signals over copper cable, fiber-optic, or wirelessy.
- The data link layer (layer 2) is responsible for taking an IP packet and preparing it for transmission over the communications medium. 
- Fragmentation : process of splitting up IP packets to travel over a medium with a smaller maximum transmission unit (MTU).


































