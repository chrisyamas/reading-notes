
# Notes on Duckett HTML book

## Intro (pp. 2-11)

This book is designed for web designers and those looking to become web designers. It's designed to be more intuitive to facilitate easier learning. The first part of the book will cover HTML (covering its use, syntax, the variety of tags,), next will cover CSS (including how its used to control the appearance of both presentation and layout of HTML content), and throughout will focus on practical guidance for building and optimizing pages.

People access the web through a browser (on their respective device) which connects to the web server that hosts the site they are visiting. Screen readers help facilitate access for those users with visual impairments. HTML and CSS, as well as content management systems, blogging software, and e-commerce platforms all help to shape the web we see when we visit a given URL. This book was writen while HTML5 and CSS3 were still being developed and gradually adopted.

When I connect to the web, we're doing so via an Internet Service Provider (ISP). When I go to visit a particular URL, my computer contacts a server network called Domain Name System (DNS) servers which tells my computer the unique IP address associated with the requested domain (traditionally up to 12 digits, but increasingly these days up to as many as 32 digits). The IP address allows my browser to contact the server hosting the requested site (a web server is a computer that is constantly connected to the internet and whose purpose is to send web pages to users). In response to this communication, the web server sends the requested page back to my web browser, and that's how I get to experience and engage with the website.

## HTML Ch. 1: "Structure" (pp. 12-39)

Every document has a structure, and web pages are (ideally) structured to optimize the quality of user experience. Just as word documents utilize hierarchies of headings, some of which having their own associated content paragraphs, so do many webpages. HTML describes webpage structure using elements that are usually made up of one opening and one closing tag (but are occasionally self-closing), these elements conveying info to the browser for what the page should look like. Each element tag includes characters between one left-angle bracket and one right-angle bracket (closing tags always include a forward slash symbol). Attributes tell us more about elements, and are made up of two parts: a name and a value. The attribute name indicates the type of information it's conveying, while the value indicates the actual info or setting for the attribute.

All HTML page structure is based around and within a <body> and <head> element. The <head> element comes first and contains info about the page (not that which will be directly shown on the page itself), but it includes the <title> element which contains the text shown in the top of the browser that should succinctly describe the page. Everything contained within the <body> element comprises the content of the page itself.

Web pages can be created and edited from scratch using code in text editors (like Atom or VS Code), or through facilitated support from content management systems, blogging platforms, or e-commerce applications. If I ever want to see how another site is built, I can inspect/view the source code.

## HTML Ch. 8: "Extra Markup" (p. 176-199)

Since the web was first created, HTML has been developed and improved into new versions. HTML 4 was released in 1997 and comprises most of the elements featured in the book. It had some presentational elements that are not included in HTML 5 (because now we really much more on CSS for styling). In 1998, XML was published to allow writing of new markup languages, and in 2000 HTML 4 was reformulated into XHMTL 1.0 to XML's rules (including requiring closing tags for all but empty elements, lowercase attribute names, double-quoted values for all attributes, eradication of deprecated elements, and all elements opened in another element to be closed in same one). To ease the transition, there were both strict and traditional versions of XHMTL 1.0, as well as XHMTL 1.0 Frameset which allowed frame partitions of browser windows, yet frames are rarely used today and have been mostly phased out. At the time of the writing of this book, HTML5 was still a work in progress.

Every HTML5 code document begins with the doctype declared as so: <!DOCTYPE html>.

Any comments in HTML code should be contained within <!-- --> so as not to be read and acted on by the browser.

Every HTML element can carry an id attribute, which uniquely identifies that element from others on the same page. Every HTML element can also carry a class element, which instead identifies several elements as a group separate/distinct from other elements. Both of these attributes can allow other code like CSS or JavaScript to uniquely apply to certain elements and not others.

Block elements (or block level elements) appear to start on a new line in the browser window (examples include <h1> <p> <ul> and <li>). Inline elements appear to continue on the same line as their neighboring elements (examples include <a> <b> <em> and <img>).

The <div> element is used to group text and elements together into one block-level box. This can be useful for containing an entire section of your page (like a header with image and table of contents) in one block, and id or class attribute can be applied to allow CSS styling of that unique <div> element or class of <div> elements.

The <span> element is the inline equivalent of <div> and can be used to contain a text section when there's no other element that makes sense to do so, or to contain a number of inline elements. It is commonly used id or class attribute to facilitate CSS styling.

The <iframe> element is used to embed another page into one's webpage (commonly used for adding a frame of Google Map into a page). The element requires a `src` attribute with the embedded page's URL, and `height` and `width` atrributes specifying the size of the iframe. While the `scrolling` and `frameborder` attributes are not included in HMTL5, there is a new `seamless` attribute which is applied when scrollbars are not desired on an iframe, and while it does not need a value it make take a value of `"seamless"`

