### Function Declaration

- Also known as a function statement.
- Can be called before its definition due to **hoisting**.

```javascript
function calAge(year) {
  return 2037 - year;
}
```

### Function Expression

- Assigning a function to a variable.
- Anonymous function assigned to a variable.

```javascript
const calAge = function (year) {
  return 2037 - year;
};
```

### Anonymous Function

- A function without a name.
- Used as a function expression, callback function, etc.

### Default Parameters

- If a parameter is not passed, it will assign a default value.
- We must follow parameter order. To skip a parameter, pass `undefined`.
- If an object is passed as a parameter and modified inside the function, the original object will also change.

```javascript
const createBooking = function (flightNum, numPassengers = 1, price = 199) {
  console.log(flightNum, numPassengers, price);
};
```

### JavaScript Function Behavior

- JavaScript only has **pass by value**, not **pass by reference**.

### First-Class Functions

- Functions are treated as values (like variables).
- Functions can be assigned, returned, and passed as arguments.

### Higher-Order Functions

- A function that receives another function as a parameter, returns a function, or both.

```javascript
const transformer = function (str, fn) {
  console.log("Transformed:", fn(str));
};

const upperCase = function (str) {
  return str.toUpperCase();
};

transformer("hello", upperCase);
```

### Callback Functions

- Used to define specific behaviors for higher-order functions.

```javascript
const greet = function (greeting) {
  return function (name) {
    console.log(`${greeting} ${name}`);
  };
};

const greetHey = greet("Hey");
greetHey("Trk");
```

### Arrow Function

```javascript
const greetArr = (greeting) => (name) => console.log(`${greeting} ${name}`);
greetArr("Hello")("Trk");
```

## Call and Bind Methods

### Call Method

- Allows a function to use `this` from a specific object.

```javascript
book.call(swiss, 583, "Trk");
```

### Bind Method

- Returns a new function with a specific object bound to `this`.

```javascript
const bookVistara = book.bind(vistara);
bookVistara("Trk", 23);

const bookVistara23 = book.bind(vistara, 23);
bookVistara23("Trk");
```

---

## IIFE (Immediately Invoked Function Expression)

```javascript
(function () {
  console.log("This will never run again");
})();

(() => console.log("Arrow IIFE"))();
```
