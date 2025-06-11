
## 🧠 Core JS Concepts

1. **Execution Context & Call Stack**
   JS code runs inside an execution context (Global/Function) with separate memory and code phases. The call stack manages function invocation order using LIFO, enabling synchronous execution.

2. **Hoisting**
   Declarations (`var`, `function`) are hoisted to the top of their scope, but only `var` is initialized as `undefined`. `let` and `const` are hoisted too, but stay in the Temporal Dead Zone (TDZ).

3. **Closures**
   A closure is a function that retains access to its lexical scope even when executed outside that scope — useful for data privacy, like in a counter function or caching.

4. **`this` Keyword**
   `this` refers to the calling context. In global scope, it's `window`; in object methods, it's the object; arrow functions lexically bind `this`; `bind`, `call`, and `apply` let you control its value.

5. **Scoping**
   Function scope applies to `var`, block scope to `let` and `const`. Lexical scoping means functions inherit variables from the parent scope in which they were defined.

6. **Currying**
   Currying breaks a multi-arg function into nested single-arg functions. It helps create reusable logic like `add(a)(b)` and enhances functional composition.

7. **Higher Order Functions**
   Functions that take other functions as arguments or return them (like `map`, `filter`, `reduce`) promote modular and reusable code — core to functional JS.

8. **Promises & Async/Await**
   Promises represent future values and handle async operations. `async/await` simplifies syntax over `.then`, and constructs like `Promise.all` let you run them in parallel.

9. **Event Loop & Concurrency**
   JS uses a single-threaded model with an event loop to manage concurrency. Microtasks (Promises) run before macrotasks (setTimeout).

   ```js
   // Output: 1, 4, 3, 2
   ```

10. **Memory Management**
    JS has automatic garbage collection via reference counting and mark-and-sweep. Memory leaks happen via unused references (e.g., closures or DOM not cleared).

---

## 🔄 Object-Oriented Concepts in JS

1. **Prototypes & Inheritance**
   JS objects inherit via prototype chains. Unlike class-based inheritance, prototypal inheritance is dynamic and allows object delegation directly.

2. **`Object.create`, `Object.assign`, Spread vs Rest**
   `Object.create` sets the prototype explicitly. `assign` and spread copy properties; rest gathers remaining values — useful in cloning or destructuring.

3. **Class vs Function Constructors**
   ES6 `class` is syntactic sugar over constructor functions. Both allow object instantiation, but `class` supports `super`, inheritance, and clearer syntax.

---

## 🧪 Data Types and Behavior

1. **Primitive vs Non-Primitive**
   Primitives (`string`, `number`, `boolean`, etc.) are immutable and passed by value. Non-primitives (`objects`, `arrays`) are passed by reference.

2. **Pass by Value vs Pass by Reference**
   Primitives copy the actual value; objects/arrays pass references, so changes affect the original object unless cloned.

3. **Type Coercion & Equality**
   `==` allows coercion, `===` enforces type + value match. Understanding falsy values like `0`, `""`, `null` helps prevent bugs.

4. **Destructuring, Spread/Rest Operator**
   Destructuring unpacks values from objects/arrays. Spread copies elements, rest collects remaining items — both simplify code and improve readability.

---

## 🛠️ Functions and Patterns

1. **Debounce vs Throttle**
   Debounce delays execution till user stops triggering; throttle limits execution to once in a time frame — both improve performance in events like scroll/search.

2. **Memoization**
   Caches function results based on inputs to avoid recalculations — useful in expensive computations like recursion or API calls.

3. **Function Composition**
   Combining simple functions to form complex logic, e.g., `compose(f, g)(x)` runs `f(g(x))` — promotes clean, functional code.

4. **IIFE (Immediately Invoked Function Expression)**
   A function that runs as soon as it’s defined — useful to create isolated scopes or modules before ES6.

---

## ⚙️ Miscellaneous (Highly Asked)

1. **Event Delegation**
   Attaching one event listener to a parent to handle child events using event bubbling — improves performance and dynamic content handling.

2. **Custom Events**
   `CustomEvent` lets you define and dispatch your own events — useful for decoupled component communication.

3. **Shallow vs Deep Copy**
   Shallow copies share nested references; deep copies clone recursively — `structuredClone()` or `lodash` can help.

4. **Polyfills**
   Polyfills are fallbacks to mimic native behavior in older browsers. Example: `Array.prototype.map` for IE.

5. **Difference between `null`, `undefined`, `NaN`**
   `null` is intentional absence, `undefined` is uninitialized, `NaN` is an invalid number — all have different types and comparisons.

6. **Difference between `for`, `for...in`, `for...of`**
   `for` is traditional loop, `for...in` iterates keys in objects, `for...of` iterates values in arrays/iterables — avoid `for...in` on arrays.

7. **Set vs Map vs Object**
   `Set` stores unique values, `Map` stores key-value pairs with any type key, `Object` is key-value but keys are always strings/symbols.

8. **JSON.stringify vs JSON.parse use cases**
   `stringify` serializes JS objects, `parse` converts JSON string to JS — useful in storage, APIs, or deep cloning (with limitations).

9. **Optional chaining and nullish coalescing (`?.`, `??`)**
   `?.` safely accesses nested properties, `??` returns RHS only if LHS is `null` or `undefined` — prevents runtime crashes.

10. **What is a Symbol and when would you use it?**
    A `Symbol` is a unique, immutable primitive often used as object keys to avoid collisions in shared or private data.

---

## 💼 Bonus for Product Companies

* **Optimizing Large Array Ops**
  Use lazy evaluation, chunking, and in-place operations like `forEach` instead of chained `map/filter`.

* **Managing Large JSON in Frontend**
  Use pagination, virtual lists, or compression to avoid memory bloat and slow rendering.

* **Real-World Closures/Currying**
  Closures: keep private state in React hooks. Currying: partially apply reusable logic like form validators.

* **Debounce in React Search**
  Prevents unnecessary API calls on every keystroke; improves UX and reduces load by waiting for user to pause.

* **When to use Map over Object**
  When keys aren’t strings or order matters — `Map` has consistent iteration and better performance for frequent additions/removals.

