## Table of Contents

- [Introduction](#introduction)
- [What Is Object Fit?](#what-is-object-fit)
- [`object-fit`](#object-fit)
- [Object Fit Values](#object-fit-values)
- [`object-fit: fill`](#object-fit-fill)
- [`object-fit: contain`](#object-fit-contain)
- [`object-fit: cover`](#object-fit-cover)
- [`object-fit: none`](#object-fit-none)
- [`object-fit: scale-down`](#object-fit-scale-down)
- [Object Fit With Images](#object-fit-with-images)
- [Object Fit With Videos](#object-fit-with-videos)
- [Object Fit and Aspect Ratio](#object-fit-and-aspect-ratio)
- [Object Fit With Width and Height](#object-fit-with-width-and-height)
- [Object Fit With Overflow](#object-fit-with-overflow)
- [Object Fit With Object Position](#object-fit-with-object-position)
- [Practical Examples](#practical-examples)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)

---

## Introduction

The CSS `object-fit` property controls how replaced content, such as an image or video, is resized to fit inside its content box.

It is especially useful when an element has fixed dimensions but the original image or video has a different aspect ratio.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

Here:

```text
width: 300px
height: 200px
        ↓
Fixed content box
        ↓
object-fit: cover
        ↓
Image fills the box
while preserving its aspect ratio
```

### Why Use `object-fit`?

Images and videos can have different dimensions and aspect ratios.

For example:

```text
Original image
800 × 600
4:3

Container
300 × 200
3:2
```

Simply setting both `width` and `height` can distort the image.

`object-fit` provides different ways to fit the content into the available space.

### Common Uses

`object-fit` is commonly used for:

- Image galleries
- Profile pictures
- Product cards
- Blog thumbnails
- Video containers
- Responsive media layouts
- Fixed-size image cards

### Basic Syntax

```css
.element {
    object-fit: value;
}
```

For example:

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

### Main `object-fit` Values

The property supports several values:

```text
fill
contain
cover
none
scale-down
```

Each value determines how the replaced content is fitted inside its content box.

### `cover` Example

One of the most common patterns is:

```css
.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

The image fills the specified area while maintaining its aspect ratio.

Parts of the image may be cropped when necessary.

### `contain` Example

```css
.card img {
    width: 100%;
    height: 200px;
    object-fit: contain;
}
```

The entire image remains visible while preserving its aspect ratio.

Depending on the aspect ratios, empty space may appear inside the content box.

### Important Distinction

`object-fit` does not set the dimensions of the element.

For example:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

Here:

```text
width
→ Sets the element's width

height
→ Sets the element's height

object-fit
→ Controls how the image content fits inside those dimensions
```

### `object-fit` and Aspect Ratio

The original media can have one aspect ratio while the element has another.

```text
Original image
     ↓
Different aspect ratio
     ↓
Element dimensions
     ↓
object-fit determines
how the image is fitted
```

This makes `object-fit` particularly useful when creating consistent media sizes.

### Important Points

```text
object-fit
│
├── Controls how replaced content fits
│   inside its content box
│
├── Commonly used with
│   ├── Images
│   └── Videos
│
├── Does not set width or height
│
└── Useful when content and container
    have different aspect ratios
```

> 💡 **Remember:** `object-fit` controls how an image or video fits inside its content box. It is especially useful when you need consistent media dimensions without unnecessarily distorting the original aspect ratio.

---

## What Is Object Fit?

`object-fit` is a CSS property that controls how the content of a replaced element fits inside its content box.

It is most commonly used with:

- Images
- Videos

### Replaced Elements

An image or video is a replaced element because its content comes from an external resource rather than being generated directly by CSS.

For example:

```html
<img src="image.jpg" alt="Example">
```

```html
<video controls src="video.mp4"></video>
```

Both can use `object-fit`.

### Why Is `object-fit` Useful?

Suppose an image has these dimensions:

```text
Original image
800 × 600
```

And you give the image element:

```css
img {
    width: 300px;
    height: 200px;
}
```

The content box has a different aspect ratio from the original image.

Without an appropriate `object-fit` value, the image may be distorted to fit the specified dimensions.

`object-fit` lets you control how the image is fitted.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

The image is fitted into the `300px × 200px` content box while maintaining its aspect ratio.

### Object Fit and Aspect Ratio

Consider:

```text
Original image
800 × 600
4:3

Content box
300 × 200
3:2
```

The aspect ratios are different.

`object-fit` determines how the original content should be handled inside the content box.

Depending on the value, the content may be:

```text
Stretched
Contained
Cropped
Displayed at natural size
Scaled down
```

### Main Values

The `object-fit` property supports five main values:

```css
object-fit: fill;
object-fit: contain;
object-fit: cover;
object-fit: none;
object-fit: scale-down;
```

Each value produces different fitting behavior.

### `fill`

```css
img {
    object-fit: fill;
}
```

The default behavior.

The replaced content is resized to fill the content box, which can distort its aspect ratio.

### `contain`

```css
img {
    object-fit: contain;
}
```

The entire content is kept visible while preserving its aspect ratio.

Empty space may remain inside the content box.

### `cover`

```css
img {
    object-fit: cover;
}
```

The content fills the entire content box while preserving its aspect ratio.

Some content may be cropped.

### `none`

```css
img {
    object-fit: none;
}
```

The replaced content is not resized to fit the content box.

The content is displayed at its natural size.

### `scale-down`

```css
img {
    object-fit: scale-down;
}
```

The browser chooses the smaller rendered size between `none` and `contain`.

### `object-fit` Does Not Set Dimensions

This is an important distinction.

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

Here:

```text
width
→ Defines the element's width

height
→ Defines the element's height

object-fit
→ Defines how the image content fits inside the element
```

### Common Image Card Pattern

```css
.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

This is useful for creating image cards where every image needs to occupy the same visual area.

```text
Different source images
        ↓
Same content-box dimensions
        ↓
object-fit: cover
        ↓
Consistent image cards
```

### Important Points

```text
object-fit
│
├── Controls how replaced content fits
│   inside its content box
│
├── Commonly used with
│   ├── Images
│   └── Videos
│
├── Does not set width or height
│
└── Helps control different aspect ratios
```

> 💡 **Remember:** `object-fit` controls how an image or video is fitted inside its content box. The `width` and `height` define the box; `object-fit` determines how the replaced content is displayed inside it.