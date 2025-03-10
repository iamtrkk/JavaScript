# JavaScript Fundamentals

## Data Types
JavaScript has 7 data types, out of which 3 are majorly used:

1. **Number**: Decimals and integers.
2. **String**: Sequence of characters.
3. **Boolean**: `true` or `false`.
4. **Undefined**: A variable that has been declared but not assigned a value.
5. **Null**: Represents an intentional absence of value.
6. **Symbol**: A unique value that cannot be changed.
7. **BigInt** (ES2020): Used for large numbers beyond the `Number` type limit.

---

## Variables

### `let`
- Values can be mutated (changed), or we can declare a variable and assign a value later.

```javascript
let age;
age = 20;
```

### `const`
- Values can be assigned only once and cannot be changed. It requires an initial value.

```javascript
const age = 20;
```

**`let` and `const` are block-scoped**, meaning they are not accessible outside the block or function they are declared in unless declared globally.

### `var` (Not commonly used)
- Used before ES6. Similar to `let`, but `var` has **function scope** instead of block scope.

---

## JavaScript Scoping Rules

- **Functions are block-scoped starting from ES6.**
- For **arrow functions**, the scope depends on whether they are declared using `const`, `let`, or `var`.

---

## JavaScript Evaluates Operators from Left to Right

```javascript
x = y = 25 - 10; 
// Both x and y will have the value 15, but if evaluated differently, x could be undefined.
```

---

## Template Literals (ES6)

```javascript
const trk = `I am ${firstName}`;
```

Multiline strings:

```javascript
const trk = `string with
multiple 
lines`; 
```

*Before ES6, we had to use `\n` for new lines.*

---

## Type Conversion (Manual)

```javascript
console.log(Number('1992')); // String to number
console.log(String(23)); // Number to string
```

## Type Coercion (Automatic)

```javascript
console.log('I am ' + 23 + ' years old'); // 23 is converted to string
console.log('23' / '2'); // Strings are converted to numbers
```

---

## Falsy Values
The following values are **falsy** (evaluate to `false` in a boolean context):

- `0`
- `''` (empty string)
- `undefined`
- `null`
- `NaN`

All other values are **truthy**.

---

## `==` vs `===`

- **`===` (Strict Comparison)**: Compares **both value and type**.
  
  ```javascript
  18 === 18 // true
  '18' === 18 // false
  ```

- **`==` (Loose Comparison)**: Performs **type coercion** before comparing.

  ```javascript
  18 == 18 // true
  '18' == 18 // true
  ```

⚠ **Avoid `==` to prevent unexpected bugs; use explicit type conversions instead.**

---

## Prompting User Input

```javascript
const trk = prompt('What is your name?');
```

---

## Expressions vs Statements

- **Expressions**: Produce a value and end with a semicolon (`;`).

```javascript
3 + 4;
const age = 2024 - 1998;
```

- **Statements**: Instructions that do not return a value.

```javascript
if (age > 18) {
  console.log("Adult");
}
```

---

## `"use strict"`

- Helps catch errors by enforcing stricter parsing and error handling.

```javascript
"use strict";
```

---

## Functions

### Function Declaration
- Can be called **before** its definition due to **hoisting**.

```javascript
function calAge(years) {
  return 2037 - years;
}
```

### Function Expression
- **Cannot** be called before definition.

```javascript
const calAge = function (years) {
  return 2037 - years;
};
```

---

## Objects

```javascript
const trk = {
  firstName: 'trk',
  birthYear: 1998,
  
  calAge: function() {
    this.age = 2024 - this.birthYear; // `this` refers to the object itself
  }
};

// Call `calAge()` first to define `trk.age`
trk.calAge();
console.log(trk.age); // Outputs the calculated age
```

### Adding Properties to Objects
```javascript
trk.location = 'CDG'; // Now `trk` object has a `location` property
```

---

## Dot vs Bracket Notation

```javascript
console.log(trk.firstName); // Dot notation
console.log(trk['firstName']); // Bracket notation
```

With bracket notation, we can access properties dynamically:

```javascript
console.log(trk['first' + nameKey]); // Computed property name
```

---

## Loop Control: `break` and `continue`

- **`break`**: Exits the loop completely.
- **`continue`**: Skips the current iteration and moves to the next one.

Useful when filtering elements, e.g., skipping non-numeric values in an array.

---

## CSS: Universal Selector (`*`)

- Used to apply styles to all elements in an HTML document.
- Useful for resetting default styles.

```css
* {
  margin: 0;
  padding: 0;
}
```
```