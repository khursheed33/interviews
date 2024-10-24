# JavaScript Interview Guide 📘

## Core JavaScript Concepts

### 1. Data Types
JavaScript has 8 data types divided into primitive and reference types.
Each type serves a specific purpose and has its own behavior in memory management.

```javascript
// Primitive Types:
let string = "hello";       // Stores text data
let number = 42;           // Stores numbers (both integers and floats)
let boolean = true;        // Stores true/false values
let undefined;            // Variable declared but not assigned
let nullValue = null;     // Intentional absence of value
let symbol = Symbol();    // Unique identifier
let bigInt = 9007199254740991n;  // Large numbers

// Reference Type:
let object = {};         // Stores collections of data and more complex entities
```

### 2. Scope
Scope determines the accessibility of variables in your code.
Understanding scope is crucial for preventing variable leaks and managing data flow.

```javascript
var globalVar = "Accessible everywhere";         // Global scope

function exampleFunction() {
    var functionVar = "Only inside function";    // Function scope
    
    if (true) {
        let blockVar = "Only in this block";     // Block scope
        const alsoBlockScoped = "Also block";    // Block scope
    }
}
```

### 3. Hoisting
Hoisting moves declarations to the top of their scope during execution.
This behavior affects how we should declare and initialize variables.

```javascript
// Variable hoisting
console.log(hoistedVar);    // undefined
var hoistedVar = 5;        // Declaration is hoisted, assignment isn't

// Function hoisting
sayHello();                // Works! Function declarations are fully hoisted
function sayHello() {
    console.log("Hello!");
}
```

### 4. Closures
Closures are functions that remember their outer scope variables.
They're essential for data privacy and maintaining state.

```javascript
function createCounter() {
    let count = 0;                  // Private variable
    return {
        increment: () => ++count,   // Has access to count
        getCount: () => count       // Has access to count
    };
}
```

### 5. this Keyword
'this' refers to the current execution context and changes based on how a function is called.
Its value depends on whether you use regular functions, arrow functions, or methods.

```javascript
const obj = {
    name: "Object",
    // Regular function: 'this' refers to obj
    regularMethod() {
        console.log(this.name);    // "Object"
    },
    // Arrow function: 'this' refers to outer scope
    arrowMethod: () => {
        console.log(this.name);    // undefined
    }
};
```

## ES6+ Features

### 1. Arrow Functions
Arrow functions provide a shorter syntax for function expressions.
They don't bind their own 'this', making them ideal for callbacks.

```javascript
// Traditional vs Arrow
function traditional(a, b) { return a + b; }
const arrow = (a, b) => a + b;    // Shorter syntax

// Arrow with single parameter and block
const square = x => {
    return x * x;                  // Can use blocks when needed
};
```

### 2. Template Literals
Template literals allow embedded expressions and multi-line strings.
They make string interpolation more readable and maintainable.

```javascript
const name = "John";
// String interpolation
const greeting = `Hello, ${name}!`;

// Multi-line string
const multiLine = `
    This is easier
    to read than
    concatenation
`;
```

### 3. Destructuring
Destructuring extracts values from objects or arrays into distinct variables.
It simplifies working with complex data structures and function parameters.

```javascript
// Object destructuring
const person = { name: "John", age: 30 };
const { name, age } = person;     // Extract properties

// Array destructuring
const [first, second] = [1, 2];   // Extract array elements
```

### 4. Spread/Rest Operator
Spread expands elements while rest collects them into an array.
These operators simplify working with arrays and function arguments.

```javascript
// Spread: expand elements
const arr = [1, 2, 3];
const newArr = [...arr, 4];       // [1, 2, 3, 4]

// Rest: collect elements
function sum(...numbers) {        // Collect all arguments
    return numbers.reduce((a, b) => a + b);
}
```

### 5. Classes
Classes provide a cleaner syntax for object-oriented programming.
They simplify inheritance and constructor patterns.

```javascript
class Animal {
    constructor(name) {           // Constructor for initialization
        this.name = name;
    }
    
    speak() {                     // Method definition
        return `${this.name} makes a sound`;
    }
}
```

