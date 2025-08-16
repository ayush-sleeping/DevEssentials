## CSS Learning Notes
> A short and comprehensive guide to CSS fundamentals, structure, and best practices
- What is CSS
> CSS (Cascading Style Sheets) is the standard stylesheet language for describing the presentation of a document written in HTML or XML. It controls the layout, colors, fonts, and overall visual appearance of web pages, allowing for separation of content and design.

<div id="top"></div>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### 📋 Table of Contents

| Section | Topic                                                                | Description                                                          |
| ------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| 1       | [CSS Overview](#css-overview)                                        | Basic introduction to CSS                                            |
| 2       | [CSS Syntax & Selectors](#css-syntax--selectors)                     | How CSS is written and applied                                       |
| 3       | [Colors & Units](#colors--units)                                     | Color formats and measurement units                                  |
| 4       | [Box Model](#box-model)                                              | Margin, border, padding, content                                     |
| 5       | [Typography](#typography)                                            | Fonts, text styles, and alignment                                    |
| 6       | [Backgrounds & Borders](#backgrounds--borders)                       | Styling backgrounds and borders                                      |
| 7       | [Display & Positioning](#display--positioning)                       | Layout, positioning, and stacking                                    |
| 8       | [Flexbox](#flexbox)                                                  | Modern layout with flexbox                                           |
| 9       | [Grid](#grid)                                                        | Two-dimensional layout with grid                                     |
| 10      | [Responsive Design](#responsive-design)                              | Media queries and mobile-first                                       |
| 11      | [Transitions & Animations](#transitions--animations)                 | CSS transitions and keyframes                                        |
| 12      | [Pseudo-classes & Pseudo-elements](#pseudo-classes--pseudo-elements) | Advanced selectors                                                   |
| 13      | [Variables & Custom Properties](#variables--custom-properties)       | Reusable values                                                      |
| 14      | [CSS Functions](#css-functions)                                      | Common functions like `calc()`, `var()`, `clamp()`, `min()`, `max()` |
| 15      | [Transforms](#transforms)                                            | 2D/3D transformations (`scale`, `rotate`, `translate`, `skew`)       |
| 16      | [Z-Index & Stacking Context](#z-index--stacking-context)             | How elements layer on top of each other                              |
| 17      | [CSS Specificity & Cascade](#css-specificity--cascade)               | How conflicts are resolved (inline vs class vs id)                   |
| 18      | [CSS Inheritance](#css-inheritance)                                  | Which properties inherit by default                                  |
| 19      | [CSS Functions & Filters](#css-filters)                              | Blur, grayscale, drop-shadow, brightness                             |
| 20      | [Clipping & Masking](#clipping--masking)                             | Creating shapes with `clip-path`, `mask`                             |
| 21      | [CSS Shapes & Object Fit](#css-shapes--object-fit)                   | Wrapping text around shapes, controlling images                      |
| 22      | [CSS Scroll & Overflow](#css-scroll--overflow)                       | `overflow`, scroll snapping, smooth scrolling                        |
| 23      | [CSS Logical Properties](#css-logical-properties)                    | Writing direction-aware properties (good for i18n)                   |
| 24      | [CSS Layers (@layer)](#css-layers)                                   | Organizing styles with cascade layers                                |
| 25      | [CSS Functions for Layout](#css-functions-for-layout)                | `aspect-ratio`, `fit-content`, `minmax()`                            |
| 26      | [Print Styles](#print-styles)                                        | Making pages printable                                               |
| 27      | [Performance Optimization](#performance-optimization)                | Minification, avoiding repaints/reflows                              |
| 28      | [Best Practices](#best-practices)                                    | Clean, maintainable CSS                                              |
| 29      | [CSS Properties Reference Table](#css-properties-reference-table)    | Comprehensive list of CSS properties and their values                |
| 30      | [Selectors and Pseudo Classes and Elements and Attribute Selectors](#selectors-and-pseudo-classes-and-elements-and-attribute-selectors) | Advanced targeting techniques                                       |
| 31      | [Media Queries](#media-queries)                                      | Responsive design with media queries                                 |

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>




### CSS Overview

- **Definition**: CSS (Cascading Style Sheets) is used to style HTML elements.
- **Purpose**: Controls layout, colors, fonts, spacing, and responsiveness.
- **Ways to use CSS**:
  1. **Inline CSS** → `<p style="color: red;">`
  2. **Internal CSS** → inside `<style>` in HTML
  3. **External CSS** → separate `.css` file linked using `<link>`

- **Separation of concerns:** HTML for structure, CSS for presentation, JavaScript for behavior.
- **Selectors:** Target HTML elements to style them.
- **Cascade & specificity:** Rules are applied based on order and specificity.
- **Responsive design:** CSS enables layouts that adapt to different devices.



#### Basics & Syntax

CSS is written as rulesets:
```css
selector {
  property: value;
  property2: value2;
}
```

#### Include External CSS File
```html
<link rel="stylesheet" type="text/css" href="/style.css" />
```

#### Internal Styles
```html
<style type="text/css">
  div { color: #444; }
</style>
```

#### Inline Styles
```html
<tag style="property: value"> ... </tag>
```



#### Clearfix (for clearing floats)
```css
.clearfix:after {
  clear: both;
  content: " ";
  display: block;
  font-size: 0;
  height: 0;
  visibility: hidden;
}
.clearfix { display: inline-block; }
* html .clearfix { height: 1%; }
.clearfix { display: block; }
```



#### Box Model
- **margin**
- **border**
- **padding**
- **content**

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->
#



### CSS Syntax & Selectors

CSS is made up of rulesets. Each ruleset consists of a selector and a declaration block:


- **Syntax**:
  ```css
  selector {
    property: value;
  }

**Example:**
```css
h1 {
  color: #3498db;
  font-size: 2rem;
}
```

**Selectors:**
- `element` (e.g., `h1`, `p`)
- `.class` (e.g., `.btn`)
- `#id` (e.g., `#header`)
- `[attribute]` (e.g., `[type="text"]`)
- `*` (universal selector)
- `element, element` (grouping)
- `element element` (descendant)
- `element > element` (child)
- `element + element` (adjacent sibling)
- `element ~ element` (general sibling)


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Colors & Units

Colors in CSS can be defined in several ways:

- **Named colors:** e.g., `red`, `blue`, `green`
- **Hexadecimal:** e.g., `#ff0000`, `#00ff00`, `#0000ff`
- **RGB:** e.g., `rgb(255, 0, 0)`, `rgb(0, 255, 0)`, `rgb(0, 0, 255)`
- **RGBA:** e.g., `rgba(255, 0, 0, 0.5)` (red with 50% opacity)
- **HSL:** e.g., `hsl(0, 100%, 50%)` (hue, saturation, lightness)
- **HSLA:** e.g., `hsla(0, 100%, 50%, 0.5)` (hue, saturation, lightness, alpha)

**Units:**
- **Absolute units:** `px`, `pt`, `cm`, `in`
- **Relative units:** `em`, `rem`, `vw`, `vh`, `%`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Box Model

The CSS box model describes the rectangular boxes generated for elements in the document tree and consists of:

- **Content:** The innermost part where text and images appear.
- **Padding:** Space between the content and the border, inside the element.
- **Border:** A border that surrounds the padding (if any) and content.
- **Margin:** Space outside the border, separating the element from others.

![CSS Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/boxmodel.png)

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Typography

CSS provides various properties to control the typography of your content:

- **Font properties:** `font-family`, `font-size`, `font-weight`, `font-style`
- **Text properties:** `color`, `text-align`, `text-decoration`, `text-transform`, `line-height`
- **Letter and word spacing:** `letter-spacing`, `word-spacing`

**Web-safe fonts:** Consider using web-safe fonts or providing fallbacks in your `font-family` stack.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Backgrounds & Borders

You can style the backgrounds and borders of elements using CSS:

- **Background properties:** `background-color`, `background-image`, `background-repeat`, `background-position`, `background-size`
- **Border properties:** `border-width`, `border-style`, `border-color`, `border-radius`

**Shorthand properties:**
- `background`: A shorthand property for setting all background properties.
- `border`: A shorthand property for setting all border properties.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Display & Positioning

CSS controls the display and positioning of elements on the page:

- **Display types:** `block`, `inline`, `inline-block`, `flex`, `grid`, `none`
- **Positioning schemes:** `static`, `relative`, `absolute`, `fixed`, `sticky`
- **Z-index:** Controls the stacking order of positioned elements.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Flexbox

Flexbox is a CSS layout module designed for one-dimensional layouts:

- **Container properties:** `display: flex`, `flex-direction`, `flex-wrap`, `justify-content`, `align-items`, `align-content`
- **Item properties:** `flex-grow`, `flex-shrink`, `flex-basis`, `align-self`

![Flexbox Layout](https://css-tricks.com/wp-content/uploads/2019/10/Screen-Shot-2019-10-14-at-10.07.57-PM.png)

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Grid

CSS Grid Layout is a two-dimensional layout system:

- **Container properties:** `display: grid`, `grid-template-columns`, `grid-template-rows`, `grid-area`, `gap`
- **Item properties:** `grid-column`, `grid-row`, `grid-area`

![CSS Grid Layout](https://css-tricks.com/wp-content/uploads/2019/10/Screen-Shot-2019-10-14-at-10.08.57-PM.png)

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Responsive Design

Responsive design ensures your website looks good on all devices:

- **Media queries:** Apply styles based on device characteristics (e.g., width, height, orientation).
- **Mobile-first approach:** Start with a base style for small screens, then add enhancements for larger screens.
- **Responsive units:** Use relative units like `%`, `em`, `rem`, `vw`, `vh` for flexible layouts.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Transitions & Animations

CSS transitions and animations add interactivity and flair:

- **Transitions:** Smoothly change property values over a specified duration.
- **Animations:** Create complex sequences of changes using keyframes.

**Example of a transition:**
```css
button {
  background-color: blue;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: green;
}
```

**Example of an animation:**
```css
@keyframes slidein {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}

div {
  animation: slidein 0.5s forwards;
}
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Pseudo-classes & Pseudo-elements

Pseudo-classes and pseudo-elements allow you to style elements based on their state or position:

- **Pseudo-classes:** e.g., `:hover`, `:focus`, `:nth-child()`, `:first-child`, `:last-child`
- **Pseudo-elements:** e.g., `::before`, `::after`, `::first-line`, `::first-letter`

**Example:**
```css
a:hover {
  color: red;
}

p::first-line {
  font-weight: bold;
}
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Variables & Custom Properties

CSS variables (also known as custom properties) enable you to store and reuse values:

```css
:root {
  --main-color: #3498db;
  --padding: 16px;
}

.box {
  background-color: var(--main-color);
  padding: var(--padding);
}
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Functions

CSS provides built-in functions for calculations and dynamic values:
- `calc()`: Perform calculations for property values.
  ```css
  .sidebar {
    width: calc(100vw - 300px);
  }
  ```
- `var()`: Use custom properties (CSS variables).
  ```css
  :root {
    --main-color: #3498db;
  }
  .btn {
    background: var(--main-color);
  }
  ```
- `clamp()`: Set a value within a range.
  ```css
  h1 {
    font-size: clamp(1.5rem, 4vw, 3rem);
  }
  ```
- `min()`, `max()`: Use the minimum or maximum of multiple values.
  ```css
  .box {
    width: min(400px, 90vw);
    height: max(200px, 50vh);
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Transforms

CSS transforms allow you to move, rotate, scale, and skew elements:
- Scale up:
  ```css
  .zoom {
    transform: scale(1.2);
  }
  ```
- Rotate:
  ```css
  .rotate {
    transform: rotate(45deg);
  }
  ```
- Move horizontally:
  ```css
  .move {
    transform: translateX(50px);
  }
  ```
- Skew vertically:
  ```css
  .skew {
    transform: skewY(10deg);
  }
  ```
- Combine multiple transforms:
  ```css
  .combo {
    transform: scale(1.2) rotate(45deg);
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Z-Index & Stacking Context

- `z-index` controls the stacking order of positioned elements (higher values appear above lower ones).
  ```css
  .modal {
    position: fixed;
    z-index: 1000;
  }
  .overlay {
    position: fixed;
    z-index: 999;
  }
  ```
- Stacking context is created by positioned elements (`position: relative|absolute|fixed|sticky`), opacity, transforms, and more.
- Use `z-index` carefully to avoid unexpected layering issues.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Specificity & Cascade

- **Specificity** determines which CSS rule applies when multiple rules target the same element.
  ```css
  /* Element selector */
  p { color: blue; }
  /* Class selector (higher specificity) */
  .text { color: green; }
  /* ID selector (highest specificity) */
  #main { color: red; }
  /* Inline style (highest of all) */
  <p style="color: orange;">Text</p>
  ```
- The **cascade** is the order in which rules are applied (last rule wins if specificity is equal).
- Use developer tools to inspect specificity conflicts.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Inheritance

- Some properties (like `color`, `font-family`) are inherited by child elements.
  ```css
  body {
    color: #222;
    font-family: Arial, sans-serif;
  }
  /* All text inside body inherits these unless overridden */
  ```
- Others (like `margin`, `padding`, `border`) are not inherited.
- Use `inherit`, `initial`, or `unset` to control inheritance.
  ```css
  .child {
    color: inherit;
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Functions & Filters

- **Filters** apply visual effects:
  ```css
  .blurred {
    filter: blur(4px);
  }
  .gray {
    filter: grayscale(100%);
  }
  .shadow {
    filter: drop-shadow(2px 4px 6px black);
  }
  .bright {
    filter: brightness(0.8);
  }
  ```
- Combine filters for creative effects.
  ```css
  .combo {
    filter: blur(2px) brightness(1.2);
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Clipping & Masking

- **Clipping:** Use `clip-path` to create custom shapes.
  ```css
  .circle {
    clip-path: circle(50% at 50% 50%);
  }
  .polygon {
    clip-path: polygon(0 0, 100% 0, 100% 100%);
  }
  ```
- **Masking:** Use `mask-image` to control element visibility.
  ```css
  .masked {
    mask-image: linear-gradient(to right, transparent, black);
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Shapes & Object Fit

- **Shapes:** Use `shape-outside` to wrap text around custom shapes.
  ```css
  .float-img {
    float: left;
    shape-outside: circle(50%);
    width: 200px;
    height: 200px;
    clip-path: circle(50%);
  }
  ```
- **Object Fit:** Control how images/video fit their container.
  ```css
  img.cover {
    object-fit: cover;
    width: 100%;
    height: 300px;
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Scroll & Overflow

- Control scrolling and overflow:
  ```css
  .scroll {
    overflow: auto;
    max-height: 200px;
  }
  .hidden {
    overflow: hidden;
  }
  ```
- Use `scroll-snap-type` for snap points.
  ```css
  .snap {
    scroll-snap-type: y mandatory;
  }
  .item {
    scroll-snap-align: start;
  }
  ```
- Enable smooth scrolling:
  ```css
  html {
    scroll-behavior: smooth;
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Logical Properties

- Logical properties adapt to writing direction (LTR/RTL):
  ```css
  .box {
    margin-inline-start: 2rem;
    padding-block-end: 1rem;
  }
  ```
- Useful for internationalization (i18n).

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Layers (@layer)

- Organize styles with cascade layers:
  ```css
  @layer base, components, utilities;
  @layer base {
    html { box-sizing: border-box; }
  }
  @layer components {
    .btn { padding: 1rem; }
  }
  ```
- Helps manage specificity and overrides in large projects.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CSS Functions for Layout

- `aspect-ratio`: Set width/height ratio.
  ```css
  .video {
    aspect-ratio: 16/9;
  }
  ```
- `fit-content`: Size elements based on content.
  ```css
  .container {
    width: fit-content;
  }
  ```
- `minmax()`: Used in grid layouts for flexible sizing.
  ```css
  .grid {
    display: grid;
    grid-template-columns: minmax(200px, 1fr) 2fr;
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Print Styles

- Use `@media print` to create styles for printed pages.
  ```css
  @media print {
    nav, .sidebar { display: none; }
    body { font-size: 12pt; }
  }
  ```
- Hide navigation, adjust layout, and optimize for paper.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Performance Optimization

- Minify CSS files for faster loading.
- Avoid excessive repaints/reflows by minimizing layout changes.
- Use efficient selectors and avoid deep nesting.
- Prefer hardware-accelerated properties (e.g., `transform`, `opacity`).
  ```css
  .fade {
    transition: opacity 0.3s;
    opacity: 0.5;
  }
  .move {
    transition: transform 0.3s;
    transform: translateY(10px);
  }
  ```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### CSS Properties Reference Table

| Property | Description |
|----------|------------|
| align-content | behavior of the flex-wrap property |
| align-items | alignment for items inside the container |
| align-self | alignment for the selected item |
| all | changes all properties |
| animation | binds an animation to an element |
| animation-delay | delays animation start |
| animation-direction | reverse animation or in alternate cycles |
| animation-duration | animation duration in seconds or ms |
| animation-fill-mode | style when the animation is not playing |
| animation-iteration-count | number of an animation replays |
| animation-name | name for the @keyframes animation |
| animation-play-state | the animation is running or paused |
| animation-timing-function | speed curve of an animation |
| backface-visibility | is element visible when not facing the screen |
| background | all background properties in one declaration |
| background-attachment | is the background image fixed or scrolls |
| background-blend-mode | blending mode of each background layer |
| background-clip | painting area of the background |
| background-color | background color |
| background-image | background image |
| background-origin | where the background image is positioned |
| background-position | starting position of the background image |
| background-repeat | the way the background image is repeated |
| background-size | background image size |
| border | sets all border properties in one line |
| border-bottom | bottom border properties in one line |
| border-bottom-color | color of the bottom border |
| border-bottom-left-radius | border bottom left radius |
| border-bottom-right-radius | border bottom right radius |
| border-bottom-style | border bottom style |
| border-bottom-width | border bottom width |
| border-collapse | border collapse |
| border-color | border color |
| border-image | sets an image as border |
| border-image-outset | border image area extends beyond the border box |
| border-image-repeat | border image repeated, rounded or stretched |
| border-image-slice | how to slice the border image |
| border-image-source | path to the border image |
| border-image-width | border image width |
| border-left | left border properties in one line |
| border-left-color | border left color |
| border-left-style | border left style |
| border-left-width | border left width |
| border-radius | border radius of the four rounded corners |
| border-right | right border properties in one line |
| border-right-color | border right color |
| border-right-style | border right style |
| border-right-width | border right width |
| border-spacing | border spacing |
| border-style | border style |
| border-top | top border properties in one line |
| border-top-color | border top color |
| border-top-left-radius | border top left radius |
| border-top-right-radius | border top right radius |
| border-top-style | border top style |
| border-top-width | border top width |
| border-width | border width |
| bottom | bottom offset for relative and absolute elements |
| box-shadow | shadow to element |
| box-sizing | box sizing properties |
| caption-side | placement of a table caption |
| clear | deny floating of an element |
| clip | clip an absolutely positioned element |
| color | text color |
| column-count | divide the content in columns |
| column-fill | balanced fill or not |
| column-gap | gap between the columns |
| column-rule | separator between columns, like border |
| column-rule-color | column rule color |
| column-rule-style | column rule style |
| column-rule-width | column rule width |
| column-span | column span |
| column-width | column width |
| columns | set column-width and column-count |
| content | insert content :before and :after elements |
| counter-increment | count sections |
| counter-reset | reset counter |
| cursor | cursor type when element is hovered |
| direction | writing direction, Arabic is using rtl |
| display | box display type |
| empty-cells | hide borders and background on empty table cells |
| filter | image effects: grayscale, blur, invert etc. |
| flex | item length, relative to others inside the container |
| flex-basis | initial length of a flexible item |
| flex-direction | direction of the flexible items |
| flex-flow | shorthand for flex-direction and flex-wrap |
| flex-grow | how much the item will grow relative other items |
| flex-shrink | how to shrink the item relative to other items |
| flex-wrap | wrap flexible items |
| float | float elements left or right |
| font | all font properties in one line |
| @font-face | declare non-web-safe fonts |
| font-family | font of the element |
| font-size | font size |
| font-size-adjust | control font size if the first declared option is not available |
| font-stretch | widen or narrow text |
| font-style | font style: normal, italic, oblique |
| font-variant | set small-caps |
| font-weight | use bold or thin characters |
| hanging-punctuation | can a punctuation mark be placed outside the line box? |
| height | height of the element |
| justify-content | justifies flexible container's items horizontally if necessary |
| @keyframes | specifies the animation code |
| left | left offset for relative and absolute elements |
| letter-spacing | space between characters |
| line-height | line height of text or inline-block elements |
| list-style | all list properties in one line |
| list-style-image | replace the list item marker with an image |
| list-style-position | list item markers inside or outside the content flow |
| list-style-type | set the type of the list item marker |
| margin | set the top, right, bottom and left margins in one line |
| margin-bottom | bottom margin |
| margin-left | left margin |
| margin-right | right margin |
| margin-top | margin top |
| max-height | maximum height of element |
| max-width | maximum width of element |
| @media | see media queries |
| min-height | minimum height |
| min-width | minimum width |
| nav-down | where to navigate when the the arrow-down button is pressed |
| nav-index | sets sequential navigation order |
| nav-left | where to navigate when the the arrow-left button is pressed |
| nav-right | where to navigate when the the arrow-right button is pressed |
| nav-up | where to navigate when the the arrow-up button is pressed |
| opacity | transparency level of an element |
| order | reorder elements in a container |
| outline | draw an outer border around elements |
| outline-color | outline color |
| outline-offset | gap between the element and the outline |
| outline-style | outline style |
| outline-width | outline width |
| overflow | hide, display or scroll if the content overflows its container |
| overflow-x | horizontal overflow |
| overflow-y | vertical overflow |
| padding | padding between the element border and content |
| padding-bottom | padding bottom |
| padding-left | padding left |
| padding-right | padding right |
| padding-top | padding top |
| page-break-after | adds page break after an element |
| page-break-before | adds page break before an element |
| page-break-inside | allow page break inside an element |
| perspective | how many pixels the 3D element is placed from the view |
| perspective-origin | where is the 3D element based in the x- and y-axis |
| position | positioning type: absolute, fixed, relative, static |
| quotes | set quotation marks to wrap an element |
| resize | declare resizable elements |
| right | right offset for relative and absolute elements |
| tab-size | tab character space length |
| table-layout | table layout algorithm |
| text-align | horizontal alignment of text |
| text-align-last | horizontal alignment of last line of text |
| text-decoration | overline, underline or line-through the text |
| text-indent | indentation of the first line of the text |
| text-overflow | the way how overflowed content is marked (ellipsis) |
| text-shadow | text shadow |
| text-transform | capitalization of text |
| top | top offset for relative and absolute elements |
| transform | 2D 3D transformation. See widget. |
| transform-origin | changes the position of transformed elements |
| transform-style | render nested elements in 3D |
| transition | transition properties in one line |
| transition-delay | delay before transition effect start |
| transition-duration | transition effect duration |
| transition-property | which CSS property is the transition affecting |
| transition-timing-function | speed curve of the transition |
| unicode-bidi | should the text be overridden to support more languages |
| user-select | disable user content selection |
| vertical-align | vertical alignment |
| visibility | visibility:hidden elements leave a gap |
| white-space | how are white-spaces handled |
| width | width of an element |
| word-break | text breaking rules when text reaches the end of the container |
| word-spacing | size of white space between words |
| word-wrap | break long words and wrap onto the next line |
| z-index | stack order of the element |


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Selectors and Pseudo Classes and Elements and Attribute Selectors

#### CSS Selectors

| Selector / Rule              | Meaning |
|-------------------------------|---------|
| `*`                           | All elements |
| `div`                         | All `<div>` tags |
| `div, p`                      | All `<div>` and `<p>` tags |
| `div p`                       | Paragraphs inside divs |
| `div > p`                     | All `<p>` tags, one level deep in div |
| `div + p`                     | `<p>` tags immediately after `<div>` |
| `div ~ p`                     | `<p>` tags preceded by a `<div>` |
| `.classname`                  | All elements with given class |
| `#idname`                     | Element with given ID |
| `div.classname`               | `<div>` with given class |
| `div#idname`                  | `<div>` with given ID |
| `#idname *`                   | All elements inside an element with that ID |

#### Pseudo Classes & Elements

| Selector / Rule               | Meaning |
|-------------------------------|---------|
| `a:link`                      | Link in normal state |
| `a:active`                    | Link in clicked state |
| `a:hover`                     | Link with mouse hover |
| `a:visited`                   | Visited link |
| `p::after {content:"yo"}`     | Add content after `<p>` |
| `p::before`                   | Add content before `<p>` |
| `input:checked`               | Checked inputs |
| `input:disabled`              | Disabled inputs |
| `input:enabled`               | Enabled inputs |
| `input:focus`                 | Input has focus |
| `input:in-range`              | Value is in allowed range |
| `input:out-of-range`          | Value is out of range |
| `input:valid`                 | Input with valid value |
| `input:invalid`               | Input with invalid value |
| `input:optional`              | Input without `required` |
| `input:required`              | Input with `required` attribute |
| `input:read-only`             | Input with `readonly` |
| `input:read-write`            | Input without `readonly` |
| `div:empty`                   | Element with no children |
| `p::first-letter`             | First letter in `<p>` |
| `p::first-line`               | First line in `<p>` |
| `p:first-of-type`             | First of its type |
| `p:last-of-type`              | Last of its type |
| `p:lang(en)`                  | `<p>` with language attribute "en" |
| `:not(span)`                  | Element that is not a `<span>` |
| `p:first-child`               | First child of its parent |
| `p:last-child`                | Last child of its parent |
| `p:nth-child(2)`              | Second child of its parent |
| `p:nth-child(3n+1)`           | Child by formula (an+b) |
| `p:nth-last-child(2)`         | Second child from the end |
| `p:nth-of-type(2)`            | Second `<p>` of its parent |
| `p:nth-last-of-type(2)`       | Second `<p>` from the end |
| `p:only-of-type`              | Unique of its type |
| `p:only-child`                | Only child of its parent |
| `:root`                       | Document’s root element |
| `::selection`                 | Portion selected by user |
| `:target`                     | Highlight active anchor |

#### Attribute Selectors

| Selector / Rule               | Meaning |
|-------------------------------|---------|
| `a[target]`                   | Links with `target` attribute |
| `a[target="_blank"]`          | Links opening in new tab |
| `[title~="chair"]`            | Title attribute contains the word "chair" |
| `[class^="chair"]`            | Class starts with "chair" |
| `[class|="chair"]`            | Class is "chair" or starts with "chair-" |
| `[class*="chair"]`            | Class contains "chair" |
| `[class$="chair"]`            | Class ends with "chair" |
| `input[type="button"]`        | Input of type "button" |


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Media Queries

| **Topic**              | **Details / Syntax** |
|-------------------------|-----------------------|
| **General Syntax**      | `@media not|only mediatype and (media feature) { CSS Code }` |
| **Link External File**  | `<link rel="stylesheet" media="mediatype and|not|only (media feature)" href="mystylesheet.css">` |
| **Viewport ≤ 480px**    | `@media screen and (max-width: 480px) { ... }` |
| **Width OR Height check** | `@media screen and (max-width: 600px), (max-height: 500px) { ... }` |
| **Print Style**         | `@media print { ... }` |
| **Dark Mode**           | `@media (prefers-color-scheme: dark) { ... }` |



#### 📂 Media Types
- **all** → All devices
- **print** → Printers
- **screen** → Screens (desktop, mobile, tablet)
- **speech** → Screen readers



#### 🔎 Media Features
| **Feature**       | **Description** |
|-------------------|-----------------|
| `width`           | Viewport width |
| `height`          | Viewport height |
| `orientation`     | Orientation of the viewport (`portrait` / `landscape`) |
| `aspect-ratio`    | Ratio between width & height |
| `color`           | Number of bits per color |
| `color-index`     | Number of displayable colors |
| `monochrome`      | Greyscale device color depth |
| `resolution`      | Device resolution (dpi, dppx) |
| `scan`            | Scanning process of the device |
| `grid`            | Device is grid or bitmap |



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->
