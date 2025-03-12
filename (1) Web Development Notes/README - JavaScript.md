# **Introduction to JavaScript**

## **1. What is JavaScript?**

- **JavaScript** is a programming language used to create dynamic and interactive elements on websites.
- It is primarily used to:
    - Manipulate HTML and CSS.
    - Create interactive web elements (e.g., buttons, forms).
    - Handle events (e.g., clicks, keystrokes).
    - Perform asynchronous tasks (e.g., fetching data from an API).

## **2. Why Use JavaScript?**
 
- **Interactivity**: JavaScript allows you to add interactivity to your websites (e.g., pop-ups, animations, form validation).
- **Control**: It enables the control of the web page's behaviour without needing to reload or interact with the server.
- **Versatility**: JavaScript can be used on both the client-side (in the browser) and the server-side (using Node.js).
- **Extensibility**: It has a rich ecosystem of libraries and frameworks (e.g., React, Angular, Vue.js) that help in building complex applications.

### JavaScript Engine
Each browser uses a unique JavaScript engine that interprets and runs JavaScript code. Below are the engines used by some of the most popular browsers:

| Browser        | JavaScript Engine |
|----------------|-------------------|
| Chrome         | V8                |
| Firefox        | SpiderMonkey      |
| Safari         | JavaScript Core   |
| Microsoft Edge | Chakra            |

---

## **3. JavaScript Syntax**

### Basic Structure of JavaScript Code:

```javascript
// This is a single-line comment

/*
   This is a multi-line comment
   that spans multiple lines
*/

// Declaration of a variable
let x = 5;

// Declaring a function
function greet() {
    console.log("Hello, world!");
}
```

- **Variable Declaration**: `let` and `const` are used to declare variables. `var` is also used but less common in modern JavaScript due to issues with scope.
    - `let`: Used for variables that can be reassigned.
    - `const`: Used for constants (values that cannot be reassigned).
	- **`var`**: The traditional way to declare variables (function-scoped).


---

## **4. Variables and Data Types**

### Variable Declaration:

```javascript
let name = "John";  // String
const age = 30;      // Number
let isActive = true; // Boolean
```


### JavaScript Comparisons

| Operator | Description                                 |
| -------- | ------------------------------------------- |
| `==`     | loose equality (compares value and type)    |
| `===`    | Strict equality (compares value and type)   |
| `!==`    | Strict inequality (compares value and type) |
| `>=`     | Greater than or equal to                    |
| `<=`     | Less than or equal to                       |
| `>`      | Greater than                                |
| `<`      | Less than                                   |

### Comparison Operators

- **Equality:**

- `==` checks for loose equality (performs type coercion).

```javascript

3 == "3"; // true, because the types are coerced.

```

- `===` checks for strict equality (no type coercion).

```javascript

3 === "3"; // false, because the types differ.

```

Examples:
```javascript
3 == "3"     // true (loose equality)
3 === "3"    // false (strict equality)
```
### **JavaScript Logical Operators**

| Operator | Description |
| -------- | ----------- |
| `&&`     | Logical AND |
| ` \|\| ` | Logical OR  |
| `!`      | Logical NOT |
### **Outputting Results Using Logical OR (`||`)**

#### **Shortened Method for FizzBuzz Example**:

```javascript
for (let i = 1; i <= 50; i++) {
    let output = '';
    if (i % 3 === 0) output += 'Fizz';
    if (i % 5 === 0) output += 'Buzz';
    console.log(output || i);
}
```

- **Explanation of `output || i`**:
    - The expression `output || i` is a **logical OR** operation. It checks if `output` is a non-empty string.
    - **If `output` is not empty** (meaning `i` is divisible by 3 or 5), it will print the value of `output` (which will be either `"Fizz"`, `"Buzz"`, or `"FizzBuzz"`).
    - **If `output` is empty** (meaning `i` is neither divisible by 3 nor 5), it will print the value of `i` instead.
    - This allows you to combine checking conditions and outputting values more efficiently in one line. The logical OR (`||`) ensures that `i` is used as a fallback when `output` is empty.

---

##### Why This is Useful:

- **Concise Code**: Instead of having multiple `if-else` statements to handle the different cases, you can create the result string (`output`) and use it directly. This reduces the need for complex branching logic.
- **Fallback Value**: The `||` operator provides a quick way to default to `i` if there’s no "Fizz" or "Buzz" for that number.

---
---
Examples:
```javascript
true && false   // false
true || false   // true
!true           // false
```

### JavaScript Types

JavaScript has different data types, which include both primitive and complex types:

1. **Number**  
   Used for both integers and floating-point numbers.

   Examples:
   ```javascript
   10 + 2    // 12
   10 - 2    // 8
   2 * 2     // 4
   10 / 2    // 5
   10 % 3    // 1 (modulus: remainder of division)
   ```

2. **String**  
   A sequence of characters used to represent text.

   Examples:
   ```javascript
   "Hello" + "world!"    // "Helloworld!"
   "Hello " + "world!"   // "Hello world!"
   'This isn\'t very nice'  // Correct handling of single quote
   10 + "34"    // "1034" (string concatenation)
   10 - "7"     // 3 (implicit type conversion)
   "hello" - "bye"  // NaN (Not a Number, invalid operation)
   ```
   
3. **Boolean**  
   Represents logical entities with two values: `true` or `false`.

   Examples:
   ```javascript
   3 > 2         // true
   5 >= 5        // true
   3 === 3       // true (strict equality)
   3 !== 3       // false (strict inequality)
   
   true + true   // 2 (true is treated as 1)
   false + true  // 1
   "A" > "B"     // false (lexical comparison)
   "a" > "A"     // true (lowercase is greater)
   ```

4. **Undefined**  
   A variable that has been declared but not yet assigned a value.

   Example:
   ```javascript
   var x;
   console.log(x);    // undefined
   ```

5. **Null**  
   Represents an intentional absence of any value.

6. **Symbol** (introduced in ECMAScript 6)  
   A unique and immutable primitive value often used as the key for object properties.

7. **Object**  
   A collection of key-value pairs, where keys are strings or symbols, and values can be of any type.

   Example:
   ```javascript
   var user = {
     name: "John",
     age: 24,
     hobby: "soccer"
   };
   ```

---
### JavaScript Data Types:

|Data Type|Example|Description|
|---|---|---|
|**String**|`"Hello"`|Sequence of characters|
|**Number**|`10`, `3.14`|Numeric values|
|**Boolean**|`true`, `false`|Logical value (true or false)|
|**Array**|`[1, 2, 3]`|Ordered collection of values|
|**Object**|`{name: "John", age: 30}`|Collection of key-value pairs|
|**Null**|`null`|Represents an empty or non-existent value|
|**Undefined**|`undefined`|Represents an uninitialized variable|
### **`undefined` in JavaScript**

In JavaScript, **`undefined`** is a **primitive value** that represents the absence of a value. However, it’s used a little differently than `null` in other languages.

#### **When is a variable `undefined`?**

- **Uninitialized variables**: If you declare a variable but don’t assign a value to it, its value will be `undefined`.
    
    ```javascript
    let x;
    console.log(x); // Outputs: undefined
    ```
    
    In this example, the variable `x` is declared, but it hasn’t been assigned any value yet. So its value is automatically `undefined`.
    
- **Function parameters**: If a function is called with fewer arguments than the function parameters, the missing parameters are automatically assigned `undefined`.
    
    ```javascript
    function greet(name) {
      console.log(name);
    }
    
    greet(); // Outputs: undefined
    ```
    
- **Accessing non-existent object properties**: If you try to access a property that doesn’t exist on an object, JavaScript will return `undefined`.
    
    ```javascript
    const person = { name: "Alice" };
    console.log(person.age); // Outputs: undefined (because "age" is not a property of the object)
    ```
    
- **Explicit assignment**: You can also explicitly assign `undefined` to a variable or object property:
    
    ```javascript
    let x = undefined;
    console.log(x); // Outputs: undefined
    ```
    

---

### **`null` in JavaScript**

On the other hand, **`null`** is another special value, but it is used to indicate the **intentional absence of any object value**. It is often used when you want to explicitly set a variable to "no value" or "empty."

#### **When is a variable `null`?**

- **Explicit assignment**: You would assign `null` to a variable when you want to explicitly indicate that it’s empty or should not reference any object.
    
    ```javascript
    let x = null;
    console.log(x); // Outputs: null
    ```
    
- **Usage**: `null` is commonly used to indicate the absence of an object or a placeholder for an object that may be assigned later.
    

---

### **Why does JavaScript use `undefined`?**

