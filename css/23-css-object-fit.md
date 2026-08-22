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

---

## `object-fit`

The CSS `object-fit` property specifies how the content of a replaced element, such as an image or video, should be resized to fit inside its content box.

### Syntax

```css
.element {
    object-fit: value;
}
```

The main values are:

```text
fill
contain
cover
none
scale-down
```

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

Here, the image element has a `300px × 200px` content box, and `object-fit: cover` controls how the image content is fitted inside that box.

### `object-fit` Requires a Content Box

`object-fit` controls how the replaced content fits inside the element's content box.

For example:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: contain;
}
```

The dimensions are controlled separately:

```text
width
→ Defines the width of the element

height
→ Defines the height of the element

object-fit
→ Defines how the image content fits inside the element
```

### Applying `object-fit` to Images

```html
<img
    class="profile-image"
    src="profile.jpg"
    alt="Profile"
>
```

```css
.profile-image {
    width: 200px;
    height: 200px;
    object-fit: cover;
}
```

This is useful for profile images because different source images can be displayed inside the same square area.

### Applying `object-fit` to Videos

`object-fit` can also be used with video elements.

```html
<video
    class="video"
    controls
    src="video.mp4">
</video>
```

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: cover;
}
```

The video content is fitted into the specified content box according to the selected `object-fit` value.

### `object-fit` Does Not Crop the Element

When using:

```css
img {
    object-fit: cover;
}
```

the element itself is not cropped.

Instead, the replaced content is fitted into the element's content box, and portions of the content may not be visible.

For example:

```text
Image
800 × 600
    ↓
Content box
300 × 200
    ↓
object-fit: cover
    ↓
Content fills the box
    ↓
Some image content may be outside the visible area
```

### `object-fit` and Aspect Ratio

The property becomes especially useful when the aspect ratio of the media differs from the aspect ratio of its content box.

For example:

```text
Original image
4:3

Content box
16:9
```

Different `object-fit` values produce different results.

```text
fill
→ May distort the image

contain
→ Keeps the entire image visible

cover
→ Fills the box and may crop content

none
→ Keeps the natural size

scale-down
→ Uses the smaller appropriate size
```

### Important Points

```text
object-fit
│
├── Applies to replaced elements
│
├── Commonly used with
│   ├── <img>
│   └── <video>
│
├── Controls content fitting
│
├── Does not define width or height
│
└── Helps handle different aspect ratios
```

> 💡 **Remember:** `object-fit` controls how replaced content is resized and fitted inside its content box. It does not determine the element's width or height.

---

## Object Fit Values

The `object-fit` property accepts five main values:

```text
fill
contain
cover
none
scale-down
```

Each value determines how replaced content, such as an image or video, fits inside its content box.

### `fill`

```css
img {
    object-fit: fill;
}
```

`fill` stretches the content to completely fill the content box.

The original aspect ratio may not be preserved.

For example:

```text
Original image
800 × 600
4:3

Content box
300 × 200
3:2

object-fit: fill
        ↓
Content fills the box
        ↓
Aspect ratio may be distorted
```

`fill` is the default value.

### `contain`

```css
img {
    object-fit: contain;
}
```

`contain` scales the content while preserving its aspect ratio so that the entire content fits inside the content box.

The complete image remains visible.

Empty space may remain inside the content box.

```text
Content box
┌────────────────────┐
│                    │
│     ┌────────┐     │
│     │ Image  │     │
│     └────────┘     │
│                    │
└────────────────────┘
```

### `cover`

```css
img {
    object-fit: cover;
}
```

`cover` scales the content while preserving its aspect ratio so that the content completely covers the content box.

Because the aspect ratios may be different, some parts of the content can be cropped.

```text
Content box
┌────────────────────┐
│  ┌──────────────┐  │
│  │    Image     │  │
│  │   cropped    │  │
│  └──────────────┘  │
└────────────────────┘
```

`cover` is commonly used for:

- Profile images
- Product cards
- Gallery thumbnails
- Hero images
- Blog thumbnails

### `none`

```css
img {
    object-fit: none;
}
```

`none` means the replaced content is not resized.

The content is displayed at its natural size.

If the content is larger than the content box, parts of it may not be visible.

### `scale-down`

```css
img {
    object-fit: scale-down;
}
```

`scale-down` determines the smaller rendered size between `none` and `contain`.

It can be thought of as choosing whichever would result in the smaller concrete object size.

