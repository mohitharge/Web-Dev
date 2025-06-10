# 🧠 JavaScript Logic Building + DSA Roadmap

> A practical roadmap for frontend developers (like React devs) who want to strengthen their JavaScript logic and DSA skills.

---

## 📌 Phase 1: JavaScript Syntax + Core Data Structures (5 Days)

### ✅ Day 1: JS Syntax Refresh
- Variables: `let`, `const`, `var`
- Conditionals: `if-else`, `switch`
- Loops: `for`, `while`, `for...of`, `for...in`
- Functions: normal & arrow

#### Practice:
```js
for (let i = 1; i <= 10; i++) console.log(i);
const isEven = (n) => n % 2 === 0;
```

---

### ✅ Day 2: Arrays
- Create, access, modify: `push`, `pop`, `shift`, `splice`
- Iteration: `forEach`, `map`, `filter`, `reduce`

#### Practice:
```js
let nums = [1, 2, 3, 4];
let sum = nums.reduce((acc, n) => acc + n, 0);
let doubled = nums.map(n => n * 2);
```

---

### ✅ Day 3: HashMaps (Objects, Maps)
- Objects as key-value stores
- `Map` for order & non-string keys

#### Practice:
```js
let arr = ['a', 'b', 'a'];
let freq = {};
for (let ch of arr) freq[ch] = (freq[ch] || 0) + 1;

let map = new Map();
map.set('x', 5);
console.log(map.get('x'));
```

---

### ✅ Day 4: Pointers & Sets
- Two pointers using indices
- `Set` for uniqueness

#### Practice:
```js
let arr = [1, 2, 3, 4, 1];
let seen = new Set();
let hasDuplicate = false;
for (let n of arr) {
  if (seen.has(n)) hasDuplicate = true;
  seen.add(n);
}

let nums = [2, 4, 5, 6];
let target = 9;
for (let i = 0; i < nums.length; i++) {
  for (let j = i + 1; j < nums.length; j++) {
    if (nums[i] + nums[j] === target) console.log([i, j]);
  }
}
```

---

### ✅ Day 5: Stack, Queue & Recursion
- Stack: `push`, `pop`
- Queue: `push`, `shift`
- Recursion: base + recursive case

#### Practice:
```js
let stack = [];
for (let ch of "hello") stack.push(ch);
let reversed = '';
while (stack.length) reversed += stack.pop();

let queue = [];
queue.push(1);
queue.push(2);
console.log(queue.shift());

function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
```

---

## 🚀 Phase 2: JS Problem Solving & DSA (7 Days)

### ✅ Day 1: Basic Logic
- Max in array
- Reverse string
- Palindrome check
- Vowel count

---

### ✅ Day 2: Arrays + Hash Maps
- Two Sum
- First Non-Repeating Character
- Duplicates in array
- Word frequency

---

### ✅ Day 3: Strings + Sliding Window
- Longest substring without repeat
- Max sum subarray (size K)
- Anagram check

---

### ✅ Day 4: Sorting + Two Pointers
- Two Sum II (sorted)
- Array Palindrome
- Merge sorted arrays
- Sort 0s,1s,2s

---

### ✅ Day 5: Recursion + Backtracking
- Factorial / Fibonacci
- Subsets of array
- String permutations

---

### ✅ Day 6: Stack + Queue Logic
- Valid Parentheses
- Daily Temperatures
- Queue with 2 Stacks

---

### ✅ Day 7: Mock Interview Day
- Majority Element
- Merge Intervals
- Group Anagrams
- Product Except Self

---

## 🛠️ Tools & Resources
- [JS Tutor Visualizer](https://pythontutor.com/javascript.html)
- [PlayCode](https://playcode.io/)
- [Neetcode.io](https://neetcode.io/)
- [JavaScript.info](https://javascript.info/)
- [LeetCode Easy Problems](https://leetcode.com/problemset/all/?difficulty=Easy)

---

## ✍️ Author
**Mohit Harge** · Frontend Engineer | React Specialist

---

> Want this as a Notion template or interactive GitHub tracker? DM me.
