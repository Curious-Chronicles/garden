---
index: SS13
marks: 10
tags: entrance, c-programming, oop
related: [[]]
status: Completed
created: [[2023-05-06]]
---

## 1. Basic programming concepts (variables, data types, operators, expressions, etc.)

1. Variables:
	- Definition: Variables are named memory locations used to store data values that can be manipulated and accessed in a program.
	- Example (C code):
```c
int age = 25;
float salary = 2500.50;
char grade = 'A';
```

2. Data Types:
	- Definition: Data types specify the kind of data that can be stored in a variable. Common data types include integers, floating-point numbers, characters, and booleans.
	- Example (C code):
```c
int num = 10;
float pi = 3.14;
char letter = 'A';
```

3. Operators:
	- Definition: Operators are symbols or keywords that perform operations on data values. Examples include arithmetic operators" (+, -, *, /)", comparison operators "(>, <, ==)", and logical operators "(&&, ||)".
	- Example (C code):
```c
int result = 10 + 5;
bool isEqual = (x == y);
```

4. Expressions:
	- Definition: Expressions are combinations of variables, values, and operators that evaluate to a single value. They can perform calculations or compare values.
	- Example (C code):
```c
int sum = num1 + num2;
bool isPositive = (num > 0);
```

5. Control Structures (if-else, loops):
	- Definition: Control structures allow the program to make decisions or repeat a block of code based on certain conditions. Examples include if-else statements and loops (for, while).
	- Example (C code):
```c
if (age >= 18) {
    printf("You are an adult.");
} else {
    printf("You are a minor.");
}

for (int i = 0; i < 5; i++) {
    printf("%d ", i);
}

while (count > 0) {
    printf("Countdown: %d\n", count);
    count--;
}
```


## 2. Control structures (if-else, switch-case, loops)

1. If-else statements:
	- Definition: If-else statements allow the program to make decisions based on a condition. If the condition is true, a specific block of code is executed; otherwise, an alternative block of code is executed.
	- Example (C code):
```c
int num = 10;
if (num > 0) {
    printf("Number is positive");
} else {
    printf("Number is non-positive");
}
```

2. Switch-case statements:
	- Definition: Switch-case statements provide a way to select one of many code blocks to execute based on the value of a variable or an expression.
	- Example (C code):
```c
char grade = 'B';
switch (grade) {
    case 'A':
        printf("Excellent");
        break;
    case 'B':
        printf("Good");
        break;
    case 'C':
        printf("Average");
        break;
    default:
        printf("Invalid grade");
}
```

3. Loops:
	- Definition: Loops allow the program to repeat a block of code multiple times until a certain condition is met.
	- Example (C code):
```c
int i;
for (i = 1; i <= 5; i++) {
    printf("%d ", i);
}

int count = 3;
while (count > 0) {
    printf("Countdown: %d\n", count);
    count--;
}
```

4. Break and Continue statements:
	- Definition: The break statement is used to exit a loop prematurely, while the continue statement is used to skip the remaining code within a loop and move to the next iteration.
	- Example (C code):
```c
int i;
for (i = 1; i <= 10; i++) {
    if (i == 5) {
        break;
    }
    printf("%d ", i);
}

int j;
for (j = 1; j <= 10; j++) {
    if (j % 2 == 0) {
        continue;
    }
    printf("%d ", j);
}
```


## 3. Functions and pointers

1. Functions:
	- Definition: Functions are self-contained blocks of code that perform a specific task. They allow code reusability and improve the organization and modularity of the program.
	- Example (C code):
```c
// Function declaration
int addNumbers(int a, int b);

// Function definition
int addNumbers(int a, int b) {
    int sum = a + b;
    return sum;
}

// Function call
int result = addNumbers(5, 3);
```

2. Function Parameters:
	- Definition: Function parameters are variables that receive values when a function is called. They allow the function to accept input data from the caller.
	- Example (C code):
```c
int multiplyNumbers(int a, int b) {
    int product = a * b;
    return product;
}

int result = multiplyNumbers(4, 6);
```

3. Return Values:
	- Definition: Functions can return a value to the caller using the return statement. The returned value can be used in expressions or assigned to variables.
	- Example (C code):
```c
int calculateSquare(int num) {
    int square = num * num;
    return square;
}

int result = calculateSquare(5);
```

4. Pointers:
	- Definition: Pointers are variables that store memory addresses. They allow direct manipulation of memory and enable efficient memory management and data manipulation.
	- Example (C code):
```c
int number = 10;
int *ptr = &number;
```

