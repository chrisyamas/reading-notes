
# Notes on CSS - Layout article

## Understanding the display property

the `display` property determines if the box acts as inline or block, and also determines how an element's children should behave (ex. setting the property to `display: flex` makes the box a block-level box and also converts its children to flex items, enabling the flex properties that control alignment, ordering and flow).

You can't set an explicit width and height on inline elements. Any block level margin and padding will be ignored by the surrounding elements.

## Flexbox and Grid

Flexbox is a layout mechanism for one-dimensional layouts that will, by default, align the element's children next to each other, in the inline direction, and stretch them in the block direction, so they're all the same height. Items will stay on same axis and not wrap when out of space, rather will squash onto same line as each other. This can be changed using `align-items`, `justify-content` and `flex-wrap` properties. It also converts children to flex items, so rules can be written for their behavior inside a flex container (change alignment, order, justification on individual item, also how it shrinks or grows using `flex` property). `flex` property is shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`.

Grid is similar to flexbox, but controls multi-axis layouts rather than single-axis layouts. It enables rule writing on elements with `display: grid` and introduces some new primitives for layout styling like `repeat()` and `minmax()` functions. The `fr` unit (a fraction of remaining space) is useful. Where flexbox mostly treats items as a group, grid gives precise control over their placement in two dimensions. The `grid-row` and `grid-column` properties instruct elements in the grid on how to span vertically and horizontally.

## Flow layout

IF not in grid or flexbox, elements display in normal flow.

`inline-block` gives a box that has some block-level element characteristics, but still flows inline with the text.

`float` property instructs an element to "float" to the direction specified, so sibling elements "wrap" around it: an element can float `left`, `right`, or `inherit`.

*important*: When you use `float`, keep in mind that any elements following the floated element may have their layout adjusted. To prevent this, you can clear the float, either by using `clear: both` on an element that follows your floated element or with `display: flow-root` on the parent of your floated elements.

the `column-count` and `column-gap` properties allow a layout to be split into multiple columns. Also, instead of setting the number of columns that the content is split into, you can also define a minimum desired width, using `column-width`.

the `position` property changes how an element behaves in the normal flow, how it relates to other elments, with values of `relative`, `absolute`, `fixed`, and `sticky` with default being `static`.

adding `position: relative` to an elements also makes it the containing block of any child elements with `position: absolute` (so they will reposition relative to it).

When you set position to absolute, it breaks the element out of the current document flow. This means (1) you can position this element wherever you like, using top, right, bottom and left in its nearest relative parent, and (2) all of the content surrounding an absolute element reflows to fill the remaining space left by that element.

elements with `position: fixed` stay anchored based on the `top`, `right`, `bottom`, and `left` values that you set.

`sticky` achieve the anchored, fixed aspects of `fixed` and the flow-honoring aspects of `relative`, with the element(s) staying anchored to the `top`, `right`, `bottom`, and `left` values that you set.

# Notes on Duckett HTML/CSS Ch. 15: "Layout" (pp. 358-404)

CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or inline box. The former starting on a new line and acting as main building blocks of any layout, while the latter flow between surrounding text.

If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.

CSS has the following position schemes that allow you to control the layout of a page: normal flow, relative positioning, and ansolute positioning. You specify the positioning scheme using the `position` property in CSS. You can also float elements using the `float` property.

To indicate where a box should be positioned, you may also need to use box offset properties to tell the browser how far from the top or bottom and left or right it should be placed.

You don't need to indicate normal flow (where each block-level element sits on top of the next one) but the syntax would be `position: static`

Use `position` property with value of `relative` to move an element in relative positioning in relation to where it would have been in normal flow. follow with offset properties of `top` or `bottom` and `left` or `right` to indicate the posiitoning like:
```
p.example {
  position: relative;
  top: 10px;
  left: 100px;
}
```

When `position: absolute` is applied, the box is taken out of normal flow and no longer affects the position of other elements on the page.

When `position: fixed` is applied, the element is positioned in relation to the browser window so it stays fixed in place when the user scrolls.

To control which element sits on top of another in the case of overlapping elements (the default is for the elements that appear later in the code to be on top) use the `z-index` property with higher number values sitting closer to the front.

The `float` property allows an element to be placed as far to the left or right of the containing element as possible. Float can also be used to place elements side-by-side.

The `clear` property is used to ensure no element touches the left or right-hand sides of a box.

If a containing element only contains floated elements, some browsers will treat it as if it is zero pixels tall, but there is a solution on page 374 of book.

The `div` element can be used to create layouts that use multiple columns in their design (EXCITING!!!).

Different users will have different sized screens, so web design must work on a range of different sized screens, and also consider varying resolutions. Consequently, most designers try to create pages of around 960-1000 pixels wide (it will accomodate for most users).

Fixed width layout designs do not change size as the user increases or decreases the size of their browser window. Measurements tend to be given in pixels.

Liquid layout designs stretch and contract as the user increases or decreases the size of their broswer window. They tend to use percentages for measurements.

Examples can be found on pp. 383-386

Layout grids: many designers use a grid structure to help them position items on a page, and the same is true for web designers.

CSS frameworks aim to make my life easier by providing the code for common tasks, such as creating layout grids, styling forms, creating printer-friendly versions of pages and so on. I can include the CSS framework code in my projects rather than writing the CSS from scratch.

The 960.gs grid is given as an example on p. 392, and the stylesheet is layed out more on p. 394.

Some web page authors split up their CSS style rules into separate style sheets. For example, they might use one style sheet to control the layout and another to control fonts, colors and so on. Some authors take an even more modular approach, creating separate stylesheets to control typography, layout, forms, tables, even different styles for each sub-section of a site.

Multiple style sheets can be incorporated by either:

1. the `@import` rule in a style sheet to import other style sheets
2. multiple separate `<link>` elements in an HTML file (they can all be included in the `<head>`)