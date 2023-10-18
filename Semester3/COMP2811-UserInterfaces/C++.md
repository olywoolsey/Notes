#COMP2811 
## Classes
``` java
public class Foo {
	public Foo () {
		System.out.println(“created”);
		}
	public int aMethod() {
		return 1337;
	}
}
```
```c++
class Foo {
public:Foo() {std::cout << "created" << std::endl;}int aMethod() {return 1337;}};
```
## Constructor
- Special method that is automatically called when an object of a class is created
- To create use class name followed by ()
- The constructor has the same name as the class, it is always public, and it does not have any return value
```c++
class Foo { // the class
private:
	int myk; // creates private variable
public:
	Foo(int k) { // the constructor with parameter
		myk = k; // assigns parameter passed in to priv var
		std::cout << "created" << std::endl; // print ln
	}
	int whatsMyK() {
		return myk;
	}
	~Foo() {
		std::cout << "destroyed" << std::endl;
	}
};

// later in program ... 
Foo myObj; //will create object in class Foo, will call constructor
```