5. Pointer Arithmetic:
	- Definition: Pointer arithmetic allows incrementing or decrementing the memory address stored in a pointer based on the size of the data type it points to.
	- Example (C code):
```c
int numbers[] = {1, 2, 3, 4, 5};
int *ptr = numbers;

for (int i = 0; i < 5; i++) {
    printf("%d ", *ptr);
    ptr++;
}
```


## 4. Arrays and strings

1. Arrays:
	- Definition: Arrays are a collection of elements of the same data type that are stored in contiguous memory locations. They allow storing multiple values under a single variable name and provide easy access to individual elements using an index.
	- Example (C code):
```c
int numbers[5] = {1, 2, 3, 4, 5};
float grades[3] = {9.5, 8.7, 7.9};
char letters[4] = {'A', 'B', 'C', 'D'};
```

2. Array Indexing:
	- Definition: Array indexing is the process of accessing individual elements within an array using their position, known as the index. The index starts at 0 for the first element and increases sequentially.
	- Example (C code):
```c
int numbers[5] = {1, 2, 3, 4, 5};
int firstNumber = numbers[0];
int thirdNumber = numbers[2];
```

3. Strings:
	- Definition: Strings are sequences of characters that are represented as arrays of characters terminated by a null character ('\0'). They are commonly used to store and manipulate textual data.
	- Example (C code):
```c
char name[10] = "John";
char message[] = "Hello, World!";
```

4. String Functions:
	- Definition: String functions are pre-defined functions in C that operate on strings. They allow various operations such as copying, concatenating, comparing, and manipulating strings.
	- Example (C code):
```c
#include <string.h>

char str1[10] = "Hello";
char str2[10] = "World";

// String concatenation
strcat(str1, str2);

// String length
int length = strlen(str1);

// String comparison
int result = strcmp(str1, str2);
```

5. String Input and Output:
	- Definition: Input and output functions in C allow reading and displaying strings. They enable interaction with the user for inputting or outputting textual data.
	- Example (C code):
```c
#include <stdio.h>

char name[20];

// String input
printf("Enter your name: ");
scanf("%s", name);

// String output
printf("Hello, %s!", name);
```


## 5. Structures and unions

1. Structures:
	- Definition: Structures are user-defined data types that allow combining different types of variables under a single name. They provide a way to create complex data structures by grouping related variables together.
	- Example (C code):
```c
struct Student {
    char name[20];
    int age;
    float gpa;
};

struct Student s1;
s1.age = 20;
```

2. Structure Members:
	- Definition: Structure members are the individual variables or fields within a structure. They can have different data types and are accessed using the dot (.) operator.
	- Example (C code):
```c
struct Point {
    int x;
    int y;
};

struct Point p1;
p1.x = 10;
p1.y = 20;
```

3. Unions:
	- Definition: Unions are user-defined data types that allow storing different types of variables at the same memory location. Only one member of the union can hold a value at a given time.
	- Example (C code):
```c
union Data {
    int intValue;
    float floatValue;
};

union Data d1;
d1.intValue = 10;
```

4. Accessing Union Members:
	- Definition: Union members are accessed in the same way as structure members, using the dot (.) operator. However, since only one member can hold a value at a time, accessing the correct member is crucial.
	- Example (C code):
```c
union Data {
    int intValue;
    float floatValue;
};

union Data d1;
d1.floatValue = 3.14;

printf("%f", d1.floatValue);
```

5. Structure vs. Union:
	- Definition: Structures and unions are similar in that they allow grouping variables together. However, structures allocate memory for each member independently, while unions allocate memory that is shared by all members.
	- Example (C code):
```c
struct Rectangle {
    int length;
    int width;
};

union Shape {
    struct Rectangle rect;
    int radius;
};
```


## 6. Dynamic memory allocation

1. Dynamic Memory Allocation:
	- Definition: Dynamic memory allocation is the process of allocating and deallocating memory at runtime. It allows the program to dynamically allocate memory for variables and data structures based on the program's needs.
	- Example (C code):
```c
int *ptr = (int*) malloc(sizeof(int));
*ptr = 10;
free(ptr);
```

2. malloc() Function:
	- Definition: The malloc() function is used to dynamically allocate memory from the heap. It takes the size of the memory block to be allocated as an argument and returns a pointer to the allocated memory.
	- Example (C code):
```c
int *ptr = (int*) malloc(5 * sizeof(int));
```

