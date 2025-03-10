# Document Object Model (DOM)

The **DOM (Document Object Model)** is a structured representation of an HTML document that allows JavaScript to access and manipulate HTML elements and styles dynamically.

## DOM Structure

- `document` is the entry point to the DOM.
- `document.querySelector()` can be used to select HTML elements.

```javascript
const element = document.querySelector('.className');
```

Example DOM structure:

```
Document
 ├── <html>
 │   ├── <head>
 │   ├── <body>
 │       ├── <div>
 │       ├── <p>
 │       ├── <img>
```

---

## Mouse Events

### Selecting an Element & Adding an Event Listener

Use `querySelector()` to select an element and `addEventListener()` to trigger a function on events.

```javascript
document.querySelector('.className').addEventListener('click', function () {
  console.log('trk');
});
```

### Getting Input Value

```javascript
console.log(document.querySelector('.className').value);
```

### Adding Styles

```javascript
document.querySelector('body').style.background = 'blue';
```

---

## Key Events

Handle keyboard events using `addEventListener()`.

```javascript
document.querySelector('.className').addEventListener('keydown', function (e) {
  console.log(e.key); // Logs the pressed key
});
```

- The event object (`e`) contains details about the key press.
- `e.key` returns the name of the pressed key.