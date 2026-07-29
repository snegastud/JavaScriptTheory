# JavaScriptTheory (JS Version:v24.13.1 and JS RUNTIME:V8 engine)
**what is javascript? Can you explain what JavaScript is?**


>JavaScript is one of the core programming languages I've been working with to develop web applications. It's a single-threaded, event-driven language, and it supports asynchronous programming using Promises and async/await. In my projects, I mainly use JavaScript to implement business logic, process data, and integrate APIs.

**another answer**

>"JavaScript is one of the core programming languages used for web development. It is used to build dynamic and interactive applications and supports both frontend and backend development. In my project, I mainly use JavaScript to develop application functionality and integrate backend services."

**What is a Variable in JavaScript?**

>A variable is a named container used to store data in a program. It allows us to store, access, update, and reuse values whenever they're needed during the execution of the application.

>`For example,` in a registration form, when a user enters their name, email, and password, we store those values in variables. We then use those variables to perform validations, process the data, and send it to the backend through an API.

>In JavaScript, we generally declare variables using let and const based on the requirement."

**what is the difference between let, const,var?**

>The main difference is in scope, reassignment, and redeclaration.

>`var` is **function-scoped**. It can be redeclared and reassigned, which can sometimes lead to unexpected behavior. Because of that, we generally avoid using var in modern JavaScript.

>`let` is **block-scoped**. It can be reassigned, but it cannot be redeclared within the same scope. I use let whenever a value needs to change during execution.

>`const` is also **block-scoped**. It cannot be redeclared or reassigned, so I use it for values that should remain constant throughout the execution.

**Why don't you use var?**
>`var` is function-scoped and allows both redeclaration and reassignment. In larger codebases, this can lead to accidental overwrites and make debugging more difficult. That's why modern JavaScript development generally prefers `let` and `const`.

**what is variable scope?**
>`Variable scope` Variable scope defines where a variable can be accessed in a program. We have block scope, function scope, and global scope.

**Explain the each scope**
>`function scope` function scope means a variable declared inside a function can only be accessed within that function." Give a tiny example, like a variable inside a function that's not accessible outside.

>`block scope` it means a variable is only accessible inside a block, like an if statement or a for loop, and while switch.

>`gobal scope` global scope means a variable declared outside all functions and blocks can be accessed from anywhere in the application.

**Hosting flow**
# Hoisting Flow

```
                 JavaScript Engine
                        │
                        ▼
          ┌────────────────────────┐
          │ Memory Creation Phase  │
          └────────────────────────┘
                        │
        ┌───────────────┼────────────────┐
        │                                │
        ▼                                ▼
   var a                           let b / const c
        │                                │
        ▼                                ▼
 Memory Allocated                 Memory Allocated
        │                                │
        ▼                                ▼
 a = undefined                     🔒 TDZ (Locked)
        │                                │
        └───────────────┬────────────────┘
                        ▼
          ┌────────────────────────┐
          │  Code Execution Phase  │
          └────────────────────────┘
                        │
        ┌───────────────┼────────────────┐
        │                                │
        ▼                                ▼
 console.log(a)                  console.log(b)
        │                                │
        ▼                                ▼
   undefined                     ReferenceError
        │
        ▼
 a = 10 (Initialized)
        │
        ▼
 console.log(a)
        │
        ▼
        10
```
**What is Hoisting?**
>`Hoisting` is JavaScript's behavior of processing variable and function declarations before the code is executed.

>For var, memory is allocated and it's initialized with undefined, so accessing it before declaration returns undefined.

>For let and const, they are also hoisted, but they remain in the Temporal Dead Zone until their declaration is reached. If we access them before declaration, JavaScript throws a ReferenceError."

**what is TDZ ?**
>Sure, let me explain.

>The `Temporal Dead Zone (TDZ)` is the time when JavaScript has already created a let or const variable, but it hasn't initialized it yet.

>If we try to access the variable before its declaration, JavaScript throws a ReferenceError.

