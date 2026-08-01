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
> It is mainly used when we want to perform an action on each element without creating a new array."

**When do we use forEach()?**

`Use it when you want to:`

>Display each item
>Log values
>Update the UI

**Does forEach() return a new array?**

>"No. forEach() does not return a new array. It simply executes the callback function for each element."

**Can we use break or continue inside forEach()?**

"No. break and continue do not work inside forEach(). If we need to stop iteration early, we usually use a regular for loop or methods like find() or some() depending on the requirement."

**What is map()?**

>"map() is a built-in Higher-Order Function in JavaScript that is used to transform each element of an array and return a new array.

>It executes the callback function for every element and stores the returned values in a new array.

>Unlike forEach(), map() always returns a new array without modifying the original array."

**Why do we use map()?**

>We use map() when we want to:
>Transform data
>Modify values
>Create a new array
>without changing the original array.

```
`syntax`

array.map(function(item, index) {

    return modifiedValue;

});

array.map((item, index) => {

    return modifiedValue;

});

```
**What is filter()?**

>"filter() is a built-in Higher-Order Function in JavaScript that is used to filter elements from an array based on a condition.

>It executes the callback function for every element. If the condition returns true, the element is included in the new array. If it returns false, the element is excluded.

>filter() always returns a new array and does not modify the original array."

**Why do we use filter()?**

`We use filter() when we want to:`

>Search data
>Filter active users
>Filter products
>Filter employees
>Filter records based on a condition.

```
array.filter(function(item, index){

    return condition;

});

array.filter((item, index) => {

    return condition;

});

```
**Does filter() return one object?**

>It always `returns an array`, even if only one element matches.

**What is find()?**

>"find() is a built-in Higher-Order Function in JavaScript used to find the first element in an array that satisfies a given condition.

>It executes the callback function for each element until it finds the first matching element. Once a match is found, it stops searching and returns that element.

>If no element matches the condition, it returns undefined."

**Why do we use find()?**

We use find() when we need only one matching record.

`Examples:`

>Find an employee by ID
>Find a product by Product ID
>Find a customer by Email
>Find an order by Order Number

```
syntax

array.find(function(item){

    return condition;

});

array.find(item => item.id === 101);

```
**Difference between filter() and find()?**

| `filter()`                       | `find()`                                |
| -------------------------------- | --------------------------------------- |
| Returns all matching elements    | Returns only the first matching element |
| Returns an array                 | Returns a single object/value           |
| Continues checking every element | Stops after the first match             |

**What happens if no record is found?**

>find() returns undefined if no element satisfies the condition."

**When would you use find() instead of filter()?**

>"I use find() when I need only one matching record, such as searching for an employee by ID or a product by Product ID. Since find() stops after the first match, it's more efficient than filter(), which checks the entire array and returns all matching elements."

**What is reduce()?**

>"reduce() is a built-in Higher-Order Function in JavaScript used to reduce an array into a single value.

>It executes a callback function for each element and accumulates the result into one final value.

>We commonly use reduce() to calculate totals, sums, averages, counts, or to transform an array into a single object."

**Why do we use reduce()?**

>Whenever you need one final result from an array.

`Examples:`

>Total salary
>Total cart amount
>Total order value
>Count employees
>Group data

```
syntax:

array.reduce(function(accumulator, currentValue) {

    return updatedAccumulator;

}, initialValue);

```
**Difference between map(), filter(), find(), and reduce()?**


| Method     | Purpose                            | Returns             |
| ---------- | ---------------------------------- | ------------------- |
| `map()`    | Transform data                     | New array           |
| `filter()` | Filter data                        | New array           |
| `find()`   | Find first matching element        | Single object/value |
| `reduce()` | Combine all values into one result | Single value        |

**What is Lexical Scope?**

>"Lexical Scope means a function can access variables from its own scope and its outer scope.

>In simple terms, an inner function can access variables from its parent function and the global scope, but a parent function cannot access variables declared inside its child function."

`example`
```
let company = "SAP";

function project() {

    let projectName = "Product Cart";

    function developer() {

        console.log(company);
        console.log(projectName);

    }

    developer();

}

project();

"In this example, the developer() function is defined inside the project() function. Since it's written inside project(), it can access the projectName variable from its parent function and the company variable from the global scope.

This behavior is called Lexical Scope.

```
**What is a Closure?**

>"A Closure is created when an inner function remembers and can access the variables of its outer function even after the outer function has finished executing.

