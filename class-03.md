
# Notes on the Duckett HTML book

## Ch. 3: "Lists" (pp.62-73)

The `<ol>` element creates an ordered list, and each list item is placed in `<li>` tags. Same is done with unordered lists but the element is `<ul>`.

The `<dl>` element creates a definition list and usually consists of terms and definitions with terms contained in `<dt>` and definitions in `<dl>`.

You can nest lists (putting one list inside of another), and browsers will adjust the style automatically.

## Ch. 13: "Boxes" (pp. 300-329)

CSS treats each HTML element like it lives in its own box.

The dimensions of each box can be adjusted using `width` and `height` properties. Width can be limited to within a certain range with the `min-width` and `max-width` properties, and height with `min-height` and `max-height`.

The `overflow` property addresses when content in a box is larger than a box itself, and can take on a `hidden` value which just hides any extra content that doesn't fit or a `scroll` value which adds a scrollbar to the box for users to use to see the missing content.

Each box has three available properties that can be adjusted to control its appearance:

1. A border (even if not visible, i.e. specified at 0 pixels wide) which separates the edge of one box from another.
2. Margins which sit outside the edge of the border. Margin width can be set to create a gap between the borders of two adjacent boxes.
3. Padding which is the space between the border of a box and any content contained within it. Adding padding can increase readability of the box's contents.

The `padding` and `margin` properties help a lot with adding space between various items on the page.

`border-width` controls width of a border, and can take on the values of `thin` `medium` or `thick`, and can also be addressed just to one edge of the box by adding top, right, bottom, or left respectively into the middle of the property like `border-top-width`.

`border-style` controls the style of a border and can take on the values of:

- `solid` single solid line
- `dotted` a series of square dots
- `dashed` a series of short lines
- `double` two solid lines (with `border-width` being sum of the two lines width)
- `groove` appears to be carved into the page
- `ridge` appears to stick out from the page
- `inset` appears embedded into the page
- `outset` looks like it is coming out of the screen
- `hidden` / `none` no border is shown

just like with `border-top-width` any edge of the border can be styled by adding top, left, right, or bottom into the middle of the property name.

`border-color` specifies the border color, and again individual edges can also be adressed as above.

`border` property is the shorthand that allows width, style, and color to be specified all in one property, and the values need to be coded in that specific order, like so:
```
p {
  width: 250px;
  border: 3px dotted #0088dd;}
```

`padding` property allows specification of (can use top, right, bottom, left like `padding-top`). Shorthand is in the clockwise top, right, bottom, left order as so:
`padding: 10px 5px 3px 1px;`
Or this shorthand which means top and bottoms should be 10px and left and right should be 5px:
`padding: 10px 5px;`

`margin` property controls the gap between boxes (value commonly given in pixels). can use top, right, bottom, left like `margin-top`. Shorthand is in the clockwise top, right, bottom, left order as so:
`margin: 1px 2px 3px 4px;`
Or this shorthand which means top and bottom should be 20 px and left and right should be 10 px:
`margin: 20px 10px;`

to center a box on the page (or inside the element it sits in) set the `left-margin` and `right-margin` to `auto`. in order to center a box on the page, set a `width` for the box (otherwise it will take up the full width of the page). an example:
`margin: 10px auto 10px auto;`
(for older brwosers the `text-align` property should be adjusted for the body, refer to book on this)

`display` property allows inline to be turned into block or vice versa (or to hide an element from the page). a value of `inline` will change block-level to inline, value of `block` will do the opposite, value of `inline-block` will cause block-level element to flow like an inline element while retaining other features of block-level, and `none` hides an elment from the page (while it remains in the source code).

`visibility` property allows boxes to be hidden from users while leaving a space where the element would have been, it can take on value of `hidden` or `visible`.

`border-image` property applies an image to any box order, by taking a background image and slicing it into nine pieces. The property requires:

1. the image URL
2. where to slice the image
3. what to do with the straight edges, with possible values of `stretch`, `repeat`, or `round` which scales the tile image so they fit.

