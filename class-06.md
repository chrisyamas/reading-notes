
# Notes on John Sonmez's piece on The Problem Domain

Summary: coding is much harder when we don't fully understand the problem we are trying to solve, so we need to either gain a better understanding of the problem at hand or to reduce the scope to a smaller, more easily conceptualized piece of the problem and then work out from there.

This is why John uses the same, simple application of a "Protein Tracker" to teach a variety of new concepts to his students throughout his coding courses. When we are familiar with one part of the problem, it makes solving the less familiar parts more doable. The alternative (complete unfamiliarity) can be overwhelming to the point of paralysis (or at least sluggish progress).

Such an alternative is exemplified by John's example of a double-sided, homogenous pattern jigsaw puzzle.

He further compares code-writing to solving a jigsaw puzzle, where the "big picture" being modeled/solved is the problem domain and coders pull from this big picture to compile the components necessary for the solution. This is very hard in the real word, as programmers are given incomplete information, the information they do get is difficult to understand, and the "picture" can look completely different based on one's perspective.

He discusses how easy it was to code at a firm years ago utilizing the "waterfall approach" to development (which breaksdown activities into linear sequential phases, each phase depending on the deliverables of the previous one). And while he frowns upon that approach to software development today, it illustrates the point that having more information from the get-go makes the project much easier to complete in a shorter amount of time (i.e. talk to the client/employer more fully at the start to get the most complete understanding possible of what exactly you are needing to build for them).

To make programming easier:

1. Make the problem domain easier/simpler/smaller in scope
2. Get better at understanding the problem domain

# Notes on JS Primitive Values + Object References article

Understanding the difference between primitive values and object references is crucial to mastering JS programming.

JS has eight data types:

1. Boolean
2. Null
3. Undefined
4. Number
5. BigInt
6. String
7. Symbol
8. Objects

Arrays, functions, and dates are not specificially named in this list because they are all "just objects under the hood".

When a variable is assigned with an object (rather than a primitive value like `4` or `bar`), the variable does not contain the value of the object directly: rather, it contains a **reference** to the object. For instance:
```
const moe = {
  name: 'Moe Szyslak',
  occupation: 'Bartender',
  voicedBy: 'Hank Azaria'
}
```
in the above code block, JS would create the object and store it in computer memory, and the variable `moe` contains a reference to the memory address that stores the object currently (again, does not store the object directly).

Primitive values are **immutable** (cannot be changed or mutated) while object references are **mutable** (CAN be changed or mutated).

Example, if `let word = 'snow'` is executed, and then I attempted to change/rewrite the first character in `'snow'` from `s` to `k` by running `word[0] = 'k'`, it would not work because the string is immutable (a `console.log(word)` would just return `"snow"`). You wouold have to create a new string from the old one and reassign the `word` variable with the new value:
```
word = `k${word.slice(1)}`
console.log(word) // "know"
```

Arrays, on the other hand, are an example of mutable data: they can be altered directly.

Since objects are stored as references, special care must be taken when duplicating objects and when performing equality checks on objects.

Understanding how these operations work can be confusing for newcomers to JavaScript, but they make sense once you understand how the language’s type system works.

Developing a strong grasp of primitive values, object references, and mutability is a critical step in progressing past the beginner stages of JavaScript programming.

This knowledge will help you identify bugs, understand key differences in programming paradigms, and help you understand your code at a deeper level.

# Notes on Duckett JS book

# Ch. 3: "Object Literals" (pp. 100-105)

Objects group together a set of variables and functions to create a model of something you would recognize from the real world. In an object, variables and functions take on new names.

In an object, variables become known as properties and funcfions become known as methods.

In an object, the name-value pair is rather a key-value pair.

Literal notation is the easiest and most popular way to create objects.

You access the properties or methods of an object using dot notation. You can also access properties using square brackets.

## Ch. 5: "Document Object Model" (pp. 183-242)

The Document Object Model (DOM) specifies how broswers create a model of an HTML page and how JS can access and update the contents of a web page while it is in the browser window.

The DOM specifies the way in which the browser should structure this model using a DOM tree.

People refer to the DOM tree as an Application Programming Interface (API) which lets humans interact with programs. 

As a browser loads a web page, it creates a model of that page. The model is called a DOM tree, and it is stored in the browsers' memory. It consists of four main types of nodes:

1. The Document node
2. Element nodes
3. Attribute nodes
4. Text nodes

Each node is an object with methods and properties. Scripts access and update this DOM tree (not the source HTML file). Any changes made to the DOM tree are reflected in the browser.

Accessing and updating the DOM tree involves two steps:

1. Locate the node that represents the element you want to work with.
2. Use its text content, child elements, and attributes.

The terms elements and element nodes are used interchangeably but when people say the DOM is working with an element, it is actually working with a node that represents that element.

Methods that find elements in the DOM tree are called DOM queries. When you need to work with an element more than once, you should use a variable to store the result of this query.

When people talk about story elements in variables, they are really storing the location of the element(s) within the DOM tree in a variable. The properties and methods of that element node work on the variable.

DOM queries may return on element, or they may return a NodeList, which is a collection of nodes.

`getElementByID()` and `querySelector()` can both search an entire document and return individual elements. Both use a similar syntax.

When a DOM method can return more than one element, it returns a NodeList (even if it only finds one matching element).

There are two ways to select an element from a NodeList: The `item` method and array syntax. Both require the index number of the element you want.

Array syntax is preferred over the `item()` method because it is faster. Before selecting a node from a NodeList, check that is contains nodes. If you repeatedly use the NodeList, store it in a variable.

When you have a NodeList, you can loop through each node in the collection and apply the same statements to each.

When you have an element node, you can select another element in relation to it using these five properties. This is known as traversing the DOM.

Traversing the DOM can be difficult because some browsers add a text node whenever they come across whitespace between elements.

When you select a text node, you can retrieve or amend the content of it using the `nodeValue` property.

The `textContent` property allows you to collect or update just the text that is in the containing element (and its children).

There are two very different approaches to adding or removing content from a DOM tree: the `innerHTML` property and DOM manipulation. DOM manipulation easily targets individual nodes in the DOM tree, whereas `innerHTML` is better suited to updating entire fragments.

Using the `innerHTML` property, you can access and amend the contents of an element, including any child elements.

DOM manipulation offers another technique to add new content to a page (rather than `innerHTML`). It involves (1) `createElement()`, (2) `createTextNode()`, and (3) `appendChild()`.

DOM manipulation can also be used to remove elements from the DOM tree.

Choosing between different techniques for adding HTML to a web page depends on the task (and how the site might be developed in the future).

If you add HTML to a page using `innerHTML` (or several jQuery methods), you need to be aware of Cross-Site Scripting Attacks or XSS; otherwise, an attacker could gain access to your users' accounts.

You should consequently validate info going in to the server. Make sure that your users can only input characters they need to use and limit where this content will be shown on the page.

Any content generated by users that contain characters that are used in code should be escaped on the server. You must control any markup added to the page.

Once you have an element node, you can use other properties and methiods on that element node to access and change its attributes.

moderns browsers come with tools that help you inspect the page loaded in the browser and understand the structure of the DOM tree.

Firefox has similar built-in tools, but you can also download a DOM inspector tool that shows the text nodes.