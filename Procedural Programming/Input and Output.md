#COMP1711
## I/O Principles
#### Input
- putting data into a system
- keyboard, mouse, speech, video, touchscreen
#### Output
- reporting system results
- monitor/screen, printer, speakers

## C
- c treats all i/o sources/ destinations as files
- accessed through file pointers(FILE \*)
- has 3 built-in file pointers for i/o (in <stdio.h>)
	- stdin - the keyboard
	- stdout - the terminal
	- stderr - the terminal

## formatted output - printf
- Part of the <stdio.h> library
- Provides simple formatted output to stdout (the terminal)
```c
printf( “format_string”, list_of_arguments );
```
- format_string can contain % which is a specifier for a required argument
	- %i integer
	- %f float
	- %c char
	- %s string
	- (more than 20 total)
		- %i, %f will adjust to the length of the argument
		- If we require a completely fixed format we can specify it
		- %4i specifies a 4 digit integer (padded with white space if not)
		- %8.3f specified a float with 3 decimal places and 8 total characters
		- If you use a fixed format you must ensure you do not overflow it

## Formatted input - scanf
```c
scanf( format_string, &argument_list );
```
- The format_string is specified with required types as with printf()
- implicit casting (or error) if incorrect type is given
- The argument_list supplies the address of the program variable
- Where the data will be stored in memory
- You must ensure that the [[Arguments]] have the correct type
- For example:
```c
int k;
scanf( “ Input an int: %i”, &k );
```
- scanf isnt very secure so there is also a "safer intput"
```c
char buffer[100];
fgets( buffer, 100, stdin );
```
Data provided at the terminal is, by default, a string
- We can read an input string into a string buffer
- Reads either 100 characters or until a newline (return key)
- Explicitly defines the data source (FILE *stdin)
- don't use gets()
#### Processing the buffer
- C provides formatted string processing using sscanf()
- Uses the same rules as scanf() for stdin
- Processes a known char buffer rather than user input• Still assumes a format so needs checking
- For example:
```c
char buffer[100];
int age;
char name[40];
printf( “Enter first name and age:”);
fgets( buffer, 100, stdin );
sscanf( buffer, “%s %i” name, &age );
```

## Command Line Input
#### argc and argv
- needs to cahange the main function to access
```c
int main ( int argc, char *argv[] ) {
	...;
	return 0
}
```
- argc is an int, the number of arguments
- argv is an [[Arrays in C]] of strings, contains arguments
```c
#include <stdio.h>
int main( int argc, char *argv[] ) {
	if ( argc > 1 ) {
		printf( “%s\n”, argv[1] );
	}
	return 0;
}
```
	accepts one string on the command line
	most linux commands on the terminal are run using this format
- argc, argv read the entire commandine
	- argc is always at least 1
	- argv[0] is the program itself
##### atoi() and atof() from <stdlib.h>
- i = atoi( string ); converts a string to an int
- f = atof( string ); converts a string to a float
- atoi()/atof() will attempt to convert any string passed to them
- You should ensure that a valid string is used

## External file input/output
- reading / writing is a common task
- have to define with a pointer
	- "FILE \*fp;*"
- OPen a file (assign fp) ginen a file name as a string
	- fp = fopen( filename, mode);
		- mode is normally read **"r"** or write  **"w"** (**"wr"** is both)
		- writing assumes the filename exists, if it doesn't it will return null but if this isn't tested then it will edit the wrong data
- close a file (free the pointer fp)
	- fclose( fp );

## Formatted input/output
```c
fprintf( fp, format_string, arguments );
```
- behaves like printf
```c
fscanf( fp, format_string, arguments );
```
- behaves like scanf
- Safer input ( or unformatted files ) to a buffer string of length n
	- fgets( buffer, n, fp );
-  fgets() returns a null pointer if no string is read
- We can (and should!) test for that