JavaScript's choice of **`undefined`** serves as a way to represent a **variable that exists but has not been assigned any value yet**. In some ways, it can be seen as a built-in indicator that the variable was intentionally **not initialized**, rather than an accidental absence of value like `null` might suggest.

- `undefined` can be a bit confusing because it’s not just the absence of a value (like `null`), but also a default value that JavaScript assigns automatically in certain scenarios (like for uninitialized variables or function parameters).
- `null`, on the other hand, is something you as the programmer deliberately assign to indicate that the variable or object reference should be empty.

---

### **In Conclusion**:

- **`undefined`** is a built-in JavaScript value that typically means a variable or property has been declared but not assigned a value.
- **`null`** is used to explicitly indicate that a variable or object reference is intentionally empty.
- JavaScript's use of `undefined` can seem a bit different from other languages, but it's important to understand the distinction to avoid confusion when you're working with variables, objects, and functions.

If you want to make sure you're handling undefined or null values properly, you can use checks like:

```javascript
if (x === undefined) {
  // Handle undefined
}

if (x === null) {
  // Handle null
}
```
---
## **5. Functions**

### Function Declaration:

#### Example 1:

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(5, 3));  // Outputs: 8
```

#### Example 2:

```javascript
function greet() {
    console.log("Hello, world!");
}
greet();  // Call the function
```

- **Function**: A block of code designed to perform a task or calculate a value.
- **Return**: Returns a value from a function.
- **Parameters**: Variables passed into a function for processing.

---

### Passing an Array to a Function

Arrays are passed just like any other variable. Special array methods (like `map()`) are often used to process them.

#### Example: Passing and Processing an Array

```javascript
function printArray(arr) {
    console.log(arr);
}

let numbers = [1, 2, 3, 4, 5];
printArray(numbers);  // Outputs: [1, 2, 3, 4, 5]
```

#### Example: Using `map()` to Transform an Array

```javascript
function squareArray(arr) {
    return arr.map(item => item ** 2);
}

console.log(squareArray([2, 4, 6]));  // Outputs: [4, 16, 36]
```

- **map()**: Creates a new array by applying the provided function to each element.
- **Note**: Unlike `forEach()`, `map()` returns a new array and leaves the original unchanged.

---

### Passing an Object to a Function

Objects, being complex data types passed by reference, can be handled with special techniques like **object destructuring**.

#### Example: Object Destructuring in Function Parameters

```javascript
function displayUser({ name, age }) {
    console.log(`${name} is ${age} years old.`);
}

const user = { name: "Alice", age: 30, city: "Wonderland" };
displayUser(user);  // Outputs: "Alice is 30 years old."
```

- **Destructuring**: Extracts object properties directly in the parameter list for cleaner code.

---

### Rest Parameters

The rest parameter syntax (`...args`) allows you to pass an indefinite number of arguments as an array.

#### Example: Using Rest Parameters

```javascript
function sumAll(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sumAll(1, 2, 3, 4));  // Outputs: 10
```

- **Rest Parameter**: Gathers all remaining arguments into an array, enabling flexible function inputs.

---

### Function Expression:

```javascript
var greet = function() {
    console.log("Hello, world!");
};
greet();
```

---

### Arrow Functions (ES6+):

```javascript
const multiply = (a, b) => a * b;

console.log(multiply(4, 2));  // Outputs: 8
```

- **Arrow Function**: A shorter syntax for writing functions.

---

These notes now cover the basics of function declarations, passing arrays and objects to functions, and using rest parameters, giving you a solid foundation for handling various data types in JavaScript functions.
## **6. Conditional Statements**

- ### if statement: `if`
  Example:
  ```javascript
  if (age >= 18) {
    console.log("You are an adult.");
  }
  ```

- #### Else Statement: `else`
  Example:
  ```javascript
  if (age >= 18) {
    console.log("You are an adult.");
  } else {
    console.log("You are a minor.");
  }
  ```

- #### Else-if Statement: `else if`
  Example:
  ```javascript
  if (age > 60) {
    console.log("Senior citizen");
  } else if (age >= 18) {
    console.log("Adult");
  } else {
    console.log("Minor");
  }
  ```

- #### **Ternary Operator**: 
- A compact alternative to `if-else`.
  ```javascript
  let message = (age >= 18) ? "Adult" : "Minor";
  ```

- #### **Switch**  
  Example:
  ```javascript
  switch (day) {
    case 1:
      console.log("Monday");
      break;
    case 2:
      console.log("Tuesday");
      break;
    default:
      console.log("Unknown day");
  }
  ```

---
## **7. Loops**

### **For Loop**:

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

- **For Loop**: Repeats a block of code a specified number of times.

### **ForEach Loop**:

#### **What is `forEach`?**

`forEach` is a **method** available for **arrays** in JavaScript. It allows you to loop through every item in the array and do something with each item (like print it to the console, change it, or anything else).

#### Basic Syntax:

```javascript
array.forEach(function(item) {
    // code to run for each item in the array
});
```

- **`array`**: This is the array you want to loop through.
- **`function(item)`**: This is the function that will be run for each element in the array.
    - `item` is the current element of the array in that loop.
#### Simple Example:

Let's say you have an array of fruits:

```javascript
let fruits = ["apple", "banana", "cherry"];
```

Now, you want to print each fruit to the console. Here’s how you do that with `forEach`:

```javascript
fruits.forEach(function(fruit) {
    console.log(fruit);
});
```

#### **How It Works**:

1. **`fruits.forEach`**: This tells JavaScript to loop over the `fruits` array.
2. **`function(fruit)`**: For each element in the array, this function will run. It takes the current element as a parameter (which we call `fruit` here).
3. **`console.log(fruit)`**: For every fruit in the array, it prints that fruit to the console.

#### Output:

```
apple
banana
cherry
```

Each fruit is printed on a new line.

---
> A `foreach` loop doesn't always have to have a function, you could just use the item

```javascript
array.forEach(item => {
    // code to run for each item in the array
});
```

This is using an **arrow function** (`item => { console.log(item); }`), which is shorthand for defining a function. It's not required to use an arrow function; you could also use a regular function like this:

```javascript
let array = [1, 2, 3, 4, 5];
array.forEach(function(item) {
    console.log(item);
});
```

Or even pass in a named function:

```javascript
function logItem(item) {
    console.log(item);
}

let array = [1, 2, 3, 4, 5];
array.forEach(logItem);
```

In all cases, you're still just passing a function to `.forEach()`, but the syntax differs based on whether you're using an arrow function, a traditional function expression, or a named function.

So, to clarify: A `.forEach()` loop doesn't **require** an arrow function specifically, but rather any type of function (like a regular function or an anonymous function) can be used. Arrow functions are just a common, more concise choice!

``` JavaScript
let array = [1, 2, 3, 4, 5];

array.forEach(item => {     
	console.log(item); 
});

