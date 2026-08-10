## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Backgrounds?](#what-are-css-backgrounds)
- [Why Are CSS Backgrounds Important?](#why-are-css-backgrounds-important)
- [Background Color](#background-color)
- [Background Image](#background-image)
- [Background Repeat](#background-repeat)
- [Background Position](#background-position)
- [Background Size](#background-size)
- [Background Attachment](#background-attachment)
- [Background Shorthand](#background-shorthand)
- [Multiple Backgrounds](#multiple-backgrounds)
- [Background Origin](#background-origin)
- [Background Clip](#background-clip)
- [Background Blend Mode](#background-blend-mode)
- [Common Use Cases](#common-use-cases)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)

---

# Introduction

CSS backgrounds are used to control the **background appearance of HTML elements**.

They allow you to add visual backgrounds such as:

- Colors
- Images
- Patterns
- Multiple background layers

For example:

```css
body {
    background-color: lightblue;
}
```

This applies a light blue background to the `<body>` element.

A background image can also be added:

```css
.hero {
    background-image: url("hero.jpg");
}
```

CSS provides several properties to control how backgrounds are displayed.

Some commonly used background properties are:

```css
background-color
background-image
background-repeat
background-position
background-size
background-attachment
```

These properties can be used individually or combined to create different background effects.

---

> 💡 **Pro Tip:** Learn the individual background properties first. Once you understand how each property works, the `background` shorthand becomes much easier to use.

---

> 💡 **Remember:** CSS backgrounds control the visual background of an element without changing the actual HTML content inside it.

---

# What Are CSS Backgrounds?

CSS backgrounds define the visual area behind the content of an HTML element.

A background can be a:

- Color
- Image
- Repeating pattern
- Combination of multiple images and colors

For example:

```css
.box {
    background-color: lightblue;
}
```

This gives the element a light blue background.

---

## Background Color

A background can be created using a color:

```css
.box {
    background-color: yellow;
}
```

The color appears behind the element's content.

---

## Background Image

A background can also use an image:

```css
.hero {
    background-image: url("hero.jpg");
}
```

The image is displayed behind the element's content.

---

## Background Pattern

Background images can be repeated to create patterns.

```css
.pattern {
    background-image: url("pattern.png");
    background-repeat: repeat;
}
```

This can be useful for decorative backgrounds.

---

## Multiple Backgrounds

CSS also allows multiple background images to be applied to the same element.

```css
.element {
    background-image:
        url("foreground.png"),
        url("background.png");
}
```

The first image is placed above the second image.

This makes it possible to create layered background designs without adding multiple HTML elements.

---

## Common Background Properties

CSS provides several properties for controlling backgrounds:

```css
background-color
background-image
background-repeat
background-position
background-size
background-attachment
background-origin
background-clip
background-blend-mode
```

These properties control different aspects of how a background is displayed.

---

> 💡 **Pro Tip:** Think of CSS backgrounds as a separate visual layer behind an element's content. Once you understand the individual background properties, you can combine them to create complex designs without changing the HTML structure.

---

> 💡 **Remember:** A CSS background belongs to the element itself. It is different from an `<img>` element, which is actual content in the HTML document.

---

# Why Are CSS Backgrounds Important?

CSS backgrounds are important because they help control the **visual appearance and presentation** of web elements.

They can be used to make websites more visually appealing while keeping decorative elements separate from the actual HTML content.

---

## 1. Improve Visual Design

Backgrounds can make sections and components more attractive.

```css
.card {
    background-color: #f5f5f5;
}
```

This gives the card a clear visual background.

---

## 2. Add Background Images

Background images can be used for large visual sections such as hero areas.

```css
.hero {
    background-image: url("hero.jpg");
}
```

This allows an image to become part of the visual design without adding an `<img>` element.

---

## 3. Create Visual Sections

Different background colors can visually separate sections of a webpage.

```css
.header {
    background-color: #222;
}

.content {
    background-color: #fff;
}

.footer {
    background-color: #222;
}
```

This creates a clear visual distinction between different parts of the page.

---

## 4. Create Decorative Patterns

Background images can be repeated to create patterns.

```css
.pattern {
    background-image: url("pattern.png");
    background-repeat: repeat;
}
```

This can be useful for decorative areas without adding extra HTML elements.

---

## 5. Create Image-Based Hero Sections

Background images are commonly used for hero sections.

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center;
}
```

This allows the image to cover the entire section while maintaining its visual presentation.

---

## 6. Create Layered Designs

CSS supports multiple background images.

```css
.element {
    background-image:
        url("foreground.png"),
        url("background.png");
}
```

This allows multiple visual layers to be combined within a single element.

---

## 7. Separate Content from Decoration

Backgrounds are useful for decorative visuals that are not part of the actual page content.

For example:

```css
.section {
    background-image: url("decorative-pattern.png");
}
```

The pattern is visual decoration, while the actual content remains in the HTML.

This can help keep the HTML structure simpler.

---

## 8. Reduce Unnecessary HTML

Some decorative elements do not need additional HTML elements.

Instead of:

```html
<div class="background">
    <div class="content">
        ...
    </div>
</div>
```

a background can sometimes be applied directly:

```css
.content {
    background-image: url("pattern.png");
}
```

This can keep the document structure cleaner.

---

## 9. Support Responsive Designs

Background properties can be adjusted for different screen sizes.

For example:

```css
.hero {
    background-size: cover;
    background-position: center;
}
```

These properties help background images adapt to different container sizes.

---

## 10. Common Real-World Uses

CSS backgrounds are commonly used for:

- Website sections
- Hero banners
- Cards
- Navigation areas
- Decorative patterns
- Image overlays
- Buttons
- Landing pages
- Headers
- Footers

---

> 💡 **Pro Tip:** Use CSS backgrounds mainly for **visual presentation and decoration**. If an image is meaningful content that users need to understand, an `<img>` element with appropriate alternative text is often more suitable.

---

> 💡 **Remember:** CSS backgrounds help control the visual layer behind an element. They are especially useful for **colors, decorative images, patterns, and section backgrounds**.

---

# Background Color

The `background-color` property is used to set the **background color** of an HTML element.

```css
.element {
    background-color: lightblue;
}
```

The color appears behind the element's content.

---

## Basic Example

```html
<div class="box">
    This is a box.
</div>
```

```css
.box {
    background-color: lightblue;
}
```

The `<div>` receives a light blue background.

---

## Using Color Names

CSS supports predefined color names.

```css
.box {
    background-color: red;
}
```

Other examples:

```css
background-color: blue;
background-color: green;
background-color: yellow;
background-color: orange;
background-color: purple;
```

---

## Using Hexadecimal Colors

Hexadecimal color values can also be used.

```css
.box {
    background-color: #3498db;
}
```

Example:

```css
.header {
    background-color: #222222;
}
```

---

## Using RGB

RGB values can be used to define a background color.

```css
.box {
    background-color: rgb(52, 152, 219);
}
```

The three values represent:

```text
Red
Green
Blue
```

---

## Using RGBA

`rgba()` allows you to specify a color with transparency.

```css
.box {
    background-color: rgba(0, 0, 0, 0.5);
}
```

The fourth value controls the alpha channel.

```text
0   → Completely transparent
1   → Completely opaque
```

For example:

```css
background-color: rgba(0, 0, 0, 0.2);
```

creates a partially transparent black background.

---

## Using HSL

HSL can also be used for background colors.

```css
.box {
    background-color: hsl(200, 70%, 50%);
}
```

HSL represents:

```text
Hue
Saturation
Lightness
```

---

## Transparent Background

The `transparent` keyword can be used when no visible background color is required.

```css
.box {
    background-color: transparent;
}
```

This allows the background behind the element to remain visible.

---

## Background Color and Content

The background color appears behind the element's content.

```css
.card {
    background-color: lightgray;
    padding: 20px;
}
```

The background covers the element's background area, including the area occupied by its padding.

```text
┌─────────────────────────────┐
│         Padding             │
│   ┌─────────────────────┐   │
│   │       Content       │   │
│   └─────────────────────┘   │
└─────────────────────────────┘
      Background Color
```

---

## Background Color and Border

A background color can be combined with a border.

```css
.card {
    background-color: lightblue;
    border: 2px solid blue;
}
```

The border and background can be styled independently.

---

## Example: Card

```html
<div class="card">
    <h2>CSS Backgrounds</h2>
    <p>Learning background colors.</p>
</div>
```

```css
.card {
    background-color: #f5f5f5;
    padding: 20px;
    border: 1px solid #ddd;
}
```

---

## Example: Header

```css
header {
    background-color: #222;
    color: white;
    padding: 20px;
}
```

This creates a dark header background.

---

## Example: Button

```css
button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
}
```

The background color helps visually distinguish the button from surrounding content.

---

## Changing Background Color on Hover

`background-color` can be combined with pseudo-classes.

```css
button {
    background-color: blue;
}

button:hover {
    background-color: darkblue;
}
```

When the user moves the pointer over the button, the background color changes.

---

## Using CSS Variables

Background colors can also use CSS custom properties.

```css
:root {
    --primary-color: #3498db;
}

.button {
    background-color: var(--primary-color);
}
```

This makes it easier to reuse the same color throughout a project.

---

## Common Uses

`background-color` is commonly used for:

- Page backgrounds
- Headers
- Footers
- Cards
- Buttons
- Navigation bars
- Sections
- Forms
- Alerts
- Modals

---

## `background-color` vs `color`

These two properties control different things.

```css
.element {
    background-color: blue;
    color: white;
}
```

Here:

```text
background-color
        ↓
Background of the element

color
        ↓
Text color
```

---

> 💡 **Pro Tip:** Use `background-color` for the visual background and `color` for the foreground text. Always make sure there is enough contrast between them for readability.

---

> 💡 **Remember:** `background-color` changes the color behind an element's content. It does not change the text color — that is controlled by the `color` property.

---

# Background Image

The `background-image` property is used to set an **image as the background** of an HTML element.

```css
.element {
    background-image: url("image.jpg");
}
```

The image is displayed behind the element's content.

---

## Basic Example

```html
<div class="hero">
    <h1>Welcome</h1>
</div>
```

```css
.hero {
    background-image: url("hero.jpg");
}
```

The image becomes the background of the `.hero` element.

---

## Using `url()`

The `url()` function specifies the location of the background image.

```css
.box {
    background-image: url("image.jpg");
}
```

The image path can be:

- A relative path
- An absolute URL
- A path from another directory

Example:

```css
.box {
    background-image: url("../images/background.jpg");
}
```

---

## Using an Absolute URL

A background image can also come from another website.

```css
.box {
    background-image: url("https://example.com/image.jpg");
}
```

However, external resources should be used carefully because they depend on network availability and the external server.

---

## Background Image with a Color

A background color can be combined with a background image.

```css
.box {
    background-color: lightgray;
    background-image: url("pattern.png");
}
```

The image is displayed over the background color.

If the image does not cover the entire background area, the background color can still be visible.

---

## Background Image Does Not Change the Content

A background image is visual decoration and does not become an HTML content element.

For example:

```css
.hero {
    background-image: url("hero.jpg");
}
```

The image is not part of the document content in the same way as:

```html
<img src="hero.jpg" alt="Hero image">
```

This distinction is important when deciding whether an image is decorative or meaningful content.

---

## Background Image and Text

Text can appear above a background image.

```html
<section class="hero">
    <h1>Welcome to My Website</h1>
</section>
```

```css
.hero {
    background-image: url("hero.jpg");
}
```

The result can be visualized as:

```text
┌───────────────────────────────┐
│                               │
│      Background Image         │
│                               │
│       Welcome to My Website   │
│                               │
└───────────────────────────────┘
```

---

## Background Image and `background-repeat`

By default, a background image can repeat if it is smaller than the element.

```css
.box {
    background-image: url("pattern.png");
}
```

The image can repeat horizontally and vertically.

The `background-repeat` property can be used to control this behavior.

```css
.box {
    background-image: url("pattern.png");
    background-repeat: no-repeat;
}
```

More details about `background-repeat` will be covered in the next section.

---

## Background Image and `background-size`

The size of a background image can be controlled using:

```css
background-size
```

For example:

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
}
```

This allows the image to cover the background area.

`background-size` will be covered in detail later in this chapter.

---

## Background Image and `background-position`

The position of a background image can also be controlled.

```css
.hero {
    background-image: url("hero.jpg");
    background-position: center;
}
```

This is useful when you want to control which part of an image is visible.

`background-position` will be covered in detail later.

---

## Using Multiple Background Images

CSS allows multiple background images on the same element.

```css
.element {
    background-image:
        url("foreground.png"),
        url("background.png");
}
```

The first image is painted above the second image.

```text
Top Layer
    ↓
foreground.png

    ↓

background.png
    ↓
Bottom Layer
```

This allows multiple visual layers to be created without additional HTML elements.

---

## Background Image with a Gradient

Gradients can also be used as background images.

For example:

```css
.box {
    background-image: linear-gradient(
        to right,
        blue,
        purple
    );
}
```

A gradient is treated as a background image by CSS.

---

## Linear Gradient

A linear gradient changes colors along a straight line.

```css
.box {
    background-image: linear-gradient(
        to right,
        red,
        blue
    );
}
```

The colors transition from one side to the other.

---

## Radial Gradient

A radial gradient spreads outward from a central point.

```css
.box {
    background-image: radial-gradient(
        circle,
        white,
        blue
    );
}
```

This can be useful for creating circular lighting and decorative effects.

---

## Gradient with an Image

A gradient and image can be combined.

```css
.hero {
    background-image:
        linear-gradient(
            rgba(0, 0, 0, 0.5),
            rgba(0, 0, 0, 0.5)
        ),
        url("hero.jpg");
}
```

This creates a dark overlay above the image.

This technique is commonly used when text needs to remain readable over a background image.

---

## Example: Hero Section

```html
<section class="hero">
    <h1>Build Better Websites</h1>
    <p>Learn CSS step by step.</p>
</section>
```

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center;
    padding: 100px 20px;
}
```

This creates a large visual hero section.

---

## Example: Image Overlay

```css
.hero {
    background-image:
        linear-gradient(
            rgba(0, 0, 0, 0.5),
            rgba(0, 0, 0, 0.5)
        ),
        url("hero.jpg");
}
```

The gradient provides a darker layer over the image.

```text
┌───────────────────────────────┐
│                               │
│        Dark Overlay           │
│                               │
│       Hero Content            │
│                               │
└───────────────────────────────┘
```

---

## Common Uses

`background-image` is commonly used for:

- Hero sections
- Website banners
- Decorative patterns
- Section backgrounds
- Image overlays
- Landing pages
- Cards
- Textured backgrounds
- Gradient backgrounds

---

## `background-image` vs `<img>`

| Feature | `background-image` | `<img>` |
|---------|--------------------|---------|
| HTML content | ❌ | ✅ |
| Mainly decorative | ✅ | Can be |
| Alternative text | ❌ | ✅ |
| Easy background positioning | ✅ | Different approach |
| Common for hero backgrounds | ✅ | Sometimes |
| Part of document content | ❌ | ✅ |

If an image conveys important information, an `<img>` with appropriate `alt` text is often more suitable.

---

> 💡 **Pro Tip:** Use `background-image` when the image is primarily part of the **visual design or decoration**. Use `<img>` when the image is meaningful content that should be part of the document.

---

> 💡 **Remember:** `background-image` places an image behind an element's content. Properties such as `background-repeat`, `background-position`, and `background-size` control how that image is displayed.

---

# Background Repeat

The `background-repeat` property controls **whether and how a background image repeats** inside an element.

By default, a background image can repeat both horizontally and vertically if it is smaller than the element.

```css
.box {
    background-image: url("pattern.png");
    background-repeat: repeat;
}
```

---

## Default Behavior

The default value is:

```css
background-repeat: repeat;
```

This repeats the image in both directions.

```text
┌─────────────────────────────┐
│ 🟦 🟦 🟦 🟦 🟦 🟦 │
│ 🟦 🟦 🟦 🟦 🟦 🟦 │
│ 🟦 🟦 🟦 🟦 🟦 🟦 │
│ 🟦 🟦 🟦 🟦 🟦 🟦 │
└─────────────────────────────┘
```

---

## `repeat`

The `repeat` value repeats the background image horizontally and vertically.

```css
.box {
    background-repeat: repeat;
}
```

This is the default behavior.

It is useful for creating:

- Patterns
- Textures
- Tiles
- Decorative backgrounds

---

## `no-repeat`

The `no-repeat` value prevents the background image from repeating.

```css
.box {
    background-repeat: no-repeat;
}
```

The image appears only once.

```text
┌─────────────────────────────┐
│ 🟦                          │
│                             │
│                             │
│                             │
└─────────────────────────────┘
```

This is commonly used with large background images.

---

## `repeat-x`

The `repeat-x` value repeats the image **horizontally**.

```css
.box {
    background-repeat: repeat-x;
}
```

```text
┌─────────────────────────────┐
│ 🟦 🟦 🟦 🟦 🟦 🟦 │
│                             │
│                             │
│                             │
└─────────────────────────────┘
```

It can be useful for horizontal patterns.

---

## `repeat-y`

The `repeat-y` value repeats the image **vertically**.

```css
.box {
    background-repeat: repeat-y;
}
```

```text
┌─────────────────────────────┐
│ 🟦                          │
│ 🟦                          │
│ 🟦                          │
│ 🟦                          │
└─────────────────────────────┘
```

It can be useful for vertical patterns.

---

## `space`

The `space` value repeats the image without clipping it.

Extra space is distributed between the repeated images.

```css
.box {
    background-repeat: space;
}
```

This can result in spacing between repeated background images.

---

## `round`

The `round` value adjusts the size of the background image so that it can repeat an integer number of times without being clipped.

```css
.box {
    background-repeat: round;
}
```

The browser may resize the background image slightly to achieve this.

---

## Using Two Values

`background-repeat` can accept two values.

```css
.box {
    background-repeat: repeat no-repeat;
}
```

The first value controls the horizontal direction.

The second value controls the vertical direction.

```text
Horizontal → repeat
Vertical   → no-repeat
```

For example:

```css
background-repeat: repeat no-repeat;
```

means:

```text
X-axis → repeat
Y-axis → no-repeat
```

---

## Another Example

```css
.box {
    background-repeat: no-repeat repeat;
}
```

This means:

```text
X-axis → no-repeat
Y-axis → repeat
```

---

## Combining with `background-image`

`background-repeat` is normally used together with `background-image`.

```css
.pattern {
    background-image: url("pattern.png");
    background-repeat: repeat;
}
```

Or:

```css
.hero {
    background-image: url("hero.jpg");
    background-repeat: no-repeat;
}
```

---

## Example: Decorative Pattern

```css
.pattern {
    background-image: url("dots.png");
    background-repeat: repeat;
    padding: 40px;
}
```

The small image can create a repeating decorative pattern across the element.

---

## Example: Single Background Image

```css
.hero {
    background-image: url("hero.jpg");
    background-repeat: no-repeat;
}
```

This prevents the image from appearing multiple times.

---

## `repeat` vs `no-repeat`

| Value | Behavior |
|-------|----------|
| `repeat` | Repeats horizontally and vertically |
| `no-repeat` | Does not repeat |
| `repeat-x` | Repeats horizontally |
| `repeat-y` | Repeats vertically |
| `space` | Repeats with distributed spacing |
| `round` | Repeats while adjusting image size |

---

## Common Use Cases

`background-repeat` is commonly used for:

- Repeating patterns
- Textures
- Decorative backgrounds
- Horizontal borders
- Vertical patterns
- Single hero images

---

> 💡 **Pro Tip:** For large photographs and hero images, `background-repeat: no-repeat` is usually a good starting point. For small textures and patterns, `repeat` can be useful.

---

> 💡 **Remember:** `background-repeat` controls **how many times a background image is repeated and in which direction**. It does not control the size or position of the image.

Those are controlled by:

```css
background-size
background-position
```

---

# Background Position

The `background-position` property controls **where a background image is positioned inside an element**.

```css
.box {
    background-image: url("image.jpg");
    background-position: center;
}
```

It is especially useful when the background image does not completely fill the element or when you want to control which part of an image is visible.

---

## Basic Example

```css
.hero {
    background-image: url("hero.jpg");
    background-position: center;
}
```

The image is positioned in the center of the element.

---

## Default Position

The default value is:

```css
background-position: 0% 0%;
```

This places the background image at the top-left corner.

```text
┌─────────────────────────────┐
│ IMAGE                       │
│                             │
│                             │
│                             │
└─────────────────────────────┘
```

---

## Position Keywords

CSS provides several keywords for positioning background images.

Common values include:

```css
left
center
right
top
bottom
```

These can be combined.

---

## `left top`

```css
.box {
    background-position: left top;
}
```

The image is positioned at the top-left.

```text
┌─────────────────────────────┐
│ IMAGE                       │
│                             │
│                             │
│                             │
└─────────────────────────────┘
```

---

## `center`

```css
.box {
    background-position: center;
}
```

The image is centered horizontally and vertically.

```text
┌─────────────────────────────┐
│                             │
│          IMAGE              │
│                             │
└─────────────────────────────┘
```

---

## `right bottom`

```css
.box {
    background-position: right bottom;
}
```

The image is positioned at the bottom-right.

```text
┌─────────────────────────────┐
│                             │
│                             │
│                       IMAGE │
└─────────────────────────────┘
```

---

## Horizontal and Vertical Position

`background-position` can use two values.

```css
.box {
    background-position: left center;
}
```

The first value controls the horizontal position.

The second value controls the vertical position.

```text
Horizontal → left
Vertical   → center
```

For example:

```css
background-position: right top;
```

means:

```text
Horizontal → right
Vertical   → top
```

---

## Using Percentages

Percentages can be used to position the background image.

```css
.box {
    background-position: 50% 50%;
}
```

This centers the image.

The following is equivalent:

```css
background-position: center;
```

Other examples:

```css
background-position: 0% 0%;
background-position: 100% 100%;
```

These represent:

```text
0% 0%       → top-left
50% 50%     → center
100% 100%   → bottom-right
```

---

## Using Length Values

Length units can also be used.

```css
.box {
    background-position: 20px 30px;
}
```

The first value controls the horizontal position.

The second value controls the vertical position.

```text
Horizontal → 20px
Vertical   → 30px
```

---

## Example with `px`

```css
.hero {
    background-image: url("hero.jpg");
    background-repeat: no-repeat;
    background-position: 20px 40px;
}
```

The image is positioned:

- `20px` horizontally.
- `40px` vertically.

---

## Negative Values

Negative values can also be used.

```css
.box {
    background-position: -20px -10px;
}
```

This moves the background image toward the left and upward.

Negative positioning can be useful when only a particular part of a larger background image should be visible.

---

## Combining with `background-size`

`background-position` is often used together with `background-size`.

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center;
}
```

Here:

```text
background-size
        ↓
Controls the size of the image

background-position
        ↓
Controls which part is positioned in the container
```

This combination is very common for hero sections.

---

## Example: Hero Section

```css
.hero {
    height: 400px;
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center;
}
```

The image covers the hero section while remaining centered.

---

## Focusing on a Specific Part of an Image

Sometimes the important part of an image is not in the center.

For example:

```css
.hero {
    background-image: url("person.jpg");
    background-size: cover;
    background-position: 70% center;
}
```

This changes the horizontal position of the image so that a different part of it remains visible.

---

## `background-position-x`

The horizontal position can be controlled separately using:

```css
background-position-x
```

Example:

```css
.box {
    background-position-x: right;
}
```

---

## `background-position-y`

The vertical position can be controlled separately using:

```css
background-position-y
```

Example:

```css
.box {
    background-position-y: bottom;
}
```

---

## Common Values

| Value | Result |
|-------|--------|
| `left top` | Top-left |
| `center top` | Top-center |
| `right top` | Top-right |
| `left center` | Middle-left |
| `center` | Center |
| `right center` | Middle-right |
| `left bottom` | Bottom-left |
| `center bottom` | Bottom-center |
| `right bottom` | Bottom-right |

---

## Common Use Cases

`background-position` is commonly used for:

- Hero sections
- Banner images
- Image overlays
- Decorative backgrounds
- Background patterns
- Focusing on a specific part of an image
- Responsive image backgrounds

---

> 💡 **Pro Tip:** When using `background-size: cover`, start with `background-position: center`. If the important part of the image is being cropped, adjust the position using percentages such as `30%`, `70%`, or another value that keeps the important area visible.

---

> 💡 **Remember:** `background-position` controls **where the background image is placed**, while `background-size` controls **how large the image is**.

---

# Background Size

The `background-size` property controls the **size of a background image** inside an element.

```css
.box {
    background-image: url("image.jpg");
    background-size: cover;
}
```

It is useful when you want to control how a background image fits inside its container.

---

## Default Behavior

The default value is:

```css
background-size: auto;
```

The image keeps its original size.

```css
.box {
    background-image: url("image.jpg");
    background-size: auto;
}
```

---

## `auto`

The `auto` value keeps the background image at its natural dimensions.

```css
.box {
    background-size: auto;
}
```

This is the default behavior.

---

## Using Width and Height

You can specify the width and height of a background image.

```css
.box {
    background-size: 300px 200px;
}
```

The first value controls the width.

The second value controls the height.

```text
Width  → 300px
Height → 200px
```

---

## Using One Value

If only one value is provided:

```css
.box {
    background-size: 300px;
}
```

The width is set to `300px`.

The height is automatically calculated to preserve the image's aspect ratio.

```text
Width  → 300px
Height → auto
```

---

## Using Percentages

Percentages can be used to size the background image relative to the background positioning area.

```css
.box {
    background-size: 100% 100%;
}
```

This makes the image fill the available background area.

Another example:

```css
.box {
    background-size: 50% auto;
}
```

The image width becomes `50%` of the background positioning area while the height remains proportional.

---

## `cover`

The `cover` value scales the background image so that it **completely covers the background area**.

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
}
```

The image maintains its aspect ratio.

If necessary, parts of the image may be cropped.

```text
┌─────────────────────────────┐
│                             │
│      IMAGE                  │
│   ┌─────────────────────┐   │
│   │                     │   │
│   │     Cropped Area    │   │
│   │                     │   │
│   └─────────────────────┘   │
│                             │
└─────────────────────────────┘
```

---

## `contain`

The `contain` value scales the background image so that the **entire image fits inside the background area**.

```css
.box {
    background-image: url("image.jpg");
    background-size: contain;
}
```

The entire image remains visible.

However, empty space may remain around the image.

```text
┌─────────────────────────────┐
│                             │
│       ┌─────────────┐       │
│       │    IMAGE    │       │
│       └─────────────┘       │
│                             │
└─────────────────────────────┘
```

---

## `cover` vs `contain`

| Value | Behavior | Image Cropping | Empty Space |
|-------|----------|----------------|-------------|
| `cover` | Covers entire area | Possible | Usually no |
| `contain` | Entire image fits | No | Possible |

---

## Example: Hero Section with `cover`

```css
.hero {
    height: 400px;
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center;
}
```

This is a very common pattern for hero sections.

The image fills the entire section while keeping its aspect ratio.

---

## Example: Logo with `contain`

```css
.logo-container {
    width: 300px;
    height: 150px;
    background-image: url("logo.png");
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
}
```

The complete logo remains visible inside the container.

---

## Preserving Aspect Ratio

When using:

```css
background-size: cover;
```

or:

```css
background-size: contain;
```

the image's aspect ratio is preserved.

This prevents the image from being stretched unnaturally.

---

## Distorting an Image

Using explicit width and height values can change the image's proportions.

```css
.box {
    background-size: 300px 100px;
}
```

If these dimensions do not match the original aspect ratio, the image can appear distorted.

---

## Combining with `background-position`

`background-size` is commonly used with `background-position`.

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center;
}
```

Here:

```text
background-size
        ↓
Controls how large the image becomes

background-position
        ↓
Controls where the image is positioned
```

---

## Combining with `background-repeat`

For a full background image, these properties are often used together:

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}
```

This creates a common full-section background.

---

## Common Values

```css
background-size: auto;
background-size: 300px;
background-size: 300px 200px;
background-size: 50% auto;
background-size: cover;
background-size: contain;
```

---

## Common Use Cases

`background-size` is commonly used for:

- Hero sections
- Full-screen backgrounds
- Banners
- Cards
- Responsive layouts
- Logos
- Decorative images
- Image overlays

---

> 💡 **Pro Tip:** For responsive hero images, `background-size: cover` is often the most useful starting point. Combine it with `background-position: center` and adjust the position when important parts of the image are cropped.

---

> 💡 **Remember:** `cover` makes the background image **cover the entire area**, while `contain` makes the **entire image fit inside the area**.