
# Notes on the Duckett HTML book

## Ch. 5: "Images" (pp. 94-125)

Great images help make the difference between an average-looking site and a really engaging one.

Images should be relevant, convey info, convey the right mood, be instantly recognisable, and fit the color palette.

If you are building a site from scratch, it is good practice to create a folder for all of the images the site uses.

The `<img>` element is used to add an image into the page. It is an empty element (no closing tag) and must carry a `src` attribute with URL source and an `alt` attribute with text description of image. Can also provide `title` attribute with additional info about the image.

`height` and `width` attributes are used to specify its size.

Consider whether the elements around the image are block or inline when choosing where to place images in the code.

*Old code* used an 'align' attribute to indicate how other parts of the page flowed around an image, but now that's controlled by CSS.

Three rules for creating images for a website:

1. Save images in the right format (primarily jpeg, gif, or png)
2. Save images at the right size (should save at same pixel width and height it will appear on the website)
3. Measure images in pixels (not centimeters or inches)

Adobe Photoshop is the most popular tool for image editing, and there is a cheaper version for beginners called Photoshop Elements.

The resolution of an image on the web, for my purposes, is mostly irrelevant. I should just care about its dimensions in pixels. (an image that is 300x300 pixels at 72ppi, pixels per square inch, looks exactly the same as an image that is 300x300 pixels at 500ppi).

Vector images differ from bitmap images and are resolution-independent. Vector images are commonly created in programs such as Adobe Photoshop. They save as an SVG (Scalable Vector Graphics) file. Because vector images are created by placing points on a grid, drawing lines between those points, and filling in the lines with color: the HUGE advantage is that dimensions can be increased without affecting the quality of it.

