---
Title: 'Errors'
Description: 'In Java situations where things might go wrong in the program are predominantly handled by the Error and Exception classes.'
Subjects:
  - 'Code Foundations'
  - 'Computer Science'
Tags:
  - 'Errors'
  - 'Error Handling'
  - 'Exceptions'
  - 'Debugging'
CatalogContent:
  - 'learn-java'
  - 'paths/computer-science'
---

In Java, situations where things might go wrong in the program are predominantly handled by the following subclasses of the `java.lang.Throwable` class: `Error` and `Exception`.

The `Error` class represents illegal operations that cause serious abnormalities in the program and are not recommended to `catch`. Some examples include:

- The `ClassFormatError`, which occurs when a class file cannot be read or interpreted.
- The `IncompatibleClassChangeError`, which occurs when a base class is altered after a child class has already been initialized.
- The `NoClassDefFoundError`, which occurs when the file with the class containing the `main()` method cannot be found.

The `Exception` class refers to abnormal and unexpected events that disrupt the flow of the program but can be reasonably handled by a `catch`-statement. Some examples include:

- The `ArrayIndexOutOfBoundsException`, which occurs when attemptting to access an an index that does not exist within a given array.
- The `FileNotFoundException`, which occurs when a file with the specified path cannot be found.
- The `NumberFormatException`, which occurs when an attempt is made to convert a string to a numeric type and the string contains non-numeric characters.

## Example

A `try...catch` block is a means for a programmer to encapsulate a block of code and "catch" a potentially-thrown `Exception` (but never an `Error`) before it halts execution of the program.

In the example below, the code used in the `try` block will run until the `Exception` is thrown by the assignment to the `c` variable because division by zero, 0, is not possible. In the `catch` block, an `ArithmeticException` is thrown and yields a printed message along with details about where the `Exception` can be traced.

```java
class DivideByZero {
  public static void main(String[] args) {
    int a = 27, b = 0;
    try {
      System.out.println("I'm executed first!");
      int c = a / b; // This will throw an exception
      System.out.println("I'm never executed!");
    } catch (ArithmeticException e) {
      System.out.println("Exception Caught!");
      e.printStackTrace();
    }
      System.out.println("Done!");
  }
}
```
