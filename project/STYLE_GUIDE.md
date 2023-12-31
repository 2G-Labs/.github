# Styling Guide
Our organisation have set up some guidelines for styling code, so that it is homogeneous on all of our projects, these styling rules must be followed.

1. The starting curly brace `{` of the functions body should be after the parenthesis `()` of the function, with a space between them
    ```java
    void foo() {
               ^
               |
            Like this
    ```
2. The ending ending curly brace `}` should be at the same indent level as of the starting line.
    ```java
    {
        void foo() {
        }
    }
    ```
3. Use 4 space indention instead of tab character.
4. Use `&` at the end of the datatype for the reference to a variable, and before the var for the address of the variable.
   ```cpp
   void foo(int& a) {    // reference variable
       int* c = &a;      // address of variable a
   }
   ```
5. Use `*` at the end of the datatype for the pointer variable.
   ```cpp
   int a = 4;
   int* c = &a;    // address of variable a
   ```
6. Indent inline comments to match inline comments adjacent to the line (Align with 4 spaces from the most longest line).
   ```cpp
   int* a;             // Pointer variable
   int blackDragon;    // The variable to do something funky

   int demo;     // The demo variable
   int p;        // A variable
   int qasar;    // Align with 4 spaces from the longest line ( This is the longest)
   ```
7. If there is a difference of 40 spaces when following the indentation alignment guide, then don't align comment.
   ```cpp
   int a = 1;    // This is var `a`, next line is lengthy so we abandon the alignment guide.
   a = a * a + a - 5 * 2 % 2 + 344 * 322 * 3.1415 + 12456 - (3/4) + a++ - a-- + ++a;    // This is lengthy formula.
   ```
