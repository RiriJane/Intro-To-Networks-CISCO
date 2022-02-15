**These notes are taken from courses in Cisco Networking Academy. No copyright intended**
# Chapter 3 - Protocols and Models
## 3.4 Standard Organizations
### 3.4.1 Open Standards
- Standards are developped by international standards organization
- Open standards encourage interoperability, competition and innovation
- Guarantees no unfair advantage over a company's competition
- Make set of rules for protocols

Some standard organizations:
![Logo of standard organizations](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/standard_organization.jpg)

### 3.4.2 Internet Standards
![internet_standards.jpg]

**Internet Society (ISOC)** : responsible for promoting the open development and evolution of internet use throughout the world.
**Internet Architecture Board (IAB)** : responisble for management and development of internet standards.
**Internet Engineering Task Force (IETF)** : develops, updates, maintains internent TCP/IP technologies (process and documents for developping new protocols and updating existing protocols).
**Internet Reearch Task Force (IRTF)** : research about the internet and TCP/IP protocols

![IANA_ICANN.jpg](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/intertnet_standards.jpg)

**Internet Corporation for Assigned Names and Numbers (ICNN)** : coordinates IP address allocation, manages domain names, assigns other information used in TCP/IP protocols.
**Internet Assigned Numbers Authority (IANA)** : oversees and manage IP address allocation, domain name management and protocol identifiers for ICANN.

### 3.4.3 Electronics and Communications Standards
**Institute of Electrical and Electronics Engineers (IEEE)** : advances technology innovation, creating standards in a wide area of industries (power, energy, healthcare, telecommunications and networking).
Some IEEE networking standards :
- 802.3 Ethernet standards
- 802.11 WLAN standards
**Electronic Industries Alliance (EIA)** : known for its standards of electrical wiring, connectors, and 19-inch racks of network equipments.
**Telecommunications Industry Association (TIA)** : develops communication standards in areas such as radio equipment, cellular towers, Voice over IP (VoIP) devices, satellite, etC.
**International Telecommunications Union-Telecommunication Standardization Sector (ITU-T)** : largest standard organization that defines standars for video compression; Internet Protocol Television (IPTV), and broadband communications (DSL).

## 3.5 Reference Models
![OSI TCP/IP Reference Models](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/OSI_TCP_IP_models.jpg)
There are 2 layered models : 
1. **Open System Interconnection (OSI) Reference Model**
2. **TCP/IP Reference Model**

### 3.5.2 OSI Reference Model
![OSI Model](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/OSI_layer.jpg)
The OSI reference model describes the interaction between layers. The OSI layers are reffered to by numbers (Layer 1 for physical layer, Laver 2 for Data Link Layer, etc.).

### 3.5.3 The TCP/IP Protocol Model
![TCP/IP Reference Model](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/TCP_IP_model.jpg)
The TCP/IP protocol Model is often referred to the internet model and it was created in the early 70s. It describes what occurs in each layer. 

## 3.6 Data Encapsulation
### 3.6.1 Segmenting Messages
- Process of dividing data into smaller units to send over the network
- 2 benefits : increases speed and efficiency (if one packet fails to be transmitted than it's only that specific packet that needs to be retransmitted).
- **Multiplexing** : different packets interleaving on the network. Meaning that messages from Host A and B can pass through the network, see image below :
![Multiplexing](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/multiplexing.jpg)

### 3.6.2 Sequencing
![Sequencing](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/sequencing.jpg)
- Process of labeling packets to ensure that the receiver could ressembling the pages in the correct order.

### 3.6.3 Procotol Data Units
- **Encapsulation process** : application data is passed down the protocol stack when transmitted over the network and protocol information is added at each level
- **Protocol data unit (PDU)** : the form that a piece of data takes at any layer
- If the Transport header is TCP, it's a segment. Otherwise, if it's UDP then it's a datagram.
![Encapsulation process](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/encapsulation_process.jpg)
	- Data : Application Layer PDU
	- Segment : Transport Layer PDU
	- Packet : Network Layer PDU
	- Frame : Data Link Layer PDU
	- Bits : Physical Layer PDU

### 3.6.4 Encapsulation process
Encapsulation process works from top to bottom :
- User Data
- TCP Segment
- IP Packet
- Ethernet Frame

### 3.6.5 De-encapsulation process
Reversed process, bottom to up :
- Ethernet Frame
- IP Packet
- TCP Segment
- User Data

## 3.7 Data Access
### 3.7.1 Addresses 
![Addresses](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/addresses.jpg)
- Network and data link layers are responsible for sending data from source to destination device.
- Network layer source and destination addresses : responsible for sending the IP packet from source to destination on the same or remote network
- Data link Layer source and destination addresses : responsible for sending data link frame from on Network Interface Card (NIC) to another on the same network.

### 3.7.2 Layer 3 logical Address
![Layer 3 Logical Address](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/logical_address.jpg)
- logical address are used to deliver IP packet from source to destination
- **Source IP address** : IP address of the orignal source of the packet
- **Destination IP address** : IP address of the final destination of the packet

An IP address contains 2 parts:
1) **Network portion (IPv4) or Prefix (IPv6)** : left-most that indicates the network in which the user is a member. All devices on the same network have the same network portion of the address.
2) **Host portion (IPv4) or Interface ID (IPv6)** : the remaining part of the address which is unique for each device on the network.