>The purpose of TDZ is to prevent us from accidentally using a variable before it's properly initialized."

**What are Data Types in JavaScript?**
>Data types define the type of value that a variable can hold. JavaScript is a dynamically typed language, which means we don't need to explicitly specify the data type. JavaScript automatically determines the type based on the value assigned to the variable.

>In JavaScript, data types are mainly classified into `Primitive and Non-Primitive data types`.

**Real-Time Example**

>Imagine you're filling an employee registration form.

```Employee Name     → String
Employee Age      → Number
Is Active         → Boolean
Employee Address  → Object
Skills            → Array (Object)

```
>Each field stores a different type of data.

**Types of data type?**
```
                 Data Types
                     │
         ┌───────────┴───────────┐
         │                       │
         ▼                       ▼
   Primitive               Non-Primitive
         │                       │
         ▼                       ▼
 String                 Object
 Number                 Array
 Boolean                Function
 Undefined              Date
 Null
 Symbol
 BigInt
```
**Primtive data types** 

>*Primitive values are immutable and store a single value.*

**Each purpose of usage**
> `String` A String is used to store text or characters. We define strings using single quotes, double quotes, or backticks.
>**Example** let name = "Sneha";

> `Number` A Number is used to store both integer and decimal values.
>**Example**  let age = 25; let salary = 50000.50;

>`Boolean` A Boolean represents only two values: true or false. It is commonly used for conditions and validations.
>**Example** let isLoggedIn = true;

>`Undefined` A variable that is declared but not assigned any value has the value undefined.
>**Example** let city; console.log(city);

>`Null` null represents an intentional empty value. We assign it when a variable currently has no value.
>**Example** let manager = null;

>`Symbol` A Symbol creates a unique value. It is mainly used to create unique object property keys.
>**Example** const id = Symbol("id");

>`BigInt`  BigInt is used to store very large integers that exceed the safe limit of the Number data type.
>**Example** const amount = 123456789012345678901234567890n;

**Why are Primitive Data Types Immutable?**
>Primitive data types are immutable because once a value is created, JavaScript doesn't modify that original value. If we assign a new value, JavaScript creates a new value and the variable starts referencing it.

**Non-Primitive Data Types**
>*These store collections of values or more complex entities.*
>
```
| Type     | Example        |
| -------- | -------------- |
| Object   | `{}`           |
| Array    | `[]`           |
| Function | `function(){}` |
| Date     | `new Date()`   |

```
**Why Are Objects Mutable?**
>Objects are mutable because JavaScript allows us to modify their properties without creating a new object. The same object remains in memory, and only its contents are updated.

**What is  is Dynamic Typing?**

>"JavaScript is a dynamically typed language, which means we don't need to declare the data type of a variable. The data type is automatically determined based on the value assigned to it, and it can change during execution."

**Primitive vs Non-Primitive?**

>`Primitive data types` store a single value and are immutable. They are compared by value.

>`Non-primitive data types` store collections of values or more complex data. They are mutable and compared by reference.

**What is typeof?**
>The `typeof` operator is used to identify the data type of a value or variable.

**What is function?**

>A function is a reusable block of code designed to perform a specific task. Instead of writing the same logic multiple times, we write it once inside a function and call it whenever needed. This improves code reusability, readability, and maintainability. function is only run when its call. otherewise it doesn't run that function.

**syntax**
```
function functionName(parameter1, parameter2) {

    // Business Logic

    return value;
}
// call the funtionName(passing the arguments)
```
**what is function declartion ?**
>`function declartion` is the function define using the function keyword and followed by the funtion name.its has one advandage `function is hosited`. before declartion we can call the function . function is reusable write once we can use whenever its needed. function only run when its called.
```
>function declarations are hoisted.
console.log(add(10, 20));

function add(a, b) {
    return a + b;
}

```
**what is function expression ?**
>'function expression' is assign to a variable .unlike a normal function declartion, function expression is not fully hosited. we cannot access the function before declartion. if we try to access the before declartion it will throw that error like `ReferenceError`

