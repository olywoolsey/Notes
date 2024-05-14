# Security

**LECTURE 13**

## Examples

| Layer       | Examples of Security Protocols                |
| ----------- | --------------------------------------------- |
| Application | PGP = Pretty Good Privacy                     |
| Transport   | SSL = Secure Socket LAyer for TCP connections |
| Network     | VPN = Virtual Private Networks using IPsec    |
| Link        | WEP = Wired Equivalence Privacy for Wi-Fi     |
| Physical    | Quantum communication (incomming)             |

## Encryption
Traffic is ‘secure’ even if intercepted

Start with a plain text message M.  
Assume an encryption algorithm E exists such that it  
encrypts M into cypher text form C = E (M).  
Further assume that a corresponding decryption algorithm  
D exists such that M = D(C )
### Symmetric Key Algorithms
The 2 participants in the communication share knowledge of the unique key
- $C = E_K(M), M = D_K(C)$
- Both need the same key, hence symmetric
- Standard algorithms include DES (Data Encryption Standard) and AES (Advanced Encryption Standard)
1. Client asks for k from server.  
2. Server sends k.  
3. Client encrypts message $C = E_k (M)$ and sends.  
4. Server receives and decrypts $M = D_k (C )$
## Authentication
Client can trust they are connected to the server they think they are - server authentication