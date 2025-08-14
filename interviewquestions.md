Here are some **simple JavaScript questions** that are commonly asked in **Node.js interviews**, especially for junior to mid-level roles. These focus on core JavaScript concepts that are essential for working with Node.js:

---

### 🔹 **Basic JavaScript Questions**

1. **What are the different data types in JavaScript?**
2. **What is the difference between `var`, `let`, and `const`?**
3. **What is hoisting in JavaScript?**
4. **What is the difference between `==` and `===`?**
5. **What are arrow functions and how are they different from regular functions?**
6. **What is a closure in JavaScript?**
7. **What is the difference between `null` and `undefined`?**
8. **What is the event loop in JavaScript?**
9. **What is the purpose of `this` keyword?**
10. **What are template literals?**

---

### 🔹 **Node.js-Specific Questions**

1. **What is Node.js and how is it different from JavaScript in the browser?**
2. **What is the use of `require()` in Node.js?**
3. **What is the difference between `require` and `import`?**
4. **What are CommonJS and ES Modules?**
5. **What is the purpose of `package.json`?**
6. **What is the difference between synchronous and asynchronous code in Node.js?**
7. **What are callbacks, promises, and async/await?**
8. **What is the `fs` module used for?**
9. **How does Node.js handle concurrency?**
10. **What is middleware in Express.js?**

---
Absolutely! Here's a detailed breakdown of the **JavaScript and Node.js interview questions**, complete with **answers** and **sample scripts** to help you understand the concepts better:

---

## 🟦 **Basic JavaScript Questions**

### 1. **What are the different data types in JavaScript?**
**Answer:**  
JavaScript has:
- **Primitive types**: `String`, `Number`, `Boolean`, `Null`, `Undefined`, `Symbol`, `BigInt`
- **Non-primitive types**: `Object`, `Array`, `Function`

**Example:**
```javascript
let name = "Kabir";       // String
let age = 35;             // Number
let isManager = true;     // Boolean
let salary = null;        // Null
let department;           // Undefined
let id = Symbol("id");    // Symbol
let bigNum = 12345678901234567890n; // BigInt
let employee = { name, age };       // Object
```

---

### 2. **What is the difference between `var`, `let`, and `const`?**
**Answer:**
- `var` is function-scoped and can be redeclared.
- `let` is block-scoped and cannot be redeclared in the same scope.
- `const` is block-scoped and cannot be reassigned.

**Example:**
```javascript
function testScope() {
  if (true) {
    var x = 10;
    let y = 20;
    const z = 30;
  }
  console.log(x); // 10
  // console.log(y); // Error
  // console.log(z); // Error
}
```

---

### 3. **What is hoisting in JavaScript?**
**Answer:**  
Hoisting moves variable and function declarations to the top of their scope before code execution.

**Example:**
```javascript
console.log(a); // undefined
var a = 5;

hoisted(); // "Hoisted function"
function hoisted() {
  console.log("Hoisted function");
}
```

---

### 4. **What is the difference between `==` and `===`?**
**Answer:**
- `==` compares values with type coercion.
- `===` compares both value and type.

**Example:**
```javascript
console.log(5 == "5");  // true
console.log(5 === "5"); // false
```

---

### 5. **What are arrow functions and how are they different?**
**Answer:**
Arrow functions are concise and do not bind their own `this`.

**Example:**
```javascript
const add = (a, b) => a + b;
console.log(add(2, 3)); // 5
```

---

### 6. **What is a closure in JavaScript?**
**Answer:**
A closure is a function that remembers its outer scope even after the outer function has finished executing.

**Example:**
```javascript
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}
const counter = outer();
counter(); // 1
counter(); // 2
```

---

### 7. **What is the difference between `null` and `undefined`?**
**Answer:**
- `undefined`: variable declared but not assigned.
- `null`: explicitly set to "no value".

**Example:**
```javascript
let a;
let b = null;
console.log(a); // undefined
console.log(b); // null
```

---

### 8. **What is the event loop in JavaScript?**
**Answer:**
The event loop handles asynchronous operations by pushing callbacks to the call stack when the stack is empty.