```

Let's go further into it!

#### **Concise `forEach` with Arrow Function (One-liner)**:

You can also write the `forEach` loop in a concise way using **arrow functions**.

```javascript
let numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => console.log(num * 2));  // Multiply each number by 2
```

### Key Points About `forEach`:

- **No Index**: You don't need to manage the index (e.g., `i` in the `for` loop). The `forEach` method automatically takes care of that.
- **Cannot Break**: One limitation of `forEach` is that you cannot break out of it (i.e., stop the loop early), unlike the `for` loop where you can use `break` to exit.

---

#### Example with a Simple Explanation:

Let’s take this example:

```javascript
let numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(number) {
    console.log(number * 2);  // Multiply each number by 2
});
```

- The array `numbers` contains `[1, 2, 3, 4, 5]`.
- The function `function(number)` gets each element in the array one by one. So, `number` will be `1`, then `2`, then `3`, etc.
- `console.log(number * 2)` prints the number multiplied by 2.

#### Output:

```
2
4
6
8
10
```

---

#### **Using `if` with `forEach` on One Line:**

You can also combine `if` statements with `forEach` in a concise one-liner using the `&&` operator. Here's an example where we print only the even numbers:

```javascript
let numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => num % 2 === 0 && console.log(num));
```

In this case, the `console.log(num)` will only run for numbers that are even (i.e., when `num % 2 === 0` is true).

#### Output:

```
2
4
```

---

#### **Using `if/else` with `forEach` on One Line:**

If you want both `if` and `else` conditions in one line, you can use the **ternary operator**.

```javascript
let numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => num % 2 === 0 ? console.log(num + " is even") : console.log(num + " is odd"));
```

This will check if each number is even or odd and print the result accordingly.

#### Output:

```
1 is odd
2 is even
3 is odd
4 is even
5 is odd
```

---

#### Key Differences Between `for` and `forEach`:

- **`for` Loop**:
    - It gives you more control over the iteration process (e.g., you can modify the index or break the loop early).
    - You can loop through any iterable (arrays, strings, etc.) and even use complex conditions.
- **`forEach`**:
    - It's more concise and expressive when you just want to iterate over the entire array.
    - You cannot use `break` or `continue` inside a `forEach` loop to stop or skip iterations (it will always go through every element).

---

### **While Loop**:

```javascript
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}
```

- **While Loop**: Repeats as long as the condition is `true`.

---

## **8. Arrays**

### Array Definition:

```javascript
let fruits = ["apple", "banana", "cherry"];
```

- **Array**: A collection of items (strings, numbers, etc.) stored in a single variable.
### JavaScript Array Methods

#### Commonly Used Array Methods
| Method      | Description                                                                       |
| ----------- | --------------------------------------------------------------------------------- |
| `push()`    | Adds new elements to the end of an array.                                         |
| `pop()`     | Removes the last element of an array, and returns that element.                   |
| `shift()`   | Removes the first element of an array, and returns that element.                  |
| `unshift()` | Adds new elements to the beginning of an array.                                   |
| `concat()`  | Joins two or more arrays, and returns a copy of the joined arrays.                |
| `slice()`   | Selects a part of an array, and returns the new array.                            |
| `splice()`  | Adds/Removes elements from an array.                                              |
| `indexOf()` | Search the array for an element and returns its position.                         |
| `forEach()` | Calls a function for each array element.                                          |
| `map()`     | Creates a new array with the result of calling a function for each array element. |
#### Complete List of Array Methods

| Method          | Description                                                                 |
| --------------- | --------------------------------------------------------------------------- |
| `concat()`      | Joins two or more arrays, and returns a copy of the joined arrays.          |
| `copyWithin()`  | Copies array elements within the array, to and from specified positions.    |
| `entries()`     | Returns a key/value pair Array Iteration Object.                            |
| `every()`       | Checks if every element in an array passes a test.                          |
| `fill()`        | Fills the elements in an array with a static value.                         |
| `filter()`      | Creates a new array with every element that passes a test.                  |
| `find()`        | Returns the value of the first element that passes a test.                  |
| `findIndex()`   | Returns the index of the first element that passes a test.                  |
| `forEach()`     | Calls a function for each array element.                                    |
| `from()`        | Creates an array from an object.                                            |
| `includes()`    | Check if an array contains the specified element.                           |
| `indexOf()`     | Search the array for an element and returns its position.                   |
| `isArray()`     | Checks whether an object is an array.                                       |
| `join()`        | Joins all elements into a string, and returns the result.                   |
| `keys()`        | Returns a Array Iteration Object, containing the keys.                      |
| `lastIndexOf()` | Searches the array for an element, starting at the end.                     |
| `map()`         | Creates a new array with the result of calling a function for each element. |
| `pop()`         | Removes the last element and returns that element.                          |
| `push()`        | Adds new elements to the end of an array.                                   |
| `reduce()`      | Reduce the values to a single value (going left-to-right).                  |
| `reduceRight()` | Reduce the values to a single value (going right-to-left).                  |
| `reverse()`     | Reverses the order of the elements in an array.                             |
| `shift()`       | Removes the first element and returns that element.                         |
| `slice()`       | Selects a part of an array and returns the new array.                       |
| `some()`        | Checks if any of the elements pass a test.                                  |
| `sort()`        | Sorts the elements of an array.                                             |
| `splice()`      | Adds/Removes elements from an array.                                        |
| `toString()`    | Converts an array to a string, and returns the result.                      |
| `unshift()`     | Adds new elements to the beginning of an array.                             |
| `valueOf()`     | Returns the primitive value of an array.                                    |
#### Example
```javascript
fruits.push("orange");  // Adds "orange" to the end
fruits.pop();           // Removes the last item
fruits.shift();         // Removes the first item
fruits.unshift("kiwi"); // Adds "kiwi" to the start
```

---

## **9. Objects**

### Object Definition:

```javascript
let person = {
    name: "John",
    age: 30,
    greet: function() {
        console.log("Hello " + this.name);
    }
};

person.greet();  // Outputs: Hello John
```

- **Object**: A collection of key-value pairs. Keys are strings (properties), and values can be any data type (e.g., strings, numbers, functions).

### Creating and Accessing Objects

**Example:**

```js
// Creating an object
const person = {
  firstName: "Alice",
  lastName: "Smith",
  age: 28,
  greet: function() {
    return `Hello, my name is ${this.firstName} ${this.lastName}.`;
  }
};

// Accessing properties
console.log(person.firstName);      // Dot notation
console.log(person["lastName"]);      // Bracket notation

// Calling a method
console.log(person.greet());
```

### **Key Concepts:**

- **Properties:** Variables stored inside an object.
- **Methods:** Functions associated with an object.
- **`this` keyword:** References the current object, useful inside methods to access properties and values.

### **Understanding `this` in Objects**

When you're inside an object method, the `this` keyword refers to the object itself. To access properties or values of the object, you must use `this`.

- **Without `this`**: If you access a variable by name directly in an object's method, JavaScript will first check the local scope and then the global scope. This may lead to referencing global variables rather than object properties.
    
- **With `this`**: When you use `this.propertyName`, you're explicitly referring to the property of the object itself, avoiding any ambiguity with variables in the outer scope.
    

**Example Using `this`:**

```javascript
let firstName = "John";  // global variable

let person = {
  firstName: "Alice",  // object property
  greet: function() {
    console.log(this.firstName);  // Correctly refers to "Alice" (object property)
  }
};

person.greet();  // Output: "Alice"
```

### Dot VS Bracket Notation

Both **dot notation** and **bracket notation** are common ways to access properties of an object in JavaScript, but they are used in different scenarios. Here's a breakdown:

#### 1. **Dot notation** (e.g., `person.firstName`)

- **More common**: Dot notation is generally more frequently used because it's simpler and more readable.
- **Restrictions**: It can only be used when the property name is a valid identifier (no spaces, no special characters, etc.), and the property name must be known in advance (i.e., it must be a fixed string).
- **Example**:
    
    ```javascript
    console.log(person.firstName);  // Works if "firstName" is a valid property name
    ```
    

#### 2. **Bracket notation** (e.g., `person["lastName"]`)

- **Less common**: Bracket notation is used less often, but it's still essential in certain situations.
- **Flexibility**: It allows the use of dynamic property names (i.e., you can use variables, strings with spaces, or special characters as keys).
- **Example**:
    
    ```javascript
    console.log(person["lastName"]);  // Works with any property name, even with spaces or special characters
    ```
    

### When to use each:

- **Dot notation** is more common for most standard use cases where property names are valid identifiers (e.g., no spaces, no special characters).
- **Bracket notation** is used in these cases:
    - When property names are dynamic or stored in a variable.
    - When property names have spaces or special characters that aren't allowed in dot notation.
    - When the property name is not a valid identifier (e.g., `person["1stName"]` or `person["last-name"]`).

#### Example of a dynamic key:

```javascript
let key = "firstName";
console.log(person[key]);  // Using bracket notation to access property dynamically
```

### Recap: **Scope and the `this` Keyword**

- When accessing properties of an object within a method, use **`this.propertyName`** to ensure you're referring to the object's properties, even if there are variables with the same name elsewhere in the scope.
- **Without `this`**, JavaScript will first check the local scope and then the global scope, which might lead to accessing the wrong variable if they share the same name.

This should help clarify the use of `this`, dot notation, and bracket notation within your notes!
## **10. Events and DOM Manipulation**
### (10.0) JavaScript Basics Recap:

Before diving into objects and functions as values, let’s quickly review the basic data types:

1. **Primitive Types**:
    
    - **String**: e.g., `"Hello"`
    - **Number**: e.g., `123`
    - **Boolean**: e.g., `true`, `false`
    - **null**: special value representing "no value"
    - **undefined**: represents an uninitialized variable
    - **Symbol**: used to create unique identifiers
    - **BigInt**: large integers (e.g., `1234567890123456789012345678901234567890n`)
2. **Complex Types**:
    
    - **Object**: a collection of key-value pairs
    - **Array**: a special kind of object used for ordered data

Now let’s focus on **functions** and **objects**.

---

### (10.0.1) Functions as Objects in JavaScript

In JavaScript, functions are **first-class objects**. This means:

- Functions can be assigned to variables.
- Functions can be passed as arguments to other functions.
- Functions can be returned from other functions.
- Functions can be assigned as values to object properties.

This is where you see functions being stored as values in objects.

---

### (10.0.2) Key Concepts: Functions as Values in Objects

#### 1. **Assigning a function to an object property**

You can create an object and assign a function as one of its properties (values). Here's an example:

```javascript
const myObject = {
  name: "John",
  greet: function() {
    console.log("Hello, " + this.name);
  }
};