### 6. Promises & Async/Await
Promises handle asynchronous operations with cleaner syntax than callbacks.
Async/await further simplifies working with promises using synchronous-looking code.

```javascript
// Promise creation and handling
const promise = new Promise((resolve, reject) => {
    // Async operation here
    resolve("Success!");
});

// Async/await usage
async function getData() {
    try {
        const result = await promise;
        return result;
    } catch (error) {
        console.error(error);
    }
}
```

## Advanced Concepts

### 1. Event Loop
The event loop handles asynchronous operations in JavaScript.
It manages execution order of tasks, microtasks, and rendering.

```javascript
console.log('First');              // Synchronous
Promise.resolve().then(() => {     // Microtask
    console.log('Microtask');
});
setTimeout(() => {                 // Macrotask
    console.log('Timeout');
}, 0);
```

### 2. Prototypal Inheritance
Objects inherit properties and methods from other objects through prototypes.
This is JavaScript's fundamental mechanism for code reuse.

```javascript
function Animal(name) {
    this.name = name;
}
Animal.prototype.speak = function() {    // Shared method
    return `${this.name} speaks`;
};

const dog = new Animal("Dog");           // Inherits speak
```

### 3. Memory Management
JavaScript automatically manages memory through garbage collection.
Understanding this helps prevent memory leaks and optimize performance.

```javascript
// Memory leak example
function createNodes() {
    const nodes = [];
    for (let i = 0; i < 10000; i++) {
        nodes.push(new Array(10000));    // Large arrays
    }
    return nodes;                        // Holds reference
}
```

### 4. Design Patterns
Design patterns are reusable solutions to common programming problems.
They provide tested templates for solving issues in software design.

```javascript
// Singleton pattern
const Singleton = (function() {
    let instance;
    return {
        getInstance: function() {
            if (!instance) {
                instance = {};
            }
            return instance;
        }
    };
})();
```

### 5. Web APIs
Browser Web APIs extend JavaScript's capabilities for web development.
They provide interfaces for DOM manipulation, network requests, and more.

```javascript
// Fetch API
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error(error));

// LocalStorage API
localStorage.setItem('key', 'value');
const value = localStorage.getItem('key');
```

### 6. Error Handling
Proper error handling ensures robust and maintainable applications.
Try-catch blocks and error objects help manage runtime errors.

```javascript
try {
    // Risky operation
    throw new Error('Something went wrong');
} catch (error) {
    console.error(error.message);         // Handle error
} finally {
    // Always executes
    console.log('Cleanup');
}
```

### 7. Modules
Modules organize code into reusable, encapsulated pieces.
They help maintain clean code structure and manage dependencies.

```javascript
// math.js
export const add = (a, b) => a + b;      // Named export

// main.js
import { add } from './math.js';         // Named import
console.log(add(2, 3));                  // Use imported function
```


---

# JavaScript Additional Concepts 📘

## 1. Higher-Order Functions
Higher-order functions are functions that take other functions as arguments or return functions as their result. They are fundamental in functional programming.

### Example:

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

function processUserInput(callback) {
    const name = "Alice";
    console.log(callback(name));  // Passes greet function as a callback
}

processUserInput(greet);         // Outputs: "Hello, Alice!"
```

## 2. Functional Programming
Functional programming is a paradigm that treats computation as the evaluation of mathematical functions and avoids changing state or mutable data.

### Key Features:
- **Immutability**: Data cannot be modified after it's created.
- **First-Class Functions**: Functions can be passed as arguments, returned from other functions, and assigned to variables.

### Example:

```javascript
const numbers = [1, 2, 3, 4, 5];

// Using map (higher-order function) to create a new array without modifying the original
const squares = numbers.map(num => num * num);
console.log(squares);  // Outputs: [1, 4, 9, 16, 25]
console.log(numbers);   // Outputs: [1, 2, 3, 4, 5] (original array remains unchanged)
```

## 3. Debouncing and Throttling
Debouncing and throttling are techniques used to optimize performance in situations where a function is called repeatedly, such as during window resizing or scrolling.

### Debouncing
Delays the processing of a function until a certain time has passed since the last time it was invoked.

### Example:

```javascript
function debounce(func, delay) {
    let timeoutId;
    return function(...args) {
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => {
            func.apply(this, args);
        }, delay);
    };
}