3. calloc() Function:
	- Definition: The calloc() function is used to dynamically allocate memory from the heap and initializes the allocated memory block with zeros. It takes the number of elements and the size of each element as arguments and returns a pointer to the allocated memory.
	- Example (C code):
```c
int *ptr = (int*) calloc(5, sizeof(int));
```

4. realloc() Function:
	- Definition: The realloc() function is used to change the size of the previously allocated memory block. It takes a pointer to the previously allocated memory, the new size of the memory block, and returns a pointer to the resized memory.
	- Example (C code):
```c
int *ptr = (int*) malloc(5 * sizeof(int));
ptr = (int*) realloc(ptr, 10 * sizeof(int));
```

5. free() Function:
	- Definition: The free() function is used to deallocate memory previously allocated using malloc(), calloc(), or realloc(). It releases the memory back to the heap, making it available for reuse.
	- Example (C code):
```c
int *ptr = (int*) malloc(sizeof(int));
free(ptr);
```

6. Memory Leak:
	- Definition: Memory leak occurs when dynamically allocated memory is not properly deallocated, resulting in memory being unavailable even though it is no longer needed. It can lead to inefficient memory usage and can cause the program to run out of memory.
	- Example (C code):
```c
// Memory leak example
int *ptr = (int*) malloc(sizeof(int));
ptr = (int*) malloc(sizeof(int));  // The previous memory block is not freed
```

## 7. File handling

1. File Handling:
	- Definition: File handling refers to the process of reading from and writing to files on a computer's storage. It allows programs to store and retrieve data persistently, even after the program execution has ended.
	- Example (C code):
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("data.txt", "w");
    fprintf(file, "Hello, World!");
    fclose(file);
    return 0;
}
```

2. Opening a File:
	- Definition: Opening a file involves creating a connection between the program and the file. It allows the program to read from or write to the file. The fopen() function is used to open a file, which takes the file name and the mode as arguments and returns a file pointer.
	- Example (C code):
```c
FILE *file = fopen("data.txt", "r");
```

3. Closing a File:
	- Definition: Closing a file is necessary to release the resources associated with the file and ensure that any pending writes are completed. The fclose() function is used to close a file, which takes the file pointer as an argument.
	- Example (C code):
```c
fclose(file);
```

4. Reading from a File:
	- Definition: Reading from a file allows the program to retrieve data stored in the file. The fscanf() or fgets() function is used to read data from a file.
	- Example (C code):
```c
char buffer[100];
fscanf(file, "%s", buffer);
```

5. Writing to a File:
	- Definition: Writing to a file allows the program to store data in the file. The fprintf() or fputs() function is used to write data to a file.
	- Example (C code):
```c
fprintf(file, "Hello, World!");
```

6. Error Handling:
	- Definition: Error handling is important when working with files to handle situations where file operations fail. It ensures that the program can handle and recover from errors that may occur during file handling operations.
	- Example (C code):
```c
if (file == NULL) {
    printf("Error opening the file.");
}
```


## 8. Object-oriented programming concepts (classes, objects, inheritance, polymorphism, encapsulation, etc.)

1. Classes:
	- Definition: A class is a blueprint for creating objects in object-oriented programming. It defines the structure and behavior of objects by encapsulating data (attributes) and methods (functions) that operate on the data.
	- Example (C++ code):
```cpp
class Rectangle {
    int length;
    int width;
public:
    void setDimensions(int len, int wid) {
        length = len;
        width = wid;
    }
    int calculateArea() {
        return length * width;
    }
};
```

2. Objects:
	- Definition: An object is an instance of a class. It represents a specific entity with its own unique state and behavior. Objects are created from the class blueprint and can interact with other objects.
	- Example (C++ code):
```cpp
Rectangle rect1; // Creating an object of the Rectangle class
rect1.setDimensions(5, 3); // Calling member functions on the object
int area = rect1.calculateArea();
```

3. Inheritance:
	- Definition: Inheritance is a mechanism in object-oriented programming that allows one class to inherit the properties and behavior of another class. It enables code reuse and the creation of a hierarchy of classes.
	- Example (C++ code):
```cpp
class Square : public Rectangle {
public:
    void setSide(int side) {
        setDimensions(side, side);
    }
};

Square square1; // Creating an object of the Square class
square1.setSide(4); // Inheriting and calling member functions from Rectangle class
int area = square1.calculateArea();
```

4. Polymorphism:
	- Definition: Polymorphism is the ability of objects of different classes to respond to the same message or function call. It allows objects to be treated as instances of their own class or as instances of their parent class.
	- Example (C++ code):
```cpp
class Shape {
public:
    virtual void draw() {
        // Common drawing code for all shapes
    }
};