myObject.greet(); // Outputs: "Hello, John"
```

In this example:

- `greet` is a function assigned as a value to the key `greet` in the object `myObject`.
- You can call `myObject.greet()` to execute the function.

#### 2. **Using arrow functions as values in objects**

You can also use **arrow functions** as values in objects:

```javascript
const person = {
  name: "Alice",
  greet: () => {
    console.log("Hi, " + this.name); // "this" will not refer to person in an arrow function!
  }
};

person.greet(); // Outputs: "Hi, undefined" (because `this` behaves differently in arrow functions)
```

- Note: **Arrow functions** do **not** bind their own `this` context, which can sometimes cause unexpected behavior. It’s better to use regular functions if you want to refer to the object’s properties using `this`.

#### 3. **Functions as values for any key**

You can store **functions** under any key, not just `greet`, and they can be used like any other property of an object:

```javascript
const operations = {
  add: function(a, b) {
    return a + b;
  },
  multiply: function(a, b) {
    return a * b;
  }
};

console.log(operations.add(2, 3)); // Outputs: 5
console.log(operations.multiply(2, 3)); // Outputs: 6
```

#### 4. **Functions can return other functions**

A function can also return another function, and you can assign the returned function as an object property.

```javascript
function createGreeting(name) {
  return function() {
    console.log("Hello, " + name);
  };
}

const greetJohn = createGreeting("John");
greetJohn(); // Outputs: "Hello, John"
```

Here, `createGreeting` is a function that returns another function, and that returned function is stored in `greetJohn`. This is a useful pattern called **closures**.

---

### (10.0.3) Limits and Flexibility of JavaScript Objects

JavaScript objects are very flexible and can hold **any data type** as values, including **functions**. Here are some key things to keep in mind:

1. **Objects can hold any data type**:
    
    - You can store strings, numbers, arrays, other objects, and functions inside an object.
2. **No strict type constraints**:
    
    - JavaScript does not enforce type constraints on the values in objects. So, you could mix numbers, strings, and functions in the same object, like this:
    
    ```javascript
    const mixedObject = {
      name: "Alice",
      age: 30,
      greet: function() {
        console.log("Hello, " + this.name);
      },
      favoriteNumbers: [1, 2, 3]
    };
    ```
    
3. **Objects can be dynamic**:
    
    - You can add or remove properties (keys) from an object at any time:
    
    ```javascript
    const person = {
      name: "Bob"
    };
    
    // Adding a new property
    person.age = 25;
    
    // Removing a property
    delete person.name;
    
    console.log(person); // { age: 25 }
    ```
    
4. **Methods in objects**:
    
    - You can define **methods** (functions) within an object, and these functions can reference the object properties using `this`. Just remember that `this` can behave differently in certain cases (like arrow functions).
5. **Objects can be used to store functions as a kind of "action" map**:
    
    - For example, imagine you want to execute different actions based on a type of input. You could store functions in an object and call the appropriate one based on the input.

---

### Summary of Notes

- Functions are **first-class citizens** in JavaScript, meaning they can be treated as objects.
- You can store functions as **values in objects**, just like you can with strings, numbers, arrays, or other objects.
- Functions can be **assigned** to keys in objects.
- Functions can also be **returned** by other functions.
- **Arrow functions** may behave differently than regular functions because they don’t bind their own `this` context.
- JavaScript objects are **flexible** and allow for dynamic changes (you can add, modify, or delete properties).
- There's no hard limit on the types of values you can store in an object, and you can mix and match different data types (including functions).
---
### (10.1) Event Listener:

```javascript
let button = document.getElementById("myButton");
button.addEventListener("click", function() {
    alert("Button clicked!");
});
```

- **Event Listener**: A function that runs in response to an event (e.g., a button click).

### (10.1.1) Changing Content:

```javascript
document.getElementById("myDiv").innerHTML = "Hello, World!";
```

- **DOM Manipulation**: Modifying the content or style of HTML elements through JavaScript.

### (10.1.2) JavaScript Popup Boxes

JavaScript provides three types of popup boxes:

- **`alert()`**: Displays an alert box with a message.
  ```javascript
  alert("This is an alert!");
  ```

- **`prompt()`**: Displays a dialog box that prompts the user for input.
  ```javascript
  let name = prompt("What is your name?");
  ```

### (10.1.3) DRY Principle
- **Do Not Repeat Yourself (DRY)**: Avoid repetitive code by using functions, loops, or variables where possible to make your code more efficient and maintainable.

Example:
```javascript
function greetUser(name) {
  console.log("Hello, " + name + "!");
}
greetUser("John");
greetUser("Sarah");
```

### (10.2) DOM Manipulation

When a web page is loaded, the browser creates a Document Object Model (DOM) of the page. The DOM represents the structure of the document as a tree of nodes, allowing developers to interact with and manipulate the elements, styles, and content of the web document.

### (10.2.1) Basic Methods

- **`document.write()`**: 
  - Used to write a string of text to the document stream opened by `document.open()`. It can be useful for simple demonstrations but is generally not recommended for production code because it can overwrite the entire document if called after the document has fully loaded.
  ```javascript
  document.write("Hello, World!");
  ```

- **`window.alert()`**: 
  - Displays an alert dialog with a specified message and an OK button. This method can be useful for debugging or informing users but can disrupt the user experience if overused.
  ```javascript
  window.alert("This is an alert message!");
  ```
---
### (10.2.2) **Modifying Content:** InnerHTML Vs textContent
In JavaScript, both `innerHTML` and `textContent` are used to access or modify the content of an HTML element, but they behave differently in how they handle content and interpret it. Here’s a comparison of the two:

#### 1. **innerHTML**

- **Purpose**: Used to get or set the HTML markup (including HTML tags) inside an element.
- **Usage**: When you retrieve `innerHTML`, it returns the content of the element as a string of HTML, including any child elements or HTML tags.
- **Modifying Content**: You can also use it to set new HTML content within the element, and it will interpret the string as HTML (e.g., rendering tags).
- **Security Consideration**: Be cautious when using `innerHTML` with untrusted input as it may introduce **Cross-Site Scripting (XSS)** vulnerabilities.

**Example:**

```html
<div id="example">
  <p>Hello <strong>World</strong></p>
</div>

<script>
  let element = document.getElementById('example');
  console.log(element.innerHTML);  // Outputs: <p>Hello <strong>World</strong></p>
  element.innerHTML = '<span>New Content</span>';  // Adds new HTML content
</script>
```

#### 2. **textContent**

- **Purpose**: Used to get or set the **text** content of an element, excluding any HTML tags.
- **Usage**: When you retrieve `textContent`, it returns the plain text inside the element, without any HTML tags. If you set `textContent`, it **replaces** the content with the plain text, and any existing HTML tags inside the element will be removed.
- **Modifying Content**: When setting `textContent`, any HTML tags inside the element will be removed (no HTML interpretation).
- **Security Consideration**: Safer for handling user input since it does not interpret HTML and is not prone to XSS vulnerabilities.

**Example:**

```html
<div id="example">
  <p>Hello <strong>World</strong></p>
</div>

<script>
  let element = document.getElementById('example');
  console.log(element.textContent);  // Outputs: Hello World
  element.textContent = 'New Text Content';  // Replaces with plain text
