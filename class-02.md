
# Notes on Duckett HTML book:

## Ch. 2: "Text" (pp. 40-61)

Structural markup: elements that you can use to describe both headings and paragraphs
Semantic markup: provides extra info/meaning (where emphasis is placed, type and origin of content, acronym meaning, etc.)

Headings, six levels of hierarchy: `<h1> <h2> <h3> <h4> <h5>` and `<h6>` (using closing tag)

Paragraph element `<p>` has closing tag, contains the text content, and each paragraph will be shown on new line by browser.

Containing text in `<b>` element will bold it.

Containing text in `<i>` element will italicize it.

The `<sup>` element will make contained text superscripted (like an exponent or date suffix) and `<sub>` element will make contained text subscripted (like in chemical formulas or with footnotes).

Browsers will treat more than one space in code for display content as only one space when displayed. This is known as **white space collapsing**.

The `<br />` element will create a line break in a paragraph or other text content holding element (like a header). It is an empty (or self-closing) element.

Another empty element is `<hr />` which adds a horizontal rule between sections (which can be used to create a break between themes).

Content management systems and HTML editors often have two views of the page being created: a visual editor (resembling the display of a word processor) and a code view (showing the code created by the visual editor).

### Semantic markup

The `<strong>` element both bolds contained text and indicates that its content has strong importance.

The `<em>` element italicizes and indicates emphasis of contained text to subtly change meaning of sentence.

With quotations, the `<blockquote>` element is used for longer quotes that take up an entire paragraph (with the `<p>` element used *inside* of it), and browsers tend to indent the content of this element. With shorter quotes, the `<q>` element is used, and browsers (apart from Internet Explorer, leading some developers to avoid using this element). Both quotation elements may use the `cite` attribute to indicate where quote is from.

When using an abbreviation or acronym, the `<abbr>` element can be used with a `title` attribute in the opening tag to specify the full term.

The `<cite>` element can be used to contain the text of the name of the work that is being referenced/cited, and the browser will also render that text to appear italicized.

For the *defining instance* of a new term (the initial introduction of it) one can use the `<dfn>` element to contain the term (while some browsers will italicize it, Safari and Chrome do not).

The `<address>` element contains the contact details for the author of the page (such as physical or email address). Browsers tend to display in italics.

The `<ins>` element shows content that has been *inserted* into a document, while `<del>` shows content that has been *deleted* from the document. The latter will usually render with a strikethrough, and the former with an underline. Another strikethrough rendering element is `<s>` which indicates that something is no longer accurate or relevant (but that should not be deleted) such as an old price that has been replaced with a sale price.

## Ch. 10: "Introducing CSS" (pp. 226-245)

The key to understanding CSS is to imagine an invisible box around every HTML element, keeping in mind now these boxes differ between the block-level and inline elements. CSS allows rule creation for how each individual box and contents will appear.

CSS associates rule with HTML elements, governing how they are displayed. Each rule contains two parts, a **selector** which indicates the element(s) the rule applies to, and a **declaration** indicating how the element(s) referred to in selector should be styled. Each declaration is comprised of a **property** indicating the ascpects of the element being changed, and a **value** specifying the new settings for the chosen property.

External CSS styling uses a `<link>` element in the `<head>` element of the HTML document to tell the browser where to fine the CSS file used to style the page. This link element should include three attributes:

1. `href` specifying the CSS file path
2. `type` specifying the type of document being linked to (value should be `text/css`)
3. `rel` specifying the relationship between the HTML page and the file it's linked to (value should be `stylesheet`)

Internal CSS styling uses a `<style>` element (usually within the `<head>` element), and should include a `type` attribute with value `text/css`. This should only be done for site's with one page, otherwise an external style sheet should be used to ensure consistent style across all pages (and making it easier to change that site-wide style).

There are many different types of selectors, including:

- **universal selector** applies to all document elements: `* {}`
- **type selector** matches element names: `h1, h2, h3 {}`
- **class selector** matches elements with class attribute value matching the one specified after the period (or full stop) symbol: example is `.note {}` which targets elements with class attribute value of `note`, or `p.note {}` which targets *only* `<p>` elements with `note` class attribute value
- **id selector** matches element whose id attribute value matches the one specified after the pound/hash symbol: `#introduction {}` targets elements with id attribute value of `introduction`
- **child selector** matches element that is direct child of another: `li>a {}` targets any `<a>` elements that are children of a `<li>` element (but not other `<a>` elements on the page)
- **descendant selector** matches an element that is a descendant of another specified element (not just a direct child): `p a {}` targets any `<a>` elements that sit inside a `<p>` element, even if there are other elements nested in between them
- **adjacent sibling selector** matches an element that is the next siblig of another: `h1+p {}` targets first `<p>` element after any `<h1>` element, but not other `<p>` elements
- **general sibling selector** matches an element that is a sinbling of another, although not necessarily the directly preceding element: `h1~p {}` would apply to any `<p>` elements that are siblings of a `<h1>` element

