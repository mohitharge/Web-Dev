## ✅ Web Fundamentals (1–1.5 hours): Full Answers

---

### **1. DOM Manipulation (Without jQuery or React)**

**Answer:**
I use vanilla JavaScript methods like `document.getElementById`, `querySelector`, `createElement`, and `appendChild` for direct DOM manipulation. For example, to dynamically add a list item:

```js
const li = document.createElement('li');
li.textContent = 'New Item';
document.querySelector('ul').appendChild(li);
```

I also manage classes with `classList.add/remove/toggle` and styles using `element.style`.

> This shows you understand JS under the hood — not just libraries.

---

### **2. Event Delegation, Bubbling, and Capturing**

**Answer:**
Event delegation leverages **event bubbling** — where events propagate from the target element up to the parent. Instead of attaching listeners to multiple children, I attach one to the parent:

```js
document.getElementById('list').addEventListener('click', (e) => {
  if (e.target.matches('li')) {
    console.log('Clicked:', e.target.textContent);
  }
});
```

This improves performance and works well with dynamically generated content.

I also understand **capturing**, which is the opposite of bubbling. If needed, I pass `true` as the third argument to `addEventListener` to trigger it in the capturing phase.

---

### **3. HTTP Basics, CORS, REST**

**Answer:**
HTTP is a stateless protocol. I understand status codes (200, 400, 401, 404, 500), headers (Content-Type, Authorization), and methods (GET, POST, PUT, DELETE, PATCH).

CORS (Cross-Origin Resource Sharing) is a browser security feature that restricts cross-origin requests unless the server explicitly allows it via headers like:

```
Access-Control-Allow-Origin: *
```

REST APIs follow a resource-based architecture. I’ve worked with them using `fetch()` and `axios`, structuring endpoints around nouns (e.g., `GET /users`, `POST /orders`), and passing data using JSON.

---

### **4. LocalStorage, SessionStorage, Cookies**

**Answer:**

* `localStorage` persists data with no expiration; great for saving UI preferences.
* `sessionStorage` lasts only for the session/tab.
* Both store string key–value pairs: `localStorage.setItem('key', JSON.stringify(data))`.

**Cookies** are used for session management and sent with every HTTP request. They're suitable for authentication tokens (with `HttpOnly`, `Secure`, `SameSite` flags for safety).

---

### **5. Performance Tips (Debounce / Throttle)**

**Answer:**
To avoid performance hits from rapid-fire events like `scroll` or `input`, I use:

* **Debounce**: delays execution until X ms after last call.
* **Throttle**: ensures a function runs at most once every X ms.

```js
function debounce(fn, delay) {
  let timeout;
  return (...args) => {
    clearTimeout(timeout);
    timeout = setTimeout(() => fn(...args), delay);
  };
}
```

I use this to optimize input validation, auto-save, and search queries.

---

## 🏗️ Frontend System Design Overview (Short but Solid)

---

### **1. Component Architecture (Reusable UI)**

**Answer:**
I follow the atomic design principle — breaking UI into **reusable, self-contained components**: buttons, form fields, cards, etc.

I focus on:

* **Props vs State** separation
* **Lifting state up** where needed
* Keeping components **pure and composable**

In large apps, I use **feature-based folders** to group related components logically.

---

### **2. MVC / MVVM / Separation of Concerns**

**Answer:**
In SPAs, I maintain:

* **Model** (data/state)
* **View** (UI rendering)
* **Controller/ViewModel** (logic between data and view)

React is inherently MVVM-ish with unidirectional data flow. I make sure to separate:

* API logic (services)
* UI logic (components)
* State management (context/store/hooks)

---

### **3. Lazy Loading / Code Splitting**

**Answer:**
I use **React.lazy** and **dynamic imports** to defer loading of non-critical components:

```js
const Chart = React.lazy(() => import('./Chart'));
```

Also, I leverage Webpack and Vite's code splitting to break the app into chunks. This improves initial load times significantly.

---

### **4. Error Boundaries**

**Answer:**
In React, I use Error Boundaries to catch runtime errors in component trees:

```js
class ErrorBoundary extends React.Component {
  state = { hasError: false };
  static getDerivedStateFromError() { return { hasError: true }; }
  componentDidCatch(error, info) { /* log */ }
  render() { return this.state.hasError ? <Fallback /> : this.props.children; }
}
```

This prevents app crashes and helps in graceful degradation.

---

### **5. How I Structure Large-Scale JS Apps**

**Answer:**
I prefer **feature-based modular structure** over type-based. For example:

```
/features/user
  - UserPage.jsx
  - userSlice.js
  - userService.js
```

I use:

* **State managers** (Zustand/Redux) for shared data
* **Service layers** for API and business logic
* **Barrel exports** for cleaner imports

This leads to better scalability and maintainability.

---

## 🧩 Bonus: JS Design Patterns I Use

**Answer:**

* **Factory Pattern**: To generate different types of components/services.
* **Module Pattern**: For encapsulating reusable utility logic.
* **Singleton Pattern**: For config or auth state.
* **Observer Pattern**: For pub-sub event systems or shared state triggers.
* **Strategy Pattern**: For plugin-based behavior (e.g., validation rules, rendering formats).

I also apply **composition over inheritance** for flexibility and testing.
