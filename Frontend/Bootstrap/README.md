## BootStrap Learning Notes
> A short and comprehensive guide to BootStrap fundamentals, structure, and best practices
- What is BootStrap
> BootStrap is a popular front-end framework for developing responsive and mobile-first websites. It provides a collection of CSS and JavaScript components that help streamline the development process and ensure a consistent design across different devices.

<div id="top"></div>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### 📋 Table of Contents

| Section | Topic                        | Description                                      |
| ------- | --------------------------- | ------------------------------------------------ |
| 1       | [Bootstrap Overview](#bootstrap-overview)         | What is Bootstrap, why use it                    |
| 2       | [Setup & CDN](#setup--cdn)                      | How to include Bootstrap (CDN, npm, etc.)        |
| 3       | [Grid System](#grid-system)                     | Responsive layout, rows, columns                 |
| 4       | [Containers](#containers)                       | Fixed, fluid, and breakpoint containers          |
| 5       | [Typography](#typography)                       | Headings, text utilities, display classes        |
| 6       | [Colors & Backgrounds](#colors--backgrounds)     | Color classes, background utilities              |
| 7       | [Spacing Utilities](#spacing-utilities)          | Margin, padding, gap classes                     |
| 8       | [Flex Utilities](#flex-utilities)                | Flexbox helpers                                  |
| 9       | [Buttons](#buttons)                             | Button styles, sizes, groups                     |
| 10      | [Button Group](#button-group)                   | Grouping buttons                                 |
| 11      | [Button Plugin](#button-plugin)                  | Button JavaScript plugin                         |
| 12      | [Forms](#forms)                                 | Form controls, validation, layout                |
| 13      | [Input Group](#input-group)                     | Grouping form inputs                             |
| 14      | [Floating Labels](#floating-labels)              | Floating label forms                             |
| 15      | [Form Layout](#form-layout)                     | Form layout options                              |
| 16      | [Form Validation](#form-validation)             | Form validation techniques                       |
| 17      | [Accordion](#accordion)                         | Expand/collapse content                          |
| 18      | [Alerts](#alerts)                               | Alert messages                                   |
| 19      | [Badge](#badge)                                 | Badge styles                                     |
| 20      | [Breadcrumb](#breadcrumb)                       | Navigation breadcrumbs                           |
| 21      | [Card](#card)                                   | Card layouts, content, images                    |
| 22      | [Carousel](#carousel)                           | Image/content sliders                            |
| 23      | [Collapse](#collapse)                           | Expand/collapse content                          |
| 24      | [Dropdowns](#dropdowns)                         | Dropdown menus                                   |
| 25      | [List Group](#list-group)                       | List group component                             |
| 26      | [Modal](#modal)                                 | Dialogs, popups                                  |
| 27      | [Navs, Tabs, Pills](#navs-tabs-pills)           | Navigation bars, tabs, pills                     |
| 28      | [Navbar](#navbar)                               | Navigation bar                                   |
| 29      | [Offcanvas Start](#offcanvas-start)             | Offcanvas sidebar                                |
| 30      | [Pagination](#pagination)                       | Pagination controls                              |
| 31      | [Placeholders](#placeholders)                   | Placeholder loading                              |
| 32      | [Popovers](#popovers)                           | Popover info boxes                               |
| 33      | [Progress](#progress)                           | Progress bars                                    |
| 34      | [Scrollspy](#scrollspy)                         | Scrollspy navigation                             |
| 35      | [Spinners](#spinners)                           | Loading spinners                                 |
| 36      | [Toasts](#toasts)                               | Toast notifications                              |
| 37      | [Tooltips](#tooltips)                           | Hover/click info boxes                           |
| 38      | [Helpers](#helpers)                             | Helper classes                                   |
| 39      | [Utility](#utility)            | Border utility classes                           |
| 40      | [Images](#images)                               | Responsive images                                |
| 41      | [Tables](#tables)                               | Table styles, responsive tables                  |
| 42      | [Figures](#figures)                             | Figure captions                                  |


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Bootstrap Overview
> Bootstrap is a popular CSS framework for building responsive, mobile-first websites quickly and easily.
- It includes a wide range of pre-designed components and utilities for layout, forms, buttons, navigation, and more.
- Bootstrap is built on a 12-column grid system and provides responsive design out of the box.
- It also offers extensive customization options through Sass variables and mixins.
- You can easily modify the look and feel of your Bootstrap components to match your brand.
- Bootstrap provides a consistent design language and a set of best practices for building user interfaces.
- It encourages a mobile-first approach and provides responsive utilities to ensure your site looks great on all devices.
- Bootstrap also includes JavaScript components for interactive features like modals, dropdowns, and carousels.
- These components are easy to use and can be customized to fit your needs.
- Bootstrap's JavaScript components rely on jQuery and Popper.js for functionality.


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Setup & CDN
> How to include Bootstrap via CDN, npm, or download. Example:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Grid System
> The **Bootstrap Grid System** uses **containers, rows, and columns** to create layouts.
> It is based on **12 columns** and supports **responsive breakpoints**.


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


#### 🏗️ Core Building Blocks
| Class | Description |
|-------|-------------|
| `container` | Fixed-width container (responsive) |
| `container-*` | Responsive container (e.g., `container-sm`, `container-lg`) |
| `container-fluid` | Full-width container spanning entire viewport |
| `row` | Wrapper for columns; ensures proper alignment |



#### 📐 Columns
| Class | Description |
|-------|-------------|
| `col-#` | Column width across all devices (`col-6` = 6/12 width) |
| `col-sm-#` | Column for **small (≥576px)** devices |
| `col-md-#` | Column for **medium (≥768px)** devices |
| `col-lg-#` | Column for **large (≥992px)** devices |
| `col-xl-#` | Column for **extra large (≥1200px)** devices |
| `col-xxl-#` | Column for **extra extra large (≥1400px)** devices |
| `col` | Auto-sizing column (fills available space) |
| `col-*` | Flexible shorthand for responsive sizes |
| `col-*-auto` | Column adjusts automatically to content |



#### 🔗 Column Utilities
| Class | Description |
|-------|-------------|
| `row-cols-#` | Sets number of columns per row (e.g., `row-cols-3`) |
| `row-cols-*-#` | Responsive row columns (e.g., `row-cols-md-2`) |
| `nesting` | Rows and cols can be nested inside each other |
| `offset-#` | Pushes column to the right by `#` columns |
| `offset-*-#` | Responsive offset (e.g., `offset-md-3`) |



#### 🎨 Gutters (Spacing between columns)
| Class | Description |
|-------|-------------|
| `gx-{size}` | Horizontal gutter (x-axis) |
| `gx-*-{size}` | Responsive horizontal gutter |
| `gy-{size}` | Vertical gutter (y-axis) |
| `gy-*-{size}` | Responsive vertical gutter |
| `g-{size}` | Both horizontal & vertical gutter |
| `g-*-{size}` | Responsive gutter size |
| `g-0` | Removes all gutters |

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Containers
> Use `.container`, `.container-fluid`, or `.container-{breakpoint}` for layout wrappers.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Typography
> Bootstrap provides powerful typography utilities such as headings, display classes, text emphasis, blockquotes, and responsive font sizes.

#### 📌 Headings
- `h1` – `h6` → Standard HTML headings
- `.h1` – `.h6` → Apply heading styles to any element

#### 📌 Display Headings
- `.display-1` → Largest
- `.display-2`
- `.display-3`
- `.display-4`
- `.display-5`
- `.display-6` → Smallest

#### 📌 Text Utilities
- `.text-muted` → Muted/subtle text
- `.lead` → For lead paragraphs (slightly larger, lighter text)
- `.mark` → Highlight text (yellow background)
- `.small` → Smaller text (e.g., inline note)
- `.initialism` → Slightly smaller uppercase text

#### 📌 Blockquotes
- `<blockquote class="blockquote">` → For quotes
- `<footer class="blockquote-footer">` → Attribution

#### 📌 Lists
- `.list-unstyled` → Removes default list styling (no bullets/margins)
- `.list-inline` → Display list items inline horizontally

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Colors & Backgrounds
> Utility classes for text and background colors, e.g. `.text-primary`, `.bg-success`.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Spacing Utilities
> Margin and padding utilities: `.m-3`, `.p-2`, `.gap-2`, etc.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Flex Utilities
> Flexbox helpers: `.d-flex`, `.justify-content-center`, `.align-items-end`.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Buttons
> Styles, sizes, states, and variants for buttons.

- `btn-primary`, `btn-secondary`, `btn-success`, `btn-danger`
- `btn-warning`, `btn-info`, `btn-light`, `btn-dark`
- `btn-link`
- `btn-outline-{color}`
- `btn-lg`, `btn-sm`
- `block buttons`
- `btn-close`, `btn-close-white`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Button Group
> Group multiple buttons together.

- `btn-group`
- `btn-group with links`
- `outlined btn-group`
- `btn-toolbar`
- `btn-group-lg`, `btn-group-sm`
- `btn-group-vertical`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Button Plugin
> JavaScript-powered button behaviors.

- `single button toggle`
- `btn-group with checkbox`
- `btn-group with radio`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Forms
> Bootstrap provides classes to style inputs, labels, selects, checkboxes, radios, switches, and ranges.

#### 📌 Form Controls
- `.form-control` → Applies Bootstrap styling to `<input>`, `<textarea>`, etc.
- `.form-label` → Styles `<label>` elements
- `.form-control-lg` → Large input field
- `.form-control-sm` → Small input field
- `.form-control-plaintext` → Displays plain text instead of input field
- `type="file"` with `.form-control` → File upload input
- `.form-control-color` → Color picker input


#### 📌 Select Inputs
- `.form-select` → Styles `<select>` dropdowns
- `.form-select-lg` → Large select dropdown
- `.form-select-sm` → Small select dropdown


#### 📌 Checkboxes & Radios
- `.form-check` → Wrapper for checkbox/radio
- `.form-check-inline` → Display checkboxes/radios inline

👉 **Checkbox Example**
- `.form-check` → Standard checkbox
- `.form-check-inline` → Inline checkbox

👉 **Radio Example**
- `.form-check` → Standard radio button
- `.form-check-inline` → Inline radio button

#### 📌 Switch
- `.form-switch` → Converts a checkbox into a toggle switch

#### 📌 Range Input
- `.form-range` → Styles range (slider) input


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Input Groups
> Easily extend form controls with text, buttons, checkboxes, and more using `.input-group`.

#### 📌 Basic Input Groups
- `.input-group` → Wraps input with additional elements
  - **Left side addon** → Element placed **before** the input
  - **Right side addon** → Element placed **after** the input
  - **Both sides addon** → Elements placed on **both sides** of input

#### 📌 Sizes
- `.input-group-lg` → Large sized input group
- `.input-group-sm` → Small sized input group

#### 📌 Input Group Variations
- **With Checkbox** → Embed a checkbox inside the input group
- **With Radio** → Embed a radio button inside the input group
- **With Button** → Add button(s) before or after input
- **With Dropdown** → Attach a dropdown menu with the input


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Floating Labels
> Wrap form controls in `.form-floating` to enable floating labels. Labels automatically scale and reposition as users interact with inputs.

#### 📌 Variants
- `.form-floating` → Basic floating label with text input
- `.form-floating` + `<textarea>` → Floating label for multiline input
- `.form-floating` + `<select>` → Floating label for dropdown

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Form Layout
> Different ways to structure forms with Bootstrap.

- `horizontal form`
- `col-form-label-{size}`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Form Validation
> Built-in validation styles and feedback messages.

- `valid-feedback`
- `valid-tooltip`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Accordion
> Expand/collapse sections of content.

- `accordion`
- `accordion-flush`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Alerts
> Contextual alert messages.

- `alert-primary`
- `alert-secondary`
- `alert-success`
- `alert-danger`
- `alert-warning`
- `alert-info`
- `alert-light`
- `alert-dark`
- `alert-link`
- `alert-dismissible`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Badge
> Small count and labeling component.

- `primary`, `secondary`, `success`, `danger`
- `warning`, `info`, `light`, `dark`
- `pill badge`
- `notification badge`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Breadcrumb
> Navigation indicator for current page location.

- `breadcrumb`
- `change divider`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Card
> Flexible content container with multiple variants.

- `card`, `card-body`
- `titles`, `text`, `links`
- `list-group`
- `card-header`, `card-footer`
- `navigation in card`
- `card-img-top`, `card-img-bottom`
- `card-img-overlay`
- `horizontal card`
- `bg-{color}`, `border-{color}`, `text-{color}`
- `bg-transparent`
- `card-group`, `grid cards`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Carousel
> Slideshow component for cycling content.

- `carousel (slides only)`
- `carousel with controls`
- `carousel-indicators`
- `carousel-caption`
- `carousel-fade`
- `carousel with intervals`
- `carousel-dark`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Collapse
> Show and hide content with toggle.

- `collapse`
- `multi-collapse`
- `collapse-horizontal`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Dropdowns
> Menu of links or actions.

- `dropdown`, `dropdown-toggle-split`
- `dropdown-menu-dark`
- `dropup`, `dropup (split)`
- `dropend`, `dropstart`
- `dropdown-item-text`
- `active dropdown-item`
- `disabled dropdown-item`
- `dropdown-menu-end`
- `dropdown-menu-*-{direction}`
- `dropdown-header`, `dropdown-divider`
- `dropdown reference`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### List Group
> Flexible and powerful list component.

- `list-group`
- `list-group-item active`, `list-group-item disabled`
- `list-group-flush`
- `list-group-numbered`
- `list-group-horizontal`, `list-group-horizontal-*`
- `list-group-item-{color}`
- `list-group-item-action`
- `custom content`
- `list-group with checkbox`
- `javascript behavior`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Modal
> Dialogs, popups, and modals.

- `modal`
- `static backdrop`
- `modal-dialog-scrollable`
- `modal-dialog-centered`
- `modal-{size}`
- `modal-fullscreen`, `modal-fullscreen-*-down`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Navs, Tabs, Pills
> Navigation components for switching views.

- `ul.nav`, `nav.nav`
- `vertical nav`
- `nav-tabs`, `nav-pills`
- `nav-fill`, `nav-justified`
- `nav-tabs with dropdown`
- `nav-pills with dropdown`
- `vertical pills`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Navbar
> Responsive navigation header.

- `navbar`, `navbar-brand`
- `navbar without using list`
- `navbar with dropdown`
- `navbar-text`
- `navbar-dark`, `navbar-light`
- `fixed-top`, `fixed-bottom`, `sticky-top`
- `brand in collapse`
- `navbar-toggler on right`, `navbar-toggler on left`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Offcanvas
> Sidebar component that can slide in/out.

- `offcanvas-start (Default)`
- `offcanvas-end`
- `offcanvas-top`
- `offcanvas-bottom`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Pagination
> Page navigation for content.

- `pagination`
- `disabled page-item`
- `active page-item`
- `pagination-lg`, `pagination-sm`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Placeholders
> Placeholder skeleton loaders.

- `placeholder`
- `placeholder bg-{color}`
- `placeholder-lg`, `placeholder-sm`, `placeholder-xs`
- `placeholder-glow`
- `placeholder-wave`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Popovers
> Small overlay content tooltips.

- `popover on right`, `popover on top`, `popover on bottom`, `popover on left`
- `dismissible popover`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Progress
> Progress bars with customization.

- `progress`, `progress-bar`
- `progress with label`
- `progress with height`
- `progress-bar bg-{color}`
- `multiple progress-bar`
- `progress-bar-striped`
- `progress-bar-striped bg-{color}`
- `progress-bar-animated`
- `progress-bar-animated bg-{color}`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Scrollspy
> Highlight navigation links based on scroll position.

- `data-bs-spy`
- `nested data-bs-spy`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Spinners
> Loading indicators.

- `spinner-border`, `spinner-border text-{color}`, `spinner-border-sm`
- `spinner-grow`, `spinner-grow text-{color}`, `spinner-grow-sm`


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Toasts
> Lightweight notification messages.

- `toast`
- `toast with button`
- `toast bg-{color} text-{color}`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Tooltips
> Hover or click activated information.

- `tooltip on top`, `tooltip on right`, `tooltip on bottom`, `tooltip on left`
- `tooltip with HTML`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Helpers
> Miscellaneous helper utilities.

- `clearfix`
- `link-{color}`
- `ratio-{ratio}`
- `fixed-top`, `fixed-bottom`, `sticky-top`, `sticky-*-top`
- `visually-hidden`, `visually-hidden-focusable`
- `stretched-link`
- `text-truncate`
- `vstack`, `hstack`, `vr`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Utilities
> Utility classes for borders, display, text, opacity, position, and more.

#### Utility: Borders
- `border`, `border-{direction}`, `border-0`, `border-{direction}-0`
- `border-{color}`
- `border-{size}`
- `rounded`, `rounded-{corner}`, `rounded-{size}`

#### Utility: Colors
- `text-{color}`, `text-body`
- `text-white`, `text-black-50`, `text-white-50`
- `bg-{color}`, `bg-white`, `bg-transparent`, `bg-gradient`


#### Utility: Display
- `d-*-none`, `d-*-inline`, `d-*-inline-block`
- `d-*-block`, `d-*-grid`, `d-*-table`, `d-*-table-cell`, `d-*-table-row`
- `d-*-flex`, `d-*-inline-flex`
- `d-print-{display}`

#### Utility: Flex
- `flex-*-row`, `flex-*-row-reverse`
- `flex-*-column`, `flex-*-column-reverse`
- `justify-content-*-{option}`
- `align-items-*-{option}`, `align-self-*-{option}`
- `flex-*-fill`, `flex-grow-{option}`, `flex-shrink-{option}`
- `flex-*-nowrap`, `flex-*-wrap`, `flex-*-wrap-reverse`
- `order-*-{order-number}`, `order-*-{order-name}`
- `align-content-*-{option}`

#### Utility: Misc
- `user-select-{option}`
- `pe-{option}`
- `overflow-{option}`
- `shadow`, `shadow-{option}`
- `w-{option}`, `h-{option}`, `mw-100`, `mh-100`
- `viewport`
- `visible`, `invisible`

#### Utility: Position
- `float-*-{option}`
- `position-{option}`
- `{direction}-{position}`
- `translate-middle`, `translate-middle-{direction}`
- `align-{option}`

#### Utility: Spacing
- `m-*-{option}`, `mt-*-{option}`, `me-*-{option}`, `mb-*-{option}`, `ms-*-{option}`, `mx-*-{option}`, `my-*-{option}`
- `p-*-{option}`, `pt-*-{option}`, `pe-*-{option}`, `pb-*-{option}`, `ps-*-{option}`, `px-*-{option}`, `py-*-{option}`
- `m{direction}-*-n{size}`
- `gap-*-{size}`

#### Utility: Text
- `text-*-start`, `text-*-center`, `text-*-end`
- `text-wrap`, `text-nowrap`, `text-break`
- `text-{option}`
- `fs-{size}`, `fw-{weight}`, `fst-{style}`, `lh-{style}`
- `font-monospace`
- `text-reset`
- `text-decoration-{option}`

#### Utility: Opacity
- `opacity-{value}`
- `bg-opacity-{value}`
- `text-opacity-{value}`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Images

- `.img-fluid` → Responsive images
- `.img-thumbnail` → Image thumbnails

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Tables
> Table styles and responsive tables with `.table`.

#### 📌 Basic Table
- `.table` → Adds basic Bootstrap table styling

#### 📌 Table Colors
- `.table-{color}` → Contextual classes for rows/cells
  - `table-primary`
  - `table-secondary`
  - `table-success`
  - `table-danger`
  - `table-warning`
  - `table-info`
  - `table-light`
  - `table-dark`

#### 📌 Table Styling
- `.table-striped` → Adds zebra-striping to rows
- `.table-hover` → Highlights row on hover
- `.table-active` → Highlights row/cell as "active"
- `.table-bordered` → Adds borders to all cells
- `.table-borderless` → Removes all borders
- `.table-sm` → Makes table more compact (smaller padding)

#### 📌 Captions
- `<caption>` → Adds caption below table by default
- `.caption-top` → Moves caption above the table

#### 📌 Responsive Tables
- `.table-responsive` → Makes table horizontally scrollable on small screens
- `.table-responsive-{breakpoint}` → Responsive at specific breakpoints
  - `table-responsive-sm`
  - `table-responsive-md`
  - `table-responsive-lg`
  - `table-responsive-xl`
  - `table-responsive-xxl`


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Figures
> Figure captions with `.figure`.




###


<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->
