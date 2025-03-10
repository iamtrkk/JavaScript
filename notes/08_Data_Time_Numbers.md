# JavaScript Numbers, Dates, and Timers

---

## **Numbers in JavaScript**
- In JavaScript, everything is a **number** (integers and decimals are treated the same).

### **Conversion to Numbers**
```javascript
Number('23'); // 23
+'23'; // 23 (shorthand)
Number.parseInt('20px', 10); // 20 (base 10)
Number.parseInt('e23'); // NaN (must start with a number)
Number.parseFloat('2.5rem'); // 2.5
```

### **Checking for NaN (Not a Number)**
```javascript
Number.isNaN(20); // false
Number.isNaN('20'); // false (because it converts to number first)
Number.isNaN(+'20X'); // true (invalid number)
Number.isNaN(23 / 0); // false (Infinity is not NaN)
```

### **Checking if a Number is Finite**
- **Better than `isNaN()`** for number validation.
```javascript
Number.isFinite(20); // true
Number.isFinite('20'); // false
Number.isFinite(+'20X'); // false
Number.isFinite(20 / 0); // false (infinity is not finite)
```

### **Checking if a Number is an Integer**
```javascript
Number.isInteger(23); // true
Number.isInteger(23.0); // true
Number.isInteger(23 / 0); // false (infinity is not an integer)
```

---

## **Math Operations**
```javascript
Math.sqrt(25); // 5 (Square root)
25 ** (1 / 2); // 5 (Same as sqrt)
8 ** (1 / 3); // 2 (Cube root)

Math.max(5, 18, '23'); // 23 (converts string to number)
Math.min(5, 18, 23); // 5

Math.PI; // 3.141592653589793
Math.trunc(23.24342); // 23 (removes decimal part)
Math.round(23.4); // 23 (round to nearest integer)
Math.ceil(23.4); // 24 (round up)
Math.floor(23.9); // 23 (round down)

(2.7).toFixed(3); // "2.700" (string with 3 decimal places)
2.7.toFixed(0); // "3" (rounded)
2.345.toFixed(2); // "2.34"

5 % 2; // 1 (modulus, remainder)
```

### **Even Number Check**
```javascript
const isEven = (num) => num % 2 === 0;
isEven(8); // true
```

### **Numeric Separators**
- **For readability only, ignored in operations**
```javascript
const num = 287_00_000;
console.log(num); // 28700000
```

---

## **BigInt (Handling Large Numbers)**
- JavaScript cannot handle very large numbers with regular `Number`.
- Use `BigInt` by adding `n` at the end.

```javascript
const bigNum = 374463482372837247943239234923472349237293n;
console.log(bigNum); // Large number remains accurate

// Operations must use BigInt
bigNum * 20n; // Valid
11n / 3n; // 3n (truncates the decimal)

// Comparisons
20 == 20n; // true (loose comparison converts)
20 === 20n; // false (strict comparison fails)
```

---

## **JavaScript Dates**
```javascript
const future = new Date(2037, 10, 19, 15, 23); // (Year, Month(0-11), Date, Hours, Minutes)
console.log(future); // Thu Nov 19 2037 15:23:00

future.getFullYear(); // 2037
future.getMonth(); // 10 (November, months are 0-based)
future.getDate(); // 19 (Day of the month)
future.getDay(); // 4 (Thursday, 0=Sunday)
future.getHours(); // 15
future.getMinutes(); // 23
future.getSeconds(); // 00

future.toISOString(); // "2037-11-19T15:23:00.000Z" (ISO format)
future.setFullYear(2024);
```

---

## **Date Internationalization (i18n)**
```javascript
const now = new Date();
const formatted = new Intl.DateTimeFormat('en-US').format(now); // MM/DD/YYYY
```

### **Custom Date Formatting**
```javascript
const options = {
  hour: 'numeric',
  minute: 'numeric',
  day: 'numeric',
  month: 'long',
  year: 'numeric',
  weekday: 'long',
};

const formattedDate = new Intl.DateTimeFormat('en-US', options).format(now);
// Example: "Wednesday, August 12, 2020, 8:44 AM"
```

### **Get User's Locale**
```javascript
const userLocale = navigator.language;
console.log(userLocale); // e.g., "en-US"
const formattedLocalDate = new Intl.DateTimeFormat(userLocale, options).format(now);
```

### **Number Formatting with Internationalization**
```javascript
new Intl.NumberFormat('en-US').format(12345566); // "12,345,566"
```

---

## **JavaScript Timers**

### **1. `setTimeout()`**
- Runs a function **once** after a delay.
```javascript
setTimeout(() => console.log('Timer done!'), 3000); // Runs after 3 seconds
```

### **2. `setInterval()`**
- Runs a function **repeatedly** at a fixed interval.
```javascript
setInterval(() => console.log('Repeating Timer!'), 3000); // Runs every 3 seconds
```

---

This guide covers **Numbers, Math, Dates, and Timers** in JavaScript! 🚀