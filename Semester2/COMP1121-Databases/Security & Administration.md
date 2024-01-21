# Security
#COMP1121
Protect against:
- Loss of confidentiality on the secrecy over data critical to organisation
- Loss of privacy on data about individuals
- Loss of integrity with invalid or corrupted data
- Loss of availability as data or systems unavailable to legitimate users
- Theft and fraud of data, identity, program, hardware
## Authorisation
- The granting of a right or privilege to enable a subject to have legitimate access to a system
- Involves authentication to determine that the author is really who they say they are
- Common authentication is a password of passphrase
- Other methods inc multi-factor authentication like Duo

## Access Method
- Methods used to enforce authorisation
- Based on the granting and revoking privileges
- A privilege allows read, write or other DBMS utilities
- Most DBMS have an approach called DAC (Discretionary Access Control)
	- SQL supports DAC through GRANT and REVOKE commands (not SQLite)
- Also MAC (Mandotary Access Control)
	- each object is assigned a security class and each subject is assigned a clearance for a security class, with rules governing the access to the objects
	- Not supported in current SQL standard

## Backup & Recovery
- Backup at regular intervals to a secure location
### Journaling
- Keep and maintain a log file (or journal) of all changes made to database to enable effective recovery in event of failure

## Integrity Constraints
- Domain Constraints
- Entity Integrity
- Referential Integrity

## Encryption
- The encoding of data such that it cannot be read without a decryption key
- Four components: 
	- encryption key
	- encryption algorithm
	- decryption key
	- decryption algorithm
### Asymmetric Encryption
- When a different key is used for encryption and encryption
- Challenges:
	- Key generation
	- Authentication of public key -> Public key infrastructure (PKI)
- Usage: 
	- Public key encryption
	- digital signatures

## Hashing
- Taking a group of characters and applying a hash function to it to generate a fixed length hash value
- One way encryption Hashes are irreversable
- Usage:
	- Verify integrity of files and messages
	- Digital signatures
	- Password verification

## RAID
- Redundant Array of In-dependant Disks
-  Hardware running the DBMS must be fault-tollerent
- With redundant components that can be integrated whenever there is a component faliure
	- e.g. disk drives, disk conrollers, CPU, power supply, cooling fans

## DBMS and Web Security
- Internet runs on TCP/IP
- Not designed with security
- All traffic travels in the clear
- Must ensure data transferred over the internet is:
	- inaccessible to anyone but the sender and receiver
	- not changed during transmission
	- Receiver can ensure it came from the sender
	- sender can ensure the receiver is genuine
	- sender cannot deny they sent it
- Measures include:
	- Proxy servers
	- Firewalls
	- Message digest algorithms and digital signatures
	- Digital certificates
	- Kerberos
	- Secure sockets layer (SSL) and Secure HTTP (S-HTTP)
	- Secure Electronic Transactions (SET) and Secure Transaction Technology (SST)

## Data & DB Administration
- Data administrator (DA)
	- Managing data resource, including database planning, development, maintenance of standards, policies, procedures, conceptual and logical database design
- Database administrator (DBA)
	- Application/physical database design to operational management including setting security and integrity control, monitoring system performance
### Data administration tasks
- Selecting appropriate productivity tools
- Assisting in the development of the corporate IT/IS and enterprise strategies
- Undertaking feasibility studies and planning for database development
- Developing a corporate data model.• Determining the organisation’s data requirements
- Setting data collection standards and establishing data formats
- Estimating volumes of data and likely growth
- Determining patterns and frequencies of data usage
- Determining data access requirements and safeguards for both legal and enterprise requirements
- Undertaking conceptual and logical database design
- Liaising with database administration staff and application developers to ensure applications meet all stated requirements
- Educating users on data standards and legal responsibilities
- Keeping up to date with IT/IS and enterprise developments
- Ensuring documentation is up to date and complete, including standards, policies, procedures
- Use of the data dictionary, and controls on end-users
- Managing the data dictionary.• Liaising with users to determine new requirements and to resolve difficulties over data access or performance
- Developing a security policy
### Db administration tasks
- Evaluating and selecting DBMS products.• Undertaking physical database design
- Implementing a physical database design using a target DBMS
- Defining security and integrity constraints
- Liaising with database application developers
- Developing test strategies
- Training users
- Responsible for “signing off” on the implemented database system
- Monitoring system performance and tuning the database as appropriate
- Performing backups routinely
- Ensuring that recovery mechanisms and procedures are in place
- Ensuring that documentation is complete, including in-house produced material
- Keeping up to date with software and hardware developments and costs, and installing updates as necessary