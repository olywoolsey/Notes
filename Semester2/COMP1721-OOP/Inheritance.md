#COMP1721
## Association
- One class knows about, and collaborates with, another
- Collaboration isnʼt just temporary
- ... so an instance of one class has a field that maintains a reference to an instance of the other
- ... allowing it to call methods on that instance whenever it wants (calling methods = ʻcollaborationʼ)
![[Pasted image 20230302140921.png]]

## Composition / Aggregation
"" X is composed of Y""
- One class (the ʻcompositeʼ) has component parts that are represented by another class
- Representation in code can be same as association
- ... although we often see cases where there are multiple parts making up the whole
- ... in which case, an instance of the composite class will need to maintain a collection of references to instances of the component class
![[Pasted image 20230302141440.png]]
```java
class Band {
	private Set<Musician> members;
	...
	public void join(Musician musician) {
		members.add(musician);
	}
	public void leave(Musician musician) {
		members.remove(musician);
	}
}
```

## Inheritance 
- Subclass inherits attributes & behaviour of the superclass
- Subclass can introduce additional attributes and new behaviour that isnʼt found in superclass
- Subclass can also alter behaviour specified by superclass
![[Pasted image 20230302142623.png]]
### When to use
If you have two classes X & Y and you want to know if Y should inherit from X, ask yourself: 
	Does the phrase “Y is a kind of X” make sense?
		If The answer is not clearly **Yes** then it should not be used

## How to use in Java
Student inherits fields and methods from Person and can add its own
```java
public class Person {
	private String givenName;
	private String familyName;
	private LocalDate dateOfBirth;
	...
}
public class Student extends Person {
	private String degree;
	private YearMonth start;
	...
}
```