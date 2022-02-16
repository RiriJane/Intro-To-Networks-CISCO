**These notes are taken from courses in Cisco Networking Academy. No copyright intended**

# Chapter 4 -  Physical Layer

## 4.1 Purpose of the Physical Layer
### 4.1.1 The Physical Connection
- **Wired network** : a device physically connected where data is transmitted through a physical cable.
- **Wireless connectio** : data is transmitted using radio waves.

**Wireless Router**

![Wireless Router](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/wireless_router.jpg)

Components of an access point :
1. Wireless antennas that are embedded inside the router
2. Ethernet switchports
3. Internet port

**Wired Connection to Wireless Router**

![Wired connection to a wireless router](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/wired_connection_router.jpg)

- ** Network Interface Cards (NICs) : connects a device to a network, used for a wired connection. 
- ** WLAN NICs** : used for wireless connection.
- End device may include both types of NICs.


## 4.1.2 Physical Layer
1. When the source sends data to destination, the last process of encapsulation sends the bits over the physical medium.
2. The physical layer encodes the frames and creates the electrical, optical or radio wave signals that represents the bits in each frame.
3. The signals are sent over the media, one at a time.
4. The destination node physical layer retrieves individual signals from the media and restores them to their bit representations.
5. It passes the bits up to the data link layer as a complete frame.



## 4.2 Physical Layer Characteristics
The physical layer standards address 3 functional areas:
1) Physical Components
2) Encoding
3) SignalingThe physical layer standards address 3 functional areas:

**Physical Components** : consist of eletronic hardware devices, media, and other connectors that transmits signals representing the bits. For example : NICs, interfaces, connectors, cable materials, etc.

**Encoding** or line encoding : method of convertion a stream of data bits into a predefined "code".
  - codes : grouping of bits used to provide a predictable pattern that can be recognized by both sender and receiver.
  - Manchester encoding : 0 bit represent high to low voltage and 1 bit represent low to high voltage. The transition is occured in the middle of each bit period. 
    - This type of encoding is used in 10 Mbps Ethernet. 
    - Faster data requires more complex encoding.
    - Used in older Ethernet standars such as 10BASE-T.
    
    ![Manchester encoding](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/manchester_encoding.jpg)

**Signaling** : the way the bits are represented 
- The physical layer standards must define what type of signal represents a 1 and 0

**Electrical Signals Over Copper Cable** : uses electrical pulses to represent bits
![Electrical Signals Over Copper Cable]

**Light Pulses Over Fiber-Optic Cable** : uses patterns of light to represent bits
![Light Pulses Over Fiber-Optic Cable]

**Microwave Signals Over Wireless** :  uses patterns of microwaves to represents bits
![Microwave Signals Over Wireless]

### 4.2.5 Bandwidth
- **Bandwidth** : capacity of data that a medium can carry
    - Measured in kilobits per second (kbps), megabits per second (Mbps) or gigabits per second (Gbps)
    - The difference of 10 Mbps and 100 Mbps is the number of bits that are transmitted per second. The bits are sent at the speed of electricity.
- **Digital bandwidth** : measures the amount of data that can flow frome one place to another in a given amount of time.

Factors that determines the bandwidth of a network :
1. The properties of the physical media
2. The technology chosen for signaling and detecting network signals

**Units of measure for bandwidth**

![Units of measure for bandwidth](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/units_measure_bandwidth.jpg)

### 4.2.6 Terms used to measure the quality of bandwidth 

**Latency** : amount of time, including delays, for data to travel.

**Throughput** : measure of the transfer of bits across the media over a given period of time.
- usually lower than the bandwidth
- factors that influence throughput : amount of traffic, type of traffic, latency created by the number of network devices encountered between source and destination

**Goodput** : measure of usable data transferred over a given period of time.
- always lower than throughput, which is lower than the bandwidth


## 4.3 Copper Cabling
### 4.3.1 Characteristics of Copper Cabling
- Most used type of cabling.
- There are 3 different types of copper cabling all for specific situations.
- Inexpensive, easy to install and low resistance to electrical current.
- Limited by distance and signal reference.
- Data is transmitted by electrical pulse.
- There is a detector in the network interface of a destination device. It must receive a signal that can be decoded to match the signal sent. 
  - **Signal attenaution** : The farther signal travels, the more it deteriorates. 
   - Copper media must follow a strict distance limitations specified by the guiding standards.

Two sources of interference :
1) **Electromagnetic interference (EMI) or radio frequency interference (RFI)** : can distort and corrupt data signals carried by a copper media. 
- To counter this type of interference, copper cables are wrapped in metallic shielding and needs proper grounding connections.
2) **Crosstalk** : caused by electric or magnetic fields. When an electrical current flows through a wire, it creates a small, circular magnetic fied through a wire that can be picked up by an adjacent wire.
- For example, in telephone circuits, it results in hearing part of another voice conversation from an adjacent circuit.
- To counter this type of interference, copper cables have opposing circuit wire pairs twisted together which cancels the crosstalk.

![Interference of data transmission](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/interference_data_transmission.png)