```
function outer() {

    let message = "Hello";

    function inner() {

        console.log(message);

    }

    return inner;

}

const display = outer();

display();

```
*`difference between closure and lexical scope`*

>Lexical Scope → An inner function can access variables from its outer function.
>Closure → An inner function remembers those outer variables even after the outer function has finished executing.

**What is a Promise?**

>"In my project, whenever I call a backend API or an external service, JavaScript doesn't get the response immediately because those operations are asynchronous. It has to wait for the server to process the request and send back the response.

>Before Promises, we mainly handled these asynchronous operations using callbacks. When multiple API calls depended on each other, the code became deeply nested, making it difficult to read, debug, and maintain. This problem is called Callback Hell.

>To solve this problem, JavaScript introduced Promises.

>A Promise represents the future result of an asynchronous operation. It doesn't return the result immediately. Instead, it waits for the operation to complete and finally returns either a successful response or an error." "So, instead of blocking the execution, JavaScript continues executing other code and processes the Promise once the response is available."

**Can you give a real-time example?**

>In my SAP CAP application, when the user opens the Employee screen, my UI5 application calls the CAP backend to fetch employee data.

>Since the backend takes some time to respond, JavaScript cannot return the data immediately. At that moment, the API returns a Promise. While the Promise is in progress, it's in the Pending state.

>If the backend successfully returns the employee data, the Promise becomes Fulfilled, and I display the data in the UI.

>If the API fails because of a network issue or server error, the Promise becomes Rejected, and I handle the error by showing an appropriate message to the user.

**If callbacks can already handle success and failure, why were Promises introduced?**

>For example, suppose I need to perform four asynchronous tasks in sequence. The second task depends on the first, the third depends on the second, and the fourth depends on the third. Using callbacks, each operation has to be written inside the previous callback, making the code deeply nested. This is known as Callback Hell.

>As the application grows, the code becomes difficult to read, debug, and maintain. We also end up writing error handling repeatedly for each callback.

>Promises were introduced to solve this problem. They allow us to chain asynchronous operations using .then() and handle errors in one place using .catch(). This results in cleaner, more readable, and maintainable code."

**What are the states of a Promise?**

"A Promise has three states:

Pending
Fulfilled
Rejected

>When a Promise is created, it starts in the Pending state because the asynchronous operation is still in progress.

>If the operation completes successfully, the Promise moves to the Fulfilled state and returns the result.

>If the operation fails, the Promise moves to the Rejected state and returns an error."

>Once a Promise is fulfilled or rejected, its state cannot change again."

**then() catch(), finally()?**

>then()=>then() block its handle the reslove state . and then its always return the new promise . we can perfrom the multiple async operations  so its called as a `promise chaning`.

>catch()=> catch() block its handle the reject state. and catch its retrun the error state. 

>finally()=>finally() method is used to execute cleanup code after a Promise completes. its regradless the its reject or fullfield . it's commonly used to hide loaders, close connections, or perform cleanup tasks."

**What is Promise Chaining?**

>"Promise Chaining is the process of executing multiple asynchronous operations one after another using multiple .then() methods. Since every .then() returns a new Promise, we can chain multiple .then() methods together. The output of one .then() becomes the input of the next .then()."

```
function login() {
    return Promise.resolve("Login Successful");
}

login()
    .then((result) => {
        console.log(result);

        return "Fetching Employee...";
    })
    .then((employee) => {
        console.log(employee);

        return "Fetching Department...";
    })
    .then((department) => {
        console.log(department);

        return "Fetching Salary...";
    })
    .then((salary) => {
        console.log(salary);
    })
    .catch((error) => {
        console.log(error);
    });
output:
Login Successful
Fetching Employee...
Fetching Department...
Fetching Salary...
```
**What is Promise.all()?**
>"The Promise.all() method is used to execute multiple Promises in parallel. It waits until all the Promises are completed successfully. If every Promise is fulfilled, it returns all the results as an array. If any one Promise is rejected, Promise.all() immediately rejects and returns that error."

`Imagine your dashboard needs to load:`

>Employee Details
>Department Details
>Project Details

>These three API calls are independent.

>Instead of calling them one after another, we can call them simultaneously.This improves performance because all three requests run at the same time.

>Even though two Promises succeeded,one rejection causes the entire Promise.all() to fail.

`Example`

```
const employeePromise = Promise.resolve("Employee Data");
const departmentPromise = Promise.resolve("Department Data");
const projectPromise = Promise.resolve("Project Data");

Promise.all([
    employeePromise,
    departmentPromise,
    projectPromise
])
.then((result) => {
    console.log(result);
})
.catch((error) => {
    console.log(error);
});

```

