
# Notes on the Duckett HTML book

## Ch. 4: "Links" (pp. 74-93)

Links are created using the `<a>` element. Users can click on anything between the opening and closing tags. Use `href` attribute to specify source of link.

There are absolute URLs that link to other sites, and relative URLs that are a shorthand because are linking to a page within the same site.

In a directory structure of a large website, the top-level folder is known as the root folder. Relationships are described in terms of family trees with parents, children, grandparents, and grandchildren. The main homepage is called index.html

When creating a link that starts up the user's email program and addresses an email to the specified email address, begin value of `href` attribute with `mailto:` before the email address.

To have a link be opened in a new window, use the `target` attribute with a value of `_blank`

Links can also be used to bring the user to a specific part of the same page by putting an id in the individual element you want to link to, and having the `href` value in the link opening tag be a `#` sign followed by the id value.

The same method can be used to link to specific parts of other pages, as long as the source code of those pages uses and id in the part you want to link to.

## Ch. 15: "Layout" (pp. 358-404)

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