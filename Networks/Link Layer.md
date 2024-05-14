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

## Where Is It?
- Implemented in each host
- Adaptor (NIC = Network Interface Card) / chip