</script>
```

#### Key Differences:

|Feature|`innerHTML`|`textContent`|
|---|---|---|
|Content Type|Returns HTML (including tags)|Returns plain text (no HTML tags)|
|Modifying Content|Sets HTML content (interprets HTML)|Sets plain text (no HTML interpretation)|
|Performance|Slower (due to HTML parsing and rendering)|Faster (since no HTML parsing is involved)|
|Security|Vulnerable to XSS (if not handled properly)|Safer, no HTML execution risks|

#### Use Cases:

- **Use `innerHTML`**: When you need to include HTML tags or elements (like `<strong>`, `<a>`, etc.) inside an element.
- **Use `textContent`**: When you want to get or set just the text without worrying about HTML tags, or when handling user input where security is a concern.

---
### (10.2.4) DOM Selectors

DOM selectors are essential for accessing and manipulating HTML elements within the DOM. The following table lists common selectors and their descriptions:
#### Selecting Elements

|Method|Description|
|---|---|
|`getElementById`|Selects a single element by its ID.|
|`getElementsByClassName`|Selects all elements with a given class.|
|`querySelector`|Selects the first element that matches a CSS selector.|
|`querySelectorAll`|Selects all elements matching a CSS selector.|
##### Examples:

- **`getElementById`**
    
    ```javascript
    document.getElementById('header');
    ```
    
    _(Selects the element with the ID "header")_
    
- **`getElementsByClassName`**
    
    ```javascript
    document.getElementsByClassName('button')[0];
    ```
    
    _(Selects all elements with the class "button")_
    
- **`querySelector`**
    
    ```javascript
    document.querySelector('.main-header');
    ```
    
    _(Selects the first element with the class "main-header")_
    
- **`querySelectorAll`**
    
    ```javascript
    document.querySelectorAll('p');
    ```
    
    _(Selects all `<p>` elements on the page)_

#### (10.2.4.1) **Things To Note When Working with `getElementsByClassName`** 
##### **IDs**:

- **IDs are unique**. There can only be **one element** with a specific ID in an entire HTML document. This is why when you use `getElementById`, it directly returns that **single element** with that ID.
- Since IDs are unique, you don’t need to worry about indexing or choosing a specific element from a collection.

For example:

```html
<p id="uniqueText">Hello World</p>
```

You can access it like this:

```javascript
const paragraph = document.getElementById('uniqueText');
```

##### **Classes**:

- **Classes can be reused**. You can have multiple elements with the same class name. Since there could be **multiple elements** with the same class, `getElementsByClassName` returns a **collection of all the elements** with that class.
- So, when using `getElementsByClassName`, it returns an **array-like collection**. To access a specific element from that collection, you need to **index** it, like `elements[0]`, `elements[1]`, etc.

For example:

```html
<p class="sharedText">Text 1</p>
<p class="sharedText">Text 2</p>
```

You would access them like this:

```javascript
const paragraphs = document.getElementsByClassName('sharedText');
const firstParagraph = paragraphs[0]; // First element with that class
```

##### In summary:

- **ID** is used when you want to target a unique element. Use `getElementById` for that, which returns the element directly.
- **Class** is used for elements that share the same style or behavior. Use `getElementsByClassName` to get a collection of elements, and then index into it if needed.

That’s why classes are a little trickier—since multiple elements can have the same class, you need to tell JavaScript which one you're referring to.

---
### (10.2.5) Attribute Manipulation

Attributes provide additional information about elements. They can be accessed and manipulated as follows:

- **Getting Attributes**
  ```javascript
  // Get the value of an attribute
  const randomValue = document.querySelector("li").getAttribute("random");
  console.log(randomValue); // Outputs the value of the 'random' attribute
  ```

- **Setting Attributes**
  ```javascript
  // Set or update the value of an attribute
  document.querySelector("li").setAttribute("random", "1000");
  ```

### (10.2.6) Changing Styles

You can manipulate the styles of elements directly or via classes. Using classes is generally preferred for better maintainability.

- **Direct Style Manipulation**
  ```javascript
  // Change inline style
  document.querySelector("h1").style.color = "blue"; // Changes the text color to blue
  document.querySelector("h1").style.fontSize = "24px"; // Changes the font size to 24px
  ```

- **Class Manipulation (Recommended)**
  - **`className`**: Get or set the class of an element.
  - **`classList`**: Provides methods to manipulate classes.
    - **Methods**:
      - `classList.add(className)`: Adds the specified class.
      - `classList.remove(className)`: Removes the specified class.
      - `classList.toggle(className)`: Toggles the specified class (adds it if it’s absent, removes it if it’s present).
      - `classList.contains(className)`: Checks if the element has a specific class.

  ```javascript
  // Example of class manipulation
  document.querySelector("li").classList.toggle("highlight"); // Toggles 'highlight' class on the first <li>
  ```

### (10.2.7) Content Manipulation

You can manipulate the content of elements in several ways:

- **`innerHTML`**: 
  - Gets or sets the HTML content inside an element. While useful, be cautious as it can expose your application to XSS (Cross-Site Scripting) attacks if used improperly.
  ```javascript
  document.querySelector("div").innerHTML = "<p>New content here!</p>";
  ```

- **Navigating the DOM**:
  - **`parentElement`**: Accesses the parent element of the selected element.
  - **`children`**: Returns a live HTMLCollection of child elements of the selected element.

  ```javascript
  // Example of navigating the DOM
  const parent = document.querySelector("li").parentElement; // Gets the parent of the first <li>
  const children = document.querySelector("ul").children; // Gets all children of the first <ul>
  ```

> **Note**: It’s important to **cache** selectors in variables to optimize performance. This reduces the number of times the DOM needs to be queried.

```javascript
var h1 = document.querySelector("h1");
// Now h1 can be reused without re-querying the DOM.
h1.style.color = "red"; // Changes the color of the cached h1 element.
```

### (10.3) **Events**

Events allow you to create interactive web pages by responding to user actions.

- **Adding Event Listeners**:
  Use `addEventListener` to listen for specific events and define the associated actions.

```javascript
var button = document.getElementById("enter");
var input = document.getElementById("userinput");
var ul = document.querySelector("ul");

button.addEventListener("click", function() {
  if (input.value > 0) {
    console.log(input.value);
    var li = document.createElement("li"); // Create a new <li> element
    li.appendChild(document.createTextNode(input.value)); // Create and append text node to <li>
    ul.appendChild(li); // Append <li> to <ul>
    input.value = ""; // Clear the input field
  }
});
```

---
#### **(10.3.1) What is an Event Listener?**

An **event listener** in JavaScript is a function that waits for a specific event to occur on a target (like a DOM element). When the event occurs, the event listener runs the associated function.

---
#### **(10.3.2) Events in JavaScript**

An event is any type of interaction the user has with the document (such as clicking a button, pressing a key, or loading a page). Common events include:
##### **Mouse Events**

|**Event**|**Description**|
|---|---|
|`click`|Triggered when a mouse button is clicked on an element.|
|`mousedown`|Triggered when a mouse button is pressed down over an element.|
|`mouseup`|Triggered when a mouse button is released over an element.|
|`mouseover`|Triggered when the mouse pointer enters the area of an element.|
|`mouseout`|Triggered when the mouse pointer leaves the area of an element.|
|`mouseenter`|Triggered when the mouse pointer enters the element (does not bubble).|
|`mouseleave`|Triggered when the mouse pointer leaves the element (does not bubble).|

---

##### **Keyboard Events**

|**Event**|**Description**|
|---|---|
|`keydown`|Triggered when a key is pressed down.|
|`keypress`|Triggered when a key is pressed and held down (deprecated in modern browsers).|
|`keyup`|Triggered when a key is released.|

---

##### **Focus Events**

|**Event**|**Description**|
|---|---|
|`focus`|Triggered when an element gains focus (e.g., when clicked on or tabbed into).|
|`blur`|Triggered when an element loses focus.|

---

##### **Form Events**

|**Event**|**Description**|
|---|---|
|`submit`|Triggered when a form is submitted (e.g., when the submit button is clicked).|
|`change`|Triggered when the value of an input element changes (e.g., after text is typed).|
|`input`|Triggered whenever the value of an `<input>` or `<textarea>` element changes.|
|`reset`|Triggered when a form's reset button is clicked.|

---

##### **Window Events**

|**Event**|**Description**|
|---|---|
|`resize`|Triggered when the window is resized.|
|`scroll`|Triggered when the user scrolls the page or an element.|
|`load`|Triggered when the page or an element (e.g., image) has finished loading.|
|`unload`|Triggered when the page is about to be unloaded (e.g., when navigating away).|

---

##### **Touch Events**

|**Event**|**Description**|
|---|---|
|`touchstart`|Triggered when a touch point is placed on the screen.|
|`touchend`|Triggered when a touch point is removed from the screen.|
|`touchmove`|Triggered when a touch point is moved across the screen.|

---

##### **Other Events**

|**Event**|**Description**|
|---|---|
|`drag`|Triggered when an element is dragged by the mouse.|
|`drop`|Triggered when a dragged element is dropped on a valid drop target.|
|`contextmenu`|Triggered when the user right-clicks on an element (opens the context menu).|

---

Let me know if you need any more information or further adjustments!

---
#### **(10.3.3) Attaching Event Listeners**

You can add an event listener to a DOM element using the `addEventListener()` method.

**Syntax:**

```javascript
element.addEventListener(event, function, useCapture);
```

- `element`: The DOM element that will listen for the event.
- `event`: A string representing the type of event (e.g., `"click"`, `"mouseover"`, etc.).
- `function`: The function that will be executed when the event is triggered.
- `useCapture`: An optional boolean that determines if the event should be captured during the capturing phase (`true`) or the bubbling phase (`false` or omitted).

##### Example:

```javascript
document.getElementById("myButton").addEventListener("click", function() {
    alert("Button clicked!");
});
```

---
#### **(10.3.4) Event Propagation**

JavaScript events propagate through the DOM in two phases:

1. **Capturing Phase**: The event starts from the root and goes down to the target element.
2. **Bubbling Phase**: After reaching the target element, the event bubbles up back to the root.

- By default, events bubble up (i.e., propagate in the bubbling phase).
- If you want to catch the event during the capturing phase, set `useCapture` to `true`.

##### Example (Capturing Phase):

```javascript
document.getElementById("parentDiv").addEventListener("click", function() {
    console.log("Captured during capturing phase");
}, true);
```

---
#### **(10.3.5) Removing Event Listeners**

You can remove an event listener using `removeEventListener()`. It requires the same parameters as `addEventListener()` (i.e., the event type, the exact function reference, and optionally, the useCapture flag).

**Syntax:**

```javascript
element.removeEventListener(event, function, useCapture);
```

**Example:**

```javascript
function showMessage() {
    alert("Message displayed!");
}