const logResize = debounce(() => {
    console.log('Resized window!');
}, 200);

window.addEventListener('resize', logResize);
```

### Throttling
Ensures that a function is only called at most once in a specified time period.

### Example:

```javascript
function throttle(func, limit) {
    let lastFunc;
    let lastRan;

    return function(...args) {
        if (!lastRan) {
            func.apply(this, args);
            lastRan = Date.now();
        } else {
            clearTimeout(lastFunc);
            lastFunc = setTimeout(() => {
                if ((Date.now() - lastRan) >= limit) {
                    func.apply(this, args);
                    lastRan = Date.now();
                }
            }, limit - (Date.now() - lastRan));
        }
    };
}

const logScroll = throttle(() => {
    console.log('Scrolled!');
}, 1000);

window.addEventListener('scroll', logScroll);
```

## 4. Asynchronous Programming: Callbacks vs. Promises vs. Async/Await
JavaScript handles asynchronous operations using callbacks, promises, and async/await. Understanding these concepts helps manage asynchronous code more effectively.

### Callbacks
Functions that are passed as arguments to other functions and are executed after the completion of the outer function.

### Example:

```javascript
function fetchData(callback) {
    setTimeout(() => {
        callback("Data received");
    }, 1000);
}

fetchData(data => {
    console.log(data);  // Outputs: "Data received"
});
```

### Promises
Objects that represent the eventual completion (or failure) of an asynchronous operation and its resulting value.

### Example:

```javascript
const fetchDataPromise = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Data received");
    }, 1000);
});

fetchDataPromise
    .then(data => console.log(data))  // Outputs: "Data received"
    .catch(error => console.error(error));
```

### Async/Await
Syntactic sugar on top of promises that allows asynchronous code to be written in a more synchronous manner.

### Example:

```javascript
async function fetchDataAsync() {
    const data = await fetchDataPromise;  // Waits for the promise to resolve
    console.log(data);                     // Outputs: "Data received"
}

fetchDataAsync();
```

## 5. The Fetch API
The Fetch API provides a modern way to make HTTP requests in the browser. It returns promises and is much cleaner than the older XMLHttpRequest.

### Example:

```javascript
fetch('https://api.example.com/data')
    .then(response => {
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        return response.json();
    })
    .then(data => console.log(data))
    .catch(error => console.error('Fetch error:', error));
```

## 6. Context and Bind
The `bind()` method creates a new function that, when called, has its `this` keyword set to a provided value.

### Example:

```javascript
const person = {
    name: "Alice",
    greet() {
        console.log(`Hello, my name is ${this.name}`);
    }
};

const greetAlice = person.greet.bind(person);
greetAlice();  // Outputs: "Hello, my name is Alice"
```

## 7. SetTimeout vs. SetInterval
Both are used for timing functions, but they have different behaviors.

### `setTimeout`
Executes a function once after a specified delay.

### Example:

```javascript
setTimeout(() => {
    console.log('Executed after 2 seconds');
}, 2000);
```

### `setInterval`
Repeatedly calls a function with a fixed time delay between each call.

### Example:

```javascript
const intervalId = setInterval(() => {
    console.log('Executed every second');
}, 1000);

// Clear the interval after 5 seconds
setTimeout(() => {
    clearInterval(intervalId);
    console.log('Interval cleared');
}, 5000);
```

Certainly! Here’s an expanded README file that includes additional JavaScript topics such as hoisting, currying, and more, along with examples.

---

## 1. Hoisting
Hoisting is JavaScript's behavior of moving declarations to the top of the current scope during the compilation phase. This applies to both variable declarations (with `var`, `let`, and `const`) and function declarations.

### Example:

```javascript
console.log(myVar); // Outputs: undefined (not a ReferenceError)
var myVar = 5;

