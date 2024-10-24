# JavaScript Interview Guide 📘

## Table of Contents
- [Core JavaScript Concepts](#core-javascript-concepts)
- [ES6+ Features](#es6-features)
- [Advanced Topics](#advanced-topics)
- [Common Interview Questions](#common-interview-questions)
- [Design Patterns](#design-patterns)

## Core JavaScript Concepts

### 1. Data Types
JavaScript has 8 data types:
- Primitive Types:
  - String
  - Number
  - Boolean
  - Undefined
  - Null
  - Symbol (ES6)
  - BigInt (ES2020)
- Reference Type:
  - Object

```javascript
// Type checking
typeof "hello"     // "string"
typeof 42          // "number"
typeof true        // "boolean"
typeof undefined   // "undefined"
typeof null        // "object" (this is a known JavaScript quirk)
typeof Symbol()    // "symbol"
typeof {}          // "object"
```

### 2. Scope
JavaScript has three types of scope:
- Global Scope
- Function Scope
- Block Scope (ES6)

```javascript
var globalVar = "I'm global";

function exampleFunction() {
    var functionVar = "I'm function-scoped";
    
    if (true) {
        let blockVar = "I'm block-scoped";
        const alsoBlockScoped = "Me too";
    }
}
```

### 3. Hoisting
Variable and function declarations are moved to the top of their scope during compilation.

```javascript
// What you write
console.log(myVar);  // undefined
var myVar = 5;

// How JavaScript interprets it
var myVar;
console.log(myVar);
myVar = 5;

// Function hoisting
sayHello();  // "Hello!" - works because function declarations are hoisted
function sayHello() {
    console.log("Hello!");
}
```

### 4. Closures
A closure is a function that has access to variables in its outer scope.

```javascript
function createCounter() {
    let count = 0;
    return {
        increment: () => ++count,
        getCount: () => count
    };
}

const counter = createCounter();
counter.increment();  // 1
counter.increment();  // 2
counter.getCount();   // 2
```

### 5. this Keyword
The value of `this` depends on how a function is called.

```javascript
// Regular function
const obj = {
    name: "Object",
    regularFunction: function() {
        console.log(this.name);
    },
    arrowFunction: () => {
        console.log(this.name);
    }
};

obj.regularFunction();  // "Object"
obj.arrowFunction();    // undefined (arrow functions don't bind their own this)
```

## ES6+ Features

### 1. Arrow Functions
```javascript
// Traditional function
function add(a, b) {
    return a + b;
}

// Arrow function
const add = (a, b) => a + b;

// Arrow function with single parameter
const square = x => x * x;

// Arrow function with object return
const createObject = () => ({ key: "value" });
```

### 2. Template Literals
```javascript
const name = "John";
const greeting = `Hello, ${name}!`;

// Multi-line strings
const multiLine = `
    This is
    a multi-line
    string
`;
```

### 3. Destructuring
```javascript
// Object destructuring
const person = { name: "John", age: 30 };
const { name, age } = person;

// Array destructuring
const numbers = [1, 2, 3];
const [first, second] = numbers;

// With default values
const { name: userName = "Anonymous" } = {};
```

### 4. Spread/Rest Operator
```javascript
// Spread operator
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];  // [1, 2, 3, 4, 5]

const obj1 = { foo: "bar" };
const obj2 = { ...obj1, baz: "qux" };  // { foo: "bar", baz: "qux" }

// Rest operator
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
```

### 5. Classes
```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }
    
    speak() {
        console.log(`${this.name} makes a sound`);
    }
}

class Dog extends Animal {
    speak() {
        console.log(`${this.name} barks`);
    }
}
```

### 6. Modules
```javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;

// main.js
import { add, subtract } from './math.js';
// or
import * as mathUtils from './math.js';
```

### 7. Promises & Async/Await
```javascript
// Promise
const fetchData = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve("Data fetched");
        }, 1000);
    });
};

// Using .then()
fetchData()
    .then(data => console.log(data))
    .catch(error => console.error(error));

// Using async/await
async function getData() {
    try {
        const data = await fetchData();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}
```

## Advanced Topics

### 1. Event Loop
```javascript
console.log('Start');

setTimeout(() => {
    console.log('Timeout');
}, 0);

Promise.resolve().then(() => {
    console.log('Promise');
});

console.log('End');

// Output:
// Start
// End
// Promise
// Timeout
```

### 2. Prototypal Inheritance
```javascript
function Animal(name) {
    this.name = name;
}

Animal.prototype.speak = function() {
    console.log(`${this.name} makes a sound`);
};

function Dog(name) {
    Animal.call(this, name);
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;
```

### 3. Generator Functions
```javascript
function* numberGenerator() {
    yield 1;
    yield 2;
    yield 3;
}

const gen = numberGenerator();
console.log(gen.next().value);  // 1
console.log(gen.next().value);  // 2
console.log(gen.next().value);  // 3
```

## Common Interview Questions

### 1. Explain Event Delegation
```javascript
// Instead of:
document.querySelectorAll('button').forEach(button => {
    button.addEventListener('click', handleClick);
});

// Use:
document.addEventListener('click', e => {
    if (e.target.matches('button')) {
        handleClick(e);
    }
});
```

### 2. Implement Debounce
```javascript
function debounce(func, delay) {
    let timeoutId;
    
    return function (...args) {
        clearTimeout(timeoutId);
        
        timeoutId = setTimeout(() => {
            func.apply(this, args);
        }, delay);
    };
}

// Usage
const debouncedSearch = debounce((query) => {
    // Search logic here
}, 300);
```

### 3. Implement Deep Clone
```javascript
function deepClone(obj) {
    if (obj === null || typeof obj !== 'object') {
        return obj;
    }
    
    const clone = Array.isArray(obj) ? [] : {};
    
    for (let key in obj) {
        if (Object.prototype.hasOwnProperty.call(obj, key)) {
            clone[key] = deepClone(obj[key]);
        }
    }
    
    return clone;
}
```

## Design Patterns

### 1. Singleton Pattern
```javascript
const Singleton = (function() {
    let instance;
    
    function createInstance() {
        return {
            method: function() {
                console.log("Method called");
            }
        };
    }
    
    return {
        getInstance: function() {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();
```

### 2. Factory Pattern
```javascript
class Vehicle {
    constructor(type, wheels) {
        this.type = type;
        this.wheels = wheels;
    }
}

class VehicleFactory {
    createVehicle(type) {
        switch(type) {
            case 'car':
                return new Vehicle('car', 4);
            case 'motorcycle':
                return new Vehicle('motorcycle', 2);
            default:
                throw new Error('Vehicle type not supported');
        }
    }
}
```

### 3. Observer Pattern
```javascript
class EventEmitter {
    constructor() {
        this.events = {};
    }
    
    on(event, callback) {
        if (!this.events[event]) {
            this.events[event] = [];
        }
        this.events[event].push(callback);
    }
    
    emit(event, data) {
        if (this.events[event]) {
            this.events[event].forEach(callback => callback(data));
        }
    }
}
```

## Best Practices

1. **Use Strict Mode**
```javascript
'use strict';
// Your code here
```

2. **Avoid Global Variables**
```javascript
// Bad
window.user = { name: "John" };

// Good
const user = { name: "John" };
```

3. **Use Meaningful Names**
```javascript
// Bad
const x = 86400000;

// Good
const MILLISECONDS_IN_A_DAY = 86400000;
```

4. **Handle Errors Properly**
```javascript
async function fetchUser() {
    try {
        const response = await fetch('/api/user');
        return await response.json();
    } catch (error) {
        console.error('Error fetching user:', error);
        throw error;
    }
}
```

## Performance Tips

1. **Use Web Workers for Heavy Computations**
```javascript
// main.js
const worker = new Worker('worker.js');
worker.postMessage({ data: complexData });
worker.onmessage = (e) => console.log(e.data);

// worker.js
self.onmessage = (e) => {
    const result = heavyComputation(e.data);
    self.postMessage(result);
};
```

2. **Optimize DOM Manipulation**
```javascript
// Bad
for (let i = 0; i < 1000; i++) {
    document.body.innerHTML += '<div>' + i + '</div>';
}

// Good
const fragment = document.createDocumentFragment();
for (let i = 0; i < 1000; i++) {
    const div = document.createElement('div');
    div.textContent = i;
    fragment.appendChild(div);
}
document.body.appendChild(fragment);
```
