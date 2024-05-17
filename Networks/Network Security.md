# Security
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
#### Issues
- The key must be communicated in advance such that both participants have knowledge of it.  
- If it is sent unencrypted, it could be intercepted.  
- Would need to communicate by some other means.  
- Could physically install key on each machine, but this would not allow network communications
- Anyone in possession of that key can read all communication.  
	- They could relay the messages to remain undetected

### Asymmetric Key Algorithms
- Each participent has a private/public key pair
- To send a message, ask for the recipients public key
- Use this to encrypt message: $C = E_{k_{pub}}(M)$
- The recipient uses their key pair to decrypt
- This way, even if C is intercepted, it cannot be read because both keys are required for decryption - and the recipient never communicates the private key $k_{pvt}$
- For this to work, $k_{pvt}$ and $k_{pub}$ need to share a special relationship, but $k_{pvt}$ cannot be inferred from $_{pub}$ Standard implementation is RSA (Rivest-Shamir-Adleman)

### In Practice
- Symmetric key algorithms are relatively efficient in code
- Asymmetric algorithms are compute intensive
**Compromise**
- Use a asymmetric algorithm to send a (short) symmetric key
- Known as a session key
- Use this key with a symmetric algorithm to encrypt and decrypt the (long) communicaction

### Man-in-the-middle Attacks
Since kpub is public, anyone can use it to encrypt a message.  
The receiver does not know who is sending the message
A possible scenario is:  
- A wants to send a message to B, using B’s key kB pub. 
- However, a third party M intercepts kB pub and instead sends his/her key kM pub to A.
- A encrypts his/her message using kM pub.  
- M intercepts the message, decrypts and reads it.  
- M then encrypts the message using kB pub and relays it to B.  
## Authentication
Client can trust they are connected to the server they think they are - server authentication
- Adds trust to the transmitted public key
- The server sends a certificate containing its public key to any new client
- The certificate gaurantees it came from the server
- The client can check this
- The client then sends their public key for communication
The certificate is signed by an approved certification authority
- Very hard but not impossible to fake this

### Obtaining a certificate
- Commercial entities buy a certificate from a certification authority. 
	-  e.g. VeriSign for SSL (Secure Sockets Layer)
	- [Java Networks](Java%20Networks.md) use X.509 certificates

## Java Security
Java provides the following packages for secure communication:  
Java Secure Socket Extension (JSSE):  
- javax.net.*  
- Includes Secure Sockets Layer (SSL) as javax.net.ssl.*  
- Also includes the more recent Transport Layer Security (TLS).  
These protocols lie inbetween the Application and Transport layers.  
Technically breaks the 5-layer TCP/IP protocol (although not the 7-layer OSI protocol; see Lecture 2)
#### SSLSocket Class
