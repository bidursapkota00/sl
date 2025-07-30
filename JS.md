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
13. [Built-in Objects](#built-in-objects)
14. [Date Objects](#date-objects)
15. [Interacting With The Browser](#interacting-with-the-browser)
16. [Windows & Frames](#windows--frames)
17. [Document Object Model (DOM)](#document-object-model-dom)
18. [Event Handling](#event-handling)
19. [Forms](#forms)
20. [Cookies](#cookies)
21. [Handling Regular Expressions](#handling-regular-expressions)
22. [Client Side Validations](#client-side-validations)

---

## Introduction to JavaScript

JavaScript is a high-level, interpreted programming language that enables interactive web pages. It's an essential part of web applications alongside HTML and CSS.

```javascript
// First JavaScript program
console.log("Hello, World!");
```

## Need of Client Side Scripting Language

Client-side scripting allows code to run in the user's browser, providing:

- Interactive user interfaces
- Form validation without server requests
- Dynamic content updates
- Reduced server load

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
- Proper indentation
- Consistent spacing

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

JavaScript can be stored in external `.js` files for better organization and reusability.

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

### Using Script Tag

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Example</title>
  </head>
  <body>
    <h1 id="heading">Original Text</h1>

    <script>
      // Inline JavaScript
      document.getElementById("heading").innerHTML =
        "Text Changed by JavaScript!";
      alert("Page loaded!");
    </script>
  </body>
</html>
```

### External Script File

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="external-script.js"></script>
  </head>
  <body>
    <script src="another-script.js"></script>
  </body>
</html>
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
// Non Primitive Data Types
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

## Operators

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

## Built-in Objects

### String Object

```javascript
let text = "Hello World";

console.log(text.length); // 11
console.log(text.toUpperCase()); // HELLO WORLD
console.log(text.toLowerCase()); // hello world
console.log(text.substring(0, 5)); // Hello
console.log(text.indexOf("World")); // 6
console.log(text.replace("World", "JavaScript")); // Hello JavaScript
```

### Number Object

```javascript
let num = 123.456;

console.log(num.toFixed(2)); // 123.46
console.log(num.toPrecision(4)); // 123.5
console.log(Number.isInteger(123)); // true
console.log(Number.parseInt("123.45")); // 123
console.log(Number.parseFloat("123.45")); // 123.45
```

### Math Object

```javascript
console.log(Math.PI); // 3.141592653589793
console.log(Math.round(4.7)); // 5
console.log(Math.ceil(4.1)); // 5
console.log(Math.floor(4.9)); // 4
console.log(Math.random()); // Random number between 0 and 1
console.log(Math.max(1, 5, 3)); // 5
console.log(Math.min(1, 5, 3)); // 1
console.log(Math.pow(2, 3)); // 8
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

```javascript
// Select by ID
let elementById = document.getElementById("myId");

// Select by class name
let elementsByClass = document.getElementsByClassName("myClass");

// Select by tag name
let elementsByTag = document.getElementsByTagName("p");

// Query selector (CSS selector)
let firstMatch = document.querySelector(".myClass");
let allMatches = document.querySelectorAll(".myClass");
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