foo(); // Outputs: "Hello, World!"
function foo() {
    console.log("Hello, World!");
}
```

### Explanation:
- The variable `myVar` is hoisted, but only the declaration is moved, not the assignment. Hence, it logs `undefined`.
- Function declarations are fully hoisted, allowing them to be called before their definition in the code.

## 2. Currying
Currying is a functional programming technique where a function with multiple arguments is transformed into a sequence of functions, each taking a single argument.

### Example:

```javascript
function add(a) {
    return function(b) {
        return a + b;
    };
}

const addFive = add(5); // Returns a function that adds 5
console.log(addFive(3)); // Outputs: 8
console.log(add(10)(2)); // Outputs: 12
```

### Explanation:
- The `add` function is curried, allowing partial application of its parameters.

## 3. Closures
A closure is a function that retains access to its outer lexical scope, even when the function is executed outside that scope.

### Example:

```javascript
function makeCounter() {
    let count = 0;
    return function() {
        count += 1;
        return count;
    };
}

const counter = makeCounter();
console.log(counter()); // Outputs: 1
console.log(counter()); // Outputs: 2
```

### Explanation:
- The inner function retains access to the `count` variable even after `makeCounter` has finished executing.

## 4. The `this` Keyword
The `this` keyword refers to the context in which a function is executed. Its value depends on how a function is called.

### Example:

```javascript
const person = {
    name: "Alice",
    greet() {
        console.log(`Hello, my name is ${this.name}`);
    }
};

person.greet(); // Outputs: "Hello, my name is Alice"

const greetFunction = person.greet;
greetFunction(); // Outputs: "Hello, my name is undefined"
```

### Explanation:
- When called as a method on `person`, `this` refers to `person`.
- When called as a standalone function, `this` refers to the global object (or `undefined` in strict mode).

## 5. The Spread Operator and Rest Parameters
The spread operator (`...`) allows an iterable (like an array) to be expanded into individual elements. Rest parameters allow functions to accept an indefinite number of arguments as an array.

### Spread Operator Example:

```javascript
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combined = [...arr1, ...arr2];
console.log(combined); // Outputs: [1, 2, 3, 4, 5, 6]
```

### Rest Parameters Example:

```javascript
function sum(...numbers) {
    return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3, 4)); // Outputs: 10
```

## 6. Module Pattern
The module pattern is a design pattern used to create private and public encapsulation for variables and functions.

### Example:

```javascript
const counterModule = (function() {
    let count = 0; // Private variable

    return {
        increment: function() {
            count++;
            return count;
        },
        decrement: function() {
            count--;
            return count;
        },
        getCount: function() {
            return count;
        }
    };
})();

console.log(counterModule.increment()); // Outputs: 1
console.log(counterModule.getCount());  // Outputs: 1
console.log(counterModule.decrement()); // Outputs: 0
```

### Explanation:
- The `count` variable is private and can only be modified via the public methods.

## 7. Array Methods: Map, Filter, Reduce
These methods provide powerful ways to manipulate arrays.

### `map()`
Creates a new array by applying a function to each element of the original array.

### Example:

```javascript
const numbers = [1, 2, 3];
const squares = numbers.map(num => num * num);
console.log(squares); // Outputs: [1, 4, 9]
```

### `filter()`
Creates a new array containing elements that satisfy a specified condition.

### Example:

```javascript
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Outputs: [2]
```

### `reduce()`
Executes a reducer function on each element of the array, resulting in a single output value.

### Example:

```javascript
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // Outputs: 6
```

## 8. Promises: Chaining and Error Handling
Promises allow for easier handling of asynchronous operations, and you can chain them for sequential execution.

### Example:

```javascript
const fetchData = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Data received");
    }, 1000);
});

fetchData
    .then(data => {
        console.log(data);  // Outputs: "Data received"
        return "Next data";
    })
    .then(nextData => {
        console.log(nextData); // Outputs: "Next data"
    })
    .catch(error => console.error("Error:", error));
```

## 9. The Fetch API
The Fetch API is a modern interface for making HTTP requests.

### Example:

```javascript
fetch('https://api.example.com/data')
    .then(response => {
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        return response.json();
    })
    .then(data => console.log(data))
    .catch(error => console.error('Fetch error:', error));
```