**Example:**
```javascript
console.log("Start");
setTimeout(() => console.log("Async"), 0);
console.log("End");
// Output: Start, End, Async
```

---

### 9. **What is the purpose of `this` keyword?**
**Answer:**
`this` refers to the object that is executing the current function.

**Example:**
```javascript
const person = {
  name: "Kabir",
  greet() {
    console.log("Hello, " + this.name);
  }
};
person.greet(); // Hello, Kabir
```

---

### 10. **What are template literals?**
**Answer:**
Template literals use backticks and `${}` for interpolation.

**Example:**
```javascript
let name = "Kabir";
console.log(`Hello, ${name}!`); // Hello, Kabir!
```

---

## 🟩 **Node.js-Specific Questions**

### 1. **What is Node.js?**
**Answer:**
Node.js is a runtime that allows JavaScript to run on the server side using the V8 engine.

---

### 2. **What is `require()` used for?**
**Answer:**
`require()` is used to import modules in Node.js.

**Example:**
```javascript
const fs = require('fs');
```

---

### 3. **Difference between `require` and `import`?**
**Answer:**
- `require`: CommonJS, synchronous
- `import`: ES Modules, asynchronous

---

### 4. **What are CommonJS and ES Modules?**
**Answer:**
- **CommonJS**: Uses `require()` and `module.exports`
- **ES Modules**: Uses `import` and `export`

---

### 5. **What is `package.json`?**
**Answer:**
It contains metadata about the project and manages dependencies.

---

### 6. **Synchronous vs Asynchronous code?**
**Answer:**
- **Synchronous**: Blocks execution
- **Asynchronous**: Non-blocking, uses callbacks/promises

**Example:**
```javascript
const fs = require('fs');

// Async
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

---

### 7. **What are callbacks, promises, and async/await?**
**Answer:**
They handle async operations.

**Example:**
```javascript
// Promise
function getData() {
  return new Promise(resolve => setTimeout(() => resolve("Done"), 1000));
}

// Async/Await
async function showData() {
  const result = await getData();
  console.log(result);
}
showData(); // Done
```

---

### 8. **What is the `fs` module?**
**Answer:**
It allows interaction with the file system.

**Example:**
```javascript
const fs = require('fs');
fs.writeFileSync('test.txt', 'Hello Node.js');
```

---

### 9. **How does Node.js handle concurrency?**
**Answer:**
Using a single-threaded event loop and non-blocking I/O.

---

### 10. **What is middleware in Express.js?**
**Answer:**
Middleware functions process requests before they reach the route handler.

**Example:**
```javascript
const express = require('express');
const app = express();

app.use((req, res, next) => {
  console.log('Middleware executed');
  next();
});

