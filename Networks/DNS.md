# Domain Name System
A host can be addressed in either
- A readable host name (i.e. www.leeds.ac.uk)
- An [IP Addresses](IP%20Addresses.md)
DNS is the way computers turn the readable host name to an [IP Addresses](IP%20Addresses.md)
## Key Concepts:
### Indirection:  
- Names replace IP addresses.  
- We rarely use IP addresses directly.  
### Hierarchy:  
- Apparent in IP addresses, their names, and the DNS server structure itself.  
### Distribution:  
- No single DNS server contains all names or IP addresses.  
- Scalable.  
### Caching:  
- Local caching of DNS results for re-use

## Uniqueness
One hostname can map to multiple IP addresses:  
- Popular servers will typically have multiple IP addresses around the world
- The DNS server may try to select the ‘closest’ to the sender
- It may also rotate through the list of IP addresses, to reduce congestion
- Popular web sites or CDNs (Content Distribution Networks), will typically have multiple addresses from which their content can be accessed (how these sites are synced is another matter)

Multiple Names can map to a single [IP Addresses](IP%20Addresses.md)
- Known as aliasing
- Especially useful in mail addresses
- Can simplify host names for web sites

## DNS Protocol
- Uses [UDP](UDP.md), although can use [TCP](TCP.md) in special circumstances (transferring lots of data from one server to another)
- Queries fail if not answered in a set time limit
	- May retry until successful
- Uses [Port](Ports.md) 53
- Messages are either 'query' or 'reply' using the same format
- A DNS query will pass through the heirarcy
	- Local host is configured to connect to a local DNS server . . .  
	- . . . which negotiates with root DNS server to find TLD server . . .  
	- . . . and then negotiates with TLD server to find Authoritative DNS server . . .  
	- . . . and then negotiates with Authoritative DNS server to resolve host name to IP address . . .  
	- . . . and then returns this IP address to the local host.  
	![](Pasted%20image%2020240509172239.png)
## DNS Caching
The query process has an overhead
- Primarily a delay, especially if one of the queries is lost and needs to be resent
- May also cause congestion as there will be a high number of messages on each server
To improve performance query results are cached on the local DNS server
- Cache is checked before the root DNS server is used
- Can cache IP addresses for TLD servers, bypassing the need to access the root server
If a query is successful:  
The returned DNS message will include a TTL, or a  
time-to-live.  
Will cache until the TTL expires, typically days
## Terminal Commands

| Command               | Reason                                                                                                     |
| --------------------- | ---------------------------------------------------------------------------------------------------------- |
| nslookup (depricated) | Resolves hostnames to IP addresses                                                                         |
| host                  | Basic resolution of hostnames and IP addresses                                                             |
| dig                   | Resolves hostnames and IP addresses<br>Can also trace the DNS query<br>Allows for a more detailed response |
