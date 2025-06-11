

## 🔥 Core Concepts (Beyond Basics)

### 1. **Reconciliation Algorithm**

* How React decides what to re-render.
* Diffing algorithm (virtual DOM vs real DOM).
* Why keys are important in lists.

### 2. **React Fiber Architecture**

* What is Fiber? Why did React rewrite its core?
* Concept of units of work and time slicing.

### 3. **Concurrent Mode (React 18+)**

* `startTransition()`, `useDeferredValue()`
* How it improves perceived performance.

---

## 🧠 Advanced Hooks & Patterns

### 4. **Custom Hooks**

* Encapsulating logic, sharing behavior across components.
* Example: `useDebounce`, `usePrevious`, `useFetch`.

### 5. **useRef vs useMemo vs useCallback**

* When and why to use them.
* Optimizing renders and keeping references stable.

### 6. **State Management Patterns**

* Prop drilling vs context vs Redux/RTK vs Zustand/Recoil/Jotai.
* When to use each depending on scale.

---

## 🧩 Component Architecture

### 7. **Controlled vs Uncontrolled Components**

* Managing form state internally vs externally.

### 8. **Compound Components Pattern**

* Design APIs for related components (e.g. `<Tabs><Tab /><TabPanel /></Tabs>`).

### 9. **Higher-Order Components (HOC) vs Render Props vs Hooks**

* Trade-offs, legacy vs modern approaches.

---

## ⚙️ Performance & Optimization

### 10. **Re-renders & Batching**

* Why a component re-renders.
* How React batches state updates (sync vs async).

### 11. **React.memo and PureComponent**

* Preventing unnecessary renders.
* Shallow comparison caveats.

### 12. **Code Splitting & Lazy Loading**

* `React.lazy`, `Suspense`, dynamic imports in Next.js.
* SSR impact & fallback handling.

---

## 🛠️ Next.js Specifics (If you're applying to roles using it)

### 13. **App Router vs Pages Router**

* Differences in routing, layouts, and server/client components.

### 14. **Server Components**

* Benefits, limitations, use cases.

### 15. **Incremental Static Regeneration (ISR)**

* How it works under the hood.

---

## 🌐 Networking & APIs

### 16. **Error Handling in React**

* Try-catch, error boundaries, suspense for data fetching.

### 17. **Fetching Strategies**

* `useEffect` vs SWR/React Query vs Server Components.
* Stale-while-revalidate, caching, deduping.

---

## 🧼 Clean Code & Testing

### 18. **Component Composition**

* Keep components small, reusable, testable.

### 19. **Testing React Apps**

* Unit testing with Jest + React Testing Library.
* Integration tests, mocking API calls.

### 20. **Accessibility (a11y)**

* Semantic HTML, ARIA roles, keyboard navigation.

---

## 🧩 TypeScript in React (if applicable)

### 21. **Typing Props, Refs, Event Handlers**

* Using generics for components and hooks.

### 22. **Discriminated Unions**

* Advanced prop typing patterns.

---

## 🧪 Interview Questions Starters

Here are a few **typical interview-style questions** from the above topics:

* What happens during React's render and commit phases?
* How does `React.memo` differ from `useMemo`?
* How would you structure a large-scale React app with reusable modules?
* Explain the difference between SSR, SSG, ISR in Next.js.
* How do you avoid prop drilling in a complex component tree?
* When would you not use `useEffect`?
* Can you explain the React 18 concurrent rendering model?
* What happens when a state update is batched inside an async function?

