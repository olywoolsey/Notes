# Network Layer
- Layer that handles [IP Addresses](IP%20Addresses.md) for hosts and routers
- Most common protocol is the Internet Protocol, or IP
	- .Describes how data is grouped into datagrams (packets).
	- The network addressing scheme.
- A datagram is produced containing the data and header information.
- Also ICMP (Internet Control Message Protocol), which is how routers communicate to ensure efficient transport of messages through the network
- Java only understands IP
## ICMP: Internet Control Message Protocol
- Used by hosts and routers to communicate network level information
- e.g. error reporting
- ICMP messages carried in IP datagrams
- **ICMP Message:** type, code plus first 8 bytes of IP datagram causing error
### traceroute command
Source sends a series of segments to the destination
- First has Time To Live = 1, second has TTL = 2... etc
When $n$th datagram arrives at the $n$th router:
- Router discards it, returns ICMP message type 11 code 0
- When received, sender calculated RTT (Round Trip Time)
- Three times for statistics; '\*'  denotes timeout
**Stopping Criteria:**
- UDP segment eventually arrives at destination host
- Destination returns 'prt unreachable' (ICMMP message type 3) because port doesn't exist
- When source gets this, it stops

## Tunnelling
- Therefore IPv4 and IPv6 must co-exist (while switching)
- IPv6 carried as payload in IPv4 datagram among IPv4 routers
![](tunnelling.png)
## Routers
> [!Note]
> Note that although an idealised router has no Application or  
> Transport layer, in reality these higher layers are sometimes used. 
> Technically breaks the layered architecture model.
> Perform two functions:

### Architecture
![](router-architecture.png)

### Run routing algorithms to determine and efficient onward path
### Forward datagrams from an incoming link to an outgoing link
- Using a forwarding table determined by the routing algorithm
### Forwarding Table
The forwarding table selects the output port for each packet.  
- Too many [IP addresses](IP%20Addresses.md) to consider each one.  
- Therefore maps ranges of IP address destinations.  
- Uses prefixes a.b.c.d/x.  
- If multiple entries, use the longest prefix x, i.e. the smallest range of addresses
#### Generalised Forwarding
Early routers only used the destination IP address to determine the onward path for each packet.  

Greater control possible by using generalised forwarding:  
- Match incoming packets to actions.  
- Can use all header fields from Transport, Network and Link layer headers.  
	- Ports (source and destination), IP addresses, protocols, . . .  
- Actions can include dropping packets — firewalling.  

Forwarding based on IP destination address only is now seen as a simple case of match-action forwarding
### Software Defined Networks
The demand for generalised forwarding has lead to the development of devices that support SDN = Software Defined Networks.  
- Flow-based forwarding based on any information in the header fields.  
- Separates the control from the data.  
- Software can exist on separate servers to the router and be broken down in modules that can be developed independently.  
- Network is programmable.  
- Widespread standard is OpenFlow
### Routing Algorithms
Global or decentralised information?  
- If global, all routers have complete knowledge of topology and link costs. Leads to link state algorithms
- If decentralised, each router knows only physically-connected routers and link costs to them
	- Iterative process of computation and information exchange with neighbours (distance vector algorithms)
Can also be static or dynamic:  
- Static suitable if routes change slowly
- Dynamic if routes change more quickly, including link cost changes
#### Dijkstra's
- Computes least cost path from source node to all others
- Gives forwarding table for that node
- Iterative: After $K$ iterations, knows least cost to $K$ destinations
- Notation:
	- c(x, y ) is link cost for x → y , or ∞ if no direct link.  
	- D(v ) is current path cost from source to v .  
	- p(v ) is the predecessor node along path to v .  
	- N′ is set of nodes whose least cost path is known
```Pseudocode
N' = {u}
for all nodes v:
	if v is a neighbor of u
		then D(v) = c(u,v)
	else
		D(v) = infinity

find w not in N' such that D(w) is a minimum
add w to N'
update D(v) for each neighbor v of w and not in N'
	D(v) = min( D(v), D(w)+c(w,v) )
	/* New cost to v is either old cost to v or known
	least path cost to w plus cost from w to v */
until N' = N
```
#### RIP: Routing Information Protocol
- Distance vector algorithm, an iterative algorithm that only knows about local links and connected nodes
- Included in BSD-UNIX1, the precursor to FreeBSD, OpenBSD etc., in 1982
- Distance metric is the number of hops (maximum of 15)
##### RIP Advertisements
- Distributed algorithm that communicates asynchronously with directly connected nodes
- Distance vectors are exchanged among neighbours every 30 seconds via a response message, also known as an advertisement
- Each advertisement is list of up to 25 destination networks with the subnetwork
- The costs, defined as the number of hops
- Smaller messages that Dijkstra’s algorithm
- Tends to have slower convergence, with no guarantees
##### RIP Link Failure and Recovery
- If no advertisement is received after 180 seconds, that neighbour or link is declared dead
- Routes via the dead neighbour are invalidated
- New advertisements send to neighbours
- Neighbours in turn send out new advertisements, if their tables changed
- Link failure information quickly propagates into the network
##### RIP Table Processing
- RIP routing tables are managed by [Application layer](Application%20Layer.md) processes called route-d ('daemon')
- Advertisements are sent in UDP packets periodically repeated
Note this technically breaks the layered network architecture
#### OSPF: Open Shortest Path First
- 'Open' = publicly available
Use link state algorithm but only on subnetwork
- Topology map known at each node
- Route computation using **Dijstra's** algorithm
Only intended to act within an **AS = Automated System**
- Each ISP will have one or more AS's
- Gives subnetwork administrator greater control
- OSPF advertisements carry one entry per neighbour
- Carried directly over IP; does not use TCP or UDP
##### Hierarchical OSPF
Even a single ISP is normally too large for the whole network to be considered, so a two-level hierarchy is typically used with local areas and a backbone
- Link-state advertisements only in the local area
- Each node has detailed area topology, but only knows the shortest path to networks in other areas
#### BGP: Border Gateway Protocol
Provides each AS as a means to:
- Obtain the reachability information of a subnetwork to all routers internal to an AS
- Propagate reachability information to all routers internal to an AS
- Determine efficient routed to subnetworks based on reachability information and policy
- Allows subnetwork to advertise it's existence to the rest of the internet
##### Basics
Pairs of routers (BGP peers) exchange routing information over semi-permanent TCP connections: BGP sessions
- Need not correspond to physical links
- **External session:** Spans to AS's
- **Internal session:** Both BGP routers in the same AS
##### BGP Route Selection
A BGP router may learn about more than one route to a prefix, in which case it needs to select one
To help in this, there are some elimination rules:  
- Each potential route is assigned a local preference by the system administrator as per any policies
- For all routes with the highest local preference, the ones with the shortest AS-PATH (i.e. the number of AS’s the packet would pass through)
- If still tied, the shortest cost (i.e. number of physical links) to the first router in the next AS is used
- If still tied, other criteria could be considered