**What is Promise.allSettled()?**

>"The Promise.allSettled() method is used to execute multiple Promises in parallel. Unlike Promise.all(), it waits for all Promises to complete, regardless of whether they are fulfilled or rejected. Instead of failing immediately, it returns the status and result of every Promise."

**Why was it introduced?**

```
Imagine this scenario:

Your application loads

Employee API 
Department API 
Project API 

Using

Promise.all()

the entire operation fails because one API failed.

Sometimes we don't want that.

We want to know

Which API succeeded?
Which API failed?

That's why JavaScript introduced

Promise.allSettled()

```
`Example coding`

const employee = Promise.resolve("Employee Loaded");

const department = Promise.reject("Department Failed");

const project = Promise.resolve("Project Loaded");

Promise.allSettled([
    employee,
    department,
    project
])
.then((result) => {

    console.log(result);

});

```
**When do you use Promise.allSettled()?**

>"I use Promise.allSettled() when I need the result of every asynchronous operation, even if some of them fail."

**What is Promise.race()?**

>"The Promise.race() method executes multiple Promises in parallel and returns the result of the Promise that settles first, whether it is fulfilled or rejected. It doesn't wait for the remaining Promises."

```
Real-Time Example

Suppose your application calls data from two servers.

Server 1
Server 2

Whichever server responds first,

your application uses that response.

That's exactly what Promise.race() does.

```
const server1 = new Promise((resolve) => {

    setTimeout(() => {
        resolve("Server 1 Response");
    }, 3000);

});

const server2 = new Promise((resolve) => {

    setTimeout(() => {
        resolve("Server 2 Response");
    }, 1000);

});

Promise.race([server1, server2])
.then((result) => {

    console.log(result);

});

```
**What is Promise.any()?**


>"The Promise.any() method executes multiple Promises in parallel and returns the first successfully fulfilled Promise. It ignores rejected Promises and continues waiting until one Promise succeeds."

>If every Promise fails.**It throws anAggregateError because all Promises failed.**
```
const server1 = Promise.reject("Server 1 Failed");

const server2 = new Promise((resolve) => {

    setTimeout(() => {

        resolve("Server 2 Success");

    },1000);

});

Promise.any([server1,server2])

.then((result)=>{

    console.log(result);

});

```

**difference between promise.race() and promise.any()?**

| Promise.race()                                 | Promise.any()                 |
| ---------------------------------------------- | ----------------------------- |
| First settled Promise wins                     | First successful Promise wins |
| Success or Failure                             | Success only                  |
| If first Promise rejects → rejects immediately | Ignores rejected Promises     |
| Waits for first settled                        | Waits for first fulfilled     |

**What is async in JavaScript?**

>Async/Await is just a cleaner way of writing Promise code.

>"The async keyword is used to declare an asynchronous function. An async function always returns a Promise,

**What is await?**

>"await is used inside an async function to pause the execution until a Promise is completed. Once the Promise is fulfilled, await returns the resolved value and continues executing the remaining code."

**Why was Async/Await introduced if Promises already exist?**

>"Promises solved the Callback Hell problem, but when an application has many dependent asynchronous operations, using multiple .then() methods can still make the code difficult to read and maintain.

>Async/Await was introduced to make asynchronous code look like synchronous code. It improves readability, simplifies debugging, and makes error handling easier using a single try...catch block."

**What are the advantages of Async/Await?**

`The main advantages are:`

>Cleaner and more readable code.
>Easier to understand because it looks like synchronous code.
>Simpler error handling using one try...catch block.
>Easier to debug because execution flows line by line."

| Promise                                   | Async/Await                                  |
| ----------------------------------------- | -------------------------------------------- |
| Uses `.then()` and `.catch()`             | Uses `async`, `await`, and `try...catch`     |
| Can become long with many `.then()` calls | Looks like normal synchronous code           |
| Error handling with `.catch()`            | Error handling with `try...catch`            |
| Good for chaining                         | Better readability for sequential operations |

**How do you handle errors in Async/Await?**

>"In Async/Await, I handle errors using a try...catch block. I place the asynchronous code inside the try block. If all operations are successful, the code executes normally. If any Promise is rejected or an error occurs, execution immediately moves to the catch block, where I handle the error."

**when will execute the catch block?**

>Network fails
>Backend returns 500
>Server is down
>Execution automatically goes to: catch(error).