the box must have a border width for the image to be shown. look to book for example of the code format.

`box-shadow` property allows a drop shadow to be added around the box, working just like the `text-shadow` property

`border-radius` allows creation o rounded corders on any box, with value indicating the size of the radius in pixels (like `border-radius: 10px;`). more complex shapes can be made by specifying difference distances for the horizontal and vertical parts of the rounded corners (like `border-radius: 80px 50px;`).

# Notes on the Duckett JS book

## Review from Reading 02 - Ch. 2: "Basic JavaScript Instructions" (pp. 70-73)

An array is a special variable that stores a list or a set of values that are related to each other, very helpful when not knowing how many items a list will contain (since you do not need to specify how many values an array will hold when you create it). Values in an array are separated by commas.

Give an array a name just like any other variable. Values are assigned inside a pair of square brackets, each value separated by a comma. They don't need to be same data type so it can store a string, number, and Boolean all in the same array. This technique is known as an **array literal** and an example of such code is:
```
let colors = ['white', 'black', 'custom'];

let el = document.getElementById('colors');
el.textContent = colors[0];
```

A different technique, using an **array constructor** used the keyword followed by `Array();` and the values are then specified in parentheses (not square brackets) with each value separated by a comma:
```
let colors = new Array('white', 'black', 'custom');

let el = document.getElementById('colors');
el.textContent = colors[0];
```

Each item in an array is automatically given a number called an index, used to access the specific items. To retrieve an item, the array name is specified along with the index number in square brackets. Each array has a property called `length` which holds the number of items in the array.

You can change the value of an item in an array by selecting it and assigning it a new value just like any other variable (using the assignment operator and the new value for the item) (example on page 73 of book).

## Ch. 4: "Decisions and Loops" from switch statements on (pp. 164-182)

A switch statement starts with a variable called the switch value. Each case indicates a possible value for this variable and the code that should run if the variable matches that value. Example
```
switch (level) {
  case 'One':
    title = 'Level 1';
    break;

  case 'Two':
    title = 'Level 2';
    break;

  case 'Three';
   title = 'Level 3';
   break;

  default:
    title = 'Test';
    break;

}
```
Unlike if...else statement, in a switch statement there is a `default` option that is none of the cases match. If a match is found, that code is run; then the `break` statement stops the rest of the switch statement running (providing better performance than multiple if statements).

If I use a data type JavaScript did not expect, it tries to make sense of the operation rather than report an error (converting the data types behind the scenes in a act known as **type coercion**). JS uses **weak typing** becasue the data type for a value can change (some other languages require data type specification i.e. they use **strong typing**).

Every value in JS thus can be treated as if it were true or false, leading to side effects. Falsy values treated as if false or the number 0, truthy as if true or the number 1.

Because the presence of an object or array can be considered truthy, it is often used to check for the existence of an element within a page. (A unary operator returns a result with just one operand).

Logical operators are processed left to right. They short-circuit (stop) as soon as they have a result - but they return the value that stopped the processing (not necessarily true or false values even it it was a logical operation).

Loops check a condition. If it returns `true`, a code block will run. Then the condition will be checked again and if it still returns `true`, the code block will run again. It repeats until the condition returns `false`. There are three common types of loops:

- for loops: good if you need to run code a specific number of times (this is the most common loop)
- while loops: good if you don't know how many times the code should run
- do...while loops: very similar to while loops but key difference: will always run the statements inside the curly braces at least once, even if the condition evaluates to false.

A for loop uses a counter as a condition. This instructs the code to run a specified number of times.

I will commonly see `break` and `continue` keywords used with loops. `break` causes the termination of the loop and tells the interpreter to go onto the next statement of code outside of the loop (it may also be used in functions). `continue` tells the interpreter to stop the current iteration, and then check the condition again (if it is true, the code runs again).

Loops are very helpful when dealing with arrays. It can check the number of items in an array. That number can then be used in the counter to control how many times a set of statements is run.

If the condition never returns false, this will cause an infinite loop where the code will not stop running until the browser runs out of memory (breaking my script).