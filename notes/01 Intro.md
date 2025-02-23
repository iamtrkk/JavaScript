# JavaScript Notes

## JavaScript Definition
JavaScript is a **synchronous, single-threaded** language, meaning it executes one line at a time.  
It has a **variable environment** (memory) and a **thread of execution**, where the code executes sequentially.

### Key Characteristics:
- **High-Level Language**: Manages memory automatically.
- **Garbage Collected**: Removes unused code automatically.
- **Interpreted or JIT (Just-In-Time) Compiled**: JS engine converts the code to machine code (binary: 0s and 1s).
- **Multi-Paradigm**: Supports multiple programming paradigms:
  - **Procedural**
  - **Object-Oriented**
  - **Functional Programming**
- **Object-Oriented**: JavaScript follows an object-oriented approach.
- **First-Class Functions**:  
  - Functions are treated as variables.
  - Functions can be passed as arguments to other functions.
  - Functions can return another function.
- **Dynamic Typing**:  
  - JavaScript is dynamically typed, meaning we don’t need to declare the data type.
  - JS automatically assigns types based on values (e.g., number or string).
- **Single-Threaded**: Executes code in a single sequence.
- **Non-Blocking Event Loop**:  
  - Used to achieve multi-threading behavior.
  - Long-running tasks execute in the background.
  - Once completed, they are placed back into the main thread.

## ES6 (2015) - Major Updates
ECMAScript 6 (ES6) was released in 2015, bringing significant changes to JavaScript.

## JavaScript Engine
A **JavaScript Engine** is a program that executes JavaScript code.  
Example: **V8 Engine** (used in Google Chrome).  

### Components of a JS Engine:
- **Call Stack**: Where code is executed.
- **Heap**: Memory storage for objects.
