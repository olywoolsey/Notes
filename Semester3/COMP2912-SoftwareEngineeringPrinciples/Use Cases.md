# Advanced Use Cases
#COMP2912
Use cases represent a transaction of value
Use Case Modelling is based on the assumption that for a use case to be used there must be a positive [[Value Proposal]] which explains why a person would want to do it
## Use Case Diagrams
- A type of [UML](UML.md) Diagram
![](Images/UseCaseDiagram.png)
**Functional Requirements** - what system should do for users
### Black Box Perspective
- From an outsiders perspective the system we are modelling is .. a black box
- The user shouldn't need to know how the internal system works
- We just need to put what they need to know and hide the backend
### Non-Functional Requirements
**Non Functional Requirements** - what design qualities the functions and whole system must have(how well it should do what it does)
#### Security
Two main issues: 
- Securing sensitive data from theft or abuse
- Securing the integrity and operation of the system
##### Firewall
Hardware and/ or Software placed between an organisation’s internal network and an external network to prevent outsiders from invading private networks
##### Zoned Security Principle
Different levels of security are appropriate based on:
How much public access is required vs. How valuable are the things we need to secure

| Attack | Defence |
| ---- | ---- |
| Unauthorised Access | Tight Password Management |
| Exploit known weaknesses in programs | Continuously upgrade Systems withpatches and new version. |
| Denial of Service(Overwhelm/ Block the entrance) | Firewall.Monitor, detect and block |
| Trojan Horse Programs | Don’t accept programs from anyone |
| Eavesdropping and Spoofing(Attack the commercial traffic on the road) | EncryptionCertification |
##### Abuse Cases
Ab-use Case (or Mis-use Case) are Use Cases that we want to stop.
The Actor is a “bad actor”. The Abuse case is a case of abusing the system.
Their [value proposal](Value%20Proposal.md) is to steal or cause harm. 
To stop them we need to reduce reward and increase effort.
Abuse case modelling is complementary with threat analysis and other cyber security approaches