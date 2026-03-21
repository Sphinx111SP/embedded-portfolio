# C Programming (Structs ,Enums ,Unions and Dynamic Memory Allocation.)
## Objective
```
We were to build a simple student record management style using:
- Structs to represent student data.
- Enums to define categories.
- Unions to store flexible data tytpes.
- Dynamic memory allocation to manage a list of students.
```
### Source code implementation.
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/* ================= ENUM ================= */
// ENUM = a user-defined type for fixed set of named constants
typedef enum {
    UNDERGRADUATE,   // automatically 0
    POSTGRADUATE     // automatically 1
} ProgramType;

/* ================= UNION ================= */
// UNION = a type where all members share the same memory location
typedef union {
    float gpa;
    int research_hours;
} AcademicInfo;

/* ================= STRUCT ================= */
// STRUCT = groups related variables into one unit
typedef struct {
    char name[100];
    int age;
    ProgramType program;
    AcademicInfo info;
} Student;

/* ================= FUNCTION PROTOTYPES ================= */
void inputStudent(Student *s);
void displayStudent(Student s);

/* ================= MAIN FUNCTION ================= */
int main() {
    int n;

    printf("Enter number of students: ");
    scanf("%d", &n);

    // DYNAMIC MEMORY ALLOCATION
    Student *students = (Student *)malloc(n * sizeof(Student));

    // CHECK IF malloc FAILED
    if (students == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // INPUT LOOP
    for (int i = 0; i < n; i++) {
        printf("\n--- Student %d ---\n", i + 1);
        inputStudent(&students[i]);
    }

    // DISPLAY LOOP
    printf("\n===== Student Records =====\n");
    for (int i = 0; i < n; i++) {
        displayStudent(students[i]);
    }

    // FREE MEMORY
    free(students);

    return 0;
}

/* ================= INPUT FUNCTION ================= */
void inputStudent(Student *s) {
    printf("Enter name: ");
    scanf(" %[^\n]", s->name);

    printf("Enter age: ");
    scanf("%d", &s->age);

    printf("Enter program (0 = Undergraduate, 1 = Postgraduate): ");
    scanf("%d", (int *)&s->program);

    // CONDITIONAL LOGIC BASED ON ENUM
    if (s->program == UNDERGRADUATE) {
        printf("Enter GPA: ");
        scanf("%f", &s->info.gpa);
    } else {
        printf("Enter research hours: ");
        scanf("%d", &s->info.research_hours);
    }
}

/* ================= DISPLAY FUNCTION ================= */
void displayStudent(Student s) {
    printf("\nName: %s\n", s.name);
    printf("Age: %d\n", s.age);

    // DISPLAY PROGRAM TYPE
    if (s.program == UNDERGRADUATE) {
        printf("Program: Undergraduate\n");
        printf("GPA: %.2f\n", s.info.gpa);
    } else {
        printf("Program: Postgraduate\n");
        printf("Research Hours: %d\n", s.info.research_hours);
    }
}
```
### Execution output
The code was compiled using clang (clang -c display)
```
nhial@DESKTOP-UOE3UBP:~$ clang -c main2.c
nhial@DESKTOP-UOE3UBP:~$ clang main2.o -o display
nhial@DESKTOP-UOE3UBP:~$ ./display
Enter number of students: 2

--- Student 1 ---
Enter name: Nhial
Enter age: 22
Enter program (0 = Undergraduate, 1 = Postgraduate): 0
Enter GPA: 3

--- Student 2 ---
Enter name: John
Enter age: 32
Enter program (0 = Undergraduate, 1 = Postgraduate): 1
Enter research hours: 7

===== Student Records =====

Name: Nhial
Age: 22
Program: Undergraduate
GPA: 3.00

Name: John
Age: 32
Program: Postgraduate
Research Hours: 7
```