Animated GIFs show several frames of an image in sequence and therefore can be used to create simple animations (GIFs are not ideal for displaying photographs, so animated GIFs are really only suitable for simple illustrations. although a lot of amateur web designers overused animated GIFs in the 1990's).

An image can be created that is partially transparent (or "see-through") for the web by selecting either a transparent GIF format (for 100% transparent) or a PNG (for semi-opaque or a drop-shadow).

Images can be examined for size and saved on the web using right-click or equivalent operation.

The `<figure>` element allow for an image (or images) to be grouped with a caption using the `<figcaption>` element nested in it.

## Ch. 11: "Color" (pp. 246-263)

`color` property allows color specification of text inside an element. it can take on rgb values, hex codes, or color names.

`background-color` property sets the background for that box.

Three aspects of color picking include adjusting the hue (near to the colloquial idea of color), saturation (amount of gray in a color), and brightness (or "value, refers to amount of black in a color).

When picking foreground and background colors, it is important to ensure that there is enough contrast for the text to be legible.

CSS3 introduced `opacity` property to specify the opacity of an element and any of its child elements, with value a number between 0.0 and 1.0 (so 0.5 value indicates 50% opacity). There is also the CSS3 `rgba` property that allows color specification but adds a fourth value to indicate opacity (that fourth value is known as an `alpha` value and is a number between 0.0 and 1.0) Example:
```
p {
  background-color: rgb(0,0,0);
  background-color: rgba(0,0,0,0.5);
}
```

CSS3 introduces an entirely new and intuitive way to specify colors. **HSL colors**: using hue, saturation, and lightness values. Saturation is again the amount of gray in a color, lightness is the amount of white (lightness) or black (darkness). Hue may be shown as a slider with values from 0 to 360, saturation as a percentage with 100% full saturation and 0% is a shade of gray. Lightness is represented as a percentage with 0% lightness as black and 100% lightness as white, and 50% as normal (lightness sometimes referred to as luminosity).

CSS3 introduces these through `hsl` or `hsla` properties, the latter using that `alpha` value like in `rgba` to represent opacity.

## Ch. 12: "Text" (pp. 264-299)

Typeface terminology:

- serif: these fonts have extra details  on the ends of the main strokes of the letters (these details known as serifs). in print these fonts were traditionally used for long passages of text because they were considered easier to read. (examples: Georgia, Times, Times New Roman)
- sans-serif: these fonts have straight ends to letters, and therefore have a much cleaner design. since screens have a much lower resolution than print, when text is small, sans-serif fonts can be clearer to read. (examples: Arial, Verdana, Helvetica)
- monospace: every letter in these fonts is the same width (non-monospace fonts have different widths). monospace fonts are commonly used for code because they align nicely, making the text easier to follow. (examples: Courier, Courier New)
- cursive: these fonts have either joining strokes or other cursive characteristics, such as handwriting styles. (examples: Comic Sans MS, Monotype Corsiva)
- fantasy: these fonts are usually decorative fonts and are often used for titles (not designed for long bodies of text) (examples: Impact, Haettenschweiler)
- weight: font weight not only adds emphasis but can also affect amount of white space and contrast on a page (could be light, medium, bold, or black).
- style: style could be normal, italic, or oblique. italic fonts have a cursive aspect to some of the lettering. oblique font styles take the normal style and put it on an angle.
- stretch: could be regular, condensed, or extended. in condensed (or narrow) versions of font the letters are thinner and closer together. extended (or expanded) versions have letters thicker and further apart.

There are several ways to use fonts. However, typefaces are subject to copyright, so the techniques you can choose from are limited by their respective licenses.

If designing on a Mac, it's important to check what typefaces look like on a PC because PCs can render type less smoothly. But if designing on a PC, it should look fine on a Mac.

The `font-family` property allows specification of typeface to use for any text inside an element, with value the name of the typeface you want to use. A list can be specified (separated by comma) of multiple options listed in priority order in case user's browser does not support a particular typeface, like so:
```
body {
  font-family: Georgia, Times, serif;
}
```

The `font-size` property enables specification of a size for the font in pixels (`px`), percentages of the default size of text in browsers (ex. `200%`), and ems which is the equivalent of the width of a letter m (ex. `1.3em`).

Programs like Word, Photoshop, and InDesign offer the same sizes of text because they using a type scale that was developed by European typographers in the sixteenth century.

Page 276 of book shows how to achieve type scale using pixels, percentages, and ems.

`@font-face` allows use of a font even if it is not installed on the user's computer, by allowing a path to a copy of the font which will be downloaded if it is not on the user's machine. when using the approach, `font-family` specifies the name of the font, `src` specifies the path to the font, and `format` specifies the format that the font is supplied in. Examples of such code are on pp. 277-278.

`font-weight` with `bold` value causes text to appear bold. `normal` value causes text to appear with normal weight.

`font-style` can have values of `normal` `italic` or `oblique`.

`text-transform` can change the case of the text with `uppercase` `lowercase` or `capitalize` values (the last causes only the first letter of each word to appear capitalized).

`text-decoration` allows for `underline` `overline` `line-through` `none` or `blink` which animates the text to make it appear to flash on or off.

`line-height` sets the height of an entire line of text. The term **leading** (pronounced ledding) is a typography term for the vertical space between lines of text. In typeface, the part of a letter that drops beneath the baseline is called a **descender** while the highest point of a letter is called the **ascender**. Leading is measured from the bottom of the descender on one line to the top of the ascender on the next. Leading in CSS is the difference between the `font-size` and the `line-height`. Increasing `line-height` makes the vertical gap between lines of text larger.

**Kerning** is the typography term for the space between each letter, controlled in CSS using the `letter-spacing` property. Helpful to increase the kerning when your heading or sentence is all in uppercase. The gap between *words* is controlled using the `word-spacing` property, and values for it should be specified in ems (it will be added on top of the default value specified by the font).

`text-align` property allows control of the alignment of text taking on values of `left` `right` `center` or `justify` which indicates that every line in a paragraph (except the last line) should be set to take up the full width of the containing box.

`vertical-align` is a COMMON source of CONFUSION. It is **not** intended to vertically alisng text in the middle of block-level elements such as `<p>` or `<div>` (although it does have this effect when used with table cells i.e. the `<td>` and `<th>` elements). It is more commonly used with inline elements such as `<img>` `<em>` `<strong>` performing a task very similar to the HTML align attribute on the `<img>` element (explained on pages 103-106). The `vertical align` property can take on values of:
```
baseline
sub
super
top
text-top
middle
bottom
text-bottom
```
it can also take a length (usually specified in pixels) or a percentage of the line height.

`text-indent` property allows indentation of the first line of text within an elment, with amount of indentation specified usually in pixels or ems. It take also take on a negative value to push text off the browser window (demonstrated on page 287).

`text-shadow` property has become commonly used (although at time of book writing was still unsupported in some browsers). It creates a drop shadow (dark version of the word just behind it). examples on p. 288 (it's very complicated)

Can specify different values for first letter or first line of text inside an element using `:first-letter` and `:first-line`, and technically they are not properties but rather **pseudo-elements**

There are also **pseudo-classes** in CSS that allow me to set different styles for links that have and have not yet been visited. `:link` allows style setting for links not yet visited while `:visited` allows style setting for links the user has clicked on.

Three pseudo-classes that allow appearance of elements to be changed when a user is interacting with them are `:hover` for when users are hovering over an element, `:active` for when an element is being activated by a user (such as a button or link click), and `:focus` for when an element has focus (which occurs when a browser discovers a user is ready to interact with an element on the page, like when a cursor is in a form input ready to accept typing then that elment is said to have focus).

Attribute selectors - while the most popular CSS selectors were introduced on page 238, there are a set of attribute selectors that allow creation of rules that apply to elements that have an attribute with a specific value:

- existence `[]` matches a specific attribute. i.e. `p[class]` targets any `<p>` element with an attribute called `class`
- equality `[=]` matches a specific attribute with a specific value. i.e. `p[class="dog"]` targets any `<p>` element with an attribute called `class` whose value is `dog`
- space `[~=]` matches a specific attribute whose value appears in a space-separated list of words. i.e. `p[class~="dog"]` targets any `<p>` element with an attribute called `class` whose value is a list of space-separated words, one of which is `dog`
- prefix `[^=]` matches a specific attribute whose value begins with a specific string. i.e. `p[attr^="d"]` targets any `<p>` element with an attribute whose value begins with the letter "d"
- substring `[*=]` matches a specific attribute whose value contains a specific substring. i.e. `p[attr*="do"]` targets any `<p>` element with an attribute whose value contains the letters "do"
- suffix `[$=]` matches a specific attribute whose value ends with a specific string. i.e. `p[attr$="g"]` targets any `<p>` element with an attribute whose value ends with the letter "g"

# Notes on Image Format Blog Post

Summary is that web designers should use JPEG for all images that contain a natural scene or photograph where variation in color and intensity is smooth, use PNG format for any image that needs transparency or for images with text and objects with sharp contrast edges like logos, and use GIF format for images that contain animations.

This summary is paraphrased from the tl;dr of the article which can be found [here](https://blog.imagekit.io/jpeg-vs-png-vs-gif-which-image-format-to-use-and-when-c8913ae3e01d).