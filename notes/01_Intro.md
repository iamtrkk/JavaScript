# JavaScript Notes

## JavaScript Definition

JavaScript is a **synchronous, single-threaded** language, meaning it executes one line at a time.  
It has a **variable environment** (memory) and a **thread of execution environment**, where the code executes sequentially.

- **Dynamic Typing**:
  - JavaScript is dynamically typed, meaning we don’t need to declare the data type.
  - JS automatically assigns types based on values (e.g., number or string).

### Key Characteristics:

- **Single-Threaded**: Executes code in a single sequence.
- **Non-Blocking Event Loop**:

  - Used to achieve multi-threading behavior.
  - Long-running tasks execute in the background.
  - Once completed, they are placed back into the main thread.

- **High-Level Language**: Manages memory automatically.
- **Garbage Collected**: Removes unused code automatically.
- **Multi-Paradigm**: Supports multiple programming paradigms:

  - **Procedural**
  - **Object-Oriented**
  - **Functional Programming**

- **Object-Oriented**: JavaScript follows an object-oriented approach.
- **First-Class Functions**:
  - Functions are treated as variables.
  - Functions can be passed as arguments to other functions.
  - Functions can return another function.

## ES6 (2015) - Major Updates

ECMAScript 6 (ES6) was released in 2015, bringing significant changes to JavaScript.

## JavaScript Engine

A **JavaScript Engine** is a program that executes JavaScript code.  
Example: **V8 Engine** (used in Google Chrome).

### Components of a JS Engine:

- **Call Stack**: Where code is executed. It maintains the order of execution of the executuion context, once a code is finished execution it pops out of the execution context
- **Heap**: Memory storage for objects.
