## C programming(Functions, Object Files and Linking with Clang)
## Objectives
```
To build a geometry calculator in C that computes the area of different shapes.By placing the function implementation in a separate file and compiling them into an object file linking them with the main program.
```

### Source Code Implementation
### Geometry.c(The Logic Module)
- This file contains the actual function implementations that calculate the areas. Note the inclusion of <math.h> to access the M_PI constant.
```c
#include <math.h>

/*Function prototypes*/
double circle_area(double diameter);
double square_area(double length);
double rectangle_area(double length, double width);
double triangle_area(double base, double height);

/*Function Definitions*/
double circle_area(double diameter){
    double radius = diameter / 2;
    return M_PI * radius * radius;
}
double square_area(double length){
    return length * length;

}
double rectangle_area(double length, double width){
    return length * width;

}
double triangle_area(double base, double height){
    return 0.5 * base * height;

}
```
### Math.c(The execution module)
- This file calls the functions. It does not contain the logic itself; it relies on prototypes to inform the compiler that these functions exist elsewhere in the program's memory.
```c
#include <stdio.h>

double circle_area(double diameter);
double square_area(double length);
double rectangle_area(double length, double width);
double triangle_area(double base, double height);

int main(){
    printf("Circle area: %.2f\n", circle_area(10));
    printf("Square area: %.2f\n", square_area(5));
    printf("Rectangle area: %.2f\n", rectangle_area(4, 6));
    printf("Triangle area: %.2f\n", triangle_area(3, 8));

    return 0;
}
```

### Compilation and linking 
- Step 1:Compile the logic into an object file
```
clang -c geometry.c
```
- Step 2:Link the files into an executable
```
clang main.c geometry.o -o program
```
- Step 3:Execute the program
```
./program
```
### Output
```
Circle area: 78.54
Square area: 25.00
Rectangle area: 24.00
Triangle area: 12.00
```

