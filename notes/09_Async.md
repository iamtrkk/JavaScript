# **Asynchronous JavaScript**

---

## **Asynchronous Code in JavaScript**
- **Non-blocking**: Execution doesn’t wait for an asynchronous task to finish.
- **Callbacks alone don’t make code asynchronous.**  
  Example: Loading an image via `src` is asynchronous by default.

---

## **AJAX (Asynchronous JavaScript and XML)**
- Allows **communication with remote servers** asynchronously.
- Can **request data from web servers dynamically** without reloading the page.

---

## **API (Application Programming Interface)**
- A piece of software **used by another piece of software** for communication.
- Examples:
  - **DOM API** (to manipulate the document)
  - **GeoLocation API** (to get user location)
  - **Online APIs** (RESTful APIs for web services)

---

## **JSON (JavaScript Object Notation)**
- A **stringified JavaScript object** used for API communication.
```json
{
  "name": "John",
  "age": 30
}
```
- **Conversion:**
```javascript
JSON.stringify({ name: 'John', age: 30 }); // Convert object to JSON string
JSON.parse('{"name":"John","age":30}'); // Convert JSON string to object
```

---

## **Promises**
- A **placeholder object** for a future asynchronous result.
- Used to replace **callbacks**, avoiding **callback hell**.
- **Lifecycle of a Promise**:
  - **Pending** (Initial state)
  - **Settled** (Either **fulfilled** or **rejected**)

### **Example of Fetch API with Promises**
```javascript
const getData = () => {
  fetch(`https://someurl/rest`)
    .then(response => response.json()) // First promise (fetch)
    .then(data => console.log(data)) // Second promise (.json())
    .catch(err => console.error(err)) // Handles errors
    .finally(() => console.log("Request completed")); // Always runs
};
```

### **Handling Errors in Promises**
```javascript
const getData = () => {
  fetch(`https://someurl/rest`)
    .then(response => response.json())
    .then(data => {
      if (!data.trk) throw new Error('No Trk found'); // Manually reject promise
    })
    .catch(err => console.error(err));
};
```

---

## **How Asynchronous JavaScript Works**
### **Single-threaded Execution & Event Loop**
- Unlike Java, **JavaScript executes one thread at a time**.
- **Asynchronous tasks** don’t block the execution due to **Web APIs** in the browser.
- Web APIs **handle async calls** and push them to the **callback queue** after completion.
- When the **call stack is empty**, the **event loop** moves tasks from the queue to execution.

---

## **Microtask Queue vs Callback Queue**
- Like the **callback queue** (setTimeout, event listeners), there’s a **microtask queue** (for promises).
- **Microtasks have priority** over normal callbacks.

### **Example: Event Loop Behavior**
```javascript
console.log("Test Start");

setTimeout(() => console.log('0 sec timer'), 0); // Goes to Callback Queue

Promise.resolve('Resolved Promise')
  .then(res => console.log(res)); // Goes to Microtask Queue (executes first)

console.log('Test End');
```
**Execution Order:**
1. `"Test Start"`
2. `"Test End"`
3. `"Resolved Promise"`
4. `"0 sec timer"`

Even if the promise **takes longer**, `setTimeout` will **wait** for the microtasks to complete.

---

## **Creating and Consuming a Custom Promise**
### **Creating a Promise**
```javascript
const lotteryPromise = new Promise(function (resolve, reject) {
  console.log('Lottery draw happening');
  setTimeout(() => {
    if (Math.random() >= 0.5) resolve('You win 🎉');
    else reject(new Error('You lost 😢'));
  }, 2000);
});
```

### **Consuming a Promise**
```javascript
lotteryPromise
  .then(res => console.log(res)) // Executes if resolved
  .catch(err => console.error(err)); // Executes if rejected
```

### **Immediate Resolved/Rejection**
```javascript
Promise.resolve("Resolves immediately").then(res => console.log(res));
Promise.reject(new Error("Rejects immediately")).catch(err => console.error(err));
```

---

## **Async/Await**
- **Syntactic sugar** over promises (`.then/.catch`).
- `async` functions run **in the background** while JavaScript executes the rest of the code.
- `await` **pauses execution** until the promise resolves.

### **Example: Fetching Data with Async/Await**
```javascript
const getVal = async function () { // Async function
  const res = await fetch('https://someurl'); // Waits for fetch
  const data = await res.json(); // Waits for JSON parsing
  console.log(data);
};
```
### **Key Features**
- The function **doesn't block** the main thread.
- **Error handling is done using `try...catch`** instead of `.catch()`.

### **Example with `try...catch`**
```javascript
const getVal = async function () {
  try {
    const res = await fetch('https://someurl');
    if (!res.ok) throw new Error('Request failed');
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.error(err);
  }
};
```

---

This guide covers **AJAX, API, JSON, Promises, Async/Await, and Event Loop** in JavaScript! 🚀