# Top 10 JavaScript Hands-on Interview Questions (3 YOE Level)

This markdown contains detailed preparation material for 3 years of JavaScript experience interviews. Each question includes core concept explanation, real-life use cases, implementation with explanations, and STAR method-based follow-up responses.

---

## 1. Debounce Function

### Core Concept

Debounce ensures that a function is invoked only after a specified delay has elapsed since the last time it was called. Useful for limiting rapid executions.

### Real-life Use Cases

* Auto-saving a form input while typing.
* Limiting API calls when a user types in a search box.

### Implementation

```js
function debounce(func, delay) {
  let timeout;
  return function (...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(this, args), delay);
  };
}
```

### Explanation

* Stores `timeout` in closure.
* Clears previous timeout on each call.
* Delays execution until after user stops triggering the function.

### Common Follow-ups (STAR)

**Q: What's the difference between debounce and throttle?**

* **Situation**: In a scroll listener project.
* **Task**: Needed to optimize performance.
* **Action**: Used `throttle` for consistent interval execution.
* **Result**: Performance improved without missing data points.

---

## 2. Deep Clone an Object

### Core Concept

Creates a true copy of an object, including nested objects, instead of a reference copy.

### Real-life Use Cases

* Immutable updates in Redux or Vuex.
* Duplicating configuration/state objects.

### Implementation

```js
function deepClone(obj) {
  if (obj === null || typeof obj !== 'object') return obj;
  if (Array.isArray(obj)) return obj.map(deepClone);
  const result = {};
  for (let key in obj) {
    result[key] = deepClone(obj[key]);
  }
  return result;
}
```

### Explanation

* Uses recursion to traverse and clone nested levels.
* Handles arrays and objects separately.

### Common Follow-ups (STAR)

**Q: Why not use JSON.stringify/parse?**

* **Situation**: Needed to clone an object containing `Date` and `undefined`.
* **Task**: Ensure clone retains full data fidelity.
* **Action**: Used custom `deepClone` function.
* **Result**: No data loss; dates remained intact.

---

## 3. Implement `call`, `apply`, `bind`

### Core Concept

Custom implementation to understand function context (`this`) binding.

### Real-life Use Cases

* Function borrowing.
* Custom function utilities.

### Implementation

```js
Function.prototype.myCall = function (context, ...args) {
  context = context || globalThis;
  context.fn = this;
  const result = context.fn(...args);
  delete context.fn;
  return result;
};
```

### Explanation

* Temporarily assigns the function to the context.
* Executes it and deletes after call.

### Common Follow-ups (STAR)

**Q: When would you use `bind` over `call`?**

* **Situation**: Event handler with preserved context.
* **Task**: Avoid losing `this` in callbacks.
* **Action**: Used `bind` to permanently fix context.
* **Result**: Callback executed in correct context.

---

## 4. Flatten a Nested Array

### Core Concept

Convert a deeply nested array into a single flat array.

### Real-life Use Cases

* UI rendering flat lists.
* Normalizing complex data structures.

### Implementation

```js
function flatten(arr) {
  return arr.reduce((acc, val) =>
    Array.isArray(val) ? acc.concat(flatten(val)) : acc.concat(val)
  , []);
}
```

### Explanation

* Uses recursion and `reduce`.
* Checks if element is an array and flattens it.

### Common Follow-ups (STAR)

**Q: How would you flatten without recursion?**

* **Situation**: Needed to flatten large array efficiently.
* **Task**: Avoid call stack issues.
* **Action**: Used iterative method with stack.
* **Result**: Handled large arrays smoothly.

---

## 5. Implement `Promise.all`

### Core Concept

Aggregate multiple promises into a single one that resolves when all do.

### Real-life Use Cases

* Parallel API requests.
* Loading multiple components/data sets.

### Implementation

```js
function promiseAll(promises) {
  return new Promise((resolve, reject) => {
    const result = [];
    let completed = 0;
    promises.forEach((p, i) => {
      Promise.resolve(p).then(val => {
        result[i] = val;
        completed++;
        if (completed === promises.length) resolve(result);
      }).catch(reject);
    });
  });
}
```

### Explanation

* Wraps all values with `Promise.resolve`.
* Resolves when all are done.
* Maintains order using index.

### Common Follow-ups (STAR)

**Q: How does `Promise.allSettled` differ?**

* **Situation**: API calls where partial failure is acceptable.
* **Task**: Capture all outcomes.
* **Action**: Used `allSettled` instead.
* **Result**: Could process successful ones and log failures.

---

## 6. Convert String to Camel Case

### Core Concept

Transforms `the-stealth-warrior` into `theStealthWarrior`.