### 4.3.2 Types of Copper Cabling
![Types of copper cabling](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/types_copper_cabling.png)

**Unshielded Twisted-Pair (UTP)**
- Most command networking media
- Uses RJ-45 connectors : used for interconnecting network host wit intermediary networking devices (switches, routers)
- In LANs, there are 4 pairs of color-coded wire that are twisted together and encased in a flexible plastic sheath. The twisting help from signal interference from other wires.
- cancellation 

![Color code wires of UTP](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/color_code_wires_UTP.jpg)

1. Outer jacket protects the copper wires from physical damage.
2. Twisted-pairs protect signal from interference.
3. Color-coded plastic insulation electrically isolates wires from each other and identifies each pair.


**Shielded twisted-pair (STP)**
- Provides better noise protection than UTP.
- More expensive and difficult to install.
- Uses RJ-45 connector.
- Combines the tehcniques of shielding to counter EMI and RFI and wire twisting to counter crosstalk.
- Uses special shield STP data connectors.
- If the cable is improperly grounded, the shield may act as an antenna and pick up unwanted signals.

![STP cable](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/straight_tip_connector.jpg)

1. Outer jacket
2. Braided or foil shield
3. Foil shields
4. Twisted pairs


**Coaxial cable** or coax
- There are 2 conductors that share the same axis. 
- Different type of connectors used with coax cable : Bayonet Neill-Concelman (BNC), N type, F type

2 types of situations :
1. **Wireless installations** : coax cables attach antennas to wireless devices, it carries radio frequency (RF) engery between the antennas and the radio equipment.
2. **Cable internet installations** : internet service providers replaces portion of the coax cable and support amplification elements with fiber-optic cable. The wiring inside is still coax cable.

![Coax cable](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/coax_cable.jpg)

1. Outer jacket : entire cable is covered with a cable jacket 
2. Braided copper shielding : surrounded in a woven copper braid or metallic foil. It acts as the second wire in the circuit and as a shield for the inner conductor. Also reduces the amount of outside electromagnetic interference. 
3. Plastic insulation : surrounds the cooper conductor
4. Copper conductor : used to transmit the electronic signals

## 4.4 UTP Cabling
### 4.4.1 Properties of UTP Cabling
![UTP cabling](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/UTP_cabling.jpg)

Ways to limit the effect of crosstalk :
- **Cancellation** : When two wires in an electrical circuit are placed close together, their magnetic fields are the opposites and cancels each other and also the EMI and RFI.
- **Varying the number of twists per wire pair** : UTP capable follows specifications concerning the number of twists or braids are permitted per meter of cable.
  - Each colored pair is twisted a different number of times.

UTP cable relies mostly on the cancellation effect produced by the twisted wire pairs to limit signal degradation.

### 4.4.2 UTP Cabling Standards and Connectors
- Conforms to standards by TIA/EIA -568
- Cables are categorized based on thei capacity of carrying bandwidth rates.
  - For example / Category 5 cable is used in 100BASE-TX Fast Ethernet Installations, Enhanced Category 5 cable, Category 6 and Category 6a.
- Cables in high cateogry are made to support higher data rates.

![3 Categories of UTP Cable](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/categories_UTP_cable.jpg)

- Category 3 : was used for voice communication over voice lines but now used for data transmission
- Category 5 and 5e : used for data transmission
  - Category 5 supports 100Mbps
  - Category 5e supports 1000 Mbps
- Category 6 : has an added separator between each wire pair to support higher speeds.
  - Supports up to 10 Gbps
- Cateogry 7 : supports 10 Gbps
- Category 8 : supports 40 Gbps

**RJ-45 UTP plugs** : male component, crimped at the end of the cable. 
![RJ-45 UTP plugs](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/RJ-46_UTP_plugs.jpg)

**RJ-45 UTP Sockets** : female component, wall, cubicle, partition outlet or patch panel.
![RJ-45 UTP sockets](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/RJ-45_UTP_sockets.jpg)

**Poorly terminated UTP Cable** : wires are exposed, untwisted and not entirely covered by the sheath.
- Improper cable termination can impact transmission performance.
![Poorly terminated UTP Cable](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/poorly_terminated_UTP_cable.jpg)

**Properly terminated UTP Cable** : wires that are untwisted only to the extent necessary to attach the connector.
![Properly terminated UTP Cable](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/properly_terminated_UTP_cable.jpg)

### 4.4.3 Straight-through and Crossover UTP Cables
**Ethernet Straight-through** : most common. Used to interconnect a host to a switch and a switch to a router.

**Ethernet Crossover** : Used to interconnect similar devices (Switch to swtich, host to host, etc.)

**Rollover cable** : Cisco proprietary. Used to connect a workstation to a router or switch console port.

- Using either types will not damage a device but the connectivity and communication will not take place. 

**T568A and T568B Standards**

![T568A and T568B Standards](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/T568A_T568B_standards.jpg)

**Cable Types and Standards**

![Cable Types and Standards](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/cable_types_standards_table.jpg)

