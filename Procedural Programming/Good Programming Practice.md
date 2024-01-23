#COMP1721
## Coding Style and Conventions
- for [[C Language]]
(also graded)

### Comments
```c
/*
Anything between these is a comment
Often used at the start to contain program information
who wrote it, how many revisions ect...
*/

code...

// Inline comment

code...   // Can also go after lines
```

### Naming of data items
- give everything a meaningful name
	**we can name:**
	- the code file
	- [[Functions]] we define
	- Variables we define

### Brackets
- C does not enforce formatting on your code (can write everything on one line)
	- {.} often defines major structure
	- { at the end of the line
	- } on a brand new line
```c
if( counter < 10 ) {
	printf( “ Counter = %i\n”, counter );
}
```

### Indentation
- does not require indentation but is useful
- Scope is generally defined by brackets {.}
- Can indent with whitespace or tabs
- Do not mix as tab spacing is not fixed-width
```c
#include <stdio.h>
int main( int argc, char *argv[] ) {       // indent for scope of main()
	if( argc > 1 ) {                       // indent for scope of if()
		printf( “%s\n”, argv[1] );
	}                                      // end of if()
	return 0;
}                                          // end of main()
```

### White space
- C compiler ignores white space
- adding white space improves readability
```c
#include <stdio.h>
int main(void){
	printf(“Hello!\n”);
	return 0;
}

// is the same as

#include <stdio.h>
  
int main( void ) {

	printf( “Hello!\n” );
	
	return 0;
}	
```

### Consistency
- Adopt a consistent style for:
	- comments
	- brackets
	- indentation
	- spacing

## Planning
- Do you understand the input?
- Do you understand how it needs to be processed?
- Do you understand the output
	Sketch a solution
	Make a flow-chat if necessary

## Testing
- always test in stages to make sure each part is working before moving onto the next part
- if compiled often then know most recent code is the problem
- often prinf() is useful for testing

#### Test Driven Design
- start by defining all the tests 
- every time you complete more of the program more tests will pass
- as soon as all tests pass then the program is complete