### Real-life Use Cases

* Converting CSS-like strings to JS variable names.
* Normalizing keys from APIs.

### Implementation

```js
function toCamelCase(str) {
  return str.replace(/[-_](\w)/g, (_, c) => c.toUpperCase());
}
```

### Explanation

* Uses regex to capture `-` or `_` followed by a letter.
* Capitalizes letter and removes delimiter.

### Common Follow-ups (STAR)

**Q: How would you handle PascalCase?**

* **Situation**: Formatting DB column names.
* **Task**: Map keys to frontend naming convention.
* **Action**: Added option for capitalizing first letter.
* **Result**: Seamless transformation of field names.

---

## 7. Event Delegation

### Core Concept

Attaching a single listener to a parent to handle all child events.

### Real-life Use Cases

* Dynamic lists where children are added at runtime.
* Avoid attaching many event listeners.

### Implementation

```js
document.getElementById('parent').addEventListener('click', (e) => {
  if (e.target.matches('.child')) {
    console.log('Child clicked:', e.target);
  }
});
```

### Explanation

* Listener added only to parent.
* Event bubbling helps catch child interactions.

### Common Follow-ups (STAR)

**Q: How does it improve performance?**

* **Situation**: Rendering list with 1000+ items.
* **Task**: Avoid memory issues.
* **Action**: Switched to event delegation.
* **Result**: Reduced 1000 listeners to just 1.

---

## 8. Memoization

### Core Concept

Caching the result of function calls for repeated inputs.

### Real-life Use Cases

* Expensive computations (Fibonacci, factorial).
* Avoiding repeated API calls in a session.

### Implementation

```js
function memoize(fn) {
  const cache = {};
  return function (...args) {
    const key = JSON.stringify(args);
    if (cache[key]) return cache[key];
    return cache[key] = fn.apply(this, args);
  };
}
```

### Explanation

* Uses JSON key as cache key.
* Stores and reuses previously computed results.

### Common Follow-ups (STAR)

**Q: How would you handle cache expiration?**

* **Situation**: Memoizing API with rate limits.
* **Task**: Refresh data after 10 minutes.
* **Action**: Added timestamp and timeout logic.
* **Result**: Balanced speed and data freshness.

---

## 9. `once()` Function

### Core Concept

Ensures a function runs only once and ignores future calls.

### Real-life Use Cases

* Analytics tracking (e.g., button clicked).
* One-time setup or configuration.

### Implementation

```js
function once(fn) {
  let called = false;
  let result;
  return function (...args) {
    if (!called) {
      called = true;
      result = fn.apply(this, args);
    }
    return result;
  };
}
```

### Explanation

* Uses closure to store execution state.
* Executes only on first call.

### Common Follow-ups (STAR)

**Q: What if I want to reset and allow it again?**

* **Situation**: Wanted re-init after logout.
* **Task**: Allow multiple `once()` instances.
* **Action**: Wrapped `once()` inside a factory.
* **Result**: Could reuse and reset behavior.

---

## 10. Reverse Words in a Sentence

### Core Concept

Reverses characters of each word while maintaining order.

### Real-life Use Cases

* CAPTCHA transformations.
* Fun UI/text games or formatting.

### Implementation

```js
function reverseWords(str) {
  return str.split(' ').map(word => word.split('').reverse().join('')).join(' ');
}
```

### Explanation

* Splits by space.
* Reverses each word individually.

### Common Follow-ups (STAR)

**Q: How would you reverse the word order too?**

* **Situation**: Reformatting logs.
* **Task**: Change word order and characters.
* **Action**: Combined reverse string with array reversal.
* **Result**: Clean and readable reversed logs.

---

## ✅ JavaScript-Centric Conceptual Questions (with In-Depth Answers)

---

### **1. What’s the difference between ES5 and ES6?**

**Core Concepts:**
ES6 (also called ECMAScript 2015) introduced modern features to make JavaScript cleaner, more modular, and less error-prone.

| Feature              | ES5                     | ES6                                       |
| -------------------- | ----------------------- | ----------------------------------------- |
| Variable Declaration | `var`                   | `let`, `const`                            |
| Functions            | Function expressions    | Arrow functions                           |
| Classes              | No native classes       | `class` syntax introduced                 |
| Modules              | No native module system | `import` / `export`                       |
| Scoping              | Function scoped         | Block scoped (`let`, `const`)             |
| String Interpolation | Concatenation (`+`)     | Template literals (`` `Hello ${name}` ``) |

**Real-World Example:**

* ES5 `var` hoisting could cause bugs in loops.
* ES6 `let` solved scoping issues in loops or closures.