- **Subnet mask (IPv4) or prefix-lenght(IPv6)** : used to identify the network portion from the host portion.

**Example of devices on the same network :**
![Devices on the same network](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/devices_same_network.jpg)

Source IPv4 address, client computer : 192.168.1.110
Destination UPv4 address, FTP server : 192.168.1.9

Source and destination are in the same network because the network portion are the same : 192.168.1

### 3.7.4 Role of the Data Link Layer Addresses: Same IP network
![Data Link Layer Addresses](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/MAC_addresses.jpg)
- If the sender and receiver of the IP packet are on the same network, the data link frame is sent directly to the receiving device. 
- **Ethernet Media Access Control (MAC) addresse : data link addresses
	- Physically embedded on the Ethernet NIC


Source MAC address : MAC address of the device that sends the data link frame with the encapsulated IP packet
Destination MAC address : MAC address of the device that receives the data link address of the receiving device

### 3.7.6 Role of the Network Layer Address
![Network Layer Address](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/network_layer_address.jpg)
The network portion will indicate when two devices are not on the same network

Source IP address, client computer : 192.168.1.110
Destination IP address, Web Server : 172.16.1.99

### 3.7.7 Role of the Data Link Layer Addresses: Different IP networks
![Data Link Layer Addresses - Different Networks](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/DLL_different_networks.jpg)
- Ethernet data link frame cannot be sent directly to the destination host because the host isn't directly reachable. 
- Ethernet frame must be sent to another device known as the router or default gateway

Source MAC Address, Ethernet interface of PC1 : AA-AA-AA-AA-AA-AA
Destination MAC Address : uses the default gateway or router's MAC address. In this case, the destination MAC address is the MAC address of the R1 Ethernet interface 11-11-11-11-11-11. This interface is attached to the same network as PC1.

The Ethernet Frame with encapsulated IP packet can be send to R1. R1 forwards the packet to the destination, Web Server. This could mean that R1 forwards the packet to another router or directly to the server if the destination is on the same network as R1.

### 3.7.8 Data Link Addresses
- Data Link Layer 2 physical address delivers the data link frame from one network interface to another on the same network.

**Host to Router**
![Data Link Addresses - Host to Router](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/data_link_address_host_router.jpg)

**Router to Router**
![Data Link Addresses - Router to Router](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/data_link_address_router_router.jpg)

**Router to Server**
![Data Link Addresses - Router to Server](https://github.com/RiriJane/Intro_To_Networks_CISCO/tree/main/images/data_link_address_router_server.jpg)

- IP packet travels from Host to Router, Router to Router, Router to Host
	- On each point, the IP packet is encapsulated in a new data link frame
	- Each data link frame contains : source data link adress of the NIC card sending the frame and the destination data link address of the NIC card receiving the frame
- Layer 2, data link protocol is used only to deliver the packet from NIC to NIC on the same network.
	- The router removes the NIC since it is received on one NIC and adds new data link information before forwarding out the exit NIC
- The IP packet is encapsulated in a data link frame that contains :
	- Source data link address : physical address of the NIC that sends the data link frame
	- Destination data link address : physical address of the NIC that receives the data link frame