app.get('/', (req, res) => res.send('Hello World'));
```

---



Here’s a list of **JavaScript programming questions** you can ask candidates during interviews. These range from basic to intermediate and are designed to test problem-solving, understanding of core concepts, and coding style.

---

## 🟦 **Basic Programming Questions**

1. **Reverse a string**
   - *Write a function to reverse a given string.*
   ```javascript
   function reverseString(str) {
     return str.split('').reverse().join('');
   }
   ```

2. **Check for palindrome**
   - *Determine if a string is a palindrome.*
   ```javascript
   function isPalindrome(str) {
     const reversed = str.split('').reverse().join('');
     return str === reversed;
   }
   ```

3. **Find the largest number in an array**
   ```javascript
   function findMax(arr) {
     return Math.max(...arr);
   }
   ```

4. **FizzBuzz**
   - *Print numbers from 1 to 100. For multiples of 3, print "Fizz", for 5 "Buzz", and for both "FizzBuzz".*
   ```javascript
   for (let i = 1; i <= 100; i++) {
     let output = '';
     if (i % 3 === 0) output += 'Fizz';
     if (i % 5 === 0) output += 'Buzz';
     console.log(output || i);
   }
   ```

5. **Count vowels in a string**
   ```javascript
   function countVowels(str) {
     return str.match(/[aeiou]/gi)?.length || 0;
   }
   ```

---

## 🟩 **Intermediate Programming Questions**

1. **Flatten a nested array**
   ```javascript
   function flattenArray(arr) {
     return arr.flat(Infinity);
   }
   ```

2. **Debounce function**
   - *Implement a debounce function to limit how often a function can fire.*
   ```javascript
   function debounce(fn, delay) {
     let timer;
     return function(...args) {
       clearTimeout(timer);
       timer = setTimeout(() => fn.apply(this, args), delay);
     };
   }
   ```

3. **Deep clone an object**
   ```javascript
   function deepClone(obj) {
     return JSON.parse(JSON.stringify(obj));
   }
   ```

4. **Find duplicates in an array**
   ```javascript
   function findDuplicates(arr) {
     return arr.filter((item, index) => arr.indexOf(item) !== index);
   }
   ```

5. **Implement a simple promise**
   ```javascript
   function asyncTask() {
     return new Promise((resolve, reject) => {
       setTimeout(() => resolve("Task complete"), 1000);
     });
   }

   asyncTask().then(console.log);
   ```

---

## 🟥 **Advanced Programming Questions**

### 1. **Implement a recursive function to calculate factorial**
```javascript
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
```

### 2. **Find the nth Fibonacci number using memoization**
```javascript
function fibonacci(n, memo = {}) {
  if (n <= 1) return n;
  if (memo[n]) return memo[n];
  memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo);
  return memo[n];
}
```

### 3. **Implement a custom `bind` function**
```javascript
Function.prototype.myBind = function(context, ...args) {
  const fn = this;
  return function(...newArgs) {
    return fn.apply(context, [...args, ...newArgs]);
  };
};
```

### 4. **Throttle function**
```javascript
function throttle(fn, limit) {
  let inThrottle;
  return function(...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => inThrottle = false, limit);
    }
  };
}
```

### 5. **Implement a simple event emitter**
```javascript
class EventEmitter {
  constructor() {
    this.events = {};
  }

  on(event, listener) {
    if (!this.events[event]) this.events[event] = [];
    this.events[event].push(listener);
  }

  emit(event, ...args) {
    if (this.events[event]) {
      this.events[event].forEach(listener => listener(...args));
    }
  }

  off(event, listenerToRemove) {
    this.events[event] = this.events[event].filter(listener => listener !== listenerToRemove);
  }
}
```

### 6. **Implement a deep equality check**
```javascript
function deepEqual(a, b) {
  if (a === b) return true;
  if (typeof a !== 'object' || typeof b !== 'object' || a == null || b == null) return false;

  const keysA = Object.keys(a), keysB = Object.keys(b);
  if (keysA.length !== keysB.length) return false;

  for (let key of keysA) {
    if (!keysB.includes(key) || !deepEqual(a[key], b[key])) return false;
  }

  return true;
}
```

### 7. **Implement a promise-based retry mechanism**
```javascript
function retry(fn, retries = 3, delay = 1000) {
  return new Promise((resolve, reject) => {
    function attempt(n) {
      fn()
        .then(resolve)
        .catch(err => {
          if (n === 0) reject(err);
          else setTimeout(() => attempt(n - 1), delay);
        });
    }
    attempt(retries);
  });
}
```

### 8. **LRU Cache Implementation**
```javascript
class LRUCache {
  constructor(limit = 5) {
    this.cache = new Map();
    this.limit = limit;
  }

  get(key) {
    if (!this.cache.has(key)) return -1;
    const value = this.cache.get(key);
    this.cache.delete(key);
    this.cache.set(key, value);
    return value;
  }

  put(key, value) {
    if (this.cache.has(key)) this.cache.delete(key);
    else if (this.cache.size === this.limit) this.cache.delete(this.cache.keys().next().value);
    this.cache.set(key, value);
  }
}
```

---


Great! Let's walk through a **complete example** of error handling using middleware in **Express.js**, with some mock data and a simple route that can trigger an error.

---

## ✅ Scenario

We’ll create a small Express app with:
- A **middleware** for error handling.
- A **route** that simulates a data fetch and throws an error if the data is missing.
- A **mock data object**.

---

## 🧩 Code Example

```javascript
const express = require('express');
const app = express();
const PORT = 3000;