---

### **2. What are Closures in JavaScript?**

**Concept:**
A closure is formed when a function "remembers" its lexical scope even after the outer function has returned.

```js
function outer() {
  let count = 0;
  return function inner() {
    return ++count;
  };
}
const counter = outer();
console.log(counter()); // 1
console.log(counter()); // 2
```

**Use Cases:**

* Encapsulation (private variables)
* Memoization
* Event handler factories

**Follow-up:**

> "How do closures lead to memory leaks?"
> **Answer (STAR):**

* **S:** We had a utility function storing event listeners with closures.
* **T:** Over time, memory usage kept increasing.
* **A:** I diagnosed that closures were holding references in global scope.
* **R:** After nullifying the references explicitly, memory stabilized.

---

### **3. What is Hoisting?**

**Concept:**
JavaScript moves variable and function declarations to the top of their scope at compile time.

```js
console.log(a); // undefined
var a = 5;
```

* `var` gets hoisted with **undefined**
* `let`/`const` get hoisted but are in **temporal dead zone**

**Use Case:**
Understanding hoisting helps prevent reference errors and bugs in large codebases.

---

### **4. What is the difference between `==` and `===`?**

| Operator | Description                        |
| -------- | ---------------------------------- |
| `==`     | Loose equality, does type coercion |
| `===`    | Strict equality, no coercion       |

```js
'5' == 5    // true
'5' === 5   // false
```

**Use Case:**
Use `===` to avoid unintentional type coercion bugs.

---

### **5. Explain Event Delegation**

**Concept:**
Instead of attaching event listeners to individual elements, you attach it to a parent and catch events as they bubble up.

```js
document.getElementById('list').addEventListener('click', function (e) {
  if (e.target.tagName === 'LI') {
    console.log('Clicked:', e.target.textContent);
  }
});
```

**Use Cases:**

* Dynamic DOM elements (e.g., dropdowns, modals)
* Performance: reduces the number of event listeners

---

### **6. What is the Event Loop?**

**Concept:**
The Event Loop handles asynchronous code by placing callbacks in the task/microtask queues and running them after the current stack is empty.

```js
console.log('Start');

setTimeout(() => console.log('Timeout'), 0);

Promise.resolve().then(() => console.log('Promise'));

console.log('End');
```

**Output:**

```
Start
End
Promise
Timeout
```

**Use Case:**
Helps debug async code and understand race conditions in React, APIs.

---

### **7. Explain `this` keyword in different contexts**

**Concept:**

| Context        | `this` refers to                      |
| -------------- | ------------------------------------- |
| Global scope   | `window` (in browser)                 |
| Object method  | the object                            |
| Arrow function | Lexical `this` (from enclosing scope) |
| Class          | Instance of the class                 |

```js
const obj = {
  name: 'Mohit',
  greet() {
    return `Hi ${this.name}`;
  }
};
```

**Common Bug:** Losing `this` in callbacks or `setTimeout`.

---

### **8. What is the difference between `null` and `undefined`?**

| Type        | Description                        |
| ----------- | ---------------------------------- |
| `undefined` | Variable declared but not assigned |
| `null`      | Explicitly assigned “nothing”      |

```js
let a;
console.log(a); // undefined
let b = null;
console.log(b); // null
```

---

### **9. Explain Prototypal Inheritance**

**Concept:**
JavaScript objects inherit directly from other objects via the prototype chain.

```js
function Animal(name) {
  this.name = name;
}
Animal.prototype.speak = function () {
  return `${this.name} speaks`;
};

const dog = new Animal('Rex');
dog.speak(); // "Rex speaks"
```

**Use Case:** Custom behavior reuse before ES6 `class`.

---

### **10. What is the difference between `map`, `forEach`, and `reduce`?**

| Method      | Purpose                    | Returns      |
| ----------- | -------------------------- | ------------ |
| `map()`     | Transform items            | New array    |
| `forEach()` | Perform side-effects       | `undefined`  |
| `reduce()`  | Accumulate to single value | Final result |

```js
const nums = [1, 2, 3];
nums.map(x => x * 2);     // [2, 4, 6]
nums.forEach(x => sum += x);
nums.reduce((acc, x) => acc + x, 0); // 6
```

---

## ✅ Bonus Non-JS Conceptuals (1-liners)

### **11. What are Semantic HTML tags?**

Tags that convey meaning to both the browser and developer — e.g., `<header>`, `<footer>`, `<article>`, `<nav>` improve accessibility and SEO.

### **12. What is CSS Preprocessing (e.g., SASS)?**

It allows variables, nesting, mixins, and functions — making styles modular and DRY.

---