If used, the `<meta>` element lives in the `<head>` element and contains info about the page, which provides a number of purposes including use by search engines. The element can contain a `description` attribute that should be less than 155 characters, a `keywords` attribute of comma-separated words characteristic of the page, a `robots` attribute indicating whether search engines should add the page to their results or not (with value of `"noindex"` if page shouldn't be added, and `"nofollow"` if it should be added but pages it links to shouldn't), `author` attribute, `pragma` which prevents browser from caching the page, and `expires` to indicate when the caching of a page should expire (must be in format of `06 Feb 2020 23:59:59 GMT`).

Escape characters are used in HTML code to display as page content any characters that are otherwise reserved by HTML code (and read by the browser as such). Some include less-than sign, greater-than sign, ampersand, and quotation marks of any kind. For example, to display a normal quotation mark on a webpage it would need to be typed into the code as either `&quot;` or `&#34;`.

## HTML Ch. 17: "HTML5 Layout" (pp. 428-451)

While traditional HTML layouts used `<div>` elements with `class` or `id` attributes to group together related page elements, HTML5 introduced a new set of elements that allow the page parts to be divided up (without necessarily using `<div>`). 

### These new elements include:

- The `<header>` and `<footer>` elements used for either a main header or footer at the top or bottom of each page, or a header or footer for an individual `<article>` or `<section>`.
- The `<nav>` element used to contain the major navigational blocks on the site such as the primary site navigation.
- The `<article>` element as a container for any section of a page that could stand alone and potentially be syndicated. Article elements can be nested inside each other, like a blog post within an article, or each comment on an article living within it's own article element.
- The `<aside>` element has two purposes: (1) when inside an `<article>` element it contains info related to article but not essential to overall meaning (like a pullquote or glossary), or (2) when outside an `<article>` element contains content related to the entire page (like links to other sections of the site, list of recent posts, search box, or recent tweets by the author).
- The `<section>` element groups related content together, and typically each section has its own heading. Might contain several distinct `<article>` elements with common theme or purpose, or a long article might contain multiple `<section>` elements to split it up.
- The `<hgroup>` element groups together a set of one or more `<h1>` through `<h6>` elements to treat them as one single heading (this element has had mixed reception by developers).
- The `<figure>` element can contain content referenced from the main flow of an article but not necessary/integral to page's flow. Could include images, videos, graphs, diagrams, code samples, or text that supports the main body of an article. Should contain a `<figcaption>` element to provide text description for the content.
- The `<div>` element still has a place with these new HTML5 layout elements, because it's still an important way to group together related elements. It should be used when there is no suitable element to group a set of elements (such as having a wrapper for the entire page).
- The `<a>` element can be placed around a block level element to turn the entire block into a link (while not a new element or use, it is now viewed as acceptable).
- To help older browsers understand that the new HTML5 elements should be treated as block-level and not inline, include the below block of code in your CSS style sheet:
```
header, section, footer, aside, nav, article, figure, figcaption {
    display: block;}
```
- For versions of Internet Explorer older than version IE9, the below JavaScript known as HTML5 shiv or HTML5 shim (this one is hosted on Google's servers) can be used (and should be placed within the conditional comment [also included below] which checks if the browser version is less than IE9):
```
<!--[if lt IE ]>
    <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->
```

## HTML Ch. 18: "Process & Design" (pp. 452-475)

Websites should be designed with their target audience in mind, considering the demographic characteristics of both the individuals and companies who are most likely to visit.

For individuals, these characteristics could include:

- age range
- gender breakdown
- country of residence
- urban or rural
- income
- level of education
- occupation
- work hours / week
- frequency of web use
- type of browsing device

For companies:

- size of company/department
- position of those visiting the site
- using site for themselves, or someone else?
- size of budget they control

Think about the **why*8: what are the key underlying motivations (what brings them to the site generally) and specific goals (what bring them to the site right *now*). What are they trying to achieve?

Figure out what information they need so they can achieve their goals quickly and effectively.

How often will people visit your site? How frequently does content need to change (could be very dynamic or very static or somewhere in the middle, depending on type of site and what users want from it)?

A site map is a diagram of the pages that will be used to structure the site, showing how those pages can be grouped. To help build this, I can use a technique called card sorting in which I place each piece of info a user might need to know on separate pieces of paper, then organized the related info into groups. Each group relates to a page, and on big site, pages can be grouped together as differect sections of the website. The resultant site map usually starts with the homepage, then branches out from there.

A wireframe is a simple sketch of the key info needed for each page, taking into consideration both information hierachy and space needed for each piece of info. Sketch or shade areas where each element of the page will go (like logo, primary nav, headings, main text bodies, user logins, etc.). Don't include color scheme, font choices, backgrounds or images in the wireframe. This is just the step that helps you know what information, in what order, in what general layout: appearance and style come later.

Visual design is meant to communicate a message. Designers need to organize and prioritize the info on the page to get the message across and help users find what they're looking for. This can be achieved by making parts of the page look **distinct** from surrounding content (thus drawing attention toward or away from those items) and ultimately creating a **visual hierarchy**. Organization can occur through simplification as **similar** content is grouped together in **blocks** or **chunks**, so users can identify the purpose without processing each individual item.

A **visual hierarchy** is created through visual contrast of size, color, style, and images to efficiently convey the key message and help users (most of whom just skim pages) find what they are looking for.

Visual elements should be grouped by similarity, which makes the page content easier to comprehend. This can be done through use of:

- Proximity - placing several items close together (or even nest groups within larger groups)
- Closure - a real or imaginary box formed around elements, providing a recognisable pattern/form
- Continuance - placing related elements in a line or curve going in the same direction (used to direct reader from one part of page to the next)
- White Space - leaving a larger gap between separate/unrelated content groups
- Color - placing a background color behind related items to emphasize their connection
- Borders - line(s) drawn around the group border, or between it and its neighbors

Consistent style of related parts, and headings to both group items under it while differentiating from items not under the heading.

Site navigation should not just orient and guide users, but help them understand what the site is about and how it is organized. Good navigation follows these principles:

- Be concise (quick and easy to read, with a limited number of options)
- Be clear (ideally using single descriptive words for links rather than phrases)
- Be selective (primary navigation should reflect only the overarching sections/content of site)
- Provide context (the web page version of "You Are Here", typically done through a color or visual marker to indicate the current page)
- Be interactive (links should be big enough to click on, and appearance of a nav item should change to be distinct from rest of page content when user hovers over or clicks on the item)
- Be consistent (number of nav items should be proportional to page size, and while secondary nav will change from page to page, primary nav should remain the same)


# Notes on Duckett JS book

## Intro

To make webpages more interactive, Javascript can:

1. **Access** content - select any HTML element, attribute, or text
2. **Modify** content - add elements, attributes, and text to page (or remove them)
3. **Program** rules - specify set of steps for browser to follow, thereby accessing and changing page content
4. **React** to events - specify that a script should run when a specific event has occurred

A few examples of JS in the browser include slideshows, forms, reloading just *part* of a page, filtering data.

First part of book will cover core concepts, then remaining will cover practical applications.

## JS Ch. 1: "The ABC of Programming" (pp. 11-52)

### What is a script and how do I create one?

A script is a series of instructions (like a recipe, handbook, or manual). To write a script, first state the goal and then list the tasks that need to be completed for it to be achieved (define the goal, design the script, code each step). Flowcharts are helpful to this end, giving a high-level view of the tasks. Each task can be broken into sequence of steps. The steps can be translated into the individual lines of code that form the script.

To translate the steps into code, need a grasp of both the vocabulary and syntax to create instructions the computer can follow. Need to think like a computer. They solve problems programmatically, following a series of steps, one after another.

### How do computers fit in with the world around them?

Computers create models of the world using data. Each physical thing in the world can be represented as an object. There are different types of objects, and also different instances of the same type of object. Object characteristics are known as properties, and each has a name and value that provide information about the individual object instance.

Events occur when a user interacts with objects, which can change the values of the properties in the objects. Programs are designed to respond to events (in other words, an event can trigger a particular functionality of a script). 

Methods represent things people need to do with objects (such as retrieving or updating the values of an object's properties). They can tell you something about the object (using the property info) and change the value of one or more of the properties. The method code can contain many instructions that together represent one task. Events trigger methods, and methods can retrieve or update an object's properties.

Web browsers are programs built using objects. There is a `window` object (the representation of a window or tab) and the `location` property of the `window` object is the URL of the current page. Each web page is modeled using a `document` object, with `title` property that conveys what's between the opening and closing tags of the `<title>` element for that HTML page, and the `lastModified` property gives the date the page was last updated.

- Using the document object, I can access or change what users see on the page and respond to how they intereact with it.
- When browsers create a model of a web page, they create not only a `document` object but also a new object for each element on the page (these objects together are decribed in the **Document Object Model**).

How a browser sees a web page:

1. Receives a page as HTML code (each page as separate document)
2. Creates a model of the page and stores it in memory (top of model is a **document object**, each subsequent object is called a **node**)
3. Uses a rendering engine to show the page on screen (including applying CSS styling to the HTML content)

All major browsers use a JavaScript interpreter to translate my instructions (in JavaScript) into instructions the computer can follow.

### How do I write a script for a web page?

HTML is the content layer, CSS the presentation layer, and JS the behavior layer. Together they form the basis of a popular approach to building pages called progressive enhancement.

JavaScript is written in plain text, just like HTML and CSS. Use the HTML `<script>` element to link to a JS file from an HTML page. This tells the browser it is coming across as a script. The script's `src` attribute tells people where the JS file is stored.

Linking a JS script to an HTML doc does *not* change anything else in the source code. A developer *can* write scripts directly into HTML docs, but it's a best practice to *instead* put scripts in their own JS files.

Example of JavaScript below:

```
document.write('Good afternoon!');
```

In the above line of JS code:

- `document` object represents the entire web page
- the dot `.` after it is known as the member operator, which allows access to the object's methods and properties (also know as members of the object)
- the entire `write('Good afternoon!');` section is a method of the `document` object that allows new content to be written into the page where the `<script>` element sits
- the data within the parentheses comprise the parameter(s) of the method (in this example, providing the text of what should be written into the page)

Javascript runs where it is found in the HTML (when the broswer comes across the `<script>` element, it stops to load the script and then checks to see if it needs to do anything).