This is useful when you want content to remain at its natural size when it already fits, but scale down when necessary.

### Quick Comparison

| Value | Aspect Ratio | Entire Content Visible | Can Crop |
|---|---|---|---|
| `fill` | May distort | Yes | No |
| `contain` | Preserved | Yes | No |
| `cover` | Preserved | Not always | Yes |
| `none` | Preserved | Not always | Content may extend beyond box |
| `scale-down` | Preserved | Depends | May not show all content |

### Visual Comparison

Suppose the content box has a different aspect ratio from the original image:

```text
fill
→ Stretch to fill

contain
→ Fit completely inside

cover
→ Fill completely and crop if necessary

none
→ Keep natural size

scale-down
→ Use the smaller result of none or contain
```

### Choosing a Value

Use:

```text
fill
→ When stretching is acceptable

contain
→ When the entire image must remain visible

cover
→ When the box must be completely filled

none
→ When the content should keep its natural size

scale-down
→ When the content should not become larger than its natural size
  but may be scaled down when necessary
```

### Example

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

Changing only the value changes how the same image is displayed:

```css
object-fit: fill;
```

```css
object-fit: contain;
```

```css
object-fit: cover;
```

```css
object-fit: none;
```

```css
object-fit: scale-down;
```

The `width` and `height` remain the same; only the way the content fits inside the box changes.

### Important Points

```text
object-fit values
│
├── fill
│   └── Fill box, may distort
│
├── contain
│   └── Show entire content, preserve ratio
│
├── cover
│   └── Fill box, preserve ratio, may crop
│
├── none
│   └── Keep natural size
│
└── scale-down
    └── Smaller result of none or contain
```

> 💡 **Remember:** `contain` prioritizes showing the entire content, while `cover` prioritizes filling the entire content box. `fill` can distort the content, `none` keeps its natural size, and `scale-down` chooses the smaller result of `none` and `contain`.

---

## `object-fit: fill`

The `fill` value causes the replaced content to fill the element's content box.

It is the default value of the `object-fit` property.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: fill;
}
```

The image is resized so that it fills the entire `300px × 200px` content box.

### Aspect Ratio

`fill` does not preserve the original aspect ratio of the content.

For example:

```text
Original image
800 × 600
4:3

Content box
300 × 200
3:2

object-fit: fill
        ↓
Image fills the entire box
        ↓
Original aspect ratio may change
```

The image can therefore appear stretched or compressed.

### Example With a Wide Image

Suppose the original image is:

```text
800 × 400
2:1
```

and the content box is:

```text
300 × 300
1:1
```

With:

```css
img {
    width: 300px;
    height: 300px;
    object-fit: fill;
}
```

the image is stretched to fill the square.

The result can look distorted because the original `2:1` aspect ratio is not preserved.

### Example With a Tall Image

Suppose the original image is:

```text
400 × 800
1:2
```

and the content box is:

```text
300 × 200
3:2
```

With:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: fill;
}
```

the image is resized to exactly match the content box.

Again, the aspect ratio can be distorted.

### `fill` vs `contain`

Compare:

```css
img {
    object-fit: fill;
}
```

with:

```css
img {
    object-fit: contain;
}
```

`fill`:

```text
Content fills the entire box
        ↓
Aspect ratio may change
        ↓
Possible distortion
```

`contain`:

```text
Content fits inside the box
        ↓
Aspect ratio preserved
        ↓
Empty space may remain
```

### `fill` vs `cover`

Compare:

```css
img {
    object-fit: fill;
}
```

with:

```css
img {
    object-fit: cover;
}
```

`fill`:

```text
Fills the box
+
May distort
```

`cover`:

```text
Fills the box
+
Preserves aspect ratio
+
May crop content
```

### When Is `fill` Useful?

`fill` can be useful when:

- Distortion is acceptable.
- The content needs to fill the exact dimensions.
- The original aspect ratio is not important.
- The content is designed to stretch.

For photographs and other images where proportions matter, `contain` or `cover` is often more appropriate.

### Important Points

```text
object-fit: fill
│
├── Default object-fit value
│
├── Fills the entire content box
│
├── Does not preserve aspect ratio
│
├── Can stretch or compress content
│
└── Does not crop content just to preserve
    the original aspect ratio
```

> 💡 **Remember:** `object-fit: fill` makes the replaced content fill the entire content box, but it can distort the content because the original aspect ratio is not preserved.