class Circle : public Shape {
public:
    void draw() {
        // Drawing code specific to circles
    }
};

Shape* shape1 = new Circle(); // Polymorphic behavior
shape1->draw(); // Calls the draw() function of the Circle class
```

5. Encapsulation:
	- Definition: Encapsulation is the process of hiding the internal implementation details of an object and exposing only the necessary interfaces to interact with it. It provides data abstraction and protects the integrity of data.
	- Example (C++ code):
```cpp
class BankAccount {
private:
    int accountNumber;
    double balance;
public:
    void deposit(double amount) {
        balance += amount;
    }
    double getBalance() {
        return balance;
    }
};

BankAccount account1;
account1.deposit(1000);
double balance = account1.getBalance();
```


## 9. Exception handling

1. Exception Handling:
	- Definition: Exception handling is a mechanism in programming that allows the program to handle and recover from unexpected or exceptional situations that may occur during program execution. It provides a structured approach to deal with errors, ensuring proper flow control and error reporting.
	- Example (C++ code):
```cpp
try {
    // Code that may throw an exception
    throw SomeException(); // Throw an exception explicitly
}
catch (SomeException& ex) {
    // Code to handle the exception
}
```

2. Exceptions:
	- Definition: An exception is an abnormal condition or event that occurs during the execution of a program, disrupting the normal flow of code. Exceptions can be caused by various factors such as runtime errors, invalid inputs, or exceptional conditions.
	- Example (C++ code):
```cpp
void divide(int a, int b) {
    if (b == 0) {
        throw DivisionByZeroException(); // Throwing an exception for division by zero
    }
    int result = a / b;
}
```

3. try-catch Blocks:
	- Definition: A try-catch block is used to catch and handle exceptions in a controlled manner. The code that may potentially throw an exception is enclosed within the try block, and the catch block is used to catch and handle the thrown exception.
	- Example (C++ code):
```cpp
try {
    // Code that may throw an exception
}
catch (SomeException& ex) {
    // Code to handle the exception
}
```

4. throw Statement:
	- Definition: The throw statement is used to explicitly throw an exception within the code. It is typically used when an exceptional condition is encountered and the program needs to transfer control to the appropriate catch block.
	- Example (C++ code):
```cpp
if (input < 0) {
    throw NegativeNumberException(); // Throwing an exception for negative input
}
```

5. Exception Types:
	- Definition: Exception types are specific classes or data types used to represent different types of exceptions. They are used to categorize and handle exceptions based on their nature or cause.
	- Example (C++ code):
```cpp
class FileNotFoundException : public Exception {
    // Custom exception class for file not found error
};

try {
    // Code that may throw a FileNotFoundException
}
catch (FileNotFoundException& ex) {
    // Code to handle the file not found exception
}
```


## 10. Standard libraries and headers (stdio.h, string.h, math.h, etc.)

1. Standard Libraries:
	- Definition: Standard libraries refer to a collection of pre-written functions and modules that provide commonly used functionality in programming. These libraries are developed, tested, and maintained by the programming language community or the platform vendor. They provide a wide range of functionalities, such as input/output operations, string manipulation, mathematical calculations, memory management, etc.
	- Example: One of the commonly used standard libraries in C is the "stdio.h" library, which provides functions for input and output operations, such as "printf" and "scanf".

2. Headers:
	- Definition: Headers, also known as header files, are files that contain declarations and definitions of functions, types, constants, and macros that are needed by a program. These headers are included at the beginning of a program to make the declarations and definitions available for use in the program.
	- Example: The "stdio.h" header provides the declarations and definitions of input/output functions like "printf" and "scanf". By including this header in a C program using the "#include" directive, the program gains access to these functions.

3. Commonly Used Standard Libraries and Headers:
   - stdio.h: Provides functions for input/output operations, such as reading and writing data to the console or files.
   - string.h: Contains functions for string manipulation, such as copying, concatenating, comparing, and searching strings.
   - math.h: Offers mathematical functions, including trigonometric, logarithmic, exponential, and rounding functions.
   - stdlib.h: Provides functions for general-purpose tasks like memory allocation, random number generation, sorting, etc.
   - time.h: Includes functions for time and date manipulation, measuring elapsed time, and generating random seeds.
   - ctype.h: Contains functions for character handling and classification, such as checking if a character is a digit or an alphabetic character.

Example (C code):
```c
#include <stdio.h>

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    printf("The entered number is: %d\n", num);
    return 0;
}
```
