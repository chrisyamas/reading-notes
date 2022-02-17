
# Notes on Duckett JS book, Ch. 10: "Error Handling & Debugging"

To find the source of an error, it helps to know how scripts are processed. The order in which statements are executed can be complex; some tasks cannot complete until another statement or function has been run.

The JS interpreter uses the concept of execution contexts. There is one global execution context: plus, each function creates a new execution context. They correspond to variable scope.

The JS interpreter processes one line of code at a time. When a statement needs data from another function, it stacks (or piles) the new function on top of the current task.

Each time a script enters a new execution context, there are two phases of activity:

1. Prepare: the new scope is created; variables, functions, and arguments are created
2. Execute: now it can assign values to variables; reference functions and run their code; execute statements

In the interpreter, each execution context has its own `variables` object. It holds the variables, functions, and parameters available within it. Each execution context can also access it parent's `variables` object.

If a JS statement generates an error, then it throws and exception. At that point, the interpreter stops and looks for exception-handling code.

Error objects can help you find where your mistakes are and browsers have tools to help you read them.

There are two things to do to deal with errors: (1) debug the script to fix errors and (2) handle errors gracefully.

Debugging is about deduction: eliminating potential causes of an error. Here is a workflow for techniques you will meet over the next 20 pages. Try to narrow down where the problem might be, then look for clues.

The JS console will tell you when there is a problem with a script, where to look for the problem, and what kind of issue it seems to be. The JS console is just one of several developer tools that are found in all modern browsers.

Browsers that have a console have a `console` object, which has several methods that you rscript can use to display data in the console. The object is documented in the Console API.

In addition to `console.log()` there is `console.info()` which can be used for general information, `console.warn()` which can be used for warnings, and `console.error()` which can be used to hold errors. To write a set of related data to the console, you can use the `console.group()` method to group the messages together and indicate the end of the group with `console.groupEnd()`.

You can pause the execution of a script on any line using breakpoints. Then you can check the values stored in variables at that point in time.

If you set multiple breakpoints, you can step through them one-by-one to see where values change and a problem might occur.

You can indicate that a breakpoint should be triggered only if a condition that you specify is met. The condition can use existing variables.

The `debugger` keyword can be used within a conditional statement so that it only triggers the breakpoint if the condition is met.

If you know your code might fail, use `try`, `catch`, and `finally`. Each one is given its own code block.

If you know something might cause a problem for your script, you can generate your own errors before the interpreter creates them.

Other tips to try to use when debugging scripts:

- try code in another browser
- write numbers to the console to see which items get logged
- strip it back, removing parts of code until you're down to the minimum you need
- explain the code (as if to someone else, rubber duck)
- search google or stackoverflow, etc
- add problematic code to a code playground site like JSBin.com, JSFiddle.com, or Dabblet.com
- use validation tools like jslint, jshint, jsonlint, or a jQuery debugger plugin available for Chrome