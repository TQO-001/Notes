## 12. JSON (JavaScript Object Notation)

> JSON is the “language” of data exchange on the web. Think of it as a text‑based way to represent objects and arrays that any system can read.

---

### 12.1 What Is JSON?
JSON is a text-based, human-readable format used to represent structured data. It is based on a subset of JavaScript's object and array literal syntax and is commonly used for data exchange between clients and servers, configuration files, and local storage.

```json
{
  "name": "Thulani",
  "age": 22,
  "skills": ["JavaScript", "React", "Node.js"]
}
```

---

### 12.2 JSON Syntax Rules

- **Objects** use `{}` with **string** keys and values separated by `:`
- **Arrays** use `[]`, values separated by commas
- **Primitives**: strings (always double quotes), numbers, booleans (`true`/`false`), `null`
- **No trailing commas** allowed

```json
{
  "title": "Hello",
  "count": 10,
  "active": true,
  "tags": ["js", "json"],
  "money": null
}
```

---

### 12.3 Converting Between JSON & JS

|Operation|Code|
|---|---|
|**Stringify** JS → JSON|`JSON.stringify(obj)`|
|**Parse** JSON → JS|`JSON.parse(jsonString)`|

```js
const user = { name: 'Thulani', age: 22 };
const jsonStr = JSON.stringify(user);
// → '{"name":"Thulani","age":22}'

const parsed = JSON.parse(jsonStr);
// → { name: 'Thulani', age: 22 }
```

> **Tip:** Always wrap `JSON.parse()` in `try/catch` if the source might be malformed.

---

### 12.4 JSON & `fetch()`

When you `fetch()` in JS, you’ll often get a JSON response:

```js
async function loadUsers() {
  const res = await fetch('/api/users');
  if (!res.ok) throw new Error('Network error');
  const users = await res.json();  // parse JSON body
  console.log(users);              // JS array/object
}
```

- `.json()` is itself asynchronous (returns a Promise).
- Combine with error‑handling (`res.ok`, `try/catch`).

---

### 12.5 Best Practices

- **Validate JSON** before parsing if you don’t control the source.
- **Pretty‑print** when storing or inspecting:

    ```js
    JSON.stringify(obj, null, 2)  // indents with 2 spaces
    ```

- **Don’t over‑nest**: deeply nested JSON is hard to work with.
- **Keep keys consistent** (e.g., always use camelCase or snake_case).
- **Limit data size**: avoid sending huge payloads to the client.

---

### 12.6 Quick Practice Ideas

- Fetch and display data from `https://jsonplaceholder.typicode.com/posts`.
- Store a user’s preferences in `localStorage` as JSON.
- Build a tiny “settings” panel that reads/writes a JSON file (mock with a local object).

---
### 12.7 Autism for Evil
> Pretty much that's all there is to it—JSON’s core is really as simple as that. It’s just:

1. **Objects** (`{ "key": value, … }`)
2. **Arrays** (`[ value, … ]`)
3. **Primitives** (strings in double‑quotes, numbers, booleans, and `null`)
4. No trailing commas, and keys must be strings.

In JavaScript, you can convert between JSON and JavaScript objects using `JSON.stringify()` and `JSON.parse()`:

```javascript
// JavaScript object
const user = {
  name: "Thulani",
  age: 22
};

// Convert to JSON string
const jsonString = JSON.stringify(user);

// Convert back to JavaScript object
const parsedUser = JSON.parse(jsonString);
```

This is particularly useful when sending data to a server or storing it in local storage.

Beyond that, everything else is just how you apply it: parsing with `JSON.parse()`, serializing with `JSON.stringify()`, handling errors, and making sure your data isn’t so deeply nested or huge that it becomes unwieldy.

## 13. Web Storage (localStorage & sessionStorage)

> Browser‑based storage for persisting data on the client. Ideal for settings, tokens, and small amounts of state.

---

### 13.1 Storage Types

|Feature|`localStorage`|`sessionStorage`|
|---|---|---|
|Lifetime|Persists until explicitly cleared|Lives until the browser/tab closes|
|Scope|Across all tabs/windows of origin|Only within the same tab|
|Capacity|~5–10 MB (varies by browser)|Same as localStorage|
|Data type|Strings only|Strings only|

---

### 13.2 Basic API

```js
// Store a value
localStorage.setItem('theme', 'dark');

// Retrieve a value
const theme = localStorage.getItem('theme'); // "dark"

// Remove a key
localStorage.removeItem('theme');

// Clear all data
localStorage.clear();
```

> **Tip:** Swap `localStorage` for `sessionStorage` when you want per‑session data (e.g., a “draft” that resets on tab close).

---

### 13.3 Storing Objects
Since storage only holds strings, use JSON:

```js
const user = { name: 'Thulani', age: 22 };

// Save object
localStorage.setItem('user', JSON.stringify(user));

// Load object
const stored = localStorage.getItem('user');
const parsedUser = stored ? JSON.parse(stored) : null;
```

> **Side‑Note:** Always guard `JSON.parse()` with a null check or `try/catch` if the data might be missing or malformed.

---

### 13.4 Common Use Cases
- **Theme toggler**: Remember dark/light mode
- **Auth token**: Store JWT for API calls
- **Form drafts**: Auto‑save user input between visits
- **Shopping cart**: Persist items if user refreshes

---

### 13.5 Best Practices
- **Limit size**: Don’t store large blobs (use IndexedDB for large data)
- **Security**: Don’t store sensitive data (passwords, unencrypted tokens)
- **Expiration**: Implement your own TTL if needed (e.g., store timestamp and check on read)
- **Sync**: Use the `storage` event to sync between tabs:
    
    ```js
    window.addEventListener('storage', (e) => {
      if (e.key === 'theme') {
        applyTheme(e.newValue);
      }
    });
    ```
    

---

### 13.6 Quick Practice

- Build a **dark mode** toggle that persists your choice.
- Create a **“continue where you left off”** form auto‑save.
- Store a simple **to‑do list** in `localStorage` and load it on page refresh.

---

With this, you’ve got **client‑side persistence** nailed—no need to re‑fetch or lose user state on refresh or across sessions! Next up: Finally, dive into React fundamentals with confidence that your JSON & storage knowledge is rock‑solid.