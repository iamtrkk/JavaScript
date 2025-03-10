# JavaScript Arrays and Methods

### Always check if you need to mutate the original array before using any method.

---

## **Basic Array Operations**

### **Creating an Array**
```javascript
let arr = ['a', 'b', 'c', 'd', 'e'];
```

### **Slice()**
- Used to create a shallow copy of an array.
- **Does not** mutate the original array.

```javascript
arr.slice(2);      // ['c', 'd', 'e']
arr.slice(2, 4);   // ['c', 'd']
arr.slice(-2);     // ['d', 'e']
arr.slice(1, -2);  // ['b', 'c']
arr.slice();       // ['a', 'b', 'c', 'd', 'e'] (same as [...arr])
```

### **Mutating Methods (Modify Original Array)**
- **Push()** → Adds element at the end.
- **Unshift()** → Adds element at the start.
- **Pop()** → Removes element from the end.
- **Shift()** → Removes element from the start.
- **Splice()** → Removes elements from any index (mutates the original array).
- **Reverse()** → Reverses the array (mutates the original array).

### **Concat()**
- Combines two arrays into a new array (does not mutate the original).

```javascript
const arr2 = ['f', 'g'];
const newArr = arr.concat(arr2); // ['a', 'b', 'c', 'd', 'e', 'f', 'g']
```

- **Same as:**
```javascript
const newArr = [...arr, ...arr2];
```

### **Join()**
- Converts an array into a string.

```javascript
arr.join('-'); // 'a-b-c-d-e'
```

---

## **Accessing Elements**

### **at()**
- Retrieves elements by index (works with strings too).
```javascript
arr.at(0);    // 'a'
arr.at(-1);   // 'e' (easier than arr[arr.length - 1])
```

---

## **Looping Over Arrays**

### **For Loop**
```javascript
for (const element of arr) {
  console.log(element);
}
```

### **For Loop with Index**
```javascript
for (const [i, element] of arr.entries()) {
  console.log(i, element);
}
```

### **ForEach()**
- **Cannot use break or continue** (unlike for loops).
- Works with arrays, maps, and sets (sets don’t have keys).

```javascript
arr.forEach(function (element) {
  console.log(element);
});
```

### **ForEach with Index**
```javascript
arr.forEach(function (element, i, arr) {
  console.log(i, element);
});
```

---

## **Array Data Transformation**

### **1. Map()**
- Transforms each element and returns a **new array**.
- The length of the output array **is the same** as the input array.

```javascript
const mapped = arr.map((char) => char.toUpperCase()); // ['A', 'B', 'C', 'D', 'E']
```

---

### **2. Filter()**
- Filters elements based on a condition.
- The output array **may have fewer elements**.

```javascript
const numbers = [1, -2, 3, -4, 5];
const filtered = numbers.filter(num => num > 0); // [1, 3, 5]
```

---

### **3. Reduce()**
- Accumulates values and returns a **single result**.

```javascript
const balance = numbers.reduce((acc, cur) => acc + cur, 0);
```
- `acc` = accumulator (stores result from previous iterations).
- `cur` = current element.
- `0` = initial value.

---

### **4. Find()**
- Returns the **first element** that matches the condition.

```javascript
const firstNegative = numbers.find(num => num < 0); // -2
```

### **5. FindIndex()**
- Returns the **index** of the first matching element.

```javascript
const firstNegativeIndex = numbers.findIndex(num => num < 0); // 1
```

**Difference between `indexOf()` and `findIndex()`**:
- `findIndex()` allows **conditions**.
- `indexOf()` requires **exact value**.

---

### **6. Some()**
- Returns `true` if **any** element matches the condition.

```javascript
const hasPositive = numbers.some(num => num > 0); // true
```

### **7. Every()**
- Returns `true` if **all** elements match the condition.

```javascript
const allPositive = numbers.every(num => num > 0); // false
```

---

## **Flattening Arrays**

### **8. Flat()**
- Flattens nested arrays.

```javascript
const arrNested = [[1, 2, 3], [4, 5], 6];
arrNested.flat(); // [1, 2, 3, 4, 5, 6]
```

- **For deeper nesting:**
```javascript
arrNested.flat(2); // Flattens two levels deep
```

### **9. FlatMap()**
- Maps and flattens **one level deep**.

```javascript
const numArr = [[1, 2], [3, 4]];
numArr.flatMap(arr => arr.map(num => num * 10)); // [10, 20, 30, 40]
```

---

## **Sorting**

### **10. Sort()**
- **Mutates the original array** (create a copy using `slice()` if needed).
- Default sorting is **alphabetical (converts numbers to strings)**.

```javascript
arr.sort(); // Works for strings
```

### **Sorting Numbers**
- **Ascending order:**
```javascript
numbers.sort((a, b) => a - b);
```
- **Descending order:**
```javascript
numbers.sort((a, b) => b - a);
```

---

## **Filling and Creating Arrays**

### **11. Fill()**
- Fills an array with a value.

```javascript
const x = new Array(5).fill(0); // [0, 0, 0, 0, 0]
```

- Filling within a range:
```javascript
x.fill(9, 2, 4); // Only fills index 2 to 3
```

---

### **12. Array.from()**
- Creates an array and fills it using a function.
- Converts iterables (maps, sets, strings) into arrays.

```javascript
const y = Array.from({ length: 7 }, () => 1); // [1, 1, 1, 1, 1, 1, 1]
```

- Creating an array with an index:

```javascript
const y = Array.from({ length: 7 }, (_, i) => i + 1); // [1, 2, 3, 4, 5, 6, 7]
```