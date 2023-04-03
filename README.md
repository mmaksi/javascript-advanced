# 1. Foundations

ECMAScript engine is required to understand JavaScript.

Brendan Eich created the first ECMAScript engine using C++.

ECMAScript engine has thse parts:

- Parser: to understand the syntax.
- Interpreter: reads the file line by line. It is faster than compiling because it doesn't translate the code to another language.
- Compiler: reads the file ahead of time and spits a new low-level language.

CallStack is where JavaScript keeps track of where we are in the code. It runs in the First In Last, Out mode.

Memory Heap is where JavaScript stores complex data structures like objects.

Stack overflow (recursion) and Memory Leak.

JavaScript uses Mark and Sweep algorithm for its garbage collection feature.

Examples of Memory Leaks: Global variables, event listeners, `setInterval()`.

JavaScript is a single threaded language. It has only one stack. That means that the ECMAScript engine is synchronous.

The Web API is what the browser provides on top of the ECMAScript engine to run asynchronous code.

`runtime image`

Asynchronous JavaScript is run on the Callback Queue. The Event Loop constantly checks whether the call stack is empty. Once it's empty it pushes the asynchronous codde for execution.

# Foundations II

## Execution Context

Every function creates its own execution context.

Initially the ECMAScript engine creates the `global()` execution context.

Whenever a function is called, the execution context is created and added to the call stack.

The Global Execution Context gives us:

- Global Object eg. `window`, `global`
- `this`
- Hoisting

Each execution context tells us what lexical environment we're currently running.

Each execution context creates two phases: creation phase + execution phase.

Functional execution contexts give us access to the `arguments` keyword.

Functional execution creates a _Variable Environment_.

In javaScript, the _Lexical Scope_ (available data and variables where the function was defined) determines our available variables. Not where the function was called (Dynamic Scope).

## Hoisting

- Function declarations are fully hoisted.
- `var` and `function expression` are partially-hoisted.
- Hoisting occurs in every execution context aka whenever the function is called.

## Function Invocation

Function expression is defined at run time, when the function is called.

Function declaration is defined at parse of time, when the compiler reads the code.

Don't use `arguments` keyword and `for in` for optimizing the compiler.

## Static Scope

Lexical Scope = available data and variables where the function was defined.

Each function has access to variables defined in its execution context and its parent's.

## Function Scope vs. Block Scope

Block Scope was introduced with ES6.

## `this` Keyword

`this` is the object that the function is a property of.

For the `this` keyword, it is Dynamically Scoped which means it doesn't matter where it was defined. It matters where it was called.

Arrow functions are lexically scoped.

## call(), apply(), bind()

Every function if JavaScript is an object and it must have the `.call()` method.

`function.call(object, param1, param2)` to call the function on that object with multiple parameters.

`function.call(object, [param1, param2])` to call the function on that object with an array of parameters.

`function.bind(object)` to bind the function to the object and returns a new function. This is usually used to change the context of the `this` keyword.

