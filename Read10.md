# Call stack

A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.

`function greeting() {`
   `// [1] Some codes here`
   `sayHi();`
 `  // [2] Some codes here`
`}`
`function sayHi() {`
 `  return "Hi!";`
`}`

`// Invoke the 'greeting' function`
`greeting();`

# The JavaScript Call Stack - What It Is and Why It's Necessary

*The JavaScript engine (which is found in a hosting environment like the browser), is a single-threaded interpreter comprising of a heap and a single call stack. The browser provides web APIs like the DOM, AJAX, and Timers.*

This article is aimed at explaining what the call stack is and why it is needed. An understanding of the call stack will give clarity to how “function hierarchy and execution order” works in the JavaScript engine.

The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.

The understanding of the call stack is vital to Asynchronous programming (which we will look at in a later article).

In Asynchronous JavaScript, we have a callback function, an event loop, and a task queue. The callback function is acted upon by the call stack during execution after the call back function has been pushed to the stack by the event loop.

But before we jump the gun, let us first attempt to answer the question - What is the call stack?

At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

Let’s break down our definition:

LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

Let us take a look at a code sample to demonstrate LIFO by printing a stack trace error to the console.

function firstFunction(){
  throw new Error('Stack Trace Error');
}

`function secondFunction(){`
  `firstFunction();`
`}`

`function thirdFunction(){`
 ` secondFunction();`
`}`

`thirdFunction();`

You will notice that the arrangement of the functions as a stack begins with the firstFunction() (which is the last function that got into the stack, and is popped out to throw the error), followed by the secondFunction(), and then the thirdFunction() (which is the first function that gets pushed into the stack when the code is executed).

Temporarily store: When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

## JavaScript error messages && debugging

Most of your time as a developer is spent reading code followed by debugging that same code, most likely to be able to read it or solve an “unexpected feature” (which, joking aside, is more correctly known as a “bug”).

`(function testing(){`
  `var obj = {`
   ` add`
  `}`
  `function add(a, b) {`
    `var result = a + b`
   ` return result.split('')`
  `}`
  `var stringResult = obj.add("1", "2")`
 ` var result = obj.add(1, 2)`
`})()`

Types of error messages
The first thing that indicates you that something is wrong with your code is the (in)famous error message that the one we saw just moments ago, it usually appears on your console (being developer tools of the browser, terminal or whatever else you are using).
For those already used to programming, reading an error message is like second nature, for everybody else, is something you learn either you like it or not so might as well talk a bit about each of them.
Reference errors
This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

This is also a common thing when using const and let, they are hoisted like var and function but there is a time between the hoisting and being declared so when you try to access them a reference error occurs, the fact that this happens to let and const is called Temporal Dead Zone (TDZ).