**What is the main difference between a Function Declaration and a Function Expression?**
>The main difference is hoisting. A function declaration is fully hoisted, so it can be called before its declaration. A function expression is assigned to a variable, so it can only be called after the variable has been initialized

**What is arrow function?**
>An arrow function is a shorter and more concise way of writing a function. It uses the => syntax instead of the function keyword. In my projects, I mainly use arrow functions because they improve code readability and are commonly used with callbacks and array methods."

>**What is the difference between a normal function and an arrow function?**
>The main difference is syntax. Arrow functions provide a shorter and cleaner way to write functions using the => syntax. In my projects, I mostly use arrow functions for callbacks and array methods because they improve readability. However, normal functions are still useful in scenarios where specific function behavior is required.

>**Why was Arrow Function introduced?**
>Arrow functions were introduced to reduce boilerplate code and make functions easier to write and read. They are especially useful for callbacks and array methods where concise syntax improves readability.

**REFERE MORE FUNCTION**
>https://www.w3schools.com/js/js_arrow_function.asp

**what we couldn't achieve the arrow function**
>`Hoisting` "Arrow functions are function expressions, so they are not available before initialization.". If we can try to access it through the Reference error.

>`this` "Arrow functions don't create their own this. They inherit this from the surrounding scope."

>`Constructor` "Arrow functions cannot be used as constructors."

>`When to Use` "I use arrow functions for callbacks, array methods, small utility functions, and asynchronous code where concise syntax improves readability."

>`When Not to Use` "I avoid arrow functions as object methods or constructors when specific function behavior is required."

**anonymous function:**
>"An anonymous function is simply a function without a name. A function expression is a function assigned to a variable. Most function expressions use anonymous functions, which is why these two concepts are often confused."

**coding example**
```
// Anonymous Function
function () {
    console.log("Hello");
}
// Function Expression
const greet = function () {
    console.log("Hello");
};
```
**what is call back function ?**
>A callback function is a function that is passed as an argument to another function and is executed after the main function completes a specific task.The main purpose of using callbacks is to make functions reusable and flexible.This allows the same function to perform different operations without changing its implementation.
>`For example`, after fetching employee data from an API, one screen might display the data, another might generate a report, and another might validate the response. Instead of creating separate fetch functions, we keep one generic function and pass different callback functions depending on the requirement.
**Example coding**
```
// Success callback
function loginSuccess(user) {
    console.log("Login Successful");
    console.log(`Welcome ${user.userName}`);
    console.log(`Role : ${user.role}`);
}

// Failure callback
function loginFailure() {
    console.log("Access Denied");
}

// Main function
function login(username, onSuccess, onFailure) {

    const user = {
        userId: 101,
        userName: "ADMIN",
        role: "Administrator"
    };

    if (username === "ADMIN") {
        onSuccess(user);      // Execute success callback
    } else {
        onFailure();          // Execute failure callback
    }
}

// Function call
login("ADMIN", loginSuccess, loginFailure);

// Try this also
// login("USER", loginSuccess, loginFailure);
```
**What are Parameters and Arguments?**

>Parameters are the variables that we define in the function declaration. They act as placeholders to receive values.

>Arguments are the actual values that we pass to the function when calling it.

>For example, if I have a function like add(a, b), then a and b are parameters. When I call add(10, 20), then 10 and 20 are the arguments.

>In simple terms, parameters are defined while creating the function, and arguments are passed while calling the function."

**What are Default Parameters?**

>"Default parameters allow us to assign a default value to a function parameter.

>If the caller doesn't pass a value, JavaScript automatically uses the default value instead.

>For example, if I write a function like greet(name = "Guest"), and I call greet() without passing any argument, the output will be 'Guest'.

>In my projects, default parameters help avoid unnecessary undefined values and reduce extra validation code."

**What is the Return Statement?**

>"The return statement is used to send a value back to the function caller.