**Example answer**
>"In my project, I use try...catch to handle errors while working with asynchronous operations like API calls. I place all the await statements inside the try block. If every API call is successful, the code continues executing normally. If any API fails due to a network issue, server error, or invalid response, JavaScript immediately stops executing the remaining code inside the try block and moves to the catch block. Inside the catch block, I handle the error by logging it or displaying an appropriate error message to the user."

**Why do we use try...catch?**

>"In my project, I use try...catch around API calls to handle network errors, backend exceptions, or invalid responses, so the application can show a meaningful message to the user instead of failing silently."

**What is call stack?**

>"The Call Stack is a LIFO data structure used by the JavaScript engine to manage function execution. Every time a function is called, it is pushed onto the stack. After execution completes, it is popped from the stack. Since JavaScript is single-threaded, only one function executes at a time."

**What are Web APIs?**
>Web APIs are provided by web browser not by java script such as
```
>                Browser
        ----------------------
        |      Web APIs      |
        |--------------------|
        | setTimeout()       |
        | setInterval()      |
        | fetch()            |
        | DOM Events         |
        | Local Storage      |
        | Geolocation        |
        ----------------------
                 ▲
                 |
          JavaScript Engine
```
example:

>Web APIs are browser features used to handle asynchronous operations. For example, when JavaScript executes setTimeout(), it doesn't wait for the timer. Instead, it gives that task to the browser. "After the timer finishes, the browser places the callback function into the Callback Queue (Macrotask Queue). The Event Loop checks whether the Call Stack is empty. If it is empty, the Event Loop moves the callback from the Callback Queue into the Call Stack for execution."

**Real-Time Example**

Suppose you write:

setTimeout(() => {
    console.log("Hello");
}, 2000);

**What happens?**

>setTimeout() enters the Call Stack.
>The browser recognizes it as a Web API.
>The browser starts a 2-second timer.
>Meanwhile, the Call Stack continues executing the remaining JavaScript code.
>After 2 seconds, the callback is moved to the Callback Queue.
>The Event Loop checks whether the Call Stack is empty.
>If it's empty, the callback is pushed into the Call Stack and executed.

**What is the Callback Queue?**

>"The Callback Queue, also called the Macrotask Queue, is a queue where completed asynchronous callback functions wait before they are executed. When an asynchronous operation like setTimeout() or a DOM event finishes, its callback is placed into the Callback Queue. The callback doesn't execute immediately. It waits until the Call Stack becomes empty. Then the Event Loop moves the callback into the Call Stack for execution."

**What is the Microtask Queue?**


>"The Microtask Queue is a special queue that stores high-priority asynchronous callbacks. Callbacks created by Promises, queueMicrotask(), and MutationObserver are placed in the Microtask Queue. Before processing the Callback Queue (Macrotask Queue), the Event Loop always checks and executes all tasks in the Microtask Queue first."

| **Feature**         | **Microtask Queue**                            | **Callback Queue (Macrotask Queue)** |
| ------------------- | ---------------------------------------------- | ------------------------------------ |
| **Priority**        | High Priority                                  | Low Priority                         |
| **Executed When**   | Immediately after the Call Stack becomes empty | After all Microtasks are completed   |
| **Processed By**    | Event Loop                                     | Event Loop                           |
| **Common APIs**     | `Promise.then()`                               | `setTimeout()`                       |
|                     | `Promise.catch()`                              | `setInterval()`                      |
|                     | `Promise.finally()`                            | DOM Events (`click`, `change`)       |
|                     | `queueMicrotask()`                             | `MessageChannel` (less common)       |
|                     | `MutationObserver` (rare)                      | `postMessage` (less common)          |
| **Execution Order** | Executes first                                 | Executes after Microtasks            |

**Why does Promise.then() execute before setTimeout()?**

>"Promise.then() callbacks are stored in the Microtask Queue, while setTimeout() callbacks are stored in the Callback Queue (Macrotask Queue). The Event Loop always gives higher priority to the Microtask Queue. Therefore, once the Call Stack becomes empty, all microtasks are executed first, and only then are macrotasks executed."

**What is the Event Loop?**
 
>"The Event Loop is a mechanism that continuously monitors the Call Stack and the task queues. Whenever the Call Stack becomes empty, it first checks the Microtask Queue and executes all pending microtasks. Once the Microtask Queue is empty, it checks the Callback Queue (Macrotask Queue) and moves one callback into the Call Stack for execution. This process repeats continuously, allowing JavaScript to handle asynchronous operations efficiently."