// Mock data
const users = {
  1: { id: 1, name: 'Alice' },
  2: { id: 2, name: 'Bob' }
};

// Route that may throw an error
app.get('/user/:id', (req, res, next) => {
  const userId = req.params.id;
  const user = users[userId];

  if (!user) {
    // Simulate an error
    const error = new Error('User not found');
    error.status = 404;
    return next(error); // Pass error to middleware
  }

  res.json(user);
});

// Error-handling middleware
app.use((err, req, res, next) => {
  console.error('Error:', err.message);
  res.status(err.status || 500).json({
    error: {
      message: err.message || 'Internal Server Error'
    }
  });
});

// Start server
app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
```

---

## 🧪 How It Works

- If you visit `http://localhost:3000/user/1`, you'll get:
  ```json
  { "id": 1, "name": "Alice" }
  ```

- If you visit `http://localhost:3000/user/99`, you'll get:
  ```json
  {
    "error": {
      "message": "User not found"
    }
  }
  ```

---


Great question! In Express.js, the flow of control between middleware and route handlers is managed using the `next()` function. Here's how the app knows when to go to the **error-handling middleware**:

---

## 🔁 Middleware Flow in Express

1. **Normal Middleware or Route Handler**:
   - If everything is fine, you call `next()` to pass control to the next middleware or route.
   - If you call `next(err)` with an error object, Express **skips all remaining non-error middleware** and jumps directly to the **error-handling middleware**.

2. **Error-Handling Middleware**:
   - This is a special middleware with **four parameters**: `(err, req, res, next)`.
   - Express automatically knows to use this middleware when `next(err)` is called.

---

## 🔍 Example Breakdown

Let’s revisit this part of the code:

```javascript
app.get('/user/:id', (req, res, next) => {
  const userId = req.params.id;
  const user = users[userId];

  if (!user) {
    const error = new Error('User not found');
    error.status = 404;
    return next(error); // 🔁 This triggers the error-handling middleware
  }

  res.json(user);
});
```

- If `user` is not found, we create an error and call `next(error)`.
- Express sees that `next()` was called with an error, so it **skips any remaining middleware or routes** and goes straight to:

```javascript
app.use((err, req, res, next) => {
  console.error('Error:', err.message);
  res.status(err.status || 500).json({
    error: {
      message: err.message || 'Internal Server Error'
    }
  });
});
```

---

## 🧠 Summary

- `next()` → continues to next middleware or route.
- `next(err)` → jumps to error-handling middleware.
- Error-handling middleware must have **four parameters** to be recognized by Express.

Here’s how you can use **async/await** in Express.js with error-handling middleware. This is especially useful when you're working with asynchronous operations like database queries or external API calls.

---

## ✅ Complete Example: Async/Await with Error Handling Middleware

```javascript
const express = require('express');
const app = express();
const PORT = 3000;

// Mock async function to simulate data fetching
async function getUserById(id) {
  const users = {
    1: { id: 1, name: 'Alice' },
    2: { id: 2, name: 'Bob' }
  };

  // Simulate delay
  await new Promise(resolve => setTimeout(resolve, 100));

  if (!users[id]) {
    throw new Error('User not found');
  }

  return users[id];
}

// Async route handler
app.get('/user/:id', async (req, res, next) => {
  try {
    const user = await getUserById(req.params.id);
    res.json(user);
  } catch (err) {
    next(err); // Pass error to error-handling middleware
  }
});

// Error-handling middleware
app.use((err, req, res, next) => {
  console.error('Error:', err.message);
  res.status(500).json({
    error: {
      message: err.message || 'Internal Server Error'
    }
  });
});

// Start server
app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
```

---

## 🧠 Key Concepts

- `getUserById` is an **async function** that simulates a database call.
- Inside the route, we use `await getUserById(...)` and wrap it in a `try/catch`.
- If an error occurs, we call `next(err)` to forward it to the error-handling middleware.
- The error-handling middleware catches it and sends a proper response.

---

Would you like to see how to generalize this pattern for multiple routes or integrate it with a real database like MongoDB or PostgreSQL?


