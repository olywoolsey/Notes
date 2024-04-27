# Protocol Stack
- Are defined to pass messages between layers.
- For this reason, sometimes referred to as the protocol stack
- This modular design allows internal components to be easily replaced
- Potential for redundancy — overlapping operations carried out at more than one level
- Popular Stacks include [TCP IP](TCP%20IP.md) for the internet and [OSI Model](OSI%20Model.md) for a more general design

| Stack |
| ---- |
| Application Layer |
| Transport Layer |
| Network Layer |
| Link and Physical Layer |
household analogy:
12 kids in Ann’s house sending letters to 12 kids in Bill’s house:
hosts = houses
processes = kids
app messages = letters in envelopes
transport protocol = Ann and Bill who demux to in-house siblings
network-layer protocol = postal service