```
                    JavaScript Code
                           │
                           ▼
                    ┌─────────────┐
                    │ Call Stack  │
                    └─────────────┘
                           │
          ┌────────────────┴────────────────┐
          │                                 │
          │ Synchronous Code                │ Asynchronous Code
          │ (console.log, functions)        │ (setTimeout, fetch...)
          │                                 │
          ▼                                 ▼
     Execute Immediately             ┌─────────────────┐
                                     │ Browser Web APIs│
                                     └─────────────────┘
                                              │
                          ┌───────────────────┴───────────────────┐
                          │                                       │
                          ▼                                       ▼
                Microtask Queue                          Callback Queue
             (Higher Priority)                      (Macrotask Queue)
             -------------------                    -------------------
             Promise.then()                         setTimeout()
             Promise.catch()                        setInterval()
             Promise.finally()                      DOM Events
             queueMicrotask()                       MessageChannel
                          │                                       │
                          └───────────────┬───────────────────────┘
                                          ▼
                                   ┌──────────────┐
                                   │ Event Loop   │
                                   └──────────────┘
                                          │
                                          ▼
                           Is Call Stack Empty?
                                          │
                                  Yes     ▼
                                   │  Execute ALL
                                   │  Microtasks
                                   │
                                   ▼
                          Execute ONE Callback
                          from Callback Queue
                                   │
                                   ▼
                              Call Stack
                                   │
                                   ▼
                               Execute
                                   │
                                   ▼
                                 Repeat

```
**What is an Object?**

>"An object is a collection of related data and behavior. It stores information in the form of key-value pairs. In real-time projects, we use objects to represent real-world entities like an employee, customer, product, or order. Along with data, an object can also contain methods to perform operations related to that data." `REFERENECE :VS CODE`

**Object Destructuring?**
>"Object destructuring is an ES6 feature that allows us to extract object properties directly into variables. Instead of accessing each property using dot notation multiple times, we can extract all the required properties in a single line. It makes the code cleaner, more readable, and easier to maintain. In my project, I mainly use object destructuring while handling backend API responses and CAP request data."

**What is the Spread Operator?**
>"The spread operator is an ES6 feature that I mainly use to create a copy of an object, merge multiple objects, or update specific properties without modifying the original object. Instead of manually copying each property, I can copy the entire object in a single line, which makes the code cleaner and easier to maintain."

`shallow copy and deep copy`

"In JavaScript, we create a copy of an object mainly in two ways: shallow copy and deep copy. I choose which one to use based on the type of data I'm working with."

**Shallow Copy**

>"I use a shallow copy when my object contains only simple properties or when I need to update only top-level properties. I usually create it using the spread operator (...) or Object.assign(). It's lightweight and performs well."

Real-time example:

>"In my SAP UI5 application, after receiving employee data from the backend, if I only need to update the employee's salary or status before displaying it, I create a shallow copy using the spread operator and update the required property."

```
const updatedEmployee = {
    ...employee,
    salary: 60000
};

```

**Deep Copy**

>"I use a deep copy when the object contains nested objects and I don't want changes in the copied object to affect the original object. In modern JavaScript, I use structuredClone() to create a completely independent copy."

`Real-time example:`

>"Suppose the employee object contains an address object or project details. Before editing those nested values, I create a deep copy using structuredClone(). This ensures the original data remains unchanged until the user saves the changes."

```
const copy = structuredClone(employee);

```

**Best Closing Statement**

>"So, in my project, I use shallow copy for simple property updates because it's efficient. Whenever the object contains nested data and I need complete isolation between the original and copied object, I use a deep copy."

**What is JSON? Where have you used it in your project?**


>"JSON stands for JavaScript Object Notation. It is a lightweight format used to exchange data between the frontend and the backend. In my SAP UI5 and CAP project, whenever the UI communicates with the CAP service through APIs, the request and response data are transferred in JSON format."

`Example`

>"For example, in my project, when a user creates a new employee from the SAP UI5 application, they enter details like employee ID, name, department, and salary. After clicking the Save button, the UI sends those details to the CAP backend as JSON."

**What is JSON.stringify()?**

>"Whenever the user enters details in the UI, JavaScript first creates an object with those values. Before sending the data to the backend through an API, that object needs to be converted into a JSON string because HTTP communication happens using JSON. JSON.stringify() is the JavaScript method used for that conversion. In my SAP UI5 and CAP project, I don't call JSON.stringify() manually because the framework handles it automatically, but internally this conversion happens before the request is sent to the backend."

