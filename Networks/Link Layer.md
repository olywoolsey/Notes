# Link Layer
*Responsible for transferring data from one node to a physically adjacent node*
- The Link layer controls how packets are transported between network nodes
- How e.g. your device or laptop is detected by a Wi-Fi network
- Error checking, which may be redundant (i.e. repeated at another level)
- Link layer implemented in each host:
	- Adaptor (NIC = Network Interface Card) or chip.  e.g. Ethernet card, 802.11 card, Ethernet chipset. 
	- Attaches to the host’s system buses.
	- Combination of hardware, software and firmware.
## Terminology
- **Node:** Host or Router
- **Link:** Communication channel that connect **adjacent** nodes (wired or wireless)
- **Link Layer Protocol:** The method each link uses to send data
- **Frames:** Data packets (information being sent)
- **[MAC Addresses](MAC%20Addresses.md):** For source and destination

## Services
**Framing and link access:**
- Encapsulate the datagram/packet into a frame, adding a header and possibly footer
- Channel access if the medium is shared
- [MAC Addresses](MAC%20Addresses.md) used in frame headers

**Reliable delivery between adjacent nodes:**
- Similar strategy to [TCP](TCP.md)
- Seldom used on wired links because of low error rates
- More important for wireless links with high error rates

**Flow Control**
- Pacing between adjacent sending and receiving nodes

**Error Detection**
- Errors caused by signal attenuation / noise
- Receivers detect presence of errors; signals sender to re-transmit or drops frame

**Error Correction**
- Receiver identifies and corrects bit errors using checksum, without requiring re-transmission

**Half-duplex and full-duplex**
- Half-duplex means nodes at both ends of a link can transmit, but not at same time
- Full-duplex means both nodes can transfer data simultaneously as they use different channels 
## Multiple Access Protocols
### Single, shared access channel.
- Two or more simultaneous transmissions may interfere
- Collision if node receives two or more signals at once
$\therefore$ need a multiple access protocol:
	- Distributed algorithm that determines how nodes share the channel
		- e.g. when a node transmits
	- Coordination needed for better channel sharing and communication

### Types of Multiple Access Protocols
#### Channel Partitioning
- Divide channel into 'pieces' (time slots; frequency; code)
- Allocate pieces for node exclusive use
##### TDMA = Time Division Multiple Access
- Each node gets a fixed length time slot
- Issue:
	- Used slots go idle: not an efficient use of bandwidth
	- Normally have to wait to start communicating
##### FDMA = Frequency Division Multiple Access
- Dividing channel into frequency bands
- Each node is assigned one band
- Meaning each node can listen for just their frequency therefore can send packages at the same time. 
- Issue: 
	- Not efficient use of bandwidth as can't use all frequency and some will be idle
#### Random Access
- Randomise send times to minimise chances of collision
- If collision detected, recover(i.e. transmit)
- e.g. CSMA = Carrier Sends Multiple Access, and variations
##### Slotted ALOHA
- Start sending immediately
- If hardware detects collision, resend after a random time interval
- Repeat if necessary
- If only one node is communicating it uses full bandwidth
- Issues:
	- Collisions result in wasted slots
	- Other protocols can achieve higher efficiency
#### Taking Turns
- Nodes take turns, but nodes with more to send can take longer turns (coordinate using tokens)

## Ethernet
### Frame Structure
**| Preamble | dest. address | source address | type | data (payload) | CRC |**
- Preamble has a fixed bit pattern, for synchronisation
- Destination and source [MAC Addresses](MAC%20Addresses.md)
- Type, usually IP, but can be another higher-level protocol
- CRC = Cyclic Redundancy Check, for detecting errors
### Standards
There are many different standards
- Common MAC protocol and frame format
- Different speeds: 2 Mbps, 10 Mbps, 100 Mbps, 1 Gbps, 10 Gbps
- Different [Physical Layer](Physical%20Layer.md) media: fibre, cable.
![](Pasted%20image%2020240514144209.png)