let button = document.getElementById("myButton");
button.addEventListener("click", showMessage);

// To remove the event listener:
button.removeEventListener("click", showMessage);
```

---
#### **(10.3.6) Event Object**

The event object is passed to the callback function when an event occurs. This object contains useful information about the event, such as the element that triggered it, the type of event, and other specific details.

**Common Properties:**

- `target`: The element that triggered the event.
- `type`: The type of the event (e.g., "click", "keydown").
- `bubbles`: Whether the event bubbles up or not.
- `cancelable`: Whether the event can be canceled.
- `clientX`, `clientY`: Mouse coordinates for mouse events.
- `key`: For keyboard events, returns the key pressed.

**Example:**

```javascript
document.getElementById("myButton").addEventListener("click", function(event) {
    console.log("Event type: " + event.type); // click
    console.log("Target element: " + event.target.id); // myButton
});
```

---
#### **(10.3.7) Arrow Functions in Event Listeners**

You can use arrow functions in event listeners, but be cautious because they don’t bind their own `this`. Instead, `this` inside an arrow function refers to the enclosing lexical context (usually the global object or parent scope).

**Example:**

```javascript
document.getElementById("myButton").addEventListener("click", () => {
    console.log(this);  // In an arrow function, `this` will be undefined (or the outer context).
});
```

If you want to use `this` in a traditional event listener, you should use a regular function.

---
#### **(10.3.8) Event Listener Options**

You can provide options for event listeners. These options can be passed as an object or as a boolean flag.

**Options include:**

- `capture`: A boolean specifying whether the event should be captured in the capturing phase (default is `false`).
- `once`: If `true`, the listener will be triggered at most once after being added. The listener is then removed automatically.
- `passive`: If `true`, the listener will never call `preventDefault()`. This is useful for performance optimization in certain cases, like `scroll` or `touch` events.

**Example with options:**

```javascript
document.getElementById("myButton").addEventListener("click", function() {
    console.log("Button clicked!");
}, { once: true });
```

---
#### **(10.3.9) The `this` Keyword Inside Event Handlers**

The value of `this` inside an event handler depends on how the event listener is attached:

- In a **normal function** (not an arrow function), `this` refers to the element that triggered the event.
- In an **arrow function**, `this` refers to the surrounding scope (not the event target).

**Example:**

```javascript
document.getElementById("myButton").addEventListener("click", function() {
    console.log(this); // In regular function, `this` refers to the DOM element
});
```

---
#### **(10.3.10) Event Delegation**

Event delegation is a technique where you attach a single event listener to a parent element instead of multiple listeners on child elements. This is useful when you have dynamic content or many elements to listen for events on.

**Example:**

```javascript
document.getElementById("parentDiv").addEventListener("click", function(event) {
    if (event.target && event.target.matches("button.classname")) {
        alert("Button clicked!");
    }
});
```

Here, the `click` event is handled by the parent element, but it checks if the clicked target is a specific button inside the parent.

---
#### **(10.3.11) The `preventDefault()` and `stopPropagation()` Methods**

- **`preventDefault()`**: Prevents the default action associated with the event. For example, in a `submit` event, it prevents the form from submitting.
- **`stopPropagation()`**: Stops the event from propagating (bubbling or capturing).

**Example:**

```javascript
document.getElementById("myLink").addEventListener("click", function(event) {
    event.preventDefault();  // Prevents the default behavior of following the link
    alert("Link clicked!");
});
```

---
#### **(10.3.12) Use Cases for Event Listeners**

- **Form validation**: Listening to `submit` or `input` events to validate user input.
- **Dynamic behavior**: Changing content or interacting with the page based on user input, such as a dropdown menu or a button click.
- **Mouse and keyboard interactions**: Detecting mouse movements, key presses, or drag-and-drop interactions.

---
#### **(10.3.13) Best Practices**

- **Use event delegation** when you have many similar elements (like buttons or links) that require the same event handler.
- **Avoid inline event handlers** like `<button onclick="alert('Hello!')">`, as it mixes HTML and JavaScript and doesn’t allow for easy management of event listeners.
- **Remove event listeners** when they are no longer needed (especially with dynamic elements) to avoid memory leaks.

---

### (10.4) **The Event Object in Event Listeners**

When you add an event listener to an element, the event handler function receives an **event object** as an argument. This object provides important information about the event that occurred. The event object is automatically passed by the browser to the event listener and contains various properties and methods that help you interact with and understand the event.
#### **Key Properties of the Event Object**

##### 1. `type`:
- **Description**: The type of event that was triggered (e.g., `keydown`, `click`).
- **Example**:
    ```javascript
    window.addEventListener("keydown", function(e) {
        console.log(e.type);  // Outputs: "keydown"
    });
    ```

##### 2. `target`:
- **Description**: The DOM element that triggered the event.
- **Example**:
    ```javascript
    document.getElementById("myButton").addEventListener("click", function(e) {
        console.log(e.target);  // Outputs: the DOM element clicked
    });
    ```

##### 3. `key` (for keyboard events):
- **Description**: For keyboard events like `keydown` or `keyup`, `e.key` contains the key that was pressed.
- **Example**:
    ```javascript
    window.addEventListener("keydown", function(e) {
        console.log(e.key);  // Outputs: "a", "Enter", etc., depending on key pressed
    });
    ```

##### 4. `code` (for keyboard events):
- **Description**: Represents the physical key code on the keyboard, independent of the key value.
- **Example**:
    ```javascript
    window.addEventListener("keydown", function(e) {
        console.log(e.code);  // Outputs: "KeyA" for the "A" key
    });
    ```

##### 5. `bubbles`:
- **Description**: A boolean that tells whether the event bubbles up through the DOM or not.
- **Example**:
    ```javascript
    window.addEventListener("click", function(e) {
        console.log(e.bubbles);  // Outputs: true, as "click" events bubble by default
    });
    ```

##### 6. `preventDefault()`:
- **Description**: A method used to prevent the default behavior associated with the event (e.g., preventing a form from submitting).
- **Example**:
    ```javascript
    document.getElementById("myForm").addEventListener("submit", function(e) {
        e.preventDefault();  // Prevents form submission
        alert("Form submission prevented!");
    });
    ```

##### 7. `stopPropagation()`:
- **Description**: A method used to stop the event from propagating further in the DOM (i.e., prevents bubbling or capturing).
- **Example**:
    ```javascript
    document.getElementById("myButton").addEventListener("click", function(e) {
        e.stopPropagation();  // Stops event from propagating up the DOM
        alert("Event propagation stopped!");
    });
    ```

##### 8. `altKey`, `shiftKey`, `ctrlKey`:
- **Description**: Boolean properties that indicate whether a specific modifier key (Alt, Shift, or Ctrl) was pressed during the event.
- **Example**:
    ```javascript
    window.addEventListener("keydown", function(e) {
        console.log(e.altKey);  // Outputs: true if the Alt key was pressed
        console.log(e.shiftKey);  // Outputs: true if the Shift key was pressed
        console.log(e.ctrlKey);  // Outputs: true if the Ctrl key was pressed
    });
    ```


---

|**Property**|**Description**|
|---|---|
|`type`|The type of event that was triggered (e.g., `keydown`, `click`).|
|`target`|The DOM element that triggered the event (e.g., the element clicked).|
|`key`|For keyboard events, the key that was pressed (e.g., `"a"`, `"Enter"`, etc.).|
|`code`|For keyboard events, the physical key code (e.g., `"KeyA"` for the "A" key).|
|`bubbles`|A boolean that indicates if the event bubbles up through the DOM (default is `true` for most events).|
|`preventDefault()`|A method that prevents the default action associated with the event (e.g., preventing a form submission).|
|`stopPropagation()`|A method that stops the event from propagating (bubbling or capturing) further in the DOM.|
|`altKey`|A boolean that indicates if the "Alt" key was pressed during the event.|
|`shiftKey`|A boolean that indicates if the "Shift" key was pressed during the event.|
|`ctrlKey`|A boolean that indicates if the "Ctrl" key was pressed during the event.|

---
##### **Example of Using the Event Object**

Here’s a complete example of how to use the event object in a `keydown` event:

```javascript
window.addEventListener("keydown", function(e) {
    console.log("Key pressed: " + e.key);  // Displays the key pressed (e.g., 'a', 'Enter')
    console.log("Key code: " + e.code);  // Displays the physical key code (e.g., 'KeyA')
    console.log("Alt key pressed: " + e.altKey);  // Displays whether the Alt key was pressed
    if (e.key === "Enter") {
        alert("Enter key pressed!");
    }
});
```

---

##### **Why the Event Object is Special**

- The **event object** is automatically passed into the event listener function by the browser.
- You can refer to this object with the variable name `e` (or `event`), and it gives you access to everything you need to know about the event.
- By using the event object, you can perform tasks like preventing default actions, stopping event propagation, and accessing information about what triggered the event (e.g., which key was pressed or which element was clicked).

---
### (10.7) General JavaScript Methods

|Method|Description|
|---|---|
|`addEventListener`|Attaches an event handler to a specified element.|
|`setInterval`|Repeatedly calls a function with a fixed time delay between each call.|
|`clearInterval`|Clears a timed, repeated action set by `setInterval`.|
|`setTimeout`|Executes a function after a specified delay.|
|`clearTimeout`|Clears a timed action set by `setTimeout`.|
|`JSON.parse()`|Converts a JSON string into a JavaScript object.|
|`JSON.stringify()`|Converts a JavaScript object into a JSON string.|
|`localStorage.setItem()`|Stores data in the browser's local storage.|
|`localStorage.getItem()`|Retrieves data from the browser's local storage.|
|`Array.prototype.forEach()`|Executes a provided function once for each array element.|
|`Array.prototype.map()`|Creates a new array populated with the results of calling a provided function on every element in the calling array.|

#### Examples:

- **`addEventListener`**
    
    ```javascript
    document.getElementById('button').addEventListener('click', function() {
      alert('Button clicked!');
    });
    ```
    
    _(Attaches a click event listener to an element with the ID "button")_
    
- **`setInterval`**
    
    ```javascript
    setInterval(function() {
      console.log('This will print every 2 seconds');
    }, 2000);
    ```
    
    _(Logs a message every 2 seconds)_
    
- **`clearInterval`**
    
    ```javascript
    const intervalId = setInterval(function() {
      console.log('This will stop after 5 seconds');
    }, 1000);
    
    setTimeout(function() {
      clearInterval(intervalId);
      console.log('Interval cleared');
    }, 5000);
    ```
    
    _(Clears the interval after 5 seconds)_
    
- **`setTimeout`**
    
    ```javascript
    setTimeout(function() {
      console.log('This runs after 3 seconds');
    }, 3000);
    ```
    
    _(Logs a message after a 3-second delay)_
    
- **`clearTimeout`**
    
    ```javascript
    const timeoutId = setTimeout(function() {
      console.log('This will not run');
    }, 5000);
    
    clearTimeout(timeoutId); // This will prevent the timeout from executing
    ```
    
    _(Cancels the timeout before it executes)_
    
- **`JSON.parse()`**
    
    ```javascript
    const jsonString = '{"name": "John", "age": 30}';
    const obj = JSON.parse(jsonString);
    console.log(obj.name); // "John"
    ```
    
    _(Converts a JSON string into a JavaScript object)_
    
- **`JSON.stringify()`**
    
    ```javascript
    const obj = { name: 'John', age: 30 };
    const jsonString = JSON.stringify(obj);
    console.log(jsonString); // '{"name":"John","age":30}'
    ```
    
    _(Converts a JavaScript object into a JSON string)_
    
- **`localStorage.setItem()`**
    
    ```javascript
    localStorage.setItem('username', 'john_doe');
    ```
    
    _(Stores a value in local storage)_
    
- **`localStorage.getItem()`**
    
    ```javascript
    const username = localStorage.getItem('username');
    console.log(username); // "john_doe"
    ```
    
    _(Retrieves the value from local storage)_
    
- **`Array.prototype.forEach()`**
    
    ```javascript
    const arr = [1, 2, 3];
    arr.forEach(function(element) {
      console.log(element); // Logs each element in the array
    });
    ```
    
    _(Iterates over each element of the array and performs an action)_
    
- **`Array.prototype.map()`**
    
    ```javascript
    const numbers = [1, 2, 3];
    const doubled = numbers.map(function(num) {
      return num * 2;
    });
    console.log(doubled); // [2, 4, 6]
    ```
    
    _(Creates a new array with each element doubled)_

---

## **11. Local Storage in JavaScript**

Local Storage is a web storage solution that allows web applications to store data in the user's browser. It is a simple key-value store where you can save data that persists even after the user closes the browser. Local Storage has a larger capacity compared to cookies and allows you to store data across sessions.

#### **11.1. What is Local Storage?**

- **Local Storage** allows you to store data in the browser on a permanent basis (until explicitly removed by the user or through JavaScript).
- The data is stored as **key-value pairs** and is saved within the browser, making it available even after the page is refreshed or the browser is closed.
- It is part of the **Web Storage API** and works across all modern browsers.

#### **11.2. Properties of Local Storage**

- **Persistence**: Data stored in Local Storage remains until explicitly removed. It is not cleared when the browser session ends.
- **Storage Limit**: The storage limit varies across browsers but typically allows about **5MB** of data per origin (domain).
- **Synchronous API**: Local Storage operations are synchronous, meaning they block the thread until completed.
- **Domain-specific**: Data is specific to the domain that created it, meaning you cannot access data stored by a different domain.

---

### **11.3. Using Local Storage**

Local Storage provides several key methods for storing and retrieving data:

#### **1. Storing Data**

To store data, you use the `localStorage.setItem()` method. It takes two arguments:

- A **key** (string) used to identify the data.
- A **value** (string) to be stored.

**Syntax**:

```javascript
localStorage.setItem('key', 'value');
```

**Example**:

```javascript
localStorage.setItem('username', 'JohnDoe');  // Stores 'JohnDoe' under the key 'username'
```

#### **2. Retrieving Data**

To retrieve data, use the `localStorage.getItem()` method, which takes a **key** as an argument and returns the value stored under that key.

**Syntax**:

```javascript
localStorage.getItem('key');
```

**Example**:

```javascript
let username = localStorage.getItem('username');  // Retrieves 'JohnDoe' stored under 'username'
console.log(username);  // Outputs: JohnDoe
```

#### **3. Removing Data**

You can remove specific data using the `localStorage.removeItem()` method. It takes the **key** as an argument.

**Syntax**:

```javascript
localStorage.removeItem('key');
```

**Example**:

```javascript
localStorage.removeItem('username');  // Removes the 'username' data from Local Storage
```

#### **4. Clearing All Data**

To remove all data stored in Local Storage, you can use the `localStorage.clear()` method. This will clear all key-value pairs for the current domain.

**Syntax**:

```javascript
localStorage.clear();
```

**Example**:

```javascript
localStorage.clear();  // Clears all data from Local Storage
```

---

### **11.4. Local Storage and Data Types**

Local Storage only stores data as **strings**. If you want to store non-string data types (like objects, arrays, etc.), you need to **serialize** the data into a string format using `JSON.stringify()` before storing it, and then **deserialize** it using `JSON.parse()` when retrieving it.

#### **Example: Storing and Retrieving Objects**

```javascript
// Storing an object
const user = { name: 'John', age: 30 };
localStorage.setItem('user', JSON.stringify(user));  // Serialize the object into a string

