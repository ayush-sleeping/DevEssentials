<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### Table of content :

* <a href="#Best">HTML Introduction</a>
  * <a href="#During">HTML structure</a>
  * <a href="#During">Heading</a>
  * <a href="#During">Paragraph</a>
  * <a href="#During">Images</a>
  * <a href="#During">Anchor Tags</a>
  * <a href="#During">Ordered and Unordered Lists</a>
* <a href="#During">Styles</a>
* <a href="#During">Block and Inline Displa Values</a>
* <a href="#During">Group Styles using Class Attribute</a>
* <a href="#During">Hyperlinks</a>
* <a href="#During">ID attribute</a>
* <a href="#During">HTML5 vs HTML4</a>
  * <a href="#During">Elements and Attributes in HTML5</a>
  * <a href="#During">Semantic Elements</a>
* <a href="#During">HTML Tables</a>
  * <a href="#During">Span Table rows and Columns</a>
  * <a href="#During">Layouts in Tables</a>
* <a href="#During">HTML Forms</a>
  * <a href="#During">Form Input Types</a>
  * <a href="#During">Style in Forms</a>
  * <a href="#During">GET and POST</a>
  * <a href="#During">Form Input Types</a>
  * <a href="#During">Form Input Attributes</a>
  * <a href="#During">Form Validation</a>
* <a href="#During">Embedding Multimedia</a>
  * <a href="#During"> Videos in Webpage</a>
  * <a href="#During"> Audio</a>
  * <a href="#During"> <embed> elements</a>
  * <a href="#During"> embed YT videos</a>
* <a href="#During">Vector Graphics</a>
  * <a href="#During">SVG</a>
  * <a href="#During">Circle using SVG</a>
  * <a href="#During">Rectangle using SVG</a>
  * <a href="#During"></a>
* <a href="#During"></a>



#
<!-- ---------------------------------------------------------------------------------------------------------------------- -->


Basic Structure of the HTML page:-

<!DOCTYPE html>        1.the document begin with doctype html tag, This tag tell the browser that the markup of the language in which page is written is HTML.


<html>      2. Open html tag, html tag is the building block of the page. most other tag nested within open html tag and closing html tag, html tag must be 
               closed to define the ending of the page.


<head>      3. similar to html tag, head tag also having corresponding closing tag. Note that anything contain within open tag and closing tag will not visible 
               within content area of your browser. the headtag contains important instruction for your browser, 

               (a). <title>:- First it identify the <title> of the page, actual title of the page must contain within title tag.

               (b). <meta:- >Second it contain the meta tag, meta tag communicate with both web browser and search engine to provide valuable information of your page.
                    goal of the meta tag is to pursue the searcher the click through to your website. 

               (c). <style>:- third it contain style tag, the code that is included within style tag are refer to as style rules and it define what is known as pages 
                    CSS (Cascading style sheets):{A set of rules that define the presentation of visual elements on an HTML page}.

               (d). <script>:- and next comes block of code is Javascript function, remember the javascript allows us to create interactive effects within web browser. 
                    the head tag contain the javascript  functions that will be called upon in the <body> of our HTML documents.


<body>       4. the body tag contain content, which is visible content area of your web-browser.
                here we also call our javascript function.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
HTML Paragraph Spacing:-
* We just to add "<p>   </p>".. at the opening and closing of the paragraph.


HTML Line breaks:-
* whenever we use "html paragraph spacing <p> tag", the space is too more between tow lines to avoid this we use <br> tag between <p> tag.


HTML Non-Breaking Space:-
* spacing between two characters-A commonly used entity in HTML is the nonbreaking space:" &nbsp;".A non-breaking space is a space that will not break into a new line.
  &nbsp;  :- Non-Breaking Space.


HTML Header Tags:-
* The <header> element represents a container for introductory content or a set of navigational links. 
  Open Header- "<h1>" .................close header- "</h1>".the 1 value represent the sizae of the header, smaller the value larger the header.
  A <header> element typically contains: (a). one or more heading elements (<h1> - <h6>)
                                         (b). logo or icon
                                         (c). authorship information
  Note: You can have several <header> elements in one HTML document. However, <header> cannot be placed within a <footer>, 
        <address> or another <header> element.