CSS rules *cascade*: **last rule** is what matters, in that if two selectors are identical, the latter of the two will take precedence. **specificity** also matters, so if one selector is more specific that the others, the more specific rule will take precedence (like `h1` over `*`). You can also add `!important` after any property value to indicate it be considered over other rules applying to the same element.

The value of `font-family` or `color` properties are inherited by child elements of those elements selected. Other properties are not inherited, like `background-color` or `borders`. Properties can be forced to be inherited from their parent elements through use of `inherit` value for said property.

While using External Style Sheets has clear advantages, some instances (like one page with a few extra rules) may lead authors to use internal styling (but most authors consider it better practice to just link to a separate file).

CSSS1 was released in 1996 and CSS2 in 1998, CSS3 was in development during writing of this book. When a CSS property does not displayas expected, it is referred to as a browser quirk or CSS bug.

# Notes on Duckett JS book:

## Ch. 2: "Basic JavaScript instructions" (pp. 53-84)

Each step/instruction in a script is a statement. Contents of curly braces are known as a code block. The code immediately preceding curly braces determines which code should run.

JavaScript is case sensitive.

Good to write comments to explain what the code does. Multi-line comments should start with `/*` and end with `*/` and single line comments just need a `//` before them.

A variable is what a script uses to store bits of data that may vary or change each time a script runs, and will be used for operations. The results of scripts are calculated/computed using the data stored in the variables.

Old way to declare variables: `var quantity;` where `var` is the variable keyword and `quantity` the variable name, followed by an assignment statement like `quantity = 3;` which uses `=` assignment operator to assign the variable value `3` to the variable `quantity`. A better way to now accomplish both of these steps in one is to just say `let quantity = 3;`

Numeric data type handles numbers, string data type consists of letters and other characters, and boolean data types can have one of two values: `true` or `false`.

Numbers are assigned using an operator like `=` or `*` like in:
```
price = 5;
quantity = 14;
total = price * quantity;
```

Strings are assigned using the `=` operator followed by the string contained in either single or double quote marks (as long as they match). Quotes can be used in a string by either using the other type of quote marks from what occurs on the outside, or *escaping* the quotation characters by using a backslash `\` before the character.

Assign boolean variables with values of either `true` or `false`.

Programmers can use shorthand for variables, or change their values.

Variable names must not start with a number or contain a dash or period, or contain any keywords or reserved words. Again, variables are case sensitive. They should have a name that describes the kind of info stored in them. Should use camelCase.

Array is special type of variable that stores a list of values that are related to each other. Can be created through use of array literal or array constructor.

Values in an array are accessed as in a numbered list, with list starting at zero (not one). Each item in the array is given an index number. To retrieve an item on the list, the array name is specified along with the index number in square brackets. Each array has a property called `length` which holds the number of items in the array.

Values in an arraycan be accessed or changed.

Expressions evaluate into a single value, like expressions that just assign a value to a variable or expressions that use two or more values to return a single value.

Expressions rely on operators to create a single value from one or more values. There are arithmetic operators and string operators.

## Ch. 4: "Decisions and Loops" (only up to section on switch statements) (pp. 145-162)

Flowcharts are cood for mapping out and planning for the decisions that are made in scripts to determine which lines of code should be run next. Each decision has two components (1) an evaluated expression returning a value and (2) a conditional statement that says what to do in a given situation.

Comparison operators evaluate conditions resulting in Boolean results of either true or false. Comparison operators include: is equal to `==`, is not equal to `!=`, strict equal to `===`, strict not equal to `!==`, greater than `>`, less than `<`, greater than or equal to `>=`, and less than or equal to `<=`.

Comparison operators should be structured with each operand on one side of the comparison operator with brackets () enclosing them. Operands can be expressions themselves, because expressions (like `score1 + score2`) evaluate into a single value.'

Logical operators include `&& || !` which are logical and, logical or, and logical not, respectively.

The `if` statement evaluates if a condition is `true`, and in such a case, any statements in the subsequent code block are executed.

The `if...else` statement checks a condition. If it resolves to `true` then first code block (after the `if` statement) is executed, but if it resolves to `false` then the second code block (after the `else`) is run instead.