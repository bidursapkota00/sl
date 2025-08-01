# Client Side Scripting with JavaScript

## Table of Contents

1. [Introduction to JavaScript](#introduction-to-javascript)
2. [Need of Client Side Scripting Language](#need-of-client-side-scripting-language)
3. [Formatting and Coding Conventions](#formatting-and-coding-conventions)
4. [JavaScript Files](#javascript-files)
5. [Comments](#comments)
6. [Embedding JavaScript in HTML](#embedding-javascript-in-html)
7. [NoScript Tag](#noscript-tag)
8. [Some Important Basics](#some-important-basics)
9. [Operators](#operators)
10. [Control Structures](#control-structures)
11. [Arrays and For Each Loop](#arrays-and-for-each-loop)
12. [Defining and Invoking Functions](#defining-and-invoking-functions)
13. [Objects](#objects)
14. [Built-in Objects](#built-in-objects)
15. [Date Objects](#date-objects)
16. [Interacting With The Browser](#interacting-with-the-browser)
17. [Windows & Frames](#windows--frames)
18. [Document Object Model (DOM)](#document-object-model-dom)
19. [Event Handling](#event-handling)
20. [Forms](#forms)
21. [Cookies](#cookies)
22. [Handling Regular Expressions](#handling-regular-expressions)
23. [Client Side Validations](#client-side-validations)
24. [Old Questions](#old-questions)

---

## Introduction to JavaScript

**Old Question:**

**What is JavaScript? What are the potential platforms where JavaScript can be used?**

**Explain features of JavaScript?**

**Explain types of JavaScript?**

JavaScript is a high-level, interpreted programming language that enables interactive web pages. It's an essential part of web applications alongside HTML and CSS.

### Platforms Where JavaScript Can Be Used

JavaScript has evolved far beyond its web browser origins and can now run on numerous platforms:

**Web Development:**

- Client-side scripting in web browsers
- Server-side development with Node.js
- Progressive Web Applications (PWAs)
- Single Page Applications (SPAs)

**Mobile Development:**

- Cross-platform mobile apps with React Native
- Hybrid apps using frameworks like Cordova or Ionic
- Native mobile development with NativeScript

**Desktop Applications:**

- Cross-platform desktop apps with Electron (like VS Code, Discord, Slack)
- Windows apps with Windows Script Host
- macOS automation with JXA (JavaScript for Automation)

**Server and Backend:**

- Web servers and APIs with Node.js
- Serverless functions on platforms like AWS Lambda, Vercel, Netlify
- Microservices architecture

**Machine Learning**

- TensorFlow.js: The most prominent JavaScript ML library, developed by Google.

  **It allows you to:**

- Run pre-trained models in browsers and Node.js
- Train models directly in JavaScript
- Convert models from Python TensorFlow to JavaScript
- Leverage GPU acceleration through WebGL
- Can run ml on browser, server, mobile apps, desktop apps

**Key features / characteristics:**

- **Dynamic typing:** Variables don't need explicit type declarations
- **Interpreted:** Code is executed directly without compilation
- **Event-driven:** Responds to user interactions like clicks, form submissions
- **Cross-platform:** Code can run on any device with a JavaScript engine. Runs in browsers, servers (Node.js), mobile apps, and desktop applications
- **Regular Expression Support:** Built-in support for pattern matching and text manipulation through regular expressions.
- **Extensive Ecosystem:** Massive library and framework ecosystem through npm, providing solutions for virtually any development need.
- **Asynchronous Programming:** Native support for handling asynchronous operations through callbacks, promises, and async/await syntax.
- **Automatic Memory Management:** Built-in garbage collection handles memory allocation and deallocation automatically.
- **Event-Driven Programming:** Excellent support for handling user interactions and asynchronous events through event listeners and callbacks.

### Different Types of JavaScript

**1. Client-Side JavaScript (Browser JavaScript)**

Runs in web browsers to create interactive user interfaces.
Example:

```js
// Changing webpage content dynamically
document.getElementById("myButton").addEventListener("click", function () {
  document.getElementById("output").innerHTML = "Button clicked!";
});
```

**2. Server-Side JavaScript (Node.js)**

Runs on servers to handle backend operations, databases, and APIs.
Example:

```js
// Simple web server using Node.js
const http = require("http");

const server = http.createServer((req, res) => {
  res.writeHead(200, { "Content-Type": "text/html" });
  res.end("<h1>Hello from Node.js server!</h1>");
});

server.listen(3000, () => {
  console.log("Server running on port 3000");
});
```

---

## Need of Client Side Scripting Language

**Old Question:**
**What is need for client side scripting?**

Client-side scripting allows code to run in the user's browser, providing:

- **Interactivity:** Enhances user experience by making web pages interactive.
- **Validation:** Performs form validation before data is sent to the server.
- **Manipulation:** Allows manipulation of the DOM (Document Object Model) to change content and structure of web pages dynamically.
- **Performance:** Reduces server load by handling tasks locally on the user's device.
- **Asynchronous Communication:** Enables asynchronous data exchange with the server using technologies like AJAX.

```javascript
// Example: Dynamic content without server request
document.getElementById("demo").innerHTML =
  "Content changed without page reload!";
```

## Formatting and Coding Conventions

Good JavaScript follows these conventions:

- Use camelCase for variables and functions
- Use PascalCase for constructors
- Use meaningful names
- Proper indentation and Consistent spacing
- semicolons to separate statements is considered good practice, but they are not always required
- Use curly braces to indicate code blocks
- Use comments to explain your code and improve its readability
- Include error handling in your code to prevent crashes and unexpected behavior. Use try/catch statements to handle errors gracefully.

```javascript
// Good formatting
let userName = "John";
let userAge = 25;

function calculateTotal(price, tax) {
  let total = price + price * tax;
  return total;
}

// Bad formatting (avoid this)
let n = "John";
let a = 25;
function calc(p, t) {
  return p + p * t;
}
```

## JavaScript Files

- **File extension:** JavaScript files typically have a .js file extension.
- **Script tag:** To include a JavaScript file in an HTML document, you can use a `<script>` tag and specify the file's URL in the `src` attribute.
- **Loading order:** JavaScript files are loaded and executed in the order they appear in the HTML document, from top to bottom.
- **External vs. inline scripts:** JavaScript code can be included in an HTML document either as an external file or as an inline script. External scripts are preferred for larger scripts, while inline scripts are used for smaller scripts or scripts that require specific HTML elements.

**script.js**

```javascript
function greetUser(name) {
  return "Hello, " + name + "!";
}

let message = greetUser("Alice");
console.log(message);
```

**HTML file linking to JavaScript**

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="script.js"></script>
  </head>
  <body>
    <!-- HTML content -->
  </body>
</html>
```

### Structure of JavaScript Program

- **Comments:**
  Comments are used to add explanatory notes to your code. They are not executed by the JavaScript interpreter and are often used to provide information about the code's purpose, author, or usage.
- **Variables:**
  Declare variables to store data. JavaScript is loosely typed, so you don't need to specify the data type when declaring variables.
- **Functions:**
  Functions are reusable blocks of code that perform a specific task. They can take parameters and return values
- **Conditional Statements:**
  Use conditional statements to make decisions in your code. The most common conditional statements are if, else if, and else.
- **Loops:**
  Loops allow you to execute a block of code repeatedly. Common types of loops in JavaScript are for, while, and do...while.
- **Event Handling:**
  In web development, JavaScript is often used to handle events triggered by user interactions (e.g., clicking a button, submitting a form). Event handlers are functions that respond to these events.
- **Objects and Classes:**
  JavaScript supports object-oriented programming. You can define objects and classes to represent data and behavior.
- **Error Handling:**
  JavaScript provides mechanisms for handling errors gracefully using try...catch blocks.
- **Modules and Imports (ES6):**
  In modern JavaScript (ES6 and later), you can use modules to organize your code into reusable pieces. You can export and import functions, classes, or variables from one module to another.
- **Execution:**
  Finally, your JavaScript code needs to be executed. In web development, this is often done within HTML documents by including script tags or through external JavaScript files linked to HTML.

### Advantage of external JavaScript Files

- It makes the code more modular and easier to manage.
- It allows the browser to cache the JavaScript file, which can improve website performance.
- It reduces the size of the HTML file, which can improve website loading times.

## Comments

Comments help document code and are ignored during execution.

```javascript
// Single line comment
let x = 5; // End of line comment

/*
Multi-line comment
This spans multiple lines
*/
let y = 10;

/**
 * Documentation comment (JSDoc style)
 * @param {number} a - First number
 * @param {number} b - Second number
 * @returns {number} Sum of a and b
 */
function add(a, b) {
  return a + b;
}
```

## Embedding JavaScript in HTML

**Old Question:**
**What are different way to include JavaScript in HTML document?**

### 1. Inline JavaScript

- You can write JavaScript directly within HTML elements using event attributes:

```html
<button onclick="alert('Hello!')">Click me</button>
<body onload="console.log('Page loaded')"></body>
```

### 2. Internal JavaScript with <script> tags

- Place JavaScript code directly in the HTML document between <script> and </script> tags:

```html
<script>
  function myFunction() {
    console.log("Hello from internal script");
  }
  myFunction();
</script>
```

### 3. External JavaScript files

- Link to separate .js files using the src attribute:

```html
<script src="script.js"></script>
```

## NoScript Tag

Provides fallback content when JavaScript is disabled.

```html
<!DOCTYPE html>
<html>
  <body>
    <script>
      document.write("JavaScript is enabled!");
    </script>

    <noscript>
      <p>
        JavaScript is disabled in your browser. Please enable it for full
        functionality.
      </p>
    </noscript>
  </body>
</html>
```

## Some Important Basics

### Var, let and const

```js
// you can redeclare variable with same name with var
// weird
var myname = "aalu";
console.log(myname);
myname = "pidalu";
console.log(myname);
var myname = "aarko aalu";
console.log(myname);

// you cannot redeclare variable with same name with let
let mysurname = "aalu";
console.log(mysurname);
mysurname = "pidalu";
console.log(mysurname);
//   let mysurname = "aarko aalu"; //  <------------------- error
//   console.log(mysurname);

// var is not scoped within block
// block means within curly braces like of for loops

var gods = ["ram", "laxman", "krishna"];
var weapons = ["bow", "arrow", "sudarsan"];

for (var item of gods) {
  // make it let
  console.log(item);
  for (var item of weapons) {
    // make it let
    //
  }
  console.log(item);
}

const mymiddlename = "aalu";
console.log(mymiddlename);
//   mymiddlename = "pidalu"; //  <----------------- error
//   console.log(mymiddlename);

const myarray = ["apple", "ball"];
console.log(myarray);
myarray.push("cat");
console.log(myarray);
myarray.pop();
console.log(myarray);

const myarray2 = Array(5);
console.log(myarray2);
myarray2[0] = "apple";
console.log(myarray2);
```

### Data Types

**A. Primitive Data Types:**

- **Number**
  Represents numeric values, both integers and floating-point numbers.
- **String**
  Represents text. Strings are enclosed in single (' ') or double (" ") quotes.
- **Boolean**
  Represents true or false values.
- **Undefined**
  Represents a variable that has been declared but not assigned a value.
- **Null**
  Represents the intentional absence of any object or value.
- **Symbol (ES6)**
  Represents a unique and immutable value, often used as object property keys.

**B. Composite Data Types:**

- **Object**
  Represents a collection of key-value pairs, where values can be of any data type, including other objects.
- **Array**
  Represents an ordered list of values, often of the same data type. Arrays are indexed starting from 0.
- **Function**
  Functions are a special type of object in JavaScript that can be invoked to perform a specific task. They can also be assigned to variables and passed as arguments to other functions.

```js
// ////////////////////////////////////
// Primitive Data Types
// ////////////////////////////////////

// Number
let num1 = 42;
let num2 = 3.14;

// String
let greeting = "Hello, World!";

// Boolean
let isJavaScriptFun = true;

// Undefined
// A variable that has been declared but not assigned a value.
let unassigned;
console.log(unassigned);

// Null
// Represents the intentional absence of any object value.
let emptyValue = null;

// Symbol
// Introduced in ES6, it is a unique and immutable value.
let key1 = Symbol("key");
let key2 = Symbol("key");
console.log(key1 == key2);

const email = Symbol("Email");

const employee = {
  name: "Aalu",
  age: 30,
  [email]: "a@b.c",
};

console.log(Object.keys(employee));
console.log(employee.name);
console.log(employee["name"]);
console.log(employee[email]);

for (let key in employee) {
  console.log(employee[key]);
}

console.log(Object.getOwnPropertySymbols(employee));

// ////////////////////////////////////
// Non Primitive Data Types (Object, Array, Functions)
// ///////////////////////////////////

// Object
// Used to store collections of data and more complex entities.
let person = {
  name: "John",
  age: 30,
};
console.log(person);

// Array
// A special type of object used for storing ordered collections.
let arr = [1, 2, 3, 4, 5, "s", 1.2];
console.log(arr);

// Function
// Also an object, represents a block of code designed to perform a particular task.
function add(a, b) {
  return a + b;
}

// Adding a custom property to the function
add.description = "This function adds two parameters.";
add.string = function (a, b) {
  return `${a}${b}`;
};

console.log(add(2, 3));
console.log(add("2", 3));
console.log(add(2, "3"));
console.log(add.description);
console.log(add.string(2, 3));

// Functions as Constructors
// Functions can be used as constructors to create objects
function Person(name, age) {
  this.name = name;
  this.age = age;

  this.greet = function () {
    return `Hi!, I am ${this.name}`;
  };
}

const john = new Person("John", 30);
console.log(john.name);
console.log(john);
console.log(john.greet());

class Person2 {
  name;
  age;

  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }
}

const ram = new Person2("John", 30);
console.log(ram.greet());
```

### Statement, Expression and Keywords

- A statement is a piece of code that performs an action or a task.
- An expression is a piece of code that evaluates to a value.
- Set of reserved words that have special meanings within the language is called keywords.
- A block is a set of statements enclosed within curly braces {}.

```js
// declaration statement
let x;
let y = 5;

// assignment statement
x = 10;
x = y + 2;

// conditional statement
if (x > y) {
  console.log("X is greater than Y");
} else if (x === y) {
  console.log("x is equal to y");
} else {
  console.log("x is less than y");
}

// switch statement
switch (x) {
  case 5:
    console.log("x is 5");
    break;
  case 10:
    console.log("x is 10");
    break;
  default:
    console.log("x is something else");
}

// function declaration statement
// return statement
function greet(name) {
  return "Hello " + name + "!";
}

// loop statement
for (let i = 0; i < 5; i++) {
  console.log(i);
}

let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}

i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);

// Break and Continue Statements
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    // break;
    continue;
  }
  console.log(i);
}

// Expression Statement
let z = x + y;
z = x % 3;
console.log(z);
console.log(greet("ram"));

// ternary expression
let age = 16;
let isAdult = age >= 18 ? "Yes" : "No";
console.log(isAdult);

// Try...Catch Statement
try {
  let result = riskyOperation();
  console.log(result);
} catch (error) {
  console.log("An error occurred", error);
  if (error instanceof ReferenceError) {
    throw new Error("Reference Error");
  }
} finally {
  console.log("This will always run");
}

// Object and Array Initializer Expressions
let person = {
  myfirstName: "John",
  mylastName: "Doe",
  myage: 30,
};

let numbers = [1, 2, 3, 4, 5];

// Property Access Expressions
let firstName = person.myfirstName; // "John"
let lastNumber = numbers[4]; // 5

// Destructuring Expressions
let [first, second] = numbers; // first is 1, second is 2
let { myfirstName, myage } = person; // name is "Bob", age is 25

console.log(first, second);
console.log(myfirstName, myage);
```

## Operators

- Operators are special symbols or keywords used to perform operations on operands.
- Operands can be variables, values, or expressions, and operators determine how these operands are manipulated or compared.

### Arithmetic Operators

```javascript
let a = 10,
  b = 3;

console.log(a + b); // Addition: 13
console.log(a - b); // Subtraction: 7
console.log(a * b); // Multiplication: 30
console.log(a / b); // Division: 3.333...
console.log(a % b); // Modulus: 1
console.log(a ** b); // Exponentiation: 1000
```

### Assignment Operators

```javascript
let x = 5;
x += 3; // x = x + 3 = 8
x -= 2; // x = x - 2 = 6
x *= 4; // x = x * 4 = 24
x /= 3; // x = x / 3 = 8
```

### Comparison Operators

```javascript
let num1 = 5,
  num2 = "5";

console.log(num1 == num2); // true (value comparison)
console.log(num1 === num2); // false (strict comparison)
console.log(num1 != num2); // false
console.log(num1 !== num2); // true
console.log(num1 > 3); // true
console.log(num1 <= 5); // true
```

### Logical Operators

```javascript
let isTrue = true,
  isFalse = false;

console.log(isTrue && isFalse); // AND: false
console.log(isTrue || isFalse); // OR: true
console.log(!isTrue); // NOT: false
```

### typeof Operator

```js
let a = 1;

const type = typeof a;
console.log(type);
console.log(typeof type);
```

### Spread Operator

```js
// spread operator
const originalArray = [1, 2, 3];
const copyarr1 = originalArray;
copyarr1[1] = 5;
console.log(copyarr1, originalArray);

const copyarr2 = [...originalArray];
copyarr2[1] = 7;
console.log(copyarr2, originalArray);

const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const concatenatedArray = [...array1, ...array2];
console.log(concatenatedArray);

const array = [1, 2, 3];
const newArray = [0, ...array, 4];
console.log(newArray);

const person1 = {
  name: "Ram",
  age: 24,
};
const person2 = person1;
person2.address = "Lalitpur";
console.log(person2);
console.log(person1);

const person3 = { ...person1 };
person3.address = "Kathmandu";
console.log(person3);

const person4 = { ...person1, address: "Bhaktapur", isDead: false };
console.log(person4);

const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };
const mergedObject = { ...obj1, ...obj2 };
console.log(mergedObject);

const numbers = [1, 2, 3];
const add1 = (a, b, c) => a + b + c;
console.log(add1(...numbers));

const add2 = (...args) => args[0] + args[1] + args[2];
console.log(add2(1, 2, 3));
console.log(add2(...numbers));

function add3(...args) {
  return arguments[0] + arguments[1] + arguments[2];
  // return args[0] + args[1] + args[2];
}
console.log(add3(1, 2, 3));
console.log(add3(...numbers));

const str = "hello";
const chars = [...str];
console.log(chars); // ['h', 'e', 'l', 'l', 'o']
```

## Control Structures

### If-Else Statement

```javascript
let age = 18;

if (age >= 18) {
  console.log("You can vote!");
} else if (age >= 16) {
  console.log("You can get a driver's license!");
} else {
  console.log("You're too young for both!");
}
```

### Switch Statement

```javascript
let day = 3;
let dayName;

switch (day) {
  case 1:
    dayName = "Monday";
    break;
  case 2:
    dayName = "Tuesday";
    break;
  case 3:
    dayName = "Wednesday";
    break;
  default:
    dayName = "Unknown day";
}

console.log(dayName); // Wednesday
```

### Loops

#### For Loop

```javascript
// Basic for loop
for (let i = 1; i <= 5; i++) {
  console.log("Count: " + i);
}

// For loop with array
let colors = ["red", "green", "blue"];
for (let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}
```

#### While Loop

```javascript
let count = 1;
while (count <= 3) {
  console.log("While loop count: " + count);
  count++;
}
```

#### Do-While Loop

```javascript
let num = 1;
do {
  console.log("Do-while count: " + num);
  num++;
} while (num <= 3);
```

## Arrays and For Each Loop

### Array Creation and Manipulation

```javascript
// Creating arrays
let fruits = ["apple", "banana", "orange"];
let numbers = [1, 2, 3, 4, 5];
let mixed = ["text", 42, true, null];

// Array methods
fruits.push("grape"); // Add to end
fruits.unshift("mango"); // Add to beginning
let removed = fruits.pop(); // Remove from end
fruits.splice(1, 1); // Remove at index 1

console.log(fruits); // ["mango", "banana", "orange"]
console.log("Length: " + fruits.length);
```

### For Each Loop

```javascript
let animals = ["cat", "dog", "bird"];

// forEach method
animals.forEach(function (animal, index) {
  console.log(index + ": " + animal);
});

// Arrow function version
animals.forEach((animal, index) => {
  console.log(`${index}: ${animal}`);
});

// For-in loop
for (let index in animals) {
  console.log(index + ": " + animals[index]);
}

// For-of loop
for (let animal of animals) {
  console.log(animal);
}
```

## Defining and Invoking Functions

### Function Declaration

```javascript
// Function declaration
function greet(name) {
  return "Hello, " + name + "!";
}

// Function call
let message = greet("John");
console.log(message); // Hello, John!
```

### Function Expression

```javascript
// Function expression
let multiply = function (a, b) {
  return a * b;
};

let result = multiply(4, 5);
console.log(result); // 20
```

### Arrow Functions

```javascript
// Arrow function
let add = (a, b) => a + b;
let square = (x) => x * x;

console.log(add(3, 4)); // 7
console.log(square(5)); // 25
```

### Function with Default Parameters

```javascript
function introduce(name = "Guest", age = 0) {
  return `Hi, I'm ${name} and I'm ${age} years old.`;
}

console.log(introduce()); // Hi, I'm Guest and I'm 0 years old.
console.log(introduce("Alice", 25)); // Hi, I'm Alice and I'm 25 years old.
```

### Anonymous Functions

```html
<button onclick="(function(){console.log('button clicked');})();">Click</button>
```

### Normal function vs Arrow function

```js
function normalFunction(a, b) {
  return a + b;
}

// Or as a function expression:
const normalFun = function (a, b) {
  return a + b; // requires return keyword to retrun value
};

const arrowFunction = (a, b) => a + b; // does not require return

// Normal fn has its own 'this' context
// which is dynamically scoped based on how the function is called.
const obj1 = {
  value: 10,
  normalFunction: function () {
    console.log(this.value); // `this` refers to `obj1`
  },
};

obj1.normalFunction(); // logs 10

// Arrow function does not have its own 'this' context
const obj = {
  value: 10,
  arrowFunction: () => {
    console.log(this.value); // `this` refers to the outer scope, not `obj`
  },
};

obj.arrowFunction(); // logs `undefined`

function OuterContext() {
  this.value = 20;

  const obj = {
    value: 10,
    arrowFunction: () => {
      console.log(this.value); // `this` refers to `OuterContext`'s `this`
    },
  };

  obj.arrowFunction(); // Output: 20
}

new OuterContext();

// Normal function have arguments object
// that contains all the arguments passed to the function
function normalFunction() {
  console.log(arguments);
}
normalFunction(1, 2, 3); // logs [1, 2, 3]

// Arrow function does not have arguments objects
const arrowFunction2 = (...args) => {
  console.log(args);
};

arrowFunction2(1, 2, 3); // logs [1, 2, 3]

// Normal function can be used as constructor
function Employee(name) {
  this.name = name;
}

const person = new Employee("Ram");
console.log(person);

// Hoisting
// Normal Function declarations are hoisted, meaning they can be called before they are defined in the code.
sayHello("Alice");
// sayHi("Alice");
// sayHi2("Alice");
function sayHello(name) {
  console.log("Hello, " + name + "!");
}

const sayHi = function (name) {
  console.log("Hello, " + name + "!");
};
sayHi("Alice");

const sayHi2 = (name) => {
  console.log("Hello, " + name + "!");
};
sayHi2("Alice");
```

## Objects

### Class

```js
class Vehicle {
  // Public
  color;

  // "Protected" by convention (underscore prefix)
  _engine;

  // Private (truly private)
  #serialNumber;

  constructor(color, engine) {
    this.color = color;
    this._engine = engine; // "Protected"
    this.#serialNumber = Math.random().toString(36); // Private
  }

  // Protected method by convention
  _startEngine() {
    console.log(`${this._engine} engine starting...`);
  }

  showDetails() {
    console.log(`${this.#serialNumber} car with color ${color} is ready`);
  }
}

class Car extends Vehicle {
  constructor(color, engine, doors) {
    super(color, engine);
    this.doors = doors;
  }

  start() {
    // Can access "protected" properties from parent
    // console.log(`Car with ${this._engine} engine`);

    // Can call "protected" method from parent
    this._startEngine();

    // Cannot access private properties from parent
    // console.log(this.#serialNumber); // Error!

    super.showDetails();
  }
}

// Usage Examples
const car1 = new Car("red", "V6", 4);
car1.start();

// "Protected" properties are still accessible (by convention only)
console.log("Accessing 'protected':", car1._engine); // V6 (works but shouldn't be used)
```

### Different ways to create objects

```js
const person = {
  name: "Ram",
  age: 23,
  address: {
    district: "Lalitpur",
    country: "Nepal",
  },
  kill: function () {
    this.isDead = true;
  },
};
console.log(person);
person.age = 33;
console.log(person.age);
console.log(person["age"]);
person.isAlive = true;
person["isDead"] = false;
console.log(person);
console.log(person.isAlive);
delete person.isAlive;
console.log(person.isAlive);
person.kill();
console.log(person);

function Person(name, age) {
  this.name = name;
  this.age = age;
}
const person2 = new Person("Ram", 50);
person2.isAlive = true;
console.log(person2);

const person3 = new Object({
  name: "aalu",
  surname: "pidalu",
  age: 1,
});

console.log(person3.age);
person3.age = 2;
person3.address = "karkalo";
person3["root"] = "soil";
console.log(person3.age);
console.log(person3);
```

## Built-in Objects

### String Object

```javascript
let str = "hello, world!   ";
let str2 = new String("Hello, world!   ");
let str3 = String("hello, world!   ");
console.log(str);
console.log(str2);
console.log(str3);

console.log(str.length);
console.log(str2.length);
console.log(str2.charAt(1));
console.log(str2.includes("world"));
console.log(str2.includes("world", 7));
console.log(str2.indexOf("world"));
console.log(str2.indexOf("o"));
console.log(str2.lastIndexOf("o"));
console.log(str2.slice(7, 12));
console.log(str2.slice(7, -4));
console.log(str.substring(7, 12));
console.log(str.substring(12, 7)); //if a> b, swaps
console.log(str.substring(7, -1)); // if a > b, swaps   and -ve numbers = 0
console.log(str.split(","));
console.log(str.toUpperCase());
console.log(str);
console.log(str.trim());
console.log(str.trim().length);
console.log(str.replace("world", "javascript"));
console.log(str);
console.log(str.startsWith("hello"));
console.log(str.endsWith(" "));
console.log(str.endsWith("world"));
console.log(str.endsWith("world", 12));

let country = "Nepal";
let city = "Lalitpur";
let address = city.concat(", ", country, "!");
console.log(address);
```

### Number Object

```javascript
let num1 = Number(13);
let num2 = new Number(13);
let num3 = 13;

console.log(num1);
console.log(num2);
console.log(num3);

console.log(Number("42")); // Output: 42
console.log(Number(true)); // Output: 1
console.log(Number(false)); // Output: 0
console.log(Number(null)); // Output: 0
console.log(Number("aalu")); // Output: NaN
console.log(Number(undefined)); // Output: NaN

console.log(Number.MAX_VALUE); // Output: 1.7976931348623157e+308
console.log(Number.MIN_VALUE); // Output: 5e-324
console.log(Number.POSITIVE_INFINITY); // Output: Infinity
console.log(Number.NEGATIVE_INFINITY); // Output: -Infinity
console.log(Number.NaN); // Output: NaN

console.log(Number.isFinite(42)); // Output: true
console.log(Number.isFinite(Infinity)); // Output: false

console.log(Number.isInteger(42)); // Output: true
console.log(Number.isInteger(42.1)); // Output: false

console.log(Number.isNaN(NaN)); // Output: true.   does not work with string and undefined
console.log(Number.isNaN(42)); // Output: false

console.log(Number.parseFloat("42.42")); // Output: 42.42
console.log(Number.parseFloat("42")); // Output: 42

console.log(Number.parseInt("42.42")); // Output: 42
console.log(Number.parseInt("42")); // Output: 42

let num = 123.456;

console.log(num.toFixed(2)); // 123.46
console.log(num.toPrecision(4)); // 123.5
```

### Math Object

```javascript
// Constants
console.log(Math.PI); // 3.141592653589793
console.log(Math.E); // 2.718281828459045

// Common functions
console.log(Math.abs(-5)); // 5
console.log(Math.round(4.7)); // 5
console.log(Math.floor(4.7)); // 4
console.log(Math.ceil(4.2)); // 5
console.log(Math.max(1, 3, 2)); // 3
console.log(Math.min(1, 3, 2)); // 1
console.log(Math.random()); // Random number between 0 and 1
console.log(Math.sqrt(25)); // 5
console.log(Math.pow(2, 3)); // 8
console.log(Math.sign(-5)); // -1
console.log(Math.sign(5)); // 1
```

## Date Objects

```javascript
// Creating date objects
let now = new Date();
let specificDate = new Date(2024, 0, 15); // January 15, 2024
let fromString = new Date("2024-01-15");

console.log(now); // Current date and time

// Getting date components
console.log(now.getFullYear()); // Current year
console.log(now.getMonth()); // Month (0-11)
console.log(now.getDate()); // Day of month
console.log(now.getDay()); // Day of week (0-6)
console.log(now.getHours()); // Hours
console.log(now.getMinutes()); // Minutes
console.log(now.getSeconds()); // Seconds

// Setting date components
now.setFullYear(2025);
now.setMonth(11); // December
now.setDate(25); // Christmas

console.log(now.toDateString()); // Formatted date string
console.log(now.toTimeString()); // Formatted time string
```

## Interacting With The Browser

### Window Object

```javascript
// Window properties
console.log(window.innerWidth); // Browser window width
console.log(window.innerHeight); // Browser window height
console.log(window.location.href); // Current URL

// Window methods
window.alert("This is an alert!");
let userResponse = window.confirm("Do you want to continue?");
let userInput = window.prompt("Enter your name:");

// Navigation
// window.open("https://example.com", "_blank");
// window.close(); // Close current window
// window.location.href = "https://example.com"; // Navigate to URL
```

### Example

```html
<html>
  <head>
    <title>Window Object</title>
  </head>
  <body>
    <h1>Window Object Example</h1>
    <button id="openWindow">Open New Window</button>
    <button id="changeLocation">Change Location</button>
    <div style="height: 200vh"></div>
    <script>
      console.log(
        "Window inner size: " + window.innerWidth + "x" + window.innerHeight
      );

      // Handling button clicks
      document.getElementById("openWindow").addEventListener("click", () => {
        window.open("https://www.apple.com");
      });

      document
        .getElementById("changeLocation")
        .addEventListener("click", () => {
          window.location.href = "https://www.apple.com";
        });

      // Handling window events
      window.addEventListener("resize", () => {
        console.log(
          "Window resized to: " + window.innerWidth + "x" + window.innerHeight
        );
      });

      window.addEventListener("scroll", () => {
        console.log("Window scrolled. Scroll position: " + window.scrollY);
      });

      // Storing a string
      localStorage.setItem("username", "John Doe");

      //   window.localStorage.removeItem("username");
      // Storing an object
      const user = {
        name: "John Doe",
        age: 30,
        email: "johndoe@example.com",
      };
      localStorage.setItem("user", JSON.stringify(user));

      // Retrieving a string
      const username = localStorage.getItem("username");
      console.log(username); // Output: John Doe

      // Retrieving an object
      const userRetrived = JSON.parse(localStorage.getItem("user"));
      console.log(user); // Output: { name: 'John Doe', age: 30, email: 'johndoe@example.com' }
    </script>
  </body>
</html>
```

### Popup Example

**Old Question:**
**Question**

- The alert() method displays a simple message to the user in an alert box.
- The confirm() method displays a confirmation dialog box with two buttons: OK and Cancel.
- The prompt() method displays a dialog box with a text input field where the user can enter data.

```html
<html>
  <head>
    <title>Pop Up</title>
  </head>
  <body>
    <h1>Project 1</h1>
    <button onclick="deleteProject()">Delete Project</button>
    <script>
      function deleteProject() {
        const isConfirmed = confirm("Are you sure to delete?");
        if (isConfirmed) {
          const projectName = prompt("Type Project Name to Verify Deletion");
          if (projectName == "Project 1") {
            document.body.removeChild(document.getElementsByTagName("h1")[0]);
          } else {
            alert("Project Name did not match");
          }
        } else {
          alert("Deleteion Cancelled");
        }
      }
    </script>
  </body>
</html>
```

### Screen Object

```javascript
console.log(screen.width); // Screen width
console.log(screen.height); // Screen height
console.log(screen.availWidth); // Available screen width
console.log(screen.availHeight); // Available screen height
console.log(screen.colorDepth); // Color depth
```

### Navigator Object

```javascript
console.log(navigator.userAgent); // Browser information
console.log(navigator.platform); // Operating system
console.log(navigator.language); // Browser language
console.log(navigator.onLine); // Online status
console.log(navigator.cookieEnabled); // Cookie support
```

## Windows & Frames

### Working with Windows

```javascript
// Open new window
let newWindow = window.open("", "myWindow", "width=400,height=300");
newWindow.document.write("<h1>New Window Content</h1>");

// Focus and blur
// newWindow.focus();
// newWindow.blur();

// Close window
// newWindow.close();
```

### Working with Frames

```html
<!-- HTML with frames -->
<iframe id="myFrame" src="about:blank" width="300" height="200"></iframe>

<script>
  // Access frame content
  let frame = document.getElementById("myFrame");
  frame.onload = function () {
    console.log("Frame loaded");
  };

  // Write to frame
  frame.src = "data:text/html,<h1>Frame Content</h1>";
</script>
```

## Document Object Model (DOM)

### Selecting Elements

**Old Question:**
**Explain different method that are available to access DOM element using id, class, name and selector with suitable example.**

```javascript
// Select by ID
let elementById = document.getElementById("myId");

// Select by class name
// returns HTMLCollection
// does not have forEach builtin
let elementsByClass = document.getElementsByClassName("myClass");

// Select by tag name
// returns HTMLCollection
let elementsByTag = document.getElementsByTagName("p");

// Query selector (CSS selector)
let firstMatch = document.querySelector(".myClass");
// returns NodeList
// has forEach
let allMatches = document.querySelectorAll(".myClass");
```

```html
<html>
  <head>
    <title>Selecting Elements</title>
  </head>
  <body>
    <h1 id="myId">Hello</h1>
    <h1 class="myClass">Hi</h1>
    <h1 class="myClass">Hi</h1>
    <p>Hello</p>
    <p>Hello</p>
    <script>
      let elementById = document.getElementById("myId");
      let elementsByClass = document.getElementsByClassName("myClass");
      let elementsByTag = document.getElementsByTagName("p");
      let firstMatch = document.querySelector(".myClass");
      let allMatches = document.querySelectorAll(".myClass");

      window.onload = () => {
        elementById.style.color = "green";

        // [...elementsByClass].forEach()
        for (let element of elementsByClass) {
          element.style.background = "yellow";
        }

        for (let element of elementsByTag) {
          element.style.background = "pink";
        }

        firstMatch.style.color = "red";

        allMatches.forEach((element) => {
          element.style.fontStyle = "italic";
        });
      };
    </script>
  </body>
</html>
```

### Manipulating Elements

```javascript
// Change content
document.getElementById("demo").innerHTML = "<b>New HTML content</b>";
document.getElementById("demo").textContent = "New text content";

// Change attributes
let image = document.getElementById("myImage");
image.src = "new-image.jpg";
image.alt = "New image description";

// Change styles
let element = document.getElementById("myElement");
element.style.color = "red";
element.style.fontSize = "20px";
element.style.display = "none";

// Add/remove classes
element.classList.add("newClass");
element.classList.remove("oldClass");
element.classList.toggle("toggleClass");
```

### Creating and Removing Elements

```javascript
// Create new element
let newParagraph = document.createElement("p");
newParagraph.textContent = "This is a new paragraph";
newParagraph.className = "highlight";

// Append to document
document.body.appendChild(newParagraph);

// Insert before specific element
let existingElement = document.getElementById("existing");
document.body.insertBefore(newParagraph, existingElement);

// Remove element
let elementToRemove = document.getElementById("remove-me");
elementToRemove.parentNode.removeChild(elementToRemove);

// Modern remove method
// elementToRemove.remove();
```

## Event Handling

**Old Question:**
**What is JavaScript Event?**

A **JavaScript Event** is an action or occurrence that happens in the browser, like:

- A user clicks a button
- A web page loads
- A form is submitted
- A key is pressed

You can write **JavaScript code to "listen" and "respond"** to these events.

## Common Event Types

```javascript
// Click Event
element.addEventListener("click", function () {
  /* code */
});

// Keyboard Events
element.addEventListener("keyup", function (event) {
  /* code */
});
element.addEventListener("keydown", function (event) {
  /* code */
});

// Mouse Events
element.addEventListener("mouseenter", function () {
  /* code */
});
element.addEventListener("mouseleave", function () {
  /* code */
});

// Form Events
form.addEventListener("submit", function (event) {
  /* code */
});
input.addEventListener("change", function () {
  /* code */
});
```

### Inline Event Handlers

```html
<button onclick="alert('Button clicked!')">Click Me</button>
<input type="text" onchange="console.log('Input changed')" />
```

### Event Listeners

```javascript
// Add event listener
document.getElementById("myButton").addEventListener("click", function () {
  alert("Button was clicked!");
});

// Event listener with named function
function handleClick(event) {
  console.log("Button clicked!");
  console.log("Event type:", event.type);
  console.log("Target element:", event.target);
}

document.getElementById("myButton").addEventListener("click", handleClick);

// Multiple event types
let input = document.getElementById("myInput");
input.addEventListener("focus", function () {
  console.log("Input focused");
});
input.addEventListener("blur", function () {
  console.log("Input lost focus");
});
input.addEventListener("keyup", function (e) {
  console.log("Key pressed:", e.key);
});
```

### Event Object

```javascript
document.addEventListener("click", function (event) {
  console.log("Click coordinates:", event.clientX, event.clientY);
  console.log("Target element:", event.target.tagName);

  // Prevent default behavior
  if (event.target.tagName === "A") {
    event.preventDefault();
    console.log("Link click prevented");
  }
});
```

## Forms

### Form Validation and Handling

```html
<form id="myForm">
  <input type="text" id="username" placeholder="Username" required />
  <input type="email" id="email" placeholder="Email" required />
  <input type="password" id="password" placeholder="Password" required />
  <button type="submit">Submit</button>
</form>

<script>
  document
    .getElementById("myForm")
    .addEventListener("submit", function (event) {
      event.preventDefault(); // Prevent form submission

      // Get form values
      let username = document.getElementById("username").value;
      let email = document.getElementById("email").value;
      let password = document.getElementById("password").value;

      // Validation
      if (username.length < 3) {
        alert("Username must be at least 3 characters");
        return;
      }

      if (!email.includes("@")) {
        alert("Please enter a valid email");
        return;
      }

      if (password.length < 6) {
        alert("Password must be at least 6 characters");
        return;
      }

      console.log("Form data:", { username, email, password });
      alert("Form submitted successfully!");
    });
</script>
```

### Form Element Access

```javascript
// Access form elements
let form = document.forms["myForm"]; // or document.getElementById("myForm")
let username = form.elements["username"];
let email = form.elements["email"];

// Get all form data
function getFormData(form) {
  let formData = {};
  for (let i = 0; i < form.elements.length; i++) {
    let element = form.elements[i];
    if (element.name) {
      formData[element.name] = element.value;
    }
  }
  return formData;
}
```

## Cookies

### Creating and Reading Cookies

```javascript
// Set cookie
function setCookie(name, value, days) {
  let expires = "";
  if (days) {
    let date = new Date();
    date.setTime(date.getTime() + days * 24 * 60 * 60 * 1000);
    expires = "; expires=" + date.toUTCString();
  }
  document.cookie = name + "=" + value + expires + "; path=/";
}

// Get cookie
function getCookie(name) {
  let nameEQ = name + "=";
  let cookies = document.cookie.split(";");
  for (let i = 0; i < cookies.length; i++) {
    let cookie = cookies[i];
    while (cookie.charAt(0) === " ") {
      cookie = cookie.substring(1, cookie.length);
    }
    if (cookie.indexOf(nameEQ) === 0) {
      return cookie.substring(nameEQ.length, cookie.length);
    }
  }
  return null;
}

// Delete cookie
function deleteCookie(name) {
  document.cookie = name + "=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";
}

// Example usage
setCookie("username", "john_doe", 7); // Set for 7 days
console.log(getCookie("username")); // john_doe
deleteCookie("username");
```

### Practical Cookie Example

```javascript
// Welcome message using cookies
function showWelcomeMessage() {
  let lastVisit = getCookie("lastVisit");
  let now = new Date();

  if (lastVisit) {
    alert("Welcome back! Your last visit was: " + lastVisit);
  } else {
    alert("Welcome to our website!");
  }

  setCookie("lastVisit", now.toString(), 30);
}

// Call on page load
window.onload = showWelcomeMessage;
```

## Handling Regular Expressions

### Creating Regular Expressions

```javascript
// Literal notation
let regex1 = /pattern/flags;

// Constructor notation
let regex2 = new RegExp("pattern", "flags");

// Common flags:
// g - global (find all matches)
// i - case insensitive
// m - multiline
```

### Pattern Matching

```javascript
let text = "The quick brown fox jumps over the lazy dog";

// Test if pattern exists
let hasQuick = /quick/i.test(text);
console.log(hasQuick); // true

// Find matches
let matches = text.match(/the/gi);
console.log(matches); // ["The", "the"]

// Replace with regex
let newText = text.replace(/the/gi, "a");
console.log(newText); // "a quick brown fox jumps over a lazy dog"

// Split with regex
let words = text.split(/\s+/);
console.log(words); // Array of words
```

### Common Patterns

```javascript
// Email validation
function validateEmail(email) {
  let emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
}

// Phone number validation (US format)
function validatePhone(phone) {
  let phoneRegex = /^\(\d{3}\)\s\d{3}-\d{4}$/;
  return phoneRegex.test(phone);
}

// Password strength (at least 8 chars, 1 uppercase, 1 lowercase, 1 number)
function validatePassword(password) {
  let passwordRegex = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)[a-zA-Z\d]{8,}$/;
  return passwordRegex.test(password);
}

// Extract numbers from string
function extractNumbers(text) {
  return text.match(/\d+/g) || [];
}

// Examples
console.log(validateEmail("user@example.com")); // true
console.log(validatePhone("(123) 456-7890")); // true
console.log(validatePassword("MyPass123")); // true
console.log(extractNumbers("I have 5 apples and 3 oranges")); // ["5", "3"]
```

## Client Side Validations

### Complete Form Validation Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Form Validation</title>
    <style>
      .error {
        color: red;
        font-size: 12px;
      }
      .valid {
        border: 2px solid green;
      }
      .invalid {
        border: 2px solid red;
      }
    </style>
  </head>
  <body>
    <form id="registrationForm">
      <div>
        <label>Full Name:</label>
        <input type="text" id="fullName" required />
        <span class="error" id="nameError"></span>
      </div>

      <div>
        <label>Email:</label>
        <input type="email" id="email" required />
        <span class="error" id="emailError"></span>
      </div>

      <div>
        <label>Phone:</label>
        <input type="tel" id="phone" required />
        <span class="error" id="phoneError"></span>
      </div>

      <div>
        <label>Age:</label>
        <input type="number" id="age" min="18" max="100" required />
        <span class="error" id="ageError"></span>
      </div>

      <div>
        <label>Password:</label>
        <input type="password" id="password" required />
        <span class="error" id="passwordError"></span>
      </div>

      <div>
        <label>Confirm Password:</label>
        <input type="password" id="confirmPassword" required />
        <span class="error" id="confirmPasswordError"></span>
      </div>

      <button type="submit">Register</button>
    </form>

    <script>
      // Validation functions
      function validateName(name) {
        return name.length >= 2 && /^[a-zA-Z\s]+$/.test(name);
      }

      function validateEmail(email) {
        return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
      }

      function validatePhone(phone) {
        return /^\d{10}$/.test(phone.replace(/\D/g, ""));
      }

      function validateAge(age) {
        return age >= 18 && age <= 100;
      }

      function validatePassword(password) {
        return (
          password.length >= 8 &&
          /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)/.test(password)
        );
      }

      // Real-time validation
      document.getElementById("fullName").addEventListener("blur", function () {
        let name = this.value;
        let errorElement = document.getElementById("nameError");

        if (!validateName(name)) {
          this.className = "invalid";
          errorElement.textContent =
            "Name must be at least 2 characters and contain only letters";
        } else {
          this.className = "valid";
          errorElement.textContent = "";
        }
      });

      document.getElementById("email").addEventListener("blur", function () {
        let email = this.value;
        let errorElement = document.getElementById("emailError");

        if (!validateEmail(email)) {
          this.className = "invalid";
          errorElement.textContent = "Please enter a valid email address";
        } else {
          this.className = "valid";
          errorElement.textContent = "";
        }
      });

      document.getElementById("phone").addEventListener("blur", function () {
        let phone = this.value;
        let errorElement = document.getElementById("phoneError");

        if (!validatePhone(phone)) {
          this.className = "invalid";
          errorElement.textContent =
            "Please enter a valid 10-digit phone number";
        } else {
          this.className = "valid";
          errorElement.textContent = "";
        }
      });

      document.getElementById("age").addEventListener("blur", function () {
        let age = parseInt(this.value);
        let errorElement = document.getElementById("ageError");

        if (!validateAge(age)) {
          this.className = "invalid";
          errorElement.textContent = "Age must be between 18 and 100";
        } else {
          this.className = "valid";
          errorElement.textContent = "";
        }
      });

      document.getElementById("password").addEventListener("blur", function () {
        let password = this.value;
        let errorElement = document.getElementById("passwordError");

        if (!validatePassword(password)) {
          this.className = "invalid";
          errorElement.textContent =
            "Password must be 8+ characters with uppercase, lowercase, and number";
        } else {
          this.className = "valid";
          errorElement.textContent = "";
        }
      });

      document
        .getElementById("confirmPassword")
        .addEventListener("blur", function () {
          let password = document.getElementById("password").value;
          let confirmPassword = this.value;
          let errorElement = document.getElementById("confirmPasswordError");

          if (password !== confirmPassword) {
            this.className = "invalid";
            errorElement.textContent = "Passwords do not match";
          } else {
            this.className = "valid";
            errorElement.textContent = "";
          }
        });

      // Form submission validation
      document
        .getElementById("registrationForm")
        .addEventListener("submit", function (event) {
          event.preventDefault();

          let isValid = true;
          let formData = {};

          // Collect and validate all data
          let fullName = document.getElementById("fullName").value;
          let email = document.getElementById("email").value;
          let phone = document.getElementById("phone").value;
          let age = parseInt(document.getElementById("age").value);
          let password = document.getElementById("password").value;
          let confirmPassword =
            document.getElementById("confirmPassword").value;

          // Validate all fields
          if (!validateName(fullName)) {
            isValid = false;
            alert("Please enter a valid name");
            return;
          }

          if (!validateEmail(email)) {
            isValid = false;
            alert("Please enter a valid email");
            return;
          }

          if (!validatePhone(phone)) {
            isValid = false;
            alert("Please enter a valid phone number");
            return;
          }

          if (!validateAge(age)) {
            isValid = false;
            alert("Please enter a valid age (18-100)");
            return;
          }

          if (!validatePassword(password)) {
            isValid = false;
            alert("Please enter a valid password");
            return;
          }

          if (password !== confirmPassword) {
            isValid = false;
            alert("Passwords do not match");
            return;
          }

          if (isValid) {
            formData = { fullName, email, phone, age, password };
            console.log("Form submitted successfully:", formData);
            alert("Registration successful!");

            // Here you would typically send data to server
            // fetch('/register', {
            //     method: 'POST',
            //     headers: {'Content-Type': 'application/json'},
            //     body: JSON.stringify(formData)
            // });
          }
        });
    </script>
  </body>
</html>
```

## Old Questions

### Write a HTML code to design a form with three radio button green, red, blue and black. Write a JavaScript code that will change the background color of the page when user clicks on particular button.

```html
<html>
  <head>
    <title>Background Color Selector</title>
    <style>
      body {
        margin: 0;
        padding: 20px;
        min-height: 100vh;
      }
    </style>
  </head>
  <body>
    <h1>Choose Background Color</h1>
    <form id="form">
      <input type="radio" id="green" name="color" value="green" />
      <label for="green">Green</label>
      <br /><br />
      <input type="radio" id="red" name="color" value="red" />
      <label for="red">Red</label>
      <br /><br />
      <input type="radio" id="blue" name="color" value="blue" />
      <label for="blue">Blue</label>
      <br /><br />
      <input type="radio" id="black" name="color" value="black" />
      <label for="black">Black</label>
    </form>

    <script>
      const radioButtons = document.querySelectorAll('input[name="color"]');

      // Add event listener to each radio button
      radioButtons.forEach((radio) => {
        radio.addEventListener("change", function () {
          if (this.checked) {
            // Change the background color of the body
            document.body.style.backgroundColor = this.value;
          }
        });
      });
    </script>
  </body>
</html>
```

### Write a JavaScript which accept user's first and last name and print them in reverse order with space between them.

```html
<html>
  <head>
    <title>Name Reverser</title>
  </head>
  <body>
    <div class="container">
      <h1>Name Reverser</h1>
      <input type="text" id="firstName" placeholder="Enter your first name" />
      <br /><br />
      <input type="text" id="lastName" placeholder="Enter your last name" />
      <br /><br />
      <button onclick="reverseName()">Reverse Name</button>
      <br /><br />
      <div id="result"></div>
    </div>

    <script>
      function reverseName() {
        var firstName = document.getElementById("firstName").value.trim();
        var lastName = document.getElementById("lastName").value.trim();

        // optional
        if (firstName === "" || lastName === "") {
          alert("Please enter both first and last name!");
          return;
        }

        var reversedName = lastName + " " + firstName;

        var resultDiv = document.getElementById("result");
        resultDiv.innerHTML = "Reversed Name: " + reversedName;
      }

      //   optional
      document.addEventListener("keypress", function (event) {
        if (event.key === "Enter") {
          reverseName();
        }
      });
    </script>
  </body>
</html>
```

### Write program in Js that highlights all words that areover 8 characters long with a red background.

```html
<html>
  <head>
    <title>Word Highlighter</title>
  </head>
  <body>
    <h1>Word Highlighter</h1>
    <p id="paragraph">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Praesentium
      tenetur esse velit expedita dolor mollitia libero explicabo, quam porro
      tempora perferendis qui suscipit tempore temporibus hic voluptatem!
      Eligendi, ad corrupti?
    </p>

    <button onclick="highlightLongWords()">
      Highlight Words Over 8 Characters
    </button>

    <script>
      function highlightLongWords() {
        // Get paragraph text
        const paragraph = document.getElementById("paragraph");
        const text = paragraph.innerText;

        // Split the text into words by space
        const words = text.split(" ");

        // Process each word
        const highlightedText = words
          .map((word) => {
            if (word.length > 8) {
              return `<mark style="background: red">${word}</mark>`;
            }
            return word;
          })
          .join(" ");

        // Display the result
        paragraph.innerHTML = highlightedText;
      }

      // Automatically highlight on page load
      // window.onload = function () {
      //   highlightLongWords();
      // };
    </script>
  </body>
</html>
```