HTML Text Formatting and Decoration:-
* Formatting elements were designed to display special types of text:
  <b> - Bold text :- The HTML <b> element defines bold text, without any extra importance.
  <strong> - Important text:- The HTML <strong> element defines text with strong importance. The content inside is typically displayed in bold.
  <i> - Italic text:- The HTML <i> element defines a part of text in an alternate voice or mood. The content inside is typically displayed in italic.
  <em> - Emphasized text:- The HTML <em> element defines emphasized text. The content inside is typically displayed in italic.
  <mark> - Marked text:- The HTML <small> element defines smaller text:
  <small> - Smaller text:- The HTML <mark> element defines text that should be marked or highlighted:
  <del> - Deleted text:- The HTML <del> element defines text that has been deleted from a document. Browsers will usually strike a line through deleted text:
  <ins> - Inserted text:- The HTML <ins> element defines a text that has been inserted into a document. Browsers will usually underline inserted text:
  <sub> - Subscript text:- The HTML <sub> element defines subscript text. Subscript text appears half a character below the normal line, and is sometimes rendered 
                           in a smaller font. Subscript text can be used for chemical formulas, like H2O:
  <sup> - Superscript text:- The HTML <sup> element defines superscript text. Superscript text appears half a character above the normal line, and is sometimes 
                             rendered in a smaller font. Superscript text can be used for footnotes, like WWW[1]:

HTML Inline Text Formatting:-
* inline elements—that is, elements that are used inside other elements.
  Paragraphs, headings, and lists are “block-level” elements. They are self-contained sections that start on a new line and take up 
  the entire width of the container. But inline elements do not start on a new line and are only as wide as the content. 
  An example is the <strong> tag.


HTML Unordered Lists:-
* An unordered list starts with the <ul> tag. Each list item starts with the <li> tag. The list items will be marked with bullets (small black circles) by default.
   
HTML Ordered Lists :-
* An ordered list starts with the <ol> tag. Each list item starts with the <li> tag. The list items will be marked with numbers by default.

HTML Image Insertion:-
* The HTML <img> tag is used to embed an image in a web page. Images are not technically inserted into a web page; images are linked to web pages. 
  The <img> tag creates a holding space for the referenced image. The <img> tag is empty, it contains attributes only, and does not have a closing tag.
  The <img> tag has two required attributes:

  src - Specifies the path to the image
  alt - Specifies an alternate text for the image
  Syntax -
  <img src="url" alt="alternatetext">

HTML Embedding Videos:-
* To show a video in HTML, use the <video></video> element. 

HTML Absolute vs. Relative File Referencing:-
* The main difference between an absolute and relative pathway is that an absolute path specifies the location from the root directory and 
  carries detailed information whereas relative path is related to the current directory and carries only a part of the absolute pathway.

HTML Link Creation:-
* To make a hyperlink in an HTML page, use the <a> and </a> tags, which are the tags used to define the links. The <a> tag indicates where 
  the hyperlink starts and the </a> tag indicates where it ends. Whatever text gets added inside these tags, will work as a hyperlink. 
  Add the URL for the link in the <a href=” ”>.

HTML Anchor Tags:-
* The HTML anchor tag defines a hyperlink that links one page to another page. It can create hyperlink to other web page as well as files, 
  location, or any URL. The "href" attribute is the most important attribute of the HTML a tag. and which links to destination page or URL.

HTML Tables:-
* HTML tables allow web developers to arrange data into rows and columns. Define an HTML Table:-
  The <table> tag defines an HTML table. Each table row is defined with a <tr> tag. Each table header is defined with a <th> tag. 
  Each table data/cell is defined with a <td> tag. By default, the text in <th> elements are bold and centered.
  By default, the text in <td> elements are regular and left-aligned.

HTML Nested Tables:-
* The nested table in HTML means creating a table on a webpage inside another table on the same web page.

