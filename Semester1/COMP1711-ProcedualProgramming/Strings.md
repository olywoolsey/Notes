#COMP1711
- arrays of characters are often thought of as strings
- there is a subtle difference between a string and a [[char]] [[Arrays in C]]
#### Char Array
- A char array is treated exactly like the other primitive types
```c
string word\[\] = {'h', 'e', 'l', 'l', 'o'};
```
#### Strings
- A string is an array of char type with an additional null character (’\\0’)
- The special (invisible) char ‘\\0’ signifies the end of the string
- It adds one element to the array
###### Strings
```c
char word[ ] = { ‘h’, ‘e’, ‘l’, ‘l’, ‘o’, ‘\0’ };
```
###### is the same as
```c
char word[ ] = "hello";
```
### Buffer
- used if the length of the string is unknown
```c
char buffer[100] = "hello";
```
- assigns the \\0 to the end then terminates from there
