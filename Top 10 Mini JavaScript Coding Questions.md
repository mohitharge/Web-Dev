These are small but **frequently asked in interviews** to test core logic, ES6 usage, and problem-solving skills.

---

## ✅ Top 10 Mini JavaScript Coding Questions (with Brief Explanations)

---

### **1. Find Duplicates in an Array**

```js
function findDuplicates(arr) {
  const seen = new Set();
  const duplicates = new Set();
  for (const item of arr) {
    if (seen.has(item)) duplicates.add(item);
    else seen.add(item);
  }
  return [...duplicates];
}

findDuplicates([1, 2, 3, 2, 4, 3]); // [2, 3]
```

---

### **2. Reverse a String (Multiple Ways)**

**Using Built-in Methods:**

```js
function reverseStr(str) {
  return str.split('').reverse().join('');
}
```

**Using Loop:**

```js
function reverseStr(str) {
  let res = '';
  for (let char of str) {
    res = char + res;
  }
  return res;
}
```

---

### **3. Check if a String is a Palindrome**

```js
function isPalindrome(str) {
  const cleaned = str.toLowerCase().replace(/[^a-z0-9]/g, '');
  return cleaned === cleaned.split('').reverse().join('');
}
```

---

### **4. Count the Occurrences of Each Character in a String**

```js
function charFrequency(str) {
  const map = {};
  for (let char of str) {
    map[char] = (map[char] || 0) + 1;
  }
  return map;
}

charFrequency("aabcc"); // { a: 2, b: 1, c: 2 }
```

---

### **5. Flatten a Nested Array (1 level)**

```js
function flattenOnce(arr) {
  return [].concat(...arr);
}

flattenOnce([1, [2, 3], [4, 5]]); // [1, 2, 3, 4, 5]
```

**Recursive:**

```js
function flattenDeep(arr) {
  return arr.reduce((acc, val) =>
    Array.isArray(val) ? acc.concat(flattenDeep(val)) : acc.concat(val), []);
}
```

---

### **6. Remove Falsy Values from an Array**

```js
function cleanArray(arr) {
  return arr.filter(Boolean);
}

cleanArray([0, 1, false, 2, '', 3, null]); // [1, 2, 3]
```

---

### **7. Find the First Non-Repeating Character**

```js
function firstUniqueChar(str) {
  const map = {};
  for (let char of str) map[char] = (map[char] || 0) + 1;
  for (let char of str) if (map[char] === 1) return char;
  return null;
}
```

---

### **8. Capitalize First Letter of Each Word**

```js
function capitalizeWords(str) {
  return str.replace(/\\b\\w/g, char => char.toUpperCase());
}

capitalizeWords('hello world'); // Hello World
```

---

### **9. Check if Two Strings are Anagrams**

```js
function isAnagram(a, b) {
  const normalize = str => str.split('').sort().join('');
  return normalize(a) === normalize(b);
}
```

---

### **10. Remove Duplicates from Array (1-liner)**

```js
const unique = arr => [...new Set(arr)];

unique([1, 2, 2, 3, 3, 3]); // [1, 2, 3]
```

---

## 🧠 Interview Tip:

* **Focus on writing readable code** — naming matters.
* Always **explain your approach** clearly to the interviewer.
* Add **edge case handling** if time allows (e.g., empty input, case sensitivity).

---

Would you like:

* A Markdown or PDF version of this list?
* Flashcards for rapid revision?
* Mock timed coding round with these types?

Let me know and I’ll prep it for you.
