## Week 3(Monday):C fundamentals

## Objectives
- Establish the foundational syntax of C programming. The goal was to write a basic execution thread, manage fixed-memory character arrays, and utilize formatted standard output 

## Source-code implementation

#include <stdio.h>

int main() {

    printf("Name: Nhial\n");
    printf("Year of Study: 3\n");
    printf("Course: Electrical Engineering\n");

    return 0;
}

# Core Concepts
- The Standard Library (<stdio.h>)
Unlike higher-level languages that load built-in functions automatically, C requires explicit linking to standard libraries to perform basic operations. #include <stdio.h> brings in the Standard Input/Output library, granting access to the printf function.

- The main() Execution Thread
int main() is the mandatory entry point for any compiled C program. The return 0; statement at the end is a status code sent back to the operating system, where 0 universally indicates that the program executed successfully without fatal hardware or memory errors.