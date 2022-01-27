# Notes on Javascript Readings

## Intro to JavaScript

Javascript is "a lightweight, interpreted, or just-in-time compiled programming language with first-class functions".


## Input Output in plain JavaScript

Some new type of code I haven't seen before:
```
<body>

First name: <input id="first_name">
Last name: <input id="last_name">
<button id="say">Say hi!</button>
 
<hr>
<div id="result"></div>
 
<script>
function say_hi() {
    var fname = document.getElementById('first_name').value;
    var lname = document.getElementById('last_name').value;
 
    var html = 'Hello <b>' + fname + '</b> ' + lname;
 
    document.getElementById('result').innerHTML = html;
}
 
document.getElementById('say').addEventListener('click', say_hi);
</script>

<body>
```

## JavaScript Variables

4 Ways to Declare a JavaScript Variable:
- Using `var`
- Using `let`
- Using `const`
- Using nothing

For constant variables, use `const`.

They follow logic. It's all just math!

Note: JavaScript identifiers **are** case sensitive.

Assignment operator (assigning value) --> =

"equal to" operator --> ==

Two main data types are numbers and strings.

Declare a variable with `var` or `let`.

Assign a value using =

You can assign a value when you create a variable:
```
let age = 29
```
When declaring multiple variables in one statement, separate variables with a comma, and end with semicolon. You can span multiple lines if you choose.

A variable without a declared value will have value of `undefined`.

If re-declaring a JavaScript variable with `var`, it will not lose its value.
But you cannot re-declare a variable declared with `let` or `const`. Won't work.

