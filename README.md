# JavaScriptTheory
**what is javascript? Can you explain what JavaScript is?**


>JavaScript is one of the core programming languages I've been working with to develop web applications. It's a single-threaded, event-driven language, and it supports asynchronous programming using Promises and async/await. In my projects, I mainly use JavaScript to implement business logic, process data, and integrate APIs

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