>Once JavaScript encounters the return statement, it immediately stops executing the remaining code inside that function and returns the specified value.

>For example, if I write a function to calculate the total amount, I use the return statement to send the calculated value back to wherever the function is called.

**What is the difference between Synchronous and Asynchronous Programming?**

>"JavaScript supports both synchronous and asynchronous programming.

>In synchronous programming, the code executes line by line. Each statement waits until the previous statement finishes.

>For example, if there are three tasks, Task 1 completes first, then Task 2, and finally Task 3.

>In asynchronous programming, JavaScript doesn't wait for long-running operations like API calls, database requests, or timers. Instead, it continues executing the remaining code, and once the operation completes, it handles the result later.

>In my projects, whenever I consume backend APIs, I use asynchronous programming with Promises and async/await because it improves application performance and provides a better user experience."

**What is Callback Hell?**

>"Callback Hell is a situation where multiple callbacks are nested inside one another.

>As the number of callbacks increases, the code becomes deeply nested, difficult to read, difficult to debug, and hard to maintain.

>For example, imagine a login process where we first validate the user, then fetch employee details, then retrieve permissions, and finally load dashboard data. If each step depends on the previous callback, the code becomes heavily nested.

>Because of these readability and maintenance issues, Callback Hell is considered a problem.

>To overcome Callback Hell, modern JavaScript introduced Promises and later async/await, which make asynchronous code much cleaner and easier to understand."

**Why is Callback Hell considered a problem?**

>"Callback Hell makes the code difficult to read because callbacks are nested multiple levels deep.

>It also becomes difficult to debug, maintain, and extend the application. That's why nowadays we generally use Promises or async/await instead of deeply nested callbacks."

**How do you solve Callback Hell?**

>"There are multiple ways to solve Callback Hell.

>The most common approaches are using Promises and async/await.

>These approaches flatten the code structure, improve readability, simplify error handling, and make the code easier to maintain."

**Which one do you prefer in your project?**

>"In my projects, I mostly use async/await because the code looks very similar to synchronous code, making it much easier to read, understand, and maintain."

**Higher order function?**
>"A Higher-Order Function is a function that either accepts another function as an argument, returns another function, or both.

>The main purpose of using Higher-Order Functions is to make the code more reusable and flexible.

>In my project, for example, I have a common function to fetch employee data. Different screens need different operations after fetching the data. One screen displays the employee details, another generates a report, and another exports the data.

>Instead of writing separate fetch functions for each operation, I create one common function and pass different callback functions based on the requirement. Because that function accepts another function as an argument, it is called a Higher-Order Function."

**What is the difference between a Callback Function and a Higher-Order Function?**
>"A Callback Function is a function that is passed as an argument to another function and is executed later.

>A Higher-Order Function is a function that accepts another function as an argument, returns another function, or both.

>In simple terms, the Callback Function is the function being passed, whereas the Higher-Order Function is the function receiving or returning another function."

```
Higher-Order Function → Receives Function

Callback Function → Passed Function

```
**Which one executes first?**

>"The Higher-Order Function executes first. Inside it, whenever required, it invokes the Callback Function."

**Built-in Higher-Order Functions?**

>forEach(),map(),filter(),find(),reduce()

>`syntax`

```
array.forEach(function(item, index){

});

array.forEach((item, index) => {

});

```
**What is forEach()?**

>"forEach() is a built-in Higher-Order Function in JavaScript used to iterate through each element of an array.

>It executes a callback function once for every element in the array.

>Unlike map(), forEach() does not return a new array. It is mainly used when we want to perform an operation on each element, such as displaying data, logging values, or updating the UI."

**When do we use forEach()?**

`Use it when you want to:`

>Display each item
>Log values
>Update the UI

**Does forEach() return a new array?**

>"No. forEach() does not return a new array. It simply executes the callback function for each element."

**Can we use break or continue inside forEach()?**

"No. break and continue do not work inside forEach(). If we need to stop iteration early, we usually use a regular for loop or methods like find() or some() depending on the requirement."
