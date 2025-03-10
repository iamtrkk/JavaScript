# Developer Tools & Configuration

## Prettier

- Install **Prettier** and set it as the **default formatter**.
- Enable **Format on Save** from VS Code settings.
- Customizable via `.prettierrc` file (e.g., using single quotes instead of double).
- Refer to [Prettier documentation](https://prettier.io/) for configuration options.

---

## Live Server

- Install **Live Server** globally:

  ```sh
  npm install -g live-server
  ```

- This will automatically reload the browser whenever a file is updated.
- Run it using:

  ```sh
  live-server
  ```

---

## User Snippets (VS Code)

- **Custom snippets** allow for quick shortcuts (e.g., `cl` for `console.log`).
- Configure in VS Code settings under `User Snippets`.

---

## Console Methods

Different types of `console` outputs in JavaScript:

- **`console.log()`** → General logging.
- **`console.warn()`** → Warnings (yellow text in dev tools).
- **`console.error()`** → Errors (red text in dev tools).
- **`console.table()`** → Display objects in a tabular format.

Example:

```javascript
const obj = { name: "Trk", age: 25 };
console.table(obj);
```