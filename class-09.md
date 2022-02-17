
# Notes on the DUckett HTML book

## Ch. 7: "Forms" (p. 144-175)

A user fills in a form and then presses a button to submit the information to the server. A form may have several form controls, each gathering different information. The server needs to know which piece of inputted data corresponds with which form element.

Form controls live inside the `<form>` element which requires the `action` attribute with its value being the URL for the page on the server that will received the submitted form info. the `method` attribute will have either a `get` or `post` value. The  `get` method is good for short forms and just retrieving data from web server. The `post` method is good for file upload, long forms, sensitive data (like passwords), and any time you need to add info to, or delete info from, a database.

`<input>` is used to create several different form controls with `type` attribute value determining the kind of input.

`type="text"` creates a single-line text input.

Each form control requires `name` attribute, the value of which identifies the form control and is sent along with the information users enter to the server.

`maxlength` limits the number of characters a user can enter into the text field.

*The size of the form controls should be controlled by CSS*

`input="password"` creates single-line text input with characters blocked out. `name` and `maxlength` pertain the same.

`<textarea>` element creates a multi-line text input, and should have opening and closing tag. Any text between those tas will appear in the text box when the page loads (if the user does not delete the message, it will remain, unless JavaScript is used to clear this info when the user clicks in the text area). CSS can and should be used to control width and height.

`type="radio"` creates radio buttons which allow users to pick just one of a number of options. the `name` attribute should be the same for all buttons, while the `value` attribute should be different for each (so the server knows which option the user has selected). the `checked` attribute can be used to indicate which value (if any) should be selected when the page loads, with the attribute for that form control being `checked="checked"`. Once a radio button has been selected it cannot be unselected without selecting a different option.

`type="checkbox"` allows users to select and unselect one or more options in answer to a question. needs `name` attribute to be the same for all checkbox form controls, with `value` different for each, and `checked` same as before too.

`<select>` element creates a drop down list box, and contains two or more `<option>` elements. the `<select>` element should have a `name` attribute. the `<option>` element will have the displayed text for each option between each of the opening and closing tags. it uses the unique `value` attribute for each, and the optional `selected` attribute to indicate whether that option should be selected when the page loads (if not used, first option will be shown when the page loads).

`size` attribute can be used on `<select>` element to have the drop down select box show more than one option. the `multiple` attribute with value of `"multiple"` allows users to select multiple options from the list.

`<input>` with `type="file"` creates a box that looks like a text input followed by a **browse** button, such that when a user clicks it, they can find and upload a file from their computer to the website.

