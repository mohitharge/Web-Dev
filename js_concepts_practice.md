
# ✅ JavaScript Concepts with 3–4 Scenarios Each

---

## 🔒 Closures

```js
// 1. Basic Closure
function greet(name) {
  return function(message) {
    console.log(`${message}, ${name}`);
  };
}
const sayHiToJohn = greet("John");
sayHiToJohn("Hello"); // Hello, John

// 2. Counter using Closure
function createCounter() {
  let count = 0;
  return function () {
    return ++count;
  };
}
const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2

// 3. Private Variable
function secretPassword() {
  const password = "12345";
  return {
    guess(input) {
      return input === password;
    }
  };
}
const checker = secretPassword();
console.log(checker.guess("12345")); // true

// 4. Loop with var (fixed using IIFE)
for (var i = 0; i < 3; i++) {
  (function(j) {
    setTimeout(() => console.log(j), 100);
  })(i);
}
```

---

## 🧠 `this` Keyword

```js
// 1. Global context
function show() {
  console.log(this); // In browsers: window
}
show();

// 2. Object method
const user = {
  name: "Mohit",
  sayHi() {
    console.log("Hi", this.name);
  }
};
user.sayHi(); // Hi Mohit

// 3. Losing `this` in a callback
const btn = {
  label: "Click me",
  click() {
    setTimeout(function() {
      console.log(this.label); // undefined (this is window)
    }, 1000);
  }
};
btn.click();

// 4. Fix with arrow function
const btnFixed = {
  label: "Click me",
  click() {
    setTimeout(() => {
      console.log(this.label); // Click me
    }, 1000);
  }
};
btnFixed.click();
```

---

## ⏳ Promises

```js
// 1. Basic Promise
const fetchData = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Data received"), 1000);
  });
};
fetchData().then(console.log);

// 2. Promise chaining
fetchData()
  .then(data => data + " ✅")
  .then(console.log); // Data received ✅

// 3. Promise rejection
const fail = () => Promise.reject("Error!");
fail().catch(console.error); // Error!

// 4. Multiple Promises
Promise.all([fetchData(), fetchData()])
  .then(console.log); // [ 'Data received', 'Data received' ]
```

---

## 🚀 Async/Await

```js
// 1. Basic usage
async function load() {
  const res = await fetchData();
  console.log(res);
}
load();

// 2. Try/catch handling
async function loadSafe() {
  try {
    const res = await fail();
    console.log(res);
  } catch (e) {
    console.error("Caught:", e);
  }
}

// 3. Sequential async calls
async function getAll() {
  const first = await fetchData();
  const second = await fetchData();
  console.log(first, second);
}

// 4. Parallel async calls
async function getParallel() {
  const [a, b] = await Promise.all([fetchData(), fetchData()]);
  console.log("Parallel:", a, b);
}
```

---

## 🕰️ Debounce

```js
function debounce(fn, delay) {
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}

// 1. Log search input
const logSearch = debounce(val => console.log("Searching for", val), 500);
logSearch("react");
logSearch("react hooks");

// 2. Resize event
window.addEventListener("resize", debounce(() => {
  console.log("Window resized");
}, 1000));

// 3. Button click handler (prevent spam)
document.getElementById("myBtn")?.addEventListener("click",
  debounce(() => alert("Clicked!"), 300)
);

// 4. API trigger
const debouncedApi = debounce(() => fetch("/search?q=..."), 800);
```

---

## 🔂 Throttle

```js
function throttle(fn, delay) {
  let last = 0;
  return (...args) => {
    const now = Date.now();
    if (now - last >= delay) {
      last = now;
      fn(...args);
    }
  };
}

// 1. Scroll
window.addEventListener("scroll", throttle(() => {
  console.log("Scroll event triggered");
}, 1000));

// 2. Mouse move
document.addEventListener("mousemove", throttle(e => {
  console.log("Mouse at", e.clientX, e.clientY);
}, 500));

// 3. Resize
window.addEventListener("resize", throttle(() => {
  console.log("Throttled resize");
}, 800));

// 4. Clicks
const handleClick = throttle(() => console.log("Clicked!"), 2000);
document.addEventListener("click", handleClick);
```