// Retrieving the object
const storedUser = JSON.parse(localStorage.getItem('user'));  // Deserialize the string back into an object
console.log(storedUser);  // Outputs: { name: 'John', age: 30 }
```

---

### **11.5. Checking if Local Storage is Available**

Before using Local Storage, it’s good practice to check if the browser supports it. Not all browsers may support Local Storage, especially in private or incognito modes.

#### **Checking for Local Storage Support**:

```javascript
if (typeof(Storage) !== "undefined") {
    console.log("Local Storage is supported!");
} else {
    console.log("Local Storage is not supported.");
}
```

---

### **11.6. Common Use Cases for Local Storage**

1. **Storing User Preferences**: You can store user settings like themes, language preferences, or customization options.
    
2. **Caching Data**: Local Storage can be used to cache data (such as API responses) for offline use or to reduce load times.
    
3. **Persisting User Authentication**: After the user logs in, you can store their authentication token in Local Storage to keep them logged in between sessions.
    
4. **Storing Form Data**: You can store form data temporarily as users fill out a form, to restore it later if they accidentally navigate away from the page.
    

---

### **11.7. Limitations of Local Storage**

- **Capacity**: The storage limit is typically around **5MB** per domain, which can be limiting for large-scale data storage.
- **Synchronous**: Local Storage operations are blocking, which can lead to performance issues if used excessively.
- **Security**: Data stored in Local Storage is not encrypted, so it can be accessed by anyone who has access to the browser's developer tools or the data files. Avoid storing sensitive information like passwords.
- **No Expiry**: Data in Local Storage does not expire automatically. If you need the data to expire, you must manually remove it (or use a timestamp to manage it).

---

### **11.8. Summary**

- **Local Storage** provides a simple, persistent, client-side storage solution.
- Data is stored as key-value pairs and persists across sessions.
- It’s useful for storing non-sensitive data that needs to be retained across page reloads or sessions.
- **Limitations** include capacity (around 5MB), synchronous operations, and lack of automatic expiration.

---

These notes will help you understand how to use **Local Storage** effectively within your JavaScript projects. Let me know if you need further details or examples!
## **12. Asynchronous JavaScript**

### **setTimeout()**:

```javascript
setTimeout(function() {
    console.log("This message appears after 2 seconds.");
}, 2000);
```

- **setTimeout()**: Executes a function after a specified time delay (in milliseconds).

### **Promises**:

```javascript
let promise = new Promise(function(resolve, reject) {
    let success = true;
    if (success) {
        resolve("Task completed");
    } else {
        reject("Task failed");
    }
});