**What is JSON.parse()?**

>"JSON.parse() is used to convert a JSON string into a JavaScript object. After receiving a response from the backend, the JSON data needs to be converted into an object so that we can access its properties and use it in the application. In my SAP UI5 and CAP project, I don't call JSON.parse() manually because the framework automatically performs this conversion before the response reaches my application."

`Serialization` means converting an object into a JSON string so it can be sent to a server or stored.
`Deserialization` means converting that JSON string back into a JavaScript object so we can use it in our application.

**What is an Array?**
>"An array is a built-in JavaScript data structure used to store multiple values in a single variable. Each value is stored at a specific index, starting from 0. Arrays help us manage collections of related data efficiently."

```
How to Create an Array?

const employees = [];

const employees = new Array();

```
**What is push()?**

>"push() is a built-in JavaScript array method used to add one or more elements to the end of an array. It modifies the original array and returns the new length of the array."

**What is pop()?**

>"pop() is a built-in JavaScript array method used to remove the last element from an array. It modifies the original array and returns the removed element."

**What is shift()?**

>"shift() is a built-in JavaScript array method used to remove the first element from an array. It modifies the original array and returns the removed element."

**What is unshift()?**

>"unshift() is a built-in JavaScript array method used to add one or more elements to the beginning of an array. It modifies the original array and returns the new length of the array."

**Array itreation methods**

```

for loop
for...of
forEach()

```

``` ARRAY METHODS ```

| Method          | Purpose                                | Returns                      | Modifies Original Array? | CAP Real-Time Use                         |
| --------------- | -------------------------------------- | ---------------------------- | ------------------------ | ----------------------------------------- |
| `push()`        | Add element at end                     | New length                   | ✅ Yes                    | Add a temporary record                    |
| `pop()`         | Remove last element                    | Removed element              | ✅ Yes                    | Remove last processed record              |
| `shift()`       | Remove first element                   | Removed element              | ✅ Yes                    | Remove first queued record                |
| `unshift()`     | Add element at beginning               | New length                   | ✅ Yes                    | Insert priority record                    |
| `forEach()`     | Perform an action on every element     | `undefined`                  | ❌ No                     | Logging, validation, auditing             |
| `map()`         | Transform each element                 | New array                    | ❌ No                     | Format API response                       |
| `filter()`      | Select matching elements               | New array                    | ❌ No                     | Return only active employees              |
| `find()`        | Return first matching element          | Object / Value / `undefined` | ❌ No                     | Find employee by ID                       |
| `findIndex()`   | Return index of first matching element | Index / `-1`                 | ❌ No                     | Find record position before update/delete |
| `some()`        | Check if at least one element matches  | `true` / `false`             | ❌ No                     | Check if employee already exists          |
| `every()`       | Check if all elements match            | `true` / `false`             | ❌ No                     | Validate all employees are active         |
| `reduce()`      | Convert array into a single value      | Single value                 | ❌ No                     | Total salary, dashboard summary           |
| `slice()`       | Copy part of an array                  | New array                    | ❌ No                     | Pagination, first 10 records              |
| `splice()`      | Add, remove, or replace elements       | Removed elements             | ✅ Yes                    | Remove/update temporary records           |
| `sort()`        | Sort array                             | Sorted array                 | ✅ Yes                    | Sort employees by salary/name             |
| `reverse()`     | Reverse array order                    | Reversed array               | ✅ Yes                    | Show latest records first                 |
| `includes()`    | Check if value exists                  | `true` / `false`             | ❌ No                     | Validate role/department                  |
| `indexOf()`     | Find position of value                 | Index / `-1`                 | ❌ No                     | Find array position                       |
| `lastIndexOf()` | Find last occurrence                   | Index / `-1`                 | ❌ No                     | Find last duplicate                       |


```

```

| Comparison                  | Key Difference                                                              |
| --------------------------- | --------------------------------------------------------------------------- |
| `map()` vs `forEach()`      | `map()` returns a new array; `forEach()` returns nothing.                   |
| `filter()` vs `find()`      | `filter()` returns all matches; `find()` returns the first match.           |
| `find()` vs `findIndex()`   | `find()` returns the object; `findIndex()` returns its index.               |
| `some()` vs `every()`       | `some()` checks at least one; `every()` checks all.                         |
| `slice()` vs `splice()`     | `slice()` copies without modifying; `splice()` modifies the original array. |
| `includes()` vs `indexOf()` | `includes()` returns a boolean; `indexOf()` returns the position.           |

```
