## Tailwind Learning Notes
> A short and comprehensive guide to Tailwind CSS fundamentals, structure, and best practices
- What is Tailwind CSS
> Tailwind CSS is a utility-first CSS framework for creating custom designs without having to leave your HTML. It provides low-level utility classes that let you build completely custom designs without having to fight against the framework's styles.

<div id="top"></div>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### 📋 Table of Contents

| Section | Topic                        | Description                                      |
| ------- | --------------------------- | ------------------------------------------------ |
| 1       | [Tailwind Overview](#tailwind-overview)         | What is Tailwind, why use it                     |
| 2       | [Setup & CDN](#setup--cdn)                      | How to include Tailwind (CDN, npm, etc.)         |
| 3       | [Configuration](#configuration)                 | tailwind.config.js, customizing                  |
| 4       | [Utility Classes](#utility-classes)             | Core utility classes                             |
| 5       | [Responsive Design](#responsive-design)         | Breakpoints, mobile-first                        |
| 6       | [Colors](#colors)                               | Color palette, text/bg colors                    |
| 7       | [Spacing](#spacing)                             | Margin, padding, gap                             |
| 8       | [Typography](#typography)                       | Font, size, weight, line-height                  |
| 9       | [Layout](#layout)                               | Container, box-sizing, display                   |
| 10      | [Flexbox](#flexbox)                             | Flex utilities                                   |
| 11      | [Grid](#grid)                                   | Grid utilities                                   |
| 12      | [Borders & Radius](#borders--radius)            | Border, border-radius                            |
| 13      | [Backgrounds](#backgrounds)                     | Background color, image, gradient                |
| 14      | [Shadows & Effects](#shadows--effects)          | Box-shadow, opacity, mix-blend-mode              |
| 15      | [Transitions & Animations](#transitions--animations) | Transition, duration, animation             |
| 16      | [Transforms](#transforms)                       | Scale, rotate, translate, skew                   |
| 17      | [Filters](#filters)                             | Blur, brightness, contrast                       |
| 18      | [Interactivity](#interactivity)                 | Hover, focus, active, group, peer                |
| 19      | [Pseudo-Classes](#pseudo-classes)               | First, last, odd, even, etc.                     |
| 20      | [Custom Utilities](#custom-utilities)           | Creating custom classes                          |
| 21      | [Plugins](#plugins)                             | Official and community plugins                   |
| 22      | [Best Practices](#best-practices)               | Clean, maintainable Tailwind code                |
| 23      | [Box Alignment](#box-alignment)               | justify, align, place utilities                  |
| 24      | [Sizing](#sizing)                             | width, height, min/max utilities                 |
| 25      | [Effects](#effects)                           | Box-shadow, opacity, blend modes                 |
| 26      | [SVG](#svg)                                   | SVG fill and stroke utilities                    |



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Tailwind Overview

- Utility-first CSS framework for rapid UI development.
- No opinionated styles; you compose your own using utility classes.
- Highly customizable via config file.
- Mobile-first and responsive by default.

**Example:**
```html
<div class="bg-blue-500 text-white p-4 rounded">Hello Tailwind!</div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Setup & CDN

- Install via npm, CDN, or download.
- Use PostCSS for advanced features.
- CDN is great for quick prototyping.

**Example (CDN):**
```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.3.0/dist/tailwind.min.css" rel="stylesheet">
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Configuration

- `tailwind.config.js` controls theme, colors, breakpoints, plugins.
- Extend or override default settings.
- Add custom utilities and variants.

**Example:**
```js
module.exports = {
	theme: {
		extend: {
			colors: {
				brand: '#1da1f2',
			},
		},
	},
}
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Utility Classes

- Core of Tailwind: classes for margin, padding, color, font, etc.
- Compose UI by stacking utilities.
- No need to write custom CSS for most cases.

**Example:**
```html
<button class="px-4 py-2 bg-green-600 text-white rounded shadow">Click Me</button>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Responsive Design

- Mobile-first breakpoints: `sm`, `md`, `lg`, `xl`, `2xl`.
- Use responsive prefixes: `md:bg-red-500`.
- Easily build layouts for all devices.

**Example:**
```html
<div class="bg-gray-200 md:bg-blue-200 lg:bg-green-200">Responsive!</div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Colors

- Extensive color palette: `bg-blue-500`, `text-gray-700`, etc.
- Supports custom colors via config.
- Opacity utilities: `bg-blue-500/50`.

**Example:**
```html
<span class="text-pink-600 bg-pink-100 p-2">Colorful text</span>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Spacing

- Margin: `m-4`, `mx-2`, `my-1`.
- Padding: `p-4`, `px-2`, `py-1`.
- Gap for flex/grid: `gap-4`.

**Example:**
```html
<div class="m-4 p-2 gap-2 flex">
	<div class="bg-blue-100">A</div>
	<div class="bg-blue-200">B</div>
</div>
```

#### Padding (`p`, `px`, `py`, `pt`, `pr`, `pb`, `pl`)
Padding is the **inner space** between the content and the element’s border.

- `p-{size}` → applies padding on all sides.
- `px-{size}` → padding on **left & right**.
- `py-{size}` → padding on **top & bottom**.
- `pt-{size}`, `pr-{size}`, `pb-{size}`, `pl-{size}` → padding individually.

**Example:**
```html
<div class="p-4">Padding on all sides</div>
<div class="px-6">Padding left & right</div>
<div class="pt-2">Padding only top</div>
```

#### Margin (m, mx, my, mt, mr, mb, ml)
Margin is the outer space around an element.
- `m-{size}` → applies margin on all sides.
- `mx-{size}` → margin on left & right.
- `my-{size}` → margin on top & bottom.
- `mt-{size}`, `mr-{size}`, `mb-{size}`, `ml-{size}` → margin individually.
- `m-auto` → centers the element (horizontal centering in flex/blocks).

```html
<div class="m-4">Margin on all sides</div>
<div class="mx-8">Margin left & right</div>
<div class="mt-2">Margin only top</div>
<div class="mx-auto w-64">Horizontally centered</div>
```

#### Space Between (space-x, space-y)
The space-between utilities add spacing between child elements (not outside).
- `space-x-{size}` → horizontal spacing between children.
- `space-y-{size}` → vertical spacing between children.
Works only on direct children of a flex container.

```html
<div class="flex space-x-4">
  <div class="bg-blue-300 p-2">Item 1</div>
  <div class="bg-blue-300 p-2">Item 2</div>
  <div class="bg-blue-300 p-2">Item 3</div>
</div>

<div class="flex flex-col space-y-2">
  <div class="bg-green-300 p-2">Row 1</div>
  <div class="bg-green-300 p-2">Row 2</div>
</div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Typography

- Font family: `font-sans`, `font-serif`, `font-mono`.
- Font size: `text-lg`, `text-2xl`.
- Font weight: `font-bold`, `font-light`.
- Line height: `leading-tight`, `leading-loose`.
- Letter spacing: `tracking-wide`.

**Example:**
```html
<h1 class="text-3xl font-bold tracking-tight">Heading</h1>
<p class="text-base leading-relaxed">Paragraph text</p>
```

#### Text Color
- Utilities: `text-{color}`
- Example: `text-red-500`, `text-blue-700`

#### Text Opacity
- Utilities: `text-opacity-{0–100}`
- Example: `text-red-500 text-opacity-50`

#### Font Family
- Utilities: `font-{family}`
- Example: `font-sans`, `font-serif`, `font-mono`

#### Font Size
- Utilities: `text-{size}`
- Example: `text-xs`, `text-sm`, `text-lg`, `text-2xl`

#### Font Smoothing
- Utilities: `antialiased`, `subpixel-antialiased`
- Example: `antialiased`, `subpixel-antialiased`

#### Font Style
- Utilities: `italic`, `not-italic`
- Example: `italic`

#### Font Weight
- Utilities: `font-{weight}`
- Example: `font-light`, `font-normal`, `font-bold`, `font-extrabold`

#### Font Variant Numeric
- Utilities: `normal-nums`, `ordinal`, `slashed-zero`, `lining-nums`, `oldstyle-nums`, `proportional-nums`, `tabular-nums`, `diagonal-fractions`, `stacked-fractions`
- Example: `tabular-nums`

#### Letter Spacing
- Utilities: `tracking-{size}`
- Example: `tracking-tight`, `tracking-normal`, `tracking-wide`

#### Line Height
- Utilities: `leading-{size}`
- Example: `leading-none`, `leading-tight`, `leading-relaxed`, `leading-loose`

#### List Style Type
- Utilities: `list-{type}`
- Example: `list-disc`, `list-decimal`, `list-none`

#### List Style Position
- Utilities: `list-{position}`
- Example: `list-inside`, `list-outside`

#### Placeholder Color
- Utilities: `placeholder-{color}`
- Example: `placeholder-gray-400`

#### Placeholder Opacity
- Utilities: `placeholder-opacity-{0–100}`
- Example: `placeholder-opacity-50`

#### Text Align
- Utilities: `text-{alignment}`
- Example: `text-left`, `text-center`, `text-right`, `text-justify`

#### Text Decoration
- Utilities: `underline`, `overline`, `line-through`, `no-underline`, `decoration-{color}`, `decoration-{style}`, `decoration-{thickness}`
- Example: `underline decoration-red-500`

#### Text Transform
- Utilities: `uppercase`, `lowercase`, `capitalize`, `normal-case`
- Example: `uppercase`

#### Text Overflow
- Utilities: `truncate`, `text-ellipsis`, `text-clip`
- Example: `truncate`

#### Vertical Align
- Utilities: `align-{position}`
- Example: `align-top`, `align-middle`, `align-bottom`, `align-baseline`

#### White Space
- Utilities: `whitespace-{mode}`
- Example: `whitespace-normal`, `whitespace-nowrap`, `whitespace-pre`, `whitespace-pre-line`, `whitespace-pre-wrap`

#### Word Break
- Utilities: `break-normal`, `break-words`, `break-all`
- Example: `break-words`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Layout
> Tailwind provides a wide range of utility classes to control layout, positioning, overflow, and responsiveness.

- Container: `container mx-auto`.
- Box sizing: `box-border`, `box-content`.
- Display: `block`, `inline-block`, `flex`, `grid`.

#### Breakpoints
- **Responsive prefixes**: `sm`, `md`, `lg`, `xl`, `2xl`
  Example: `md:flex`, `lg:hidden`

#### Box Decoration Break
- **Class**: `box-decoration-clone`, `box-decoration-slice`
  Controls how background/decoration applies across fragments.

#### Container
- **Class**: `container`
- Centers and sets a max-width for content based on breakpoints.

#### Box Sizing
- `box-border` → Includes border & padding in element size.
- `box-content` → Default, excludes border & padding.

#### Display
- `block`, `inline-block`, `inline`
- `flex`, `inline-flex`
- `grid`, `inline-grid`
- `hidden`, `contents`

#### Float
- `float-right`, `float-left`, `float-none`

#### Clear
- `clear-left`, `clear-right`, `clear-both`, `clear-none`

#### Isolation
- `isolate`, `isolation-auto`
  Creates a new stacking context for child elements.

#### Object Fit
- `object-contain`, `object-cover`, `object-fill`, `object-none`, `object-scale-down`

#### Object Position
- `object-top`, `object-center`, `object-bottom`
- `object-left`, `object-right`, etc.

#### Overflow
- `overflow-auto`, `overflow-hidden`, `overflow-visible`, `overflow-scroll`
- Directional: `overflow-x-*`, `overflow-y-*`

#### Overscroll Behavior
- `overscroll-auto`, `overscroll-contain`, `overscroll-none`

#### Position
- `static`, `relative`, `absolute`, `fixed`, `sticky`

#### Position Offsets
- `top-*`, `right-*`, `bottom-*`, `left-*`
  Example: `top-0`, `left-4`

#### Visibility
- `visible`, `invisible`, `collapse`

#### Z-Index
- `z-0`, `z-10`, `z-20`, `z-30`, `z-40`, `z-50`, `z-auto`


**Example:**
```html
<div class="container mx-auto p-4">Centered content</div>
<div class="flex justify-between">
	<div>Left</div>
	<div>Right</div>
</div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Flexbox
> Utilities for controlling flexbox layout, alignment, and ordering.

- Flex container: `flex`.
- Direction: `flex-row`, `flex-col`.
- Wrap: `flex-wrap`, `flex-nowrap`.
- Align/justify: `items-center`, `justify-between`.

**Example:**
```html
<div class="flex items-center justify-between">
	<span>Item 1</span>
	<span>Item 2</span>
</div>
```

#### Display
- `flex` → Apply flexbox
- `inline-flex` → Inline-level flex container

#### Flex Direction
- `flex-row` → Horizontal (default)
- `flex-row-reverse` → Reverse horizontal
- `flex-col` → Vertical
- `flex-col-reverse` → Reverse vertical

#### Flex Wrap
- `flex-wrap` → Allow wrapping
- `flex-wrap-reverse` → Reverse wrap order
- `flex-nowrap` → No wrapping (default)

#### Flex
- `flex-1` → Grow and shrink as needed, basis 0%
- `flex-auto` → Grow and shrink, basis auto
- `flex-initial` → Shrink as needed, don’t grow
- `flex-none` → Prevent grow and shrink

#### Flex Grow
- `grow` → Allow item to grow
- `grow-0` → Prevent growth

#### Flex Shrink
- `shrink` → Allow item to shrink
- `shrink-0` → Prevent shrinking

#### Order
- `order-1`, `order-2`, …, `order-12` → Set order
- `order-first` → Item always first
- `order-last` → Item always last
- `order-none` → Default order

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Grid
> Utilities for creating two-dimensional grid layouts.

- Grid container: `grid`.
- Columns: `grid-cols-3`, `col-span-2`.
- Gap: `gap-4`.

**Example:**
```html
<div class="grid grid-cols-2 gap-4">
	<div class="bg-red-100">1</div>
	<div class="bg-red-200">2</div>
</div>
```

#### Grid Template Columns
- `grid-cols-1` → 1 column
- `grid-cols-2` → 2 columns
- ...
- `grid-cols-12` → 12 columns
- `grid-cols-none` → No column grid
- `grid-cols-[value]` → Custom (e.g., `grid-cols-[200px_minmax(900px,_1fr)_100px]`)

#### Grid Column (Start / End)
- `col-span-1`, `col-span-2`, … → Span across columns
- `col-start-1`, `col-start-2`, … → Start column
- `col-end-1`, `col-end-2`, … → End column
- `col-auto` → Auto placement

#### Grid Template Rows
- `grid-rows-1` → 1 row
- `grid-rows-2`, … → Multiple rows
- `grid-rows-none` → No row grid
- `grid-rows-[value]` → Custom rows

#### Grid Row (Start / End)
- `row-span-1`, `row-span-2`, … → Span across rows
- `row-start-1`, `row-start-2`, … → Start row
- `row-end-1`, `row-end-2`, … → End row
- `row-auto` → Auto placement

#### Grid Auto Flow
- `grid-flow-row` → Place items by rows (default)
- `grid-flow-col` → Place items by columns
- `grid-flow-row-dense` → Fill in gaps by rows
- `grid-flow-col-dense` → Fill in gaps by columns

#### Grid Auto Columns
- `auto-cols-auto` → Default (auto)
- `auto-cols-min` → Min-content
- `auto-cols-max` → Max-content
- `auto-cols-fr` → Fraction unit (1fr)

#### Grid Auto Rows
- `auto-rows-auto` → Default (auto)
- `auto-rows-min` → Min-content
- `auto-rows-max` → Max-content
- `auto-rows-fr` → Fraction unit (1fr)

#### Gap
- `gap-0`, `gap-1`, … → Gap between rows & columns
- `gap-x-#` → Horizontal gap
- `gap-y-#` → Vertical gap

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Borders & Radius

- Border: `border`, `border-2`, `border-gray-400`.
- Radius: `rounded`, `rounded-lg`, `rounded-full`.
**Example:**
```html
<img class="border border-gray-400 rounded-lg" src="avatar.png" />
```

#### Border Radius (`border-radius`)
- Controls the roundness of element corners.
- **Classes**:
  - `rounded-none` → No rounding
  - `rounded-sm` → Small radius
  - `rounded` → Default radius
  - `rounded-md` → Medium radius
  - `rounded-lg` → Large radius
  - `rounded-full` → Fully rounded (circle if width=height)
- **Example**:
```html
  <div class="rounded-lg"></div>
```

#### Border Width (border-width)
- Sets the thickness of element borders.
- **Classes**:
  - `border` → Default width
  - `border-0` → No border
  - `border-2`, `border-4`, `border-8` → Specific widths
  - `border-t`, `border-r`, `border-b`, `border-l` → Side-specific
- **Example**:
```html
<div class="border-2 border-t-4"></div>
```

#### Border Color (border-color)
- Sets the color of the border.
- **Classes**:
  - `border-transparent` → Transparent
  - `border-black`, `border-white`
  - `border-gray-500`, `border-red-500`, etc. (using color palette)
- **Example**:
```html
<div class="border border-gray-500"></div>
```html
<div class="border border-blue-500"></div>
```

#### Border Opacity (border-opacity)
- Controls opacity of border color.
- **Classes**:
  - `border-opacity-0` → Invisible
  - `border-opacity-25` → 25% opacity
  - `border-opacity-50` → 50% opacity
  - `border-opacity-75` → 75% opacity
  - `border-opacity-100` → Fully opaque
- **Example**:
```html
<div class="border border-red-500 border-opacity-50"></div>
```

#### Border Style (border-style)
Defines border line style.
- **Classes**:
  - `border-solid`
  - `border-dashed`
  - `border-dotted`
  - `border-double`
  - `border-none`
- **Example**:
```html
<div class="border-4 border-dashed border-gray-600"></div>
```

#### Divide Width (divide-width)
Adds horizontal/vertical dividers between child elements.
- **Classes**:
  - `divide-x` → Vertical divider
  - `divide-y` → Horizontal divider
  - `divide-x-2`, `divide-y-4`, etc. → Thickness control
- **Example**:
```html
<div class="divide-y divide-gray-300">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

#### Divide Color (divide-color)
Controls color of dividers.
- **Classes**:
  - `divide-gray-500`
  - `divide-red-500`
  - etc.
- **Example**:
```html
<div class="divide-y divide-blue-400">
  <div>Item A</div>
  <div>Item B</div>
</div>
```

#### Divide Opacity (divide-opacity)
Adjusts divider opacity.
- **Classes**:
  - `divide-opacity-25`
  - `divide-opacity-50`
  - etc.
- **Example**:
```html
<div class="divide-y divide-gray-500 divide-opacity-50"></div>
```

#### Divide Style (divide-style)
Sets the divider line style.
- **Classes**:
  - `divide-solid`
  - `divide-dashed`
  - `divide-dotted`
  - `divide-double`
- **Example**:
```html
<div class="divide-y divide-dashed divide-gray-400"></div>
```

#### Ring Width (ring-width)
Adds outline ring around elements (useful for focus states).
- **Classes**:
  - `ring` → Default width (1px)
  - `ring-0`, `ring-1`, `ring-2`, `ring-4`, `ring-8`
- **Example**:
```html
<button class="ring-2">Click</button>
```

#### Ring Color (ring-color)
Sets ring color.
- **Classes**:
  - `ring-blue-500`
  - `ring-red-400`
  - etc.
- **Example**:
```html
<button class="ring-2 ring-blue-500">Click</button>
<button class="ring-2 ring-green-400">Click</button>
```

#### Ring Opacity (ring-opacity)
Adjusts transparency of rings.
- **Classes**:
  - `ring-opacity-25`
  - `ring-opacity-50`
  - etc.
- **Example**:
```html
<button class="ring-2 ring-blue-500 ring-opacity-50">Click</button>
<button class="ring-4 ring-purple-500 ring-opacity-50">Click</button>
```

#### Ring Offset Width (ring-offset-width)
Adds spacing between element and ring.
- **Classes**:
  - `ring-offset-0`
  - `ring-offset-2`
  - `ring-offset-4`
- **Example**:
```html
<button class="ring-2 ring-offset-2 ring-offset-white">Click</button>
```

#### Ring Offset Color (ring-offset-color)
Sets background color behind the ring (offset area).
- **Classes**:
  - `ring-offset-white`
  - `ring-offset-gray-800`
  - etc.
- **Example**:
```html
<button class="ring-2 ring-offset-2 ring-offset-white">Click</button>
<button class="ring-4 ring-pink-500 ring-offset-2 ring-offset-black">Click</button>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Backgrounds
> This section covers utilities for controlling background styles in Tailwind CSS.

- Background color: `bg-yellow-200`.
- Background image: `bg-[url('/img/bg.png')]`.
- Gradients: `bg-gradient-to-r from-blue-400 to-green-400`.
**Example:**
```html
<div class="bg-gradient-to-r from-pink-500 to-yellow-500 p-4">Gradient!</div>
```

#### **Background Attachment**
Controls how a background image behaves when scrolling.
- `bg-fixed` → The background image is fixed relative to the viewport.
- `bg-local` → The background image scrolls with the element's contents.
- `bg-scroll` → The background image scrolls with the page (default).

#### **Background Clip**
Controls whether the background extends underneath the border, padding, or content.
- `bg-clip-border` → Background extends to the border box (default).
- `bg-clip-padding` → Clips background to the padding box.
- `bg-clip-content` → Clips background to the content box.
- `bg-clip-text` → Clips background to text (used with gradients).

#### **Background Color**
Applies color to the background.
- `bg-red-500`
- `bg-green-200`
- `bg-transparent`
- `bg-current` (uses current text color).

#### **Background Opacity**
Sets the opacity of background colors.
- `bg-opacity-0` → Fully transparent.
- `bg-opacity-50` → 50% visible.
- `bg-opacity-100` → Fully opaque.

#### **Background Origin**
Controls where the background image is positioned relative to the element box.
- `bg-origin-border` → Starts from border box.
- `bg-origin-padding` → Starts from padding box (default).
- `bg-origin-content` → Starts from content box.

#### **Background Position**
Sets the position of the background image.
- `bg-top`
- `bg-bottom`
- `bg-center`
- `bg-left`
- `bg-right`

#### **Background Repeat**
Controls background image repetition.
- `bg-repeat` → Default (repeats in both directions).
- `bg-no-repeat` → No repetition.
- `bg-repeat-x` → Repeats horizontally.
- `bg-repeat-y` → Repeats vertically.
- `bg-repeat-round` → Stretches to fit.
- `bg-repeat-space` → Repeats without clipping.

#### **Background Size**
Controls the size of background images.
- `bg-auto` → Default (original size).
- `bg-cover` → Scales to cover entire element.
- `bg-contain` → Scales to fit inside element.

#### **Background Image**
Defines custom background images.
- `bg-none` → No background image.
- `bg-gradient-to-r` → Gradient (right direction).
- `bg-[url('/path/to/image.png')]` → Custom image.

#### **Gradient Color Stops**
Controls gradient color stops.
- `from-red-500` → Start color.
- `via-green-500` → Middle color (optional).
- `to-blue-500` → End color.
Example:
```html
<div class="bg-gradient-to-r from-purple-400 via-pink-500 to-red-500"></div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Shadows & Effects

- Box shadow: `shadow`, `shadow-lg`, `shadow-inner`.
- Opacity: `opacity-50`.
- Blend modes: `mix-blend-multiply`.

**Example:**
```html
<div class="shadow-lg opacity-80 mix-blend-multiply p-4">Shadowed box</div>
```

### Transitions & Animations

- Transition: `transition`, `duration-300`, `ease-in-out`.
- Animation: `animate-bounce`, `animate-spin`.

**Example:**
```html
<button class="transition duration-300 ease-in-out hover:bg-blue-600">Hover Me</button>
<div class="animate-bounce">Bouncing!</div>
```


#### **transition-property**
- Controls which CSS properties should transition.
- **Classes:**
  - `transition-none` → No transition.
  - `transition-all` → All properties.
  - `transition` → Common properties (color, bg, border, opacity, transform).
  - `transition-colors` → Background, border, text, fill, stroke colors.
  - `transition-opacity` → Only opacity.
  - `transition-shadow` → Only box-shadow.
  - `transition-transform` → Only transform.

#### **transition-duration**
- Controls how long the transition lasts.
- **Classes:** `duration-{time}`
  - Example: `duration-75`, `duration-100`, `duration-150`, `duration-200`, … up to `duration-1000`.
- Custom values can be added in `tailwind.config.js`.

#### **transition-timing-function**
- Controls the easing of the transition.
- **Classes:**
  - `ease-linear`
  - `ease-in`
  - `ease-out`
  - `ease-in-out`

#### **transition-delay**
- Adds a delay before transition starts.
- **Classes:** `delay-{time}`
  - Example: `delay-75`, `delay-100`, `delay-150`, `delay-200`, … up to `delay-1000`.



#### **animation**
- Applies predefined animations.
- **Classes:**
  - `animate-none` → No animation.
  - `animate-spin` → Rotating animation (infinite).
  - `animate-ping` → Expands and fades (used for indicators).
  - `animate-pulse` → Fades in and out (used for skeleton loaders).
  - `animate-bounce` → Bouncing effect.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Transforms
> Transforms allow you to modify elements in 2D/3D space (scale, rotate, move, skew), In Tailwind, transforms are enabled with the `transform` utility.

- Scale: `scale-110`, `scale-75`.
- Rotate: `rotate-45`, `-rotate-12`.
- Translate: `translate-x-4`, `-translate-y-2`.
- Skew: `skew-x-6`, `skew-y-3`.

**Example:**
```html
<div class="transform scale-110 rotate-12">Transformed!</div>
```

#### **1. scale**
- Scales an element larger or smaller.
- **Classes:** `scale-{amount}`, `scale-x-{amount}`, `scale-y-{amount}`
- Values: `0`, `50`, `75`, `90`, `95`, `100`, `105`, `110`, `125`, `150`
- **Examples:**
  ```html
  <div class="transform scale-125">Scaled Up</div>
  <div class="transform scale-x-75">Compressed horizontally</div>
  ```

#### **2. rotate**
- Rotates an element by degrees.
- **Classes:** `rotate-{angle}`
- **Values:** `0`, `1`, `2`, …, `180`
- **Examples:**
```html
<div class="transform rotate-45">Rotated 45 degrees</div>
<div class="transform -rotate-12">Rotated -12 degrees</div>
```

#### **3. translate**
- Moves (translates) an element along X or Y axis.
- **Classes:** `translate-x-{amount}`, `translate-y-{amount}`
- **Values:** `0`, `px`, `0.5`, `1`, `2`, … `96`, `full`
- **Examples:**
```html
<div class="transform translate-x-4">Moved right 1rem</div>
<div class="transform -translate-y-2">Moved up 0.5rem</div>
```

#### **4. skew**
- Skews (slants) an element along X or Y axis.
- **Classes:** `skew-x-{angle}`, `skew-y-{angle}`
- **Values:** `0`, `1`, `2`, … `12`
- **Examples:**
```html
<div class="transform skew-x-6">Skewed 6 degrees</div>
<div class="transform skew-y-3">Skewed 3 degrees</div>
```

#### **transform-origin**
- Sets the origin point for transformations.
- **Classes:**
  - `origin-center` (default)
  - `origin-top`, `origin-top-right`, `origin-top-left`
  - `origin-bottom`, `origin-bottom-right`, `origin-bottom-left`
  - `origin-left`, `origin-right`
- **Examples:**
```html
<div class="transform origin-top">Origin at Top</div>
<div class="transform origin-bottom-right">Origin at Bottom Right</div>
```

#### **transform**
Enables transformations (scale, rotate, translate, skew).
If omitted, transform utilities won’t work.
Example:
```html
<div class="transform">
  <div class="scale-110">Scaled Up</div>
  <div class="-rotate-12">Rotated -12 degrees</div>
  <div class="translate-x-4">Moved right 1rem</div>
  <div class="skew-y-3">Skewed 3 degrees</div>
</div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Filters

- Blur: `blur`, `blur-sm`, `blur-lg`.
- Brightness: `brightness-75`.
- Contrast: `contrast-200`.
- Grayscale: `grayscale`.
- Hue rotate: `hue-rotate-90`.

**Example:**
```html
<img class="blur-lg grayscale" src="photo.jpg" />
```

- **Enable filters**: `filter`
- **Disable filters**: `filter-none`

#### `blur`
Applies blur effect to elements.

- Examples: `blur-sm`, `blur`, `blur-md`, `blur-lg`, `blur-xl`

#### `brightness`
Adjusts brightness of an element.

- Examples: `brightness-50` (darker), `brightness-100` (normal), `brightness-150` (brighter)

#### `contrast`
Adjusts contrast of an element.

- Examples: `contrast-50` (low contrast), `contrast-100` (normal), `contrast-200` (high contrast)

#### `drop-shadow`
Applies drop shadow using filters.

- Examples: `drop-shadow-sm`, `drop-shadow`, `drop-shadow-lg`, `drop-shadow-2xl`, `drop-shadow-none`

#### `grayscale`
Converts element to grayscale.

- Examples: `grayscale` (100% gray), `grayscale-0` (none)

#### `hue-rotate`
Rotates hue of colors.

- Examples: `hue-rotate-15`, `hue-rotate-60`, `hue-rotate-90`, `hue-rotate-180`

#### `invert`
Inverts colors of an element.

- Examples: `invert` (100% invert), `invert-0` (no invert)

#### `saturate`
Adjusts color saturation.

- Examples: `saturate-50` (desaturated), `saturate-100` (normal), `saturate-200` (high saturation)

#### `sepia`
Applies sepia filter.

- Examples: `sepia` (100%), `sepia-0` (none)

#### `backdrop-filter`
Enables backdrop filter effects.

- **Enable**: `backdrop-filter`
- **Disable**: `backdrop-filter-none`

#### `backdrop-blur`
Blurs background behind the element.

- Examples: `backdrop-blur-sm`, `backdrop-blur`, `backdrop-blur-lg`, `backdrop-blur-xl`

#### `backdrop-brightness`
Adjusts brightness of background behind element.

- Examples: `backdrop-brightness-50`, `backdrop-brightness-100`, `backdrop-brightness-150`

#### `backdrop-contrast`
Adjusts contrast of background behind element.

- Examples: `backdrop-contrast-50`, `backdrop-contrast-100`, `backdrop-contrast-200`

#### `backdrop-grayscale`
Applies grayscale to background behind element.

- Examples: `backdrop-grayscale`, `backdrop-grayscale-0`

#### `backdrop-hue-rotate`
Rotates hue of background colors.

- Examples: `backdrop-hue-rotate-15`, `backdrop-hue-rotate-60`, `backdrop-hue-rotate-90`

#### `backdrop-invert`
Inverts background colors.

- Examples: `backdrop-invert`, `backdrop-invert-0`

#### `backdrop-opacity`
Adjusts opacity of background.

- Examples: `backdrop-opacity-0`, `backdrop-opacity-50`, `backdrop-opacity-100`

#### `backdrop-saturate`
Adjusts saturation of background colors.

- Examples: `backdrop-saturate-50`, `backdrop-saturate-100`, `backdrop-saturate-200`

#### `backdrop-sepia`
Applies sepia effect to background.

- Examples: `backdrop-sepia`, `backdrop-sepia-0`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Interactivity

- Hover: `hover:bg-blue-500`.
- Focus: `focus:ring-2`.
- Active: `active:scale-95`.
- Group/peer: `group-hover:bg-red-500`, `peer-focus:text-green-500`.

**Example:**
```html
<button class="hover:bg-green-500 focus:ring-2">Interactive</button>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Pseudo-Classes

- First/last: `first:mt-0`, `last:mb-0`.
- Odd/even: `odd:bg-gray-100`, `even:bg-gray-200`.
- Disabled: `disabled:opacity-50`.

**Example:**
```html
<ul>
	<li class="first:font-bold">First</li>
	<li class="last:text-red-500">Last</li>
</ul>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Custom Utilities

- Add custom classes via config or CSS.
- Useful for project-specific needs.

**Example:**
```css
.btn-brand {
	@apply bg-brand text-white px-4 py-2 rounded;
}
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Plugins

- Official plugins: forms, typography, aspect-ratio, line-clamp.
- Community plugins for more features.

**Example:**
```js
// tailwind.config.js
plugins: [require('@tailwindcss/forms'), require('@tailwindcss/typography')]
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Best Practices

- Use semantic HTML with utility classes.
- Keep class lists readable and organized.
- Customize config for your brand.
- Remove unused classes for performance.

**Example:**
```html
<main class="prose prose-lg mx-auto">
	<h1>Welcome</h1>
	<p>Use Tailwind for clean, maintainable code.</p>
</main>
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Box Alignment
> Box alignment utilities in Tailwind help you control how items are aligned inside flexbox, grid, and block containers.
- Align items: `items-center`, `justify-end`, `place-items-center`.
- Place content: `place-content-between`.

**Example:**
```html
<div class="flex items-center justify-between">...</div>
<div class="grid place-items-center">...</div>
```

#### Justify Content (`justify-*`)
Controls horizontal alignment of **flex/grid children** inside their parent.

- `justify-start` → Align items to the start
- `justify-center` → Center items
- `justify-end` → Align items to the end
- `justify-between` → Items spread out with space between
- `justify-around` → Items spaced evenly, with half-size spacing on ends
- `justify-evenly` → Items spaced evenly with equal spacing

📌 Example:
```html
<div class="flex justify-center">
  <div class="p-4 bg-blue-500">Box</div>
</div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Sizing
> The **Sizing utilities** in Tailwind CSS allow you to control the width and height of elements, including their minimum and maximum constraints.

- Width: `w-1/2`, `w-full`, `max-w-lg`.
- Height: `h-10`, `h-screen`, `min-h-0`.

**Example:**
```html
<div class="w-1/2 h-32 bg-gray-200">Sized box</div>
```

#### 1. Width (`w-`)

- Controls the **width** of an element.
- Classes:
  - `w-0`, `w-px`, `w-1`, `w-2` … `w-96` → fixed widths
  - `w-1/2`, `w-1/3`, `w-2/3`, `w-full`, `w-screen`, `w-auto` → percentage or relative widths
- Example:

```html
<div class="w-1/2 bg-blue-300">Half Width</div>
<div class="w-full bg-green-300">Full Width</div>
```

#### 2. Min-Width (min-w-)
Ensures an element has at least a minimum width.
Classes:
min-w-0, min-w-full, min-w-min, min-w-max, min-w-fit
Example:
```html
<div class="min-w-full bg-yellow-200">Cannot shrink below full width</div>
```

#### 3. Max-Width (max-w-)
Restricts the maximum width of an element.
Useful for controlling content readability.
Classes:
max-w-xs, max-w-sm, max-w-md, max-w-lg, max-w-xl, max-w-2xl … max-w-screen-xl
Example:
```html
<div class="max-w-md bg-pink-200">
  This content won’t exceed medium width.
</div>
```

#### 4. Height (h-)
Controls the height of an element.
Classes:
h-0, h-px, h-1, h-2 … h-96 → fixed heights
h-full, h-screen, h-auto
Example:
```html
<div class="h-32 bg-red-200">Fixed height 8rem</div>
<div class="h-screen bg-gray-300">Full screen height</div>
```

#### 5. Min-Height (min-h-)
Ensures an element has a minimum height.
Classes:
```html
min-h-0, min-h-full, min-h-screen
```
Example:
```html
<div class="min-h-screen bg-purple-200">Always at least screen height</div>
```

#### 6. Max-Height (max-h-)
Restricts the maximum height of an element.
Classes:
max-h-0, max-h-32, max-h-64, max-h-full, max-h-screen
Example:
```html
<div class="max-h-64 overflow-y-scroll bg-indigo-200">
  Scrollable content area with max height
</div>
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Effects

- Box-shadow: `shadow`, `shadow-xl`.
- Opacity: `opacity-60`.
- Blend modes: `mix-blend-overlay`.

**Example:**
```html
<div class="shadow-xl opacity-60 mix-blend-overlay">Effect box</div>
```

#### Box Shadow (`box-shadow`)
- Adds shadow to elements.
- **Classes**:
  - `shadow-sm` → Small shadow
  - `shadow` → Default shadow
  - `shadow-md` → Medium shadow
  - `shadow-lg` → Large shadow
  - `shadow-xl` → Extra large shadow
  - `shadow-2xl` → Strongest shadow
  - `shadow-inner` → Inner shadow
  - `shadow-none` → No shadow


#### Opacity (`opacity`)
- Controls transparency of elements.
- **Classes**:
  - `opacity-0` → Fully transparent
  - `opacity-25` → 25% visible
  - `opacity-50` → 50% visible
  - `opacity-75` → 75% visible
  - `opacity-100` → Fully visible


#### Mix Blend Mode (`mix-blend-mode`)
- Defines how an element’s content should blend with the background.
- **Classes**:
  - `mix-blend-normal`
  - `mix-blend-multiply`
  - `mix-blend-screen`
  - `mix-blend-overlay`
  - `mix-blend-darken`
  - `mix-blend-lighten`
  - `mix-blend-color-dodge`
  - `mix-blend-color-burn`
  - `mix-blend-hard-light`
  - `mix-blend-soft-light`
  - `mix-blend-difference`
  - `mix-blend-exclusion`
  - `mix-blend-hue`
  - `mix-blend-saturation`
  - `mix-blend-color`
  - `mix-blend-luminosity`


#### Background Blend Mode (`background-blend-mode`)
- Controls how multiple background layers blend together.
- **Classes**:
  - `bg-blend-normal`
  - `bg-blend-multiply`
  - `bg-blend-screen`
  - `bg-blend-overlay`
  - `bg-blend-darken`
  - `bg-blend-lighten`
  - `bg-blend-color-dodge`
  - `bg-blend-color-burn`
  - `bg-blend-hard-light`
  - `bg-blend-soft-light`
  - `bg-blend-difference`
  - `bg-blend-exclusion`
  - `bg-blend-hue`
  - `bg-blend-saturation`
  - `bg-blend-color`
  - `bg-blend-luminosity`

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### SVG

- Fill: `fill-current`, `fill-blue-500`.
- Stroke: `stroke-current`, `stroke-2`.

**Example:**
```html
<svg class="w-6 h-6 fill-blue-500 stroke-2" ...></svg>
```

#### 1. `fill`
- Controls the **fill color** of an SVG shape.
- Works with Tailwind’s **color palette**.
- Useful for setting the inside color of SVG icons.

**Examples:**
```html
<svg class="w-6 h-6 fill-red-500" xmlns="http://www.w3.org/2000/svg">
  <circle cx="12" cy="12" r="10"/>
</svg>

<svg class="w-6 h-6 fill-current text-blue-500" xmlns="http://www.w3.org/2000/svg">
  <path d="..."/>
</svg>
```

- fill-red-500 → Sets fill to red
- fill-current → Inherits text color (text-* utilities)

#### 2. `stroke`
- Controls the stroke color (outline) of SVG shapes.
- Uses Tailwind’s color palette.
- Useful for line-based icons.

```html
<svg class="w-6 h-6 stroke-green-500" xmlns="http://www.w3.org/2000/svg" fill="none">
  <circle cx="12" cy="12" r="10" stroke-width="2"/>
</svg>
```

- stroke-green-500 → Green outline
- Can be combined with fill-none for hollow shapes.

#### 3. `stroke-width`
- Controls the thickness of the stroke.
- Values are numeric (stroke-0, stroke-1, stroke-2, ...).
```html
<svg class="w-6 h-6 stroke-blue-500 stroke-2" xmlns="http://www.w3.org/2000/svg" fill="none">
  <path d="M4 6h16M4 12h16M4 18h16"/>
</svg>
```
- stroke-2 → Medium line thickness
- stroke-1 → Thin outline
- stroke-0 → No stroke

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Tailwind Overview
- Utility-first CSS framework for rapid UI development.
- Mobile-first approach with responsive design utilities.
- Highly customizable via configuration files.
- Built-in support for dark mode and theming.
- Extensive plugin ecosystem for extended functionality.
