# Analysis and Design
#COMP2912
**Analysis** - Understanding the **Problem**
**Design** - Understanding the **Solution**
## Good design is:
- simple
- easy to use
- reliable
- secure
- quick
- well integrated
- flexible for the future
## Iterative Requirement Analysis
Create overall [use cases](Use%20Cases.md) then specify on later iterations
1. Obvious [Use Cases](Use%20Cases.md)
2. Extra [Use Cases](Use%20Cases.md), simple case descriptions
3. Structured [Use Cases](Use%20Cases.md), structures Use Case descriptions, Prototypes
4. ...
## Designing a New Process
Eliminate, Simplify, Integrate or Automate
- Get rid of excess, find which process aren't being used or process that are being duplicated
- Make useful processes easier to understand
- Combine parts of the business into a system to work together easier
- Rid of human tasks that can be automated. i.e. data transfer/ analysis
## Component Based Software Architecture
- An individual component is a software package, a web service, or a module that encapsulates a set of related functions (or data).
- All system processes are placed into separate components so that all of the data and functions inside each component are semantically related (just as with the contents of classes). 
- Because of this principle, it is often said that components are modular and cohesive.With regard to system-wide co-ordination, components communicate with each other via interfaces. 
- When a component offers services to the rest of the system, it adopts a provided interface which specifies the services that other components can utilise, and how they can do so. 
- The client does not need to know about the inner workings of the component (implementation) in order to make use of it. 
- This principle results in components referred to as encapsulated
## Architecturally Significant [Use Cases](Use%20Cases.md)
- A [Use Case](Use%20Cases.md) that implies a change to the architecture of a system
- Implies technical risk and potential extra costs, e.g. internet access
- Will need to use a [Implementation Diagram](Implementation%20Diagram.md) to see infrastructure needed for these [use cases](Use%20Cases.md)
- Architecturally significant because they introduce a requirement for:
	- new actors 
	- new deployment platforms
	- new operational styles(online, batch, etc.)
	- new performance
	- new security etc...
### MuSCoW
For Prioritising [Use Cases](Use%20Cases.md)
- **Mu**  Must Have [Use Cases](Use%20Cases.md) - Develop these in Proof of Architecture
- **S**     Should Have [Use Cases](Use%20Cases.md) - Develop these in subsequent iterations
- **Co**  Could Have [Use Cases](Use%20Cases.md) - Develop these in later iterations but only if time, resources etc. allow.
- **W**    Wont Have [Use Cases](Use%20Cases.md) - Don’t do these at all but negotiate and make sure the relevant stakeholders are aware they are outside the scope of the project.
Initial Release should have all **Mu**s and nothing else. All further releases will expand on these
Identify which [Use Cases](Use%20Cases.md) might be Architecturally Significant –
- because they imply a significantly different design architecture. 
- These should be treated as Must Haves simply because the design architecture needs to take them into account. 
- They’re likely to prove expensive so the other option may be to persuade stakeholders that they should be Wont Haves
## UI Prototypes
- Use [Use Cases](Use%20Cases.md) to show what needs to be in the program
- Can be built quickly 
- May include forms and reports as well as screens!
- They should be designed to be thrown away
### Benefits
- SPEED - they can be ‘hacked’ without rigorous coding
- they show users what it could look like
- commonly used for requirements capture(users like them, they look tangible/ real)
- helps solve the IKIWISI problem
### Disadvantages
- can distract users with detail
- typically users react by debating non functional requirements qualities such as colour scheme, layout, fields i.e. the user interface (not the system) design
- WORSE they may give the impression that development is trivial.
- Developers may be reluctant to throw them away
