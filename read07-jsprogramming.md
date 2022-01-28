# Programming with JavaScript

## Control flow

It's the order in which the computer executes script statements, from first to last line (unless conditionals, loops, or other structures change the control flow.

ex. of conditional structure prompting filling in of a required entry form that was left empty:
```
if (field==empty) {
  promptUser();
  } else {
    submitForm();
  }
```
Don't only read from start to finish. The order of execution is found in the nitty gritty of program structure.


## JavaScript Functions

They are blocks of code made to perform a particular task, and are executed when "something" invokes (or calls) it.
```
function myFunction(p1, p2) {
  return p1 * p2;   // The function returns the product of p1 and p2
}
```

### JS Function Syntax

A JS function is defined with `function` keyword, followed by a **name** and then followed by parentheses **()**.
- names can contain letters, digits, underscores and dollar signs (just like variables)
- parameter names in parentheses should be separated by commas
- the function will execute the code that is written into the curly brackets **{}**.
```
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```
- the function's "**arguments** are the **values** received by the function when it is invoked".

Functions can be invoked through:
- events (such as user clicking a button)
- being called by the JavaScript code
- self-invocation (automatic calling)

A function will stop executing when it reaches a `return` statement.
- (*im a little confused by what this means*)--> if the function was invoked from a statement, JS will "return" to execute the code afer the invoking statement.
- fucntions often compute a **return value**, which is returned back to the "caller".
- example:
```
let x = myFunction(4, 3);   // Function is called, return value will end up in x

function myFunction(a, b) {
  return a * b;             // Function returns the product of a and b
}
```
The result in x will be: `12`

Functions are useful!
- allow code to be reused: define the code once, and use it many times.
- use same code many times with different arguments, to produce different results.
- example, a function converting Fahrenheit to Celsius:
```
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}
document.getElementById("demo").innerHTML = toCelsius(77);
```

The () Operator Invokes the Function
- from example above: `toCelsius` refers to function object, `toCelsius()` refers to function result
- access function without `()` will return function object, not function result.

Functions can be used as variable values, example:
```
let x = toCelsius(77);
let text = "The temperature is " + x + " Celsius";
```
even do so directly plugging the function in as the variable value:
`let text = "The temperature is " + toCelsius(77) + " Celsius";`

Local variables are convenient
- if variables are declared *within* a JS function, they become **local** to the function
- consequently, they can only be accessed from (and recognized) within their function
- benefit: variables with the same name can be used in different functions
- essentially, they are created when a function starts, and deleted when it ends
- example:
```
// code here can NOT use carName

function myFunction() {
  let carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```


## JavaScript Operators

[This is a good reference article so I'm just linking to it](https://www.w3schools.com/js/js_operators.asp) instead of outlining it.

I'll just include these topline useful takeaways:
- assignment operator `=` assigns a value to a variable
- `x = y` same as `x = y`
- `x += y` same as `x = x + y`
- `x -= y` same as `x = x - y`
- same with other operators like multiplication `*`, exponentiation `**`, division `/`, and modulus (division remainder) `%`
- increment operator is `++`, decrement is `--`
- article also covers JS String Operators, Adding Strings and Numbers, JS Comparison Operators, JS Logical Operators, JS Type Operators, and JS Bitwise Operators








