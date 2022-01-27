
# Read: 05 - Design web pages with CSS

## What is CSS?

Stands for Cascading Style Sheets, and its how you make your web page look great (determining style, layout, etc.).

CSS is rule-based (i.e. has proper syntax). A CSS document is known as a "stylesheet", and it contains multiple rules that will affect how the HTML content will be presented.
- Each rule opens with a selector, such as `<h1>` or `<p>`, which select the HTML element being styled. The selector is followed by curly braces which contain the **declarations** of the rule. Each declaration has a **property** and a **value**: the former specifying which *property* of the element is being selected for styling, and the latter being the *value* given to that property. A semi-colon goes at the end of each code line containing a property and value declaration.
- For instance, a rule making the top header font to be blue and 3 times the size of the parent element's font would look in the stylesheet like:
```
h1 {
    color: blue;
    font-size: 3em;
}
```
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/What_is_CSS) has information on each module that the CSS language is broken up into (such as [Backgrounds and Borders](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders)).


## How to Add CSS

CSS can be added externally, internally, or inline.

### External CSS

In this case, the presentation of the HTML page is affected by just a single external stylesheet. It exists as its own file but is linked to the HTML file within the HTML document's `<head>` section, like so:
```
<head>
    <link href="style.css rel="stylesheet">
<head>
```
Such external stylesheets must be saved as a .css file, and would typically contain multiple rule declarations like those explained in the 'What is CSS' article notes above.

### Internal CSS

Good to use if one particular HTML webpage is meant to have its own unique style, and uses a `<style>` element  (containing the CSS syntax) within the `<head>` section of the HTML code.

### Inline CSS

For styling a single element (without affecting similar elements on the page). For inline CSS, it's incorporated as a `style` attribute within the opening tag of the HTML element, like so:
```
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;font-size:3em;">Heading content</h1>

<body>
<html>
```

### Multiple Style Sheets

Whenever the style of an element is being defined in multiple places, the "last read" style sheet value will be the one used.

For example, in the case where an external style sheet that's linked to an HTML file defines paragraph font size as 2em like so...
```
p {
    font-size: 2em
}
```
...but the internal style sheet in the HTML code defines paragraph font size as 1em like so...
```
<head>
<link href="style.css" rel="stylesheet">
<style>
p {
    font-size: 1em
}
</style>
<head>
```
...the "last read" value (going from top to bottom, as always) was 1em, so that's what the paragraph font size will be.

### Cascading Order

Aside from the "last read" concept reconciling different values in external vs. internal style sheets, there is a prioritization (or "cascading") order that will determine which rule 'wins out' (is used):
1. Inline style (in HTML element)
2. External & Internal style sheets (in head section)
3. Browser default

## CSS color Property

`color` defines the text color when paired with a value.

Some values are as simple as the word of the color (like `red` or `green`), but more specified colors can be achieved through other values.
- For instance, a HEX value, which begins with a `#`:
```
p {color: #92a8d1;}
```
- Or an RGB value, which is comprised of three different numerical components corresponding to the intensity (from 0 to 255) of red, green, and blue, respectively, inherent to the color:
```
p {color: rgb(75, 23, 205)}
```

[CSS Reference article](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

[Myers Web CSL Tools: Reset CSS](https://meyerweb.com/eric/tools/css/reset/)