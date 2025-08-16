
## HTML5 Learning Notes
> A short and comprehensive guide to HTML5 fundamentals, structure, and best practices
- What is html
> HTML (HyperText Markup Language) is the standard markup language for creating web pages. It provides the basic structure for web content, which is enhanced and styled using CSS (Cascading Style Sheets) and made interactive with JavaScript. HTML are like skeletons for web pages, providing the essential structure and layout.

<div id="top"></div>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->


### 📋 Table of Contents

| Section | Topic | Description |
|---------|-------|-------------|
| 1 | [HTML Overview](#html-overview) | Basic introduction to HTML |
| 2 | [HTML Structure](#basic-structure-of-the-html-page) | Basic structure of HTML page |
| 3 | [Paragraph](#html-paragraph-spacing) | HTML paragraph spacing |
| 4 | [Line Breaks](#html-line-breaks) | Using line breaks in HTML |
| 5 | [Non-Breaking Space](#html-non-breaking-space) | Understanding non-breaking spaces |
| 6 | [Header Tags](#html-header-tags) | HTML header elements |
| 7 | [Text Formatting and Decoration](#html-text-formatting-and-decoration) | Text styling options |
| 8 | [Inline Text Formatting](#html-inline-text-formatting) | Inline element formatting |
| 9 | [Unordered Lists](#html-unordered-lists) | Creating bullet point lists |
| 10 | [Ordered Lists](#html-ordered-lists) | Creating numbered lists |
| 11 | [Image Insertion](#html-image-insertion) | Adding images to HTML |
| 12 | [Embedding Videos](#html-embedding-videos) | Adding videos to HTML |
| 13 | [Absolute vs. Relative File Referencing](#html-absolute-vs-relative-file-referencing) | File path concepts |
| 14 | [Link Creation](#html-link-creation) | Creating hyperlinks |
| 15 | [Anchor Tags](#html-anchor-tags) | Understanding anchor elements |
| 16 | [Tables](#html-tables) | Creating HTML tables |
| 17 | [Nested Tables](#html-nested-tables) | Tables within tables |
| 18 | [Merging Cells](#html-merging-cells) | Colspan and rowspan |
| 19 | [Text Wrapping](#html-text-wrapping) | Text wrapping properties |
| 20 | [Table Background Image](#html-table-background-image) | Adding backgrounds to tables |
| 21 | [Table Cell Alignment](#html-table-cell-alignment) | Aligning table content |
| 22 | [Forms](#html-forms) | Introduction to HTML forms |
| 23 | [Form Tags and Attributes](#html-form-tags-and-attributes) | Form element attributes |
| 24 | [Form Elements](#html-form-elements) | Different form elements |
| 25 | [Input Types](#html-input-types) | Various input types |
| 26 | [Input Restrictions](#input-restrictions) | Input validation attributes |
| 27 | [Structure beyond div](#structure-beyond-div) | Semantic HTML elements |
| 28 | [Global Attributes](#global-attributes) | Common attributes for all HTML elements |
| 29 | [Embedding External Content](#embedding-external-content) | Integrating multimedia and other content |
| 30 | [Scripts](#scripts) | Adding JavaScript to HTML |
| 31 | [Dialogs and Disclosures](#dialogs-and-disclosures) | Creating interactive dialogs and disclosures |

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->
### HTML Overview

- HTML (HyperText Markup Language) is the standard markup language for creating web pages.
- It provides the basic structure for web content, which is enhanced and styled using CSS (Cascading Style Sheets) and made interactive with JavaScript.
- HTML elements are represented by tags, which are enclosed in angle brackets.
- Tags usually come in pairs: an opening tag and a closing tag, with the content in between.

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->


### Basic Structure of the HTML page

1. The document begin with doctype html tag, This tag tell the browser that the markup of the language in which page is written is HTML.
```
<!DOCTYPE html>
```

2. Open html tag, html tag is the building block of the page. most other tag nested within open html tag and closing html tag, html tag must be
               closed to define the ending of the page.
```
<html>
```

3. similar to html tag, head tag also having corresponding closing tag. Note that anything contain within open tag and closing tag will not visible
               within content area of your browser. the headtag contains important instruction for your browser,
```
<head>


(a). <title> :
First it identify the <title> of the page, actual title of the page must contain within title tag.

(b). <meta> :
Second it contain the meta tag, meta tag communicate with both web browser and
search engine to provide valuable information of your page.
goal of the meta tag is to pursue the searcher the click through to your website.

(c). <style>:
third it contain style tag, the code that is included within style tag are refer to as style rules and
it define what is known as pages CSS (Cascading style sheets):
{A set of rules that define the presentation of visual elements on an HTML page}.

(d). <script>:
and next comes block of code is Javascript function, remember the javascript allows us to create
interactive effects within web browser. the head tag contain the javascript  functions that
will be called upon in the <body> of our HTML documents.

```

4. the body tag contain content, which is visible content area of your web-browser.
   here we also call our javascript function.
```
<body>
```

- Boilerplate
```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Document title</title>

    <!-- Make layout adapt to device width & prevent weird zoom -->
    <meta name="viewport" content="width=device-width,initial-scale=1" />

    <!-- SEO basics -->
    <meta name="description" content="One concise sentence about this page." />

    <!-- Favicons / PWA (minimal set) -->
    <link rel="icon" href="/favicon.svg" type="image/svg+xml" />
    <link rel="icon" href="/favicon.ico" sizes="any" />
    <link rel="apple-touch-icon" href="/apple-touch-icon.png" />
    <!-- Optional PWA manifest -->
    <link rel="manifest" href="/app.webmanifest" />

    <!-- Social share (Open Graph / Twitter) – optional but pragmatic -->
    <meta property="og:title" content="Document title" />
    <meta property="og:description" content="One concise sentence." />
    <meta property="og:type" content="website" />
    <meta property="og:url" content="https://example.com/page" />
    <meta property="og:image" content="https://example.com/og.jpg" />
    <meta name="twitter:card" content="summary_large_image" />
  </head>
  <body>...</body>
</html>

```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Paragraph Spacing
We just to add ``` <p>   </p>``` at the opening and closing of the paragraph.




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Line breaks
* whenever we use "html paragraph spacing ``` <p> ``` tag", the space is too more between tow lines to avoid this we use``` <br> ```tag between``` <p>``` tag.




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Non-Breaking Space
spacing between two characters - A commonly used entity in HTML is the nonbreaking space: ``` &nbsp; ```. <br>
A non-breaking space is a space that will not break into a new line. <br>
 ``` &nbsp; ``` : Non-Breaking Space.




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Header Tags

- The headers element represents a container for introductory content or a set of navigational links.
- Open Header-```<h1>```
- header- ```</h1>```.the 1 value represent the size of the header, smaller the value larger the header.
- A ```<header>``` element typically contains: <br>
  - (a). one or more heading elements ```(<h1> - <h6>)```
  - (b). logo or icon <br>
  - (c). authorship information  <br>
* Note: You can have several ```<header>``` elements in one HTML document. However,``` <header> ```cannot be placed within a``` <footer>```, ``` <address>``` or another``` <header>``` element.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Text Formatting and Decoration
Formatting elements were designed to display special types of text:

| HTML Tag    | Description                                                                                                                                         |
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| `<b>`       | **Bold text** — Defines bold text without extra importance.                                                                                        |
| `<strong>`  | **Important text** — Defines text with strong importance (typically bold).                                                                          |
| `<i>`       | **Italic text** — Defines text in an alternate voice or mood (typically italic).                                                                   |
| `<em>`      | **Emphasized text** — Defines emphasized text (typically italic).                                                                                   |
| `<mark>`    | **Marked text** — Defines text that should be marked or highlighted.                                                                                |
| `<small>`   | **Smaller text** — Defines smaller-sized text.                                                                                                      |
| `<del>`     | **Deleted text** — Defines deleted text, usually displayed with a strike-through.                                                                   |
| `<ins>`     | **Inserted text** — Defines inserted text, usually displayed with an underline.                                                                     |
| `<sub>`     | **Subscript text** — Defines subscript text (appears below the normal line). Useful for formulas like `H₂O`.                                       |
| `<sup>`     | **Superscript text** — Defines superscript text (appears above the normal line). Useful for footnotes like `WWW¹`.                                 |



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Inline Text Formatting
Inline elements—that is, elements that are used inside other elements. <br>
  - Paragraphs, headings, and lists are “block-level” elements. They are self-contained sections that start on a new line and take up
  - The entire width of the container. But inline elements do not start on a new line and are only as wide as the content.  <br>
  - An example is the ```<strong>``` tag.




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Unordered Lists
- An unordered list starts with the ```<ul> ```tag. Each list item starts with the``` <li> ```tag. The list items will be marked with bullets (small black circles) by default.




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Ordered Lists
- An ordered list starts with the ```<ol>``` tag. Each list item starts with the ```<li>``` tag. The list items will be marked with numbers by default.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Image Insertion
The HTML ```<img>``` tag is used to embed an image in a web page. Images are not technically inserted into a web page; images are linked to web pages.
- The ```<img>``` tag creates a holding space for the referenced image. The <img> tag is empty, it contains attributes only, and does not have a closing tag. <br>
- The``` <img> ```tag has two required attributes :
    - ``` src ```- Specifies the path to the image
    - ``` alt``` - Specifies an alternate text for the image
    Syntax -
    - ``` <img src="url" alt="alternatetext">```

Responsive Images (CLS-safe, bandwidth-friendly)
- Always set ```width``` & ```height``` on ```<img>``` to reserve space and avoid layout shift.
- Use ```srcset```/```sizes``` for responsive images; use ```<picture>``` for art-direction (different crops/formats).
- Lazy-load below-the-fold images with ```loading="lazy"```; consider ```decoding="async"```.
```html
<picture>
  <source srcset="/hero.avif 1x, /hero@2x.avif 2x" type="image/avif" />
  <source srcset="/hero.webp 1x, /hero@2x.webp 2x" type="image/webp" />
  <img
    src="/hero.jpg"
    srcset="/hero.jpg 1x, /hero@2x.jpg 2x"
    sizes="(min-width: 800px) 800px, 100vw"
    width="800" height="450"
    alt="Team working together in a sunny office"
    loading="lazy" decoding="async"
  />
</picture>
```

(video/audio)
- Include controls; if you autoplay, you must also set muted (browser policy).
- Add captions with ```<track kind="captions" srclang="en" src="captions.vtt">```.
- Consider ```playsinline``` on mobile; ```poster``` for a thumbnail; ```preload``` strategy.
```html
<video controls playsinline preload="metadata" width="640" height="360" poster="/poster.jpg">
  <source src="/clip.webm" type="video/webm" />
  <source src="/clip.mp4" type="video/mp4" />
  <track kind="captions" srclang="en" src="/clip.en.vtt" label="English" default />
  Sorry, your browser doesn’t support HTML video.
</video>
```


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Embedding Videos
- To show a video in HTML, use the ```<video>  </video>``` element.



#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Absolute vs. Relative File Referencing
- The main difference between an absolute and relative pathway is that an absolute path specifies the location from the root directory and
- Carries detailed information whereas relative path is related to the current directory and carries only a part of the absolute pathway.


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Link Creation
To make a hyperlink in an HTML page, use the ```<a>``` and ```</a>``` tags, which are the tags used to define the links. The ```<a>``` tag indicates where <br>
- the hyperlink starts and the </a> tag indicates where it ends. Whatever text gets added inside these tags, will work as a hyperlink. <br>
- Add the URL for the link in the ```<a href=” ”>```.




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Anchor Tags
- The HTML anchor tag defines a hyperlink that links one page to another page. It can create hyperlink to other web page as well as files,
  location, or any URL. The ```href``` attribute is the most important attribute of the HTML a tag. and which links to destination page or URL.

Links the Safe Way
- Always use meaningful link text (not “click here”).
- If you open in a new tab (```target="_blank"```), also add ```rel="noopener"``` (and usually ```noreferrer```) to prevent ```window.opener``` attacks.
```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">
  Read the docs
</a>
```

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Tables
HTML tables allow web developers to arrange data into rows and columns. Define an HTML Table. <br>
- The ```<table> ```tag defines an HTML table. Each table row is defined with a ```<tr>``` tag. Each table header is defined with a ```<th>``` tag. <br>
- Each table data/cell is defined with a ```<td>``` tag. By default, the text in ```<th>``` elements are bold and centered.
- By default, the text in``` <td>``` elements are regular and left-aligned.


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Nested Tables
- The nested table in HTML means creating a table on a webpage inside another table on the same web page.




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Merging Cells
To merge cells in HTML, use the colspan and rowspan attribute. The rowspan attribute is for the number of rows a cell should span, <br>
- whereas the colspan attribute is for a number of columns a cell should span. Both the attribute will be inside the``` <td>``` tag.  <br>
- The number will be a numeric value, for example, 2 for 2 rows if rowspan, 2 for 2 columns if column span. <br>



#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Text Wrapping
- The word-wrap property allows long words to be able to be broken and wrap onto the next line.


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Table Background Image
The background attribute can also be used to control the background of an HTML elmement, specifically page body and table backgrounds.  <br>
- You can specify an image to set background of your HMTL page or table. Following is the syntax to use background attribute with any HTML tag.  <br>
- The background is deprecated and it is recommended to use Style Sheet for background setting.        <tagname background="Image URL"...>  <br>



#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Table Cell Alignment
The <td> tag defines a standard data cell in an HTML table. An HTML table has two kinds of cells:  <br>
- Header cells - contains header information (created with the``` <th>``` element)  Data cells - contains data (created with the ```<td>``` element)  <br>
- The text in ```<td>``` elements are regular and left-aligned by default.  The text in ```<th>``` elements are bold and centered by default.   <br>




#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Forms
An HTML form is a section of a document containing normal content, markup, special elements called controls (checkboxes, radio buttons, menus, etc.),   <br>
- and labels on those controls. Users generally "complete" a form by modifying its controls (entering text, selecting menu items, etc.),  <br>
- before submitting the form to an agent for processing (e.g., to a Web server, to a mail server, etc.) <br>
    - " Used to gather input from your User. " <br>
    - " Form Data can be inputted into a Database, or sent to an Email Address." <br>
    - " Input Forms are created in HTML. " <br>
    - " Data is submitted to a PHP Script for processing. " <br>

Accessible, Modern Forms (beyond just ```<input>```)
- Always pair ```<label for="id">``` with inputs; use ```name``` for submission; use ```<fieldset>```/```<legend>``` to group related controls.
- Native validation: ```required```, ```min```, ```max```, ```pattern```, with title to hint the pattern. Use the Constraint Validation API to trigger messages.
- Useful attributes: ```autocomplete```, ```inputmode```, ```multiple```, ```accept```/```capture``` (file), ```step```, ```readonly```, ```disabled```.
```html
<form action="/signup" method="post" novalidate>
  <fieldset>
    <legend>Sign up</legend>

    <label for="email">Email</label>
    <input id="email" name="email" type="email"
           autocomplete="email" required />

    <label for="age">Age</label>
    <input id="age" name="age" type="number" min="13" max="120" step="1" />

    <label for="phone">Phone</label>
    <input id="phone" name="phone" type="tel" inputmode="numeric"
           autocomplete="tel" placeholder="98765 43210" />

    <button type="submit">Create account</button>
  </fieldset>
</form>

<script>
  document.querySelector('form').addEventListener('submit', (e) => {
    if (!e.target.checkValidity()) {
      e.preventDefault();
      e.target.reportValidity(); // native messages
    }
  });
</script>
```

Tables That Are Actually Accessible
- Use ```<caption>```, ```<thead>```, ```<tbody>```, ```<tfoot>```.
- Use ```<th scope="col|row">``` for simple tables.
- For complex headers, associate data cells with header cells using ```headers```/```id```.
```html
<table>
  <caption>Quarterly revenue (₹Lakh)</caption>
  <thead>
    <tr>
      <th scope="col">Quarter</th>
      <th scope="col">Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr><th scope="row">Q1</th><td>24.3</td></tr>
    <tr><th scope="row">Q2</th><td>27.1</td></tr>
  </tbody>
</table>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Form Tags and Attributes
List of All ```<form> ``` Attributes <br>

| Attribute         | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `accept-charset` | Specifies the character encodings used for form submission                 |
| `action`         | Specifies where to send the form-data when a form is submitted             |
| `autocomplete`   | Specifies whether a form should have autocomplete on or off                |
| `enctype`        | Specifies how the form-data should be encoded when submitting to the server (only for `method="post"`) |
| `method`         | Specifies the HTTP method to use when sending form-data                    |
| `name`           | Specifies the name of the form                                              |
| `novalidate`     | Specifies that the form should not be validated when submitted             |
| `rel`            | Specifies the relationship between a linked resource and the current document |
| `target`         | Specifies where to display the response that is received after submitting the form |





#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Form Elements

| Tag           | Description                                                        |
|---------------|--------------------------------------------------------------------|
| `<form>`      | Defines an HTML form for user input                                |
| `<input>`     | Defines an input control                                           |
| `<textarea>`  | Defines a multiline input control (text area)                      |
| `<label>`     | Defines a label for an `<input>` element                           |
| `<fieldset>`  | Groups related elements in a form                                  |
| `<legend>`    | Defines a caption for a `<fieldset>` element                       |
| `<select>`    | Defines a drop-down list                                           |
| `<optgroup>`  | Defines a group of related options in a drop-down list             |
| `<option>`    | Defines an option in a drop-down list                              |
| `<button>`    | Defines a clickable button                                         |
| `<datalist>`  | Specifies a list of pre-defined options for input controls         |
| `<output>`    | Defines the result of a calculation                                |



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



### HTML Input Types

| Input Type         | Description                                      |
|--------------------|--------------------------------------------------|
| `button`           | A clickable button (used with JavaScript)        |
| `checkbox`         | A checkbox allowing single/multiple selections   |
| `color`            | A color picker control                           |
| `date`             | A date selector (no time)                        |
| `datetime-local`   | A date and time selector (local timezone)        |
| `email`            | A field for entering email addresses             |
| `file`             | A file upload control                            |
| `hidden`           | A hidden input (invisible to users)              |
| `image`            | A graphical submit button using an image         |
| `month`            | A selector for year and month                    |
| `number`           | A field for numeric input with arrows            |
| `password`         | A masked text field for passwords                |
| `radio`            | A single-select option within a group            |
| `range`            | A slider control for selecting a range value     |
| `search`           | A text field optimized for search input          |
| `submit`           | A button to submit the form                      |
| `tel`              | A field for telephone numbers                    |
| `text`             | A single-line plain text field                   |
| `time`             | A time selector (hours and minutes)              |
| `url`              | A field for website URLs                         |
| `week`             | A selector for week and year                     |

> **Tip:** The default `type` value is `"text"` if not specified.



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->



 ### Input Restrictions

| Attribute   | Description                                                                 |
|-------------|-----------------------------------------------------------------------------|
| `checked`   | Pre-selects input on page load (used with `type="checkbox"` or `radio`)     |
| `disabled`  | Disables the input field so it's not editable or clickable                  |
| `max`       | Sets the maximum numeric/date value allowed                                 |
| `maxlength` | Limits the number of characters in a text field                             |
| `min`       | Sets the minimum numeric/date value allowed                                 |
| `pattern`   | Validates input using a custom regular expression (RegEx)                   |
| `readonly`  | Makes the field read-only (user can't edit but value is visible & sent)     |
| `required`  | Marks the field as mandatory to submit the form                             |
| `size`      | Sets the visible width (in characters) of a text field                      |
| `step`      | Sets legal number/date intervals (like 0.01, 5, etc.)                        |
| `value`     | Defines the default or pre-filled value of the input field                  |




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### Structure beyond div
Use semantic elements to describe regions:
- ```<header>, <nav>, <main>, <section>, <article>, <aside>, <footer>```
- ```<figure> + <figcaption>, <time datetime>, <address>```
- Headings (```<h1>–<h6>```) express a logical outline. It’s fine to have multiple ```<h1>```s in different sections, but most teams prefer one ```<h1>``` per page for clarity and accessibility.

```html
<a href="#main" class="skip-link">Skip to main content</a>

<header> ... site branding/nav ... </header>
<main id="main">
  <article>
    <h1>Article title</h1>
    <p>...</p>
    <figure>
      <img src="cat.jpg" alt="Black cat sleeping on a keyboard" />
      <figcaption>Our mascot hard at work.</figcaption>
    </figure>
  </article>
  <aside>Related links</aside>
</main>
<footer>© 2025</footer>

```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### Global Attributes

- ```lang="en"``` on ```<html>``` (screen readers, spellcheck)
- ```dir="ltr|rtl"```, plus ```<bdi>/<bdo>``` for bidirectional text fixes
- ```id```, ```class```, ```title```, ```hidden```, ```tabindex```, ```contenteditable```, ```spellcheck```, ```draggable```, ```translate```, ```data-*``` for custom data
- ```inert``` (modern): make subtree unfocusable/inert during modals

```html
<p lang="hi">नमस्ते</p>
<span dir="rtl">اردو</span>
<button data-track="cta">Buy</button>
<div inert>Background content disabled while dialog is open</div>
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### Embedding External Content
- (```<iframe>```)
- Use title to describe the frame.
- Consider ```loading="lazy"``` for below-the-fold iframes.
- Lock down with ```sandbox``` and ```allow``` (permissions).
- ```srcdoc``` can inline simple content.

```html
<iframe
  title="Map of Mumbai"
  src="https://maps.example.com/embed?id=123"
  loading="lazy"
  sandbox="allow-scripts allow-same-origin"
  allow="fullscreen; geolocation">
</iframe>
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### Scripts
```defer```, ```async```, and ES Modules
Put scripts in ```<head>``` with ```defer``` to download in parallel and execute after parsing.
Use ```async``` for independent scripts (order not guaranteed).
Use ES modules: ```type="module";``` optionally provide a ```nomodule``` fallback.

```html
<!-- Ordered; runs after HTML parse -->
<script src="/app.js" defer></script>

<!-- Independent; runs ASAP when loaded -->
<script src="/ads.js" async></script>

<!-- Modern modules -->
<script type="module" src="/app.mjs"></script>
<script nomodule src="/legacy.bundle.js"></script>
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### Dialogs and Disclosures
- (no heavy JS needed)
- Native modal dialogs with `<dialog>` and `.showModal()`.
- Simple show/hide content with `<details><summary>...</summary>...</details>`.
```html
<details>
  <summary>See prerequisites</summary>
  <ul><li>HTML basics</li><li>CSS basics</li></ul>
</details>

<dialog id="hire">
  <form method="dialog">
    <p>Thanks for applying!</p>
    <button>Close</button>
  </form>
</dialog>
<button onclick="document.getElementById('hire').showModal()">Open modal</button>
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->
