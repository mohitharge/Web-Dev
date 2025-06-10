

## 🌐 Browser Fundamentals

| Concept                               | What It Means                                              |
| ------------------------------------- | ---------------------------------------------------------- |
| **DOM** (Document Object Model)       | Tree-like structure of HTML page in the browser            |
| **BOM** (Browser Object Model)        | APIs provided by the browser (e.g., `window`, `navigator`) |
| **Critical Rendering Path**           | Steps browser takes to convert HTML, CSS, JS into pixels   |
| **Event Loop / Call Stack**           | How JavaScript handles asynchronous tasks                  |
| **Rendering vs Repainting vs Reflow** | Visual updates — expensive operations to be optimized      |
| **Main Thread**                       | The single-threaded JS execution thread                    |
| **Layout & Paint Phases**             | Part of how the browser renders your content               |

---

## 🧠 JavaScript Concepts (Browser-Specific)

| Concept                                       | What It Means                                                         |
| --------------------------------------------- | --------------------------------------------------------------------- |
| **Event Delegation**                          | Handling many events efficiently via bubbling                         |
| **Throttling/Debouncing**                     | Performance control over frequent events (e.g., scroll, resize)       |
| **Async/Await, Promises**                     | Handling asynchronous operations                                      |
| **LocalStorage vs SessionStorage vs Cookies** | Persistent client-side storage                                        |
| **CORS** (Cross-Origin Resource Sharing)      | Security mechanism for cross-domain requests                          |
| **Same-Origin Policy**                        | Restriction that prevents different origins from accessing each other |
| **Service Workers**                           | Background scripts for offline caching, push notifications            |
| **Web Workers**                               | Multi-threading for CPU-intensive tasks without blocking the UI       |

---

## ⚙️ Network & HTTP Concepts

| Concept                                           | What It Means                                             |
| ------------------------------------------------- | --------------------------------------------------------- |
| **DNS Resolution**                                | Translating domain name to IP                             |
| **TCP Handshake**                                 | Establishing connection before sending data               |
| **TLS/SSL**                                       | Encryption over HTTP (`https://`)                         |
| **HTTP/1.1 vs HTTP/2 vs HTTP/3**                  | Protocol versions with improved performance               |
| **HTTP Methods** (`GET`, `POST`, `PUT`, `DELETE`) | Communication verbs for APIs                              |
| **Status Codes** (`200`, `301`, `404`, `500`)     | Server responses                                          |
| **REST vs GraphQL**                               | API styles for client-server communication                |
| **Caching** (`Cache-Control`, `ETag`, `CDN`)      | Storing resources for faster loads                        |
| **Content Delivery Networks (CDNs)**              | Global distribution of static assets                      |
| **Preload/Prefetch**                              | Performance hints for critical or future-needed resources |

---

## 🧱 Core Web Development Concepts

| Concept                                  | What It Means                                             |
| ---------------------------------------- | --------------------------------------------------------- |
| **SSR vs CSR vs SSG vs ISR**             | Different ways to render pages in frameworks like Next.js |
| **SPAs vs MPAs**                         | Single-page vs multi-page architectures                   |
| **Routing (Client-side vs Server-side)** | Navigation without full page reload                       |
| **Lazy Loading**                         | Loading parts of the app only when needed                 |
| **Responsive Design**                    | Mobile-first layouts via CSS media queries                |
| **Accessibility (a11y)**                 | Making web usable by people with disabilities             |
| **SEO (Search Engine Optimization)**     | Making your site discoverable and indexable               |
| **FCP, LCP, TTI, CLS**                   | Web performance metrics (Core Web Vitals)                 |

---

## 🔐 Security Concepts

| Concept                               | What It Means                                           |
| ------------------------------------- | ------------------------------------------------------- |
| **XSS (Cross-site Scripting)**        | Inserting malicious JS into the browser                 |
| **CSRF (Cross-site Request Forgery)** | Unauthorized commands from trusted users                |
| **CSP (Content Security Policy)**     | Mitigation strategy for XSS attacks                     |
| **SameSite Cookies**                  | Controls when cookies are sent with cross-site requests |
| **JWT (JSON Web Token)**              | Stateless authentication tokens                         |

---

## 📦 Build & Tooling Concepts

| Concept                          | What It Means                                          |
| -------------------------------- | ------------------------------------------------------ |
| **Bundling**                     | Combine multiple files into one (e.g., Webpack, Vite)  |
| **Transpiling**                  | Convert modern JS (ES6+) to browser-compatible JS      |
| **Minification**                 | Remove whitespace/comments to reduce file size         |
| **Tree Shaking**                 | Remove unused code during bundling                     |
| **Source Maps**                  | Mapping minified code to original source for debugging |
| **Code Splitting**               | Load only needed code, not everything upfront          |
| **Hot Module Replacement (HMR)** | Injecting updated code during dev without full reload  |
| **Environment Variables**        | Runtime config (e.g., `process.env.API_KEY`)           |

---

## 🔧 Browser APIs & APIs You Should Know

| API                      | What It Does                                   |
| ------------------------ | ---------------------------------------------- |
| **Fetch API**            | Modern replacement for `XMLHttpRequest`        |
| **IntersectionObserver** | Detect element visibility (e.g., lazy loading) |
| **MutationObserver**     | Watch DOM changes efficiently                  |
| **Navigator API**        | Access user-agent/device data                  |
| **Geolocation API**      | Access user location                           |
| **Clipboard API**        | Copy/paste data via JS                         |
| **Notifications API**    | Trigger desktop/mobile notifications           |

---

## 🧠 Bonus: DevTools Features You Should Master

| Tool                | Use                                         |
| ------------------- | ------------------------------------------- |
| **Network tab**     | Monitor API requests, caching, latency      |
| **Performance tab** | Profile page render and JS execution        |
| **Lighthouse**      | Audit performance, accessibility, SEO       |
| **Application tab** | View LocalStorage, cookies, service workers |
| **Sources tab**     | Debug JS with breakpoints, view source maps |

---