HTML Merging Cells:-
* To merge cells in HTML, use the colspan and rowspan attribute. The rowspan attribute is for the number of rows a cell should span,
  whereas the colspan attribute is for a number of columns a cell should span. Both the attribute will be inside the <td> tag. 
  The number will be a numeric value, for example, 2 for 2 rows if rowspan, 2 for 2 columns if column span.

HTML Text Wrapping:-
* The word-wrap property allows long words to be able to be broken and wrap onto the next line.

HTML Table Background Image:-
* The background attribute can also be used to control the background of an HTML elmement, specifically page body and table backgrounds. 
  You can specify an image to set background of your HMTL page or table. Following is the syntax to use background attribute with any HTML tag.
  The background is deprecated and it is recommended to use Style Sheet for background setting.        <tagname background="Image URL"...>

HTML Table Cell Alignment:-
* The <td> tag defines a standard data cell in an HTML table. An HTML table has two kinds of cells:
  Header cells - contains header information (created with the <th> element)  Data cells - contains data (created with the <td> element)
  The text in <td> elements are regular and left-aligned by default.  The text in <th> elements are bold and centered by default. 

HTML - Introduction to Forms:-
* An HTML form is a section of a document containing normal content, markup, special elements called controls (checkboxes, radio buttons, menus, etc.), 
  and labels on those controls. Users generally "complete" a form by modifying its controls (entering text, selecting menu items, etc.), 
  before submitting the form to an agent for processing (e.g., to a Web server, to a mail server, etc.)
  " Used to gather input from your User. "
  " Form Data can be inputted into a Database, or sent to an Email Address."
  " Input Forms are created in HTML. "
  " Data is submitted to a PHP Script for processing. "

HTML  Form Tags and Attributes:-
* List of All <form> Attributes
  Attribute	     Description
  accept-charse      Specifies the character encodings used for form submission
  action             Specifies where to send the form-data when a form is submitted
  autocomplete	     Specifies whether a form should have autocomplete on or off
  enctype	     Specifies how the form-data should be encoded when submitting it to the server (only for method="post")
  method	     Specifies the HTTP method to use when sending form-data
  name	             Specifies the name of the form
  novalidate	     Specifies that the form should not be validated when submitted
  rel	             Specifies the relationship between a linked resource and the current document
  target	     Specifies where to display the response that is received after submitting the form
 
HTML Form Elements:-
* Tag	          Description
 <form>	          Defines an HTML form for user input
 <input>	  Defines an input control
 <textarea>	  Defines a multiline input control (text area)
 <label>	  Defines a label for an <input> element
 <fieldset>	  Groups related elements in a form
 <legend>	  Defines a caption for a <fieldset> element
 <select>	  Defines a drop-down list
 <optgroup>	  Defines a group of related options in a drop-down list
 <option>	  Defines an option in a drop-down list
 <button>	  Defines a clickable button
 <datalist>	  Specifies a list of pre-defined options for input controls
 <output>	  Defines the result of a calculation

HTML Input Types:-
*  Here are the different input types you can use in HTML:

  <input type="button">
  <input type="checkbox">
  <input type="color">
  <input type="date">
  <input type="datetime-local">
  <input type="email">
  <input type="file">
  <input type="hidden">
  <input type="image">
  <input type="month">
  <input type="number">
  <input type="password">
  <input type="radio">
  <input type="range">
  <input type="search">
  <input type="submit">
  <input type="tel">
  <input type="text">
  <input type="time">
  <input type="url">
  <input type="week">   Tip: The default value of the type attribute is "text".

  Input Restrictions:-
  Here is a list of some common input restrictions:-

  Attribute	    Description
  checked	   Specifies that an input field should be pre-selected when the page loads (for type="checkbox" or type="radio")
  disabled	   Specifies that an input field should be disabled
  max	           Specifies the maximum value for an input field
  maxlength	   Specifies the maximum number of character for an input field
  min	           Specifies the minimum value for an input field
  pattern	   Specifies a regular expression to check the input value against
  readonly	   Specifies that an input field is read only (cannot be changed)
  required	   Specifies that an input field is required (must be filled out)
  size	           Specifies the width (in characters) of an input field
  step	           Specifies the legal number intervals for an input field
  value	           Specifies the default value for an input field
