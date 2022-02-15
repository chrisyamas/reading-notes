
# Notes on Domain Modeling

Domain modeling - process for creating code to model concept for specific problem

A model describes various entities, attributes, behaviors, constraints.

object-oriented model: entity that stores data in properties and behaviors in methods

When articulated well it can verify + validate understanding of specific problem for stakeholders, defining a vocabulary to use within and between technical + business departments at firm.

Assessing epic fail videos along two properties (a Number type property of `epicRating` assessed from `1` to `10` and a Boolean type of `hasAnimals`) an example of `EpicFailVideo` constructor function is:
```
var EpicFailVideo = function(epicRating, hasAnimals) {
  this.epicRating = epicRating;
  this.hasAnimals = hasAnimals;
}

var parkourFail = new EpicFailVideo(7, false);
var corgiFail = new EpicFailVideo(4, true);

console.log(parkourFail);
console.log(corgiFail);
```
The two properties of `epicRating` and `hasAnimals` are the paramaters of the function declared.

Calling the function stores the data inside the parameters inside the `this.epicRating` and `this.hasAnimals` properties, ensuring newly created objects can access that data later.

The `new` keyword is invoked to instantiate two objects and the `epicFailVideo` constructor function is called to initialize their properties, and then the instantiated and initialized objects are stored inside the `parkourFail` and `corgiFail` variables.

And then the two new objects are logged to the console.

This whole process comprises the fundamentals of JS object-oriented programming.

1. `new` keyword instantiates an object
2. `this` variable is used with constructor function to initialize properties inside that object
3. the object is stored in a variable to be used later

The reading goes on into more details on the other aspects, but here is the summary at the bottom:

"Domain modeling is the process of creating a conceptual model for a specific problem. And a domain model that's articulated well can verify and validate your understanding of that problem.

Here's some tips to follow when building your own domain models.

- When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.
- Model its attributes with a constructor function that defines and initializes properties.
- Model its behaviors with small methods that focus on doing one job well.
- Create instances using the new keyword followed by a call to a constructor function.
- Store the newly created object in a variable so you can access its properties and methods from outside.
- Use the this variable within methods so you can access the object's properties and methods from inside."

# Notes on Duckett HTML book

## Ch. 6: "Tables" (pp.126-145)

A table represents information in a grid format. Examples of tables include financial reports, TV schedules, and sports results. Each block in the grid is referred to as a table cell.

The `<table>` element creates a table, with `<tr>` indicating the start of each table row, followed by one or more `<td>` elements for each cell of table data in that row. End of each cell has closing `</td>` tag and end of each row has closing `</tr>` tag. The `<th>` element is used just like the `<td>` element but to represent rather the heading for either a column or row. Even if a cell has no content, it should still have either a `<td>` or `<th>` element to represent the empty cell to ensure table renders properly.

The `colspan` attribute can be used on either `<th>` or `<td>` element to indicate how many columns that cell should run across. The `rowspan` attribute can be used on a `<th>` or `<td>` element to indicate how many rows a cell should span down the table.

For long tables, the headings of the table should sit inside the `<thead>` element, the body should sit inside the `<tbody>` element, and the footer belongs inside the `<tfoot>` element.

# Notes on the Duckett JS book

## Ch. 3: "Functions, Methods, and Objects" (pp. 106-144)

When creating an object using constructor notation, the `new` keyword and the objector constructor create a blank object. You can then add properties and methods to the object.

To update the value of properties, use dot notation or square brackets. They work on objects created using literal or constructor notation. To delete a property, use the `delete` keyword.

For creating many objects using constructor notation: sometimes you will want several objects to represent similar things. Object constructors can use a function as at template for creating objects. First, create the template with the object's properties and methods.

You create instances of the object using the constructor notation. The `new` keyword followed by a call to the function creates a new object. The properties of each object are given as arguments to the function.

The keyword `this` is commonly used inside functions and objects. Where the function is declared alters what `this` means. It always refers to one object, usually the object in whcih the function operates.

As a recap, in JS, data is represented using name/value pairs. To organize your data, you can use an array or object to group a set of related values. In arrays and objects the name is also known as a key. If you want to access items via a property name or key, use an object (but note that each key in the object must be unique). If the order of the items is important, use an array.

Arrays are actually a special type of object. They hold a related set of key/value pairs (like all objects), but the key for each value is its index number.

You can combine arrays and objects to create complex data structures: Arrays can store a series of objects (and remember their order). Objects can also hold arrays (as values of their properties).

Browsers come with a set of built-in objects that represent things like the browser window and the current web page shown in that window. These built-in objects act like a toolkit for creating interactive web pages.

The `window` object represents the current browser window or tab. It is the topmost object in the Browser Object Model, and it contains other objects that tell you about the browser.

The topmost object in the Document Object Model (or DOM) is the `document` object. It represents the web page loaded in the current browser window or tab.

Whenever you have a value that is a string, you can use the properties and methods of the `String` object on that value. Each character in a string is automatically given a number, called an **index number**. Index numbers always starts at zero and note one (just like items in an array).

In JS there are six data types: five of them (string, number, Boolean, undefined, and null) are described as simple (or primitive) data types, and the sixth is the object (and is referred to as a complex data type).

Whenever you have a value that is a number, you can use the methods and properties of the `Number` object on it.

The `Math` object has properties and methods for mathematical constants and functions.

In order to work with dates, you create an instance of the `Date` object. You can then specify the time and date that you want it to represent. Once you have created a `Date` object, the following methods let you set and retrieve the time and date that it represents.