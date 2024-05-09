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
- Especially u