promise.then(function(result) {
    console.log(result);
}).catch(function(error) {
    console.log(error);
});
```

- **Promises**: Used to handle asynchronous operations, allowing for better error handling and chaining of operations.

### Promises and Error Handling

```javascript
let promise = new Promise((resolve, reject) => {
	let success = true;
	if (success) {
		resolve("Task completed");
	} else {
		reject("Task failed");
	}
});

promise
	.then(result => console.log(result))
	.catch(error => console.log(error));
```

- **Error Handling in Async Code:** Use `.catch()` with promises or wrap `async/await` code in `try/catch` blocks.

**Example with async/await:**

```javascript
async function fetchData() {
	try {
		let response = await fetch("https://api.example.com/data");
		let data = await response.json();
		console.log(data);
	} catch (error) {
		console.error("Error fetching data:", error);
	}
}
fetchData();
```

---
## **13. Debugging Tips**

- **Console Logging:**

Use `console.log()` to print values and debug issues.

```javascript

let value = 10;
console.log("Value:", value);

```

- **Browser Developer Tools:**

Modern browsers provide tools (like Chrome DevTools) that let you inspect elements, monitor network requests, set breakpoints, and step through code.

- **Error Messages:**

Read error messages carefully in the console; they often provide line numbers and clues to what went wrong.

---
## **Key Concepts Covered**

- **JavaScript**: A programming language that adds interactivity and functionality to webpages.
- **Variables & Data Types**: Declaring variables and understanding data types (strings, numbers, objects, etc.).
- **Functions**: Defining and calling functions to organize code.
- **Conditionals & Loops**: Making decisions in code and repeating actions with loops.
- **Arrays & Objects**: Working with collections of data.
- **DOM Manipulation**: Interacting with the HTML structure to modify content dynamically.
- **Events**: Handling user interactions with JavaScript.
- **Asynchronous JavaScript**: Working with time-based functions and promises for async behavior.

---
### Programming Paradigms

Understanding programming paradigms is crucial for developing effective coding practices.

- **Declarative Programming**: A programming paradigm that expresses the logic of a computation without describing its control flow. Examples include HTML, SQL, and functional programming. It focuses on what the program should accomplish rather than how it should achieve it.

- **Imperative Programming**: A paradigm that uses statements that change a program’s state. It includes languages like JavaScript, Python, and Java. This approach emphasizes the steps to perform a task and allows for more direct control of the program flow.
---
---
# How to Use External JavaScript Files in a JavaScript File in Node.js

In a Node.js environment, you can modularize your code by using external JavaScript files. This allows you to separate different parts of your application into manageable, reusable components. Below are the key steps for using external JavaScript files in a Node.js application:

---

### 1. **Using `require()` to Include External Files**

In Node.js, you can use the `require()` function to import external JavaScript files or modules. This is the most common method to include external files.

#### Syntax:

```javascript
require('path-to-your-js-file');
```

#### Example:

Assume you have an external file `module.js`:

```javascript
// module.js
function greet(name) {
    return `Hello, ${name}!`;
}

module.exports = greet;
```

You can use `require()` to include this external file in another JavaScript file:

```javascript
// app.js
const greet = require('./module.js');  // Import the module

console.log(greet('John'));  // Output: Hello, John!
```

- **`module.exports`**: The module is exported using `module.exports` to make the functions or variables available for import in other files.
- **`require()`**: This function loads and executes the `module.js` file, making the exported content accessible in the current file.

---

### 2. **Using Relative or Absolute Paths**

- **Relative Paths**: If the external file is in the same directory or a subdirectory, you use a relative path (like `'./module.js'`).
    
    Example: `require('./folder/module.js')`
    
- **Absolute Paths**: You can also use absolute paths if you want to reference files based on the full file system path.
    
    Example: `require('/home/user/project/module.js')`
    

---

### 3. **Organizing Code Using Modules**

In Node.js, each file is treated as a separate module. You can break down your application into multiple files, each representing a distinct feature or functionality, and then export/import them as needed.

#### Example: `math.js`

```javascript
// math.js
function add(a, b) {
    return a + b;
}

function subtract(a, b) {
    return a - b;
}

module.exports = { add, subtract };
```

#### Example: `app.js`

```javascript
// app.js
const math = require('./math');  // Import math module

console.log(math.add(5, 3));  // Output: 8
console.log(math.subtract(5, 3));  // Output: 2
```

---

### 4. **Using Built-In Node.js Modules**

Node.js also provides built-in modules, such as `fs` for file system operations or `path` for working with file and directory paths. These modules are automatically available in your application without needing to install them.

Example with `path` module:

```javascript
const path = require('path');

const filePath = path.join(__dirname, 'myFolder', 'file.js');
console.log(filePath);  // Will print the absolute path to 'file.js'
```

---

### 5. **ES6 Modules in Node.js**

Node.js supports ES6 (ECMAScript 2015) modules, which allows you to use `import` and `export` syntax instead of `require()` and `module.exports`.

To use ES6 modules, follow these steps:

1. **Add `"type": "module"`** to your `package.json` file.
2. Use `import` and `export` in your JavaScript files.

Example:

```javascript
// module.mjs
export function greet(name) {
    return `Hello, ${name}!`;
}
```

```javascript
// app.mjs
import { greet } from './module.mjs';

console.log(greet('John'));  // Output: Hello, John!
```

---

### 6. **Third-Party Libraries**

You can also use third-party libraries, like `lodash` or `express`, by installing them via npm and then importing them with `require()` or `import`.

For example, after installing `lodash` using `npm install lodash`:

```javascript
// app.js
const _ = require('lodash');

let array = [1, 2, 3, 4];
let reversedArray = _.reverse(array);

console.log(reversedArray);  // Output: [4, 3, 2, 1]
```

---

### 7. **Asynchronous Loading**

In some cases, you might need to dynamically load an external JavaScript file. You can use `require()` asynchronously with the help of callback functions, though this is less common in standard Node.js modules. For more complex cases (like loading files based on conditions), you could use `fs` for reading files asynchronously.

---

### Summary

- **Modules**: External JavaScript files in Node.js are modularized using `module.exports` and imported using `require()`.
- **Paths**: Use relative (`./`) or absolute paths to reference external files.
- **Organizing**: Break your code into smaller modules to maintain clarity and reusability.
- **Built-In Modules**: Node.js provides built-in modules like `fs` and `path` to simplify tasks.
- **ES6 Modules**: Use `import` and `export` for modern module syntax in Node.js.
- **Third-Party Libraries**: Install and use external libraries via npm.