## 4.5 Fiber-Optic Cabling
### 4.5.1 Properties of Fiber-Optic Cabling
- Transmit data over longer distances and at higher bandwidth
- Less attenuation and immune to EMI and RFI
- Flexbile, extremely thin, transparent strand of pure glass

### 4.5.2 Types of Fiber Media
**Single-mode Fiber (SMF)**

![Single-Mode Fiber](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/single_mode_fiber.jpg)

- Consist of a very small core and uses expensive laser technology to send a single ray of light
- for long distance situations, hundreds of kilometers

**Multimode Fiber (MMF)**

![Multimode Fiber](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/multimode_fiber.png)

- Consist of a larger core and uses LED emitters to send light pulses
- LED enters at different angles (image)
- Popular because they can be powered by low-cost LEDs
- Provides bandwidth up to 10 Gb/s over up to 550 meters

**Difference between SMF and MMF** 
- Amout of dispersion : spreading out of a light pulse over time
- Increased dispersion : increased loss of signal strength
- MMF has greater dispersion than SMF
- MMF can traval up to 500 meters before signal loss

### 4.5.3 Fiber-Optic Cabling Usage
- **Entreprise Networks** : backbone cabling applications and interconnecting infrastructure devices
- **Fiber-to-the-home (FTTH)** : always-on broadband services to homes and small businesses
- **Long-Haul Networks** : used by service providers to connect countries and cities
- **Submarin Cable Network** : provides high-speed, high-capacity solutions capable of surviving in harsh undersea environnements

### 4.5.4 Fiber-Optic Connectors
- End of an optical fiber
- Main differences between types of connectors are dimensions and methods of coupling. 

**Straight-Tip (ST) Connectors** : first connector type used. Secured with a "Twist-on/Twist-off" bayonet-style mechanism.

![Straight-Tip Connector](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/straight_tip_connector.jpg)

**Subscriber Connector (SC) Connectors** or square connector or standard connector : widely adopted LAN and WAN connector that uses a push-pull mechanism to secure insertion. It's used with multimode and single-mode fiber.

![Subscriber Connector](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/subscriber_connector.jpg)

**Lucent Connector (LC) Simplex Connectors** : smaller version fo SC connector. Also called little or local connectors.

![Lucent Connector](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/lucent_connector.jpg)

**Duple Multimode LC Connectors** : similar to a LC simplex connecter but uses duplex connector.

![Duplex Multimode LC Connector](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/duplex_multimode_LC_connector.jpg)

### 4.5.5 Fiber Patch Cords
- Required for interconnecting infrastructure devices/
- The colors distinguishes between a single-mode and multimode patch cords.
  - Yellow is for single-mode and orange (or aqua) is for multimode fiber cables.

**SC-SC Multimode patch cord**

![SC-SC Multimode patch cord](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/SC-SC_multimode_patch_cord.jpg)

**LC-LC Single-mode patch cord**

![LC-LC Single-mode patch cord](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/LC-LC_single_mode_patch_cord.jpg)

**ST-LC Multimode Patch Cord**

![ST-LC Multimode Patch Cord](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/ST-LC_multimode_patch_cord.jpg)

**SC-ST Single-Mode Patch Cord**

![SC-ST Single-Mode Patch Cord](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/SC-ST_single_mode_patch_cord.jpg)


### 4.5.6 Fiber vs Copper
![Fiber vs Copper](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap4/fiber_vs_copper.jpg)


## Wireless Media
### 4.6.1 Properties of Wireless Media
Carries electromagnetic signals representing binary digits of data communications using radio or microwave frequencies.

Some limitations :
- **Coverage area** : certain area (buildings, structures, local terrain) can limit the effective coverage.
- **Interference** : susceptible to interference and can be disrupted with common household cordless phone, types of fluorescent lights, microwave ovens and other communications.
- **Security** 
- **Shared medium** : a wireless medium is shared amongs wireless users. Having many users accessing the WLAN results in reduced bandwidth for each user.

### 4.6.2 Wireless Standards
- **Wi-Fi(IEEE 802.11)** : WLAN tehcnology or Wi-FI. Uses contention-based protocol known as carrier sense multiple access/collision avoidance (CSMA/CA). The Wireless NIC must first listen before transmitting to determine if the radio channel is clear. If another wireless device is transmitting then the NIC must wait til the channel is clear. 
- **Bluetooth (IEEE 802.15)** : Wireless personal area network (WPAN) standard. It uses devices pairing process to communicate over distances from 1 to 100 meters.
- **WiMax (IEEE 802.16)** : Worldwide, interoperabilitw for Microware Access. Uses a point-to-multipoint topology to provide wireless broadband access.
- **Zigbee (IEEE 802.15.4) : used for low-data rate, low-power communications. For applications that require short-range, low-data rates and long battery life. Used for industrial and IoT environnements such as wireless light switches and medical device data collection.

### 4.6.3 Wireless LAN
- **Wireless Access Point (AP)** : Concentrate the wireless signals from users and connect to the existing copper-based infrastructure (Ethernet). Mostly for homes and small business. 
- **Wireless NIC adapter** : provides wireless communication capability to network hosts.























































