#COMP2811
## Not an Object
- In Java, all classes inherit from the object class
- [[C++]] you control everything so doesn't have this

## Not everything is virtual
- In Java, if you see something (not private/protected) you can redefine it.
- In [[C++]], only things that are marked as virtual can be redefined
- More efficiency: Java needs to check if the method has been overridden by a subclass. [[C++]] assumes it did not
- You can mark a virtual function as “final” to specify that it cannotbe further redefined

## Multiple Inheritance
- Java has single inheritance, but many interfaces
- [[C++]] can have multiple inheritance
- [[C++]] can end up with the diamond problem
### No interfaces
- In java an interface is a "class skeleton"
- [[C++]] is a class that has "pure virtual methods"

## Access control
- Java uses the keyword "extends"
- [[C++]] you can have different types os inheritance
	- Public inheritance-> same as Java
	- Protected inheritance-> public members of parent class become protected
	- Private inheritance-> now everything is private. Default behaviour

## Directed access to Grandpa
- access to parents parent - classes
- java can't do super.super.print()

## Initialisation
- Both call the empty constructor by default when making a class
- difference is how you call parameterised constructors
```java
class Shape {
public:
	int width, height;
	Shape() { }Shape(int h, int w): width(w), height(h){ }
};
```
```c	
class Rectangle : public Shape {
	Rectangle() {};
	Rectangle(int h, int w) : Shape(h, w) { }
};
```

## Diamond inheritance
- in [[C++]] as you can inherit multiple classes two called classes could inherit the same class
- this would give two grandparent classes which calls the constructor twice making an error
- Because the code does not know which version of the constructor to call, it calls the default (empty) constructor instead.

## Organisation
- In Java, you had folders/sub-folders that would represent packages. And your classes were exactly inside one file
- In [[C++]], it is usual to just define a class in a .h .hpp file, and have function definitions inside a .cpp file
- You can always have everything in the header file, like we have been doing
- As in C, it is easier to just include definitions

## Struct is a class
- In C++ structs inherit from a class, have methods
- Is public not private by default
- Does not give you default constructors and destructors

## Static also in functions
- The keyword static has the same use for class methods and variables, as in Java
- This makes them accessible at class level, no instance is required
- In C++ we can also declare a static variable inside a function
	- Variable will only be initialised once, the first time it is called
	- Next calls to the function will not call the initialisation again