`<input>` with `type="submit"` creates a submit button that is used to send a form to the server (it can have a name attribute but it does not need one). The `value` attribute controls the text that appears on a button (if not specified, then some browsers will display 'Submit query' which isn't great).

`<input>` with `type="image"` allows an image to be used for the submit button (with `src`, `width`, `height` and `alt` all working the same as normal).

`<button>` element allows more control over how buttons appear, and allows other elements to appear inside the button (ex. can combine text and images between opening and closing tags of `<button>`). `type="hidden"` allows for hidden form controls (to add values to forms that users cannot see, which can be useful some something like indicating which page the user was on when they submitted a form).

`<label>` makes the form accessible to vision-impaired users. it can be used by (1) wrapping around both the text description and the form input or (2) be kept separate from the form control and use the `for` attribute to indicate which form control it is a label for.

`<fieldset>` allows for a grouping of related form controls inside it, which is helpful for longer forms. Most browsers will show it with a line around the edge (the line appearance can be adjusted using CSS). the `<legend>` element can come directly after the opening `<fielset>` tag and contains a caption which helps identify the purpose of that group of form controls.

`required="required"` is a kind of form validation which is new in HTML5. validation such as this reduces the amount of work the server has to do, and enables users to see if there are problems with the form faster than if validation were performed on the server.

`<input>` with `type="date"` creates a date input in browsers (at least in newer browsers). Same respectively for `type="email"` and `type="url"`.

search input is created with `<input>` and `type="search"` to create a single-line text box for search queries, and a `placeholder` attribute allows the value to be set as the text that should be shown in the text box until the user clicks in that area.

## Ch. 14: "List, Tables & Forms" (pp. 330-357)

`list-style-type` property allows control of shape or style of a bullet point (also known as a marker). can be used on ordered and unordered list elements, and on individual or multiple list elements. for unordered lists the available values are
```
none
disc
circle
square
```
and for ordered lists:
```
decimal
decimal-leading-zero
lower-alpha
upper-alpha
lower-roman
upper-roman
```

an image can act as a bullet point using the `list-style-image` property with value starting with `url` and followed by a pair of parentheses with an image path inside in double quotes. can be used on rules that apply to the unordered list and list item elements.

`list-style-position` indicates whether the marker for each list item should appear on the inside or outside of the box containing the main points using values of `inside` or `outside`.

`list-style` is shorthand to allow appearance changes of markers' style, image, and position proeprties (in any order).

table properties include:

- `width` to set the width of the table
- `padding` to set the space between the border of each table cell and its content
- `text-transform` to convert the content of the table headers to uppercase
- `letter-spacing`, `font-size` to add additional styling to the content of the table headers
- `border-top`, `border-bottom` to set borders above and below the table headers
- `text-align` to align the writing to the left of some table cells and to the right of the others
- `background-color` to change the background color of the alternating table rows
- `:hover` to highlight a table row when a user's mouse goes over it

tips for styling tables so they're easy to follow:

- give cells padding
- distinguish headings
- shade alternate rows
- align numerals

`empty-cells` property can be used to specify whether or not the borders of empty table cells should be shown (can be good to explicitly state since browsers treat empty cells in different ways). can take on values of `show`, `hide`, or `inherit` (which instructs table cells to obey the rules of the containing table, if its nested within one).

`border-spacing` property allows control of distance between adjacent cells. value is usually specified in pixels.

when a border has been used on table cells, where two cells meet, the width of lines would be twice that of outside edges unless you use `border-collapse` property to prevent with either a `collapse` value which collapses borders into a single border where possible (ignoring `border-spacing`, pushing cells together, and ignoring `empty-cells` properties too) or `separate` which detaches borders form each other (`border-spacing` and `empty-cells` will be obeyed).

p. 341 has some good perspective and resources for styling forms

common CSS properties used to style text inputs:

- `font-size` sets the size of the text entered by the user
- `color` sets the text color, and `background-color` sets the background color of the input
- `border` adds a border around the edge of the input box, and `border-radius` can be used to created rounded corners (for browsers that support property)
- `:focus` pseudo-class is used to change the background color of the text input when it is being used, and the `:hover` psuedo-class applies the same styles when the user hovers over them
- `background-image` adds a background image to the box. Because there is a different image for each input, we are using an attribute selector looking for the value of the `id` attribute on each input.

useful CSS properties for styling submit buttons:

- `color` is used to change the color of the text on the button
- `text-shadow` can give a 3D look to the text in browsers that support this property
- `border-bottom` has been used to make the bottom border of the button slightly thicker, which gives it a more 3D feel.
- `background-color` can make the submit button stand out from other items around it (good to keep in mind consitency of style so users understand how to interact with site). a gradient background has been added for browsers that support them (covered on p. 419 of book)
- `:hover` pseudo-class has been used to change the appearance of the button when the user hovers over it (could do things like make backgounf change, text get darker, or border get thicker on the top of the button, etc.)

CSS properties commonly used with fieldsets and legends:

- `width` is used to control the width of the fieldset
- `color` is used to control the color of text
- `background-color` is used to change the color behind these items
- `border` is used to control the appearance of the border around the fieldset and/or legend
- `border-radius` is used to soften the edges  of these elements in browsers that support this property
- `padding` can be used to add space inside these elements

pp. 345-346 presents some good advice on aligning form controls with CSS

the `cursor` property allows control of type of mouse cursor to display to users. most commonly used are:
```
auto
crosshair
default
pointer
move
text
wait
help
url("cursor.gif");
```

# Notes on Duckett JS book

## Ch. 6: "Events" (pp.243-292)

There are many different event types which occur in the browser when you are browsing the web. Any of these events can be used to trigger a function in your JS code (a list selection of them found on p. 246).

When an event has occurred, it is often described as having fired or been raised. Events are said to trigger a function or script.

When the user interacts with the HTML on a web page, there are three steps involved in getting it to trigger some JS code. Together these steps are known as event handling.

1. **Select element:** Select the element node(s) you want the script to respond to.
2. **Specify event:** Indicate which event on the selected node(s) will trigger the response.
3. **Call code:** State the code you want to run when the event occurs.

Event handlers let you indicate which event you are waiting for on a particular element. There are three types of event handlers (html, traditional DOM, DOM level 2 event listeners). DO NOT use HTML event handler attributes.

All modern browswers understand the traditional DOM event handler approach, but you can only attach one function to each event handler. The syntax is:
`element.onevent = functionName;`

Event listeners are a more recent approach to handling events. They can deal with more than one function at a time but they are not supported in older browsers.

When using parameters with event handlers & listeners: because you cannot have parentheses after the function names in event handlers or listeners, passing arguments requires a workaround. You wrap the function in an anonymous function.

Event flow: HTML events nest inside other elements. If you hover or click on a link, you will also be hovering or clicking on its parent elements.

The flow of events only really matters when your code has event handlers on an element *and* one of its ancestor or descendant elements.

When an event occurs, the `event` object tells you information about the event, and the element it happened upon.

Event delegation: creating event listeners for a lot of elements can slow down a page, but event flow allows you to listen for an event on a parent element.

The `event` object has methods that change: the default behavior of an element and how the element's ancestors respond to the event.

When calling a function, the `event` object's `target` property is the best way to determine which element the event occured on. But you may see the approach using the `this` keyword.

There are W3C DOM events, HTML5 events, BOM (Browser Object Model) events to name a few.

User interface (UI) events occur as a result of interaction with the browser window rather than the HTML page contained within it, ex. a page having loaded or the browser window being resized.

The HTML events you can interact with, such as links and form elements, can gain focus. These events fire when they gain or lose focus.

The mouse events are fire when the mouse is moved and also when its buttons are clicked.

The `event` object can tell you where the cursor was positioned when an event was triggered.

The keyboard events are fired when a user interacts with the keyboard (they fire on any kind of device with a keyboard).

There are two events that are commonly used with forms. In particular you are likely to see `submit` used in form validation.

Whenever elements are added to or removed from the DOM, its structure changes. This change trigger a mutation event.

There page-level events that have been included in versions of the HTML5 spec that have become popular very quickly: `DOMContentLoaded`, `hashchange`, and `beforeunload`.
