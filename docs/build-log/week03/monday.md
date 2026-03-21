## Week 3(Monday):C fundamentals

## Objective
To demonstrate the use of variables, strings, and formatted output in C. 

## Source-code implementation

### code
```c
#include <stdio.h>

int main() {

   char myname[50] = "Nhial Majak Nhial";
   char myyear[50] = "Year 4";
   char mycourse[50] = "Electrical and Electronics Engineering";

   printf("My name is %s.I study %s and I am currently in %s."  myname, myyear, mycourse);

    return 0;
}
```
## Key Concepts

- **Character Arrays (Strings)**  
  Used to store text in C. Example: `char myname[50]`

- **Data Types**  
  `char` is used for characters and strings.

- **Functions**  
  `main()` is the entry point of every C program.

- **Standard Input/Output Library**  
  `#include <stdio.h>` allows use of `printf()`.

- **Formatted Output**  
  `printf()` uses format specifiers like `%s` to print strings.

### Explanation

- `#include <stdio.h>`  
  Includes the standard input/output library.

- `char myname[50]`  
  Declares a string variable with a maximum of 50 characters.

- `printf()`  
  Displays formatted output:
  - `%s` is used to insert string values
  - `\n` creates a new line

- `return 0;`  
  Indicates successful execution of the program.

### Output

```
My name is Nhial Majak Nhial.
I study Electrical and Electronics Engineering and I am currently in Year 4.
```