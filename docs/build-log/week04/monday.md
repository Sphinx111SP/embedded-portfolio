## Memory and pointers

### Memory address
```
A memory address refers to a location in a computer's memory where data is stored.
These addresses allow both software and hardware to access and manipulate data stored in memory.
```
### Pointers(*)
```
A variable that stores the memory address of another variable.It holds the location where the value is stored &:gets the memory address of a variable.
**Address-of operator(&)**:Gets the memory address of a variable.
**Dereference operator(*)**:Accesses the value stored at the address.
```
### Uses
```
Dynamic memory allocation
Passing large data to functions efficiently
Arrays and strings manipulation
```
### Dynamic memory allocation
| Function | Purpose | Parameters | Returns |
| :--- | :--- | :--- | :--- |
| malloc | Allocates a single block of memory | size_t size(bytes) | void* pointer or NULL |
| calloc | Allocates multiple blocks of memory | size_t num, size_t size | void* pointer od NULL |
| realloc | Changes the size of previously allocated memory | void* ptr, size_t,new_size | void* pointer or NULL |
| free | Frees previously allocated memory | void* ptr |

### Common memory related bugs
**Dangling pointer** - a pointer that still holds the address of memory that has already been freed or is no longer valid

**Memory Leak** - Allocated memory that is never freed and whose reference is lost,making it impossible to reclaim.

### Main memory segments in C.
***Text segment** - Contains the compiled machine code of the program.

**Data segment** - Stores global and static variables that are initialized before execution.

**BSS segment** - Stores global and static variables that are uninitialized or initialized to zero.

**Heap** - Used for dynamic memory allocation at runtime(malloc, calloc,realloc).

**Stack** - Stores function call frames,local variables and return addresses.