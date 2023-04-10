#COMP1721
```java
import java.util.Scanner;    // refer to java.import.Scanner as just scanner
 
class Convert {
    public static void main(String[] args) {
        System.out.print("Enter distance in miles:");
        Scanner input = new Scanner(System.in);
        double miles = input.nextDouble();
        double kilometers = miles * 1.609344;
        System.out.println(miles +  " miles is equal to " +  kilometers +  " kilometers.");
    }
}
```

## Class Name
- if public is before class then the name has to match the .java file name
- upper case for class names
- lower camel case for variable and method names

## Spacing
- Don't mix tabs and spaces
- 2 - 4 spaces per indentation
- blank lines between code sections are helpful
- keep length <80 char

## Comments
- use them to plan coding
- sensible named names should explain the process
- put above blocks of code rather than on lines
- use to describe purpose of code at high level
- don' use to explain syntax

## If
- needs boolean expression

## String
- implemented as a class called string
- text is represented by Unicode characters
- over 60 methods
- don't need to use new