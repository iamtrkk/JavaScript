# Hoisting in JS

Makes some types of variables accessible/usable in the code before they are actually declared, i.e., "Variables lifted up to the top of their scope".

- **TDZ (Temporal Dead Zone):** When we use a variable before declaration, it goes to TDZ, which throws a reference error stating that the variable is not initialized if hoisting is allowed for that variable; otherwise, it will throw a "variable not defined" error.
- Basically, `let`, `const` and `arrow functions` can't be hoisted because they are block-scoped, and only function declarations can be hoisted;

Although memory is created for these TDZ variables but they will be initialized once execution reaches that line so before that if we try to access it, it will through not initialized not undefined.

But in case of var we can access it before the execution reaces the line where it is declared and same goes for function expression

- If we try to declare an arrow function with `var` and attempt to hoist it, we will get `undefined` because `var` is `undefined` in TDZ if hoisted.

- Let and const are not available in window object as they are managed separately in TDZ it is made available once defined.
- We also cant redeclare a value using let or const but using var we can redeclare it
- But we can change the value of let without redeclare but with const nothing can be done

### Example for issue with hoisting

```javascript
if (!numProducts) deleteCart(); // delete only occurs if numProducts is zero.
var numProducts = 10;
```

Here, `deleteCart` will be executed because during the `if` block, `numProducts` will be `undefined`, which is falsy.

### Best Practice

Always use `const` or `let` if you need to change the value.

---

## Closures

- A closure gives a function access to all the variables of its parent function, even after the parent function has returned.

- or The function along with its lexical scope variable forms a closure. Lexical means the parents variables access

- Also if a function returns a function and when we call that returned function outside still it will have access to its parents variales which is already vanished and popped out of call stack but it will still can use the variables from parent function if required it will nt give undefined

- Variables which are required in closures aren't garbage collected

```javascript
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}

const increment = outer();
increment();
```

- setTimeout also forms a closure as all other variables and function and variables pops out of call stack but settimeout will have access to those variables when the the call back function is executed after time it uses those variables and function to call after timeout.

Closure is used in:

- SetTimeout
- Data hiding or encapslation: `Declare variable in a block isntead of global scope so that only function forming closure can access it`.
- currying
- memoising

---
