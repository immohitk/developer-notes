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

---

## `object-fit: contain`

The `contain` value scales the replaced content to fit completely inside its content box while preserving its original aspect ratio.

This means the entire image or video remains visible.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: contain;
}
```

The image is scaled so that it fits completely inside the `300px × 200px` content box.

### Preserving the Aspect Ratio

Unlike `fill`, `contain` preserves the original aspect ratio.

For example:

```text
Original image
800 × 600
4:3

Content box
300 × 200
3:2

object-fit: contain
        ↓
Image is scaled proportionally
        ↓
Entire image remains visible
```

Because the aspect ratios are different, some empty space can remain inside the content box.

### Empty Space

Consider a wide content box:

```text
┌──────────────────────────┐
│                          │
│      ┌────────────┐      │
│      │   Image    │      │
│      └────────────┘      │
│                          │
└──────────────────────────┘
```

The empty areas are a result of preserving the image's aspect ratio while fitting the entire image inside the content box.

### `contain` vs `fill`

With:

```css
img {
    object-fit: fill;
}
```

the content fills the entire box, but its aspect ratio may be distorted.

With:

```css
img {
    object-fit: contain;
}
```

the entire content remains visible and the aspect ratio is preserved.

```text
fill
→ Fill the entire box
→ May distort

contain
→ Fit inside the box
→ Preserve aspect ratio
→ May leave empty space
```

### `contain` vs `cover`

These two values are commonly compared.

```css
img {
    object-fit: contain;
}
```

```text
Entire image visible
+
Aspect ratio preserved
+
Possible empty space
```

While:

```css
img {
    object-fit: cover;
}
```

```text
Entire box filled
+
Aspect ratio preserved
+
Possible cropping
```

### Product Images

`contain` is useful for product images when the entire product needs to remain visible.

```css
.product-image {
    width: 300px;
    height: 300px;
    object-fit: contain;
}
```

Different products can have different shapes while remaining completely visible inside the same square area.

### Logos

`contain` is also useful for logos:

```css
.logo {
    width: 200px;
    height: 100px;
    object-fit: contain;
}
```

The logo remains completely visible without being stretched or cropped.

### Profile Images

For profile images where the entire image should remain visible:

```css
.profile-image {
    width: 200px;
    height: 200px;
    object-fit: contain;
}
```

However, `cover` is often preferred for profile pictures when the image needs to completely fill a square or circular area.

### Videos

`object-fit: contain` can also be used with videos:

```css
.video {
    width: 600px;
    height: 400px;
    object-fit: contain;
}
```

The complete video content remains visible while preserving its aspect ratio.

### When to Use `contain`

Use `contain` when:

- The entire image must remain visible.
- The original aspect ratio must be preserved.
- Cropping is not acceptable.
- Some empty space is acceptable.
- Product images need consistent containers.
- Logos need to remain completely visible.
- Media should fit inside a fixed-size area without distortion.

### Important Points

```text
object-fit: contain
│
├── Preserves aspect ratio
│
├── Keeps the entire content visible
│
├── Fits content inside the content box
│
├── May leave empty space
│
└── Does not distort the original content
```

> 💡 **Remember:** `object-fit: contain` prioritizes keeping the **entire content visible** while preserving its aspect ratio. If the content and content box have different aspect ratios, some empty space may remain.

---

## `object-fit: cover`

The `cover` value scales the replaced content while preserving its original aspect ratio so that it completely fills the element's content box.

Because the aspect ratios of the content and content box may be different, some parts of the content can be cropped.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

The image fills the entire `300px × 200px` content box while maintaining its original proportions.

### Preserving the Aspect Ratio

Unlike `fill`, `cover` preserves the original aspect ratio.

For example:

```text
Original image
800 × 600
4:3

Content box
300 × 200
3:2

object-fit: cover
        ↓
Image is scaled proportionally
        ↓
Content fills the entire box
        ↓
Some parts may be cropped
```

### Why Does Cropping Happen?

To completely fill the content box while preserving the aspect ratio, the image may need to become larger than one dimension of the box.

The excess content is then outside the visible area of the content box.

For example:

```text
Content box
┌──────────────────────┐
│  ┌────────────────┐  │
│  │      Image     │  │
│  │   ──────────   │  │
│  └────────────────┘  │
└──────────────────────┘
       ↑
   Some content
   may be cropped
```

### `cover` vs `contain`

These values have opposite priorities.

#### `contain`

```css
img {
    object-fit: contain;
}
```

```text
Entire content
      ↓
Must remain visible
      ↓
Aspect ratio preserved
      ↓
Empty space may remain
```

#### `cover`

```css
img {
    object-fit: cover;
}
```

```text
Entire content box
      ↓
Must be filled
      ↓
Aspect ratio preserved
      ↓
Content may be cropped
```

### Image Cards

`cover` is commonly used for cards with fixed image areas.

```css
.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

Different source images can then appear in the same-sized visual area.

### Profile Pictures

For a square profile image:

```css
.profile-image {
    width: 150px;
    height: 150px;
    object-fit: cover;
}
```

The image fills the square while preserving its aspect ratio.

If the source image is not square, some content is cropped.

### Circular Profile Pictures

`cover` works well with circular images:

```css
.profile-image {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
}
```

The image fills the circular area without being stretched.

### Product Cards

```css
.product-image {
    width: 100%;
    height: 250px;
    object-fit: cover;
}
```

This creates a consistent image area across different products.

However, if the entire product must remain visible, `contain` may be more appropriate.

### Hero Images

`cover` can be useful for large visual areas:

```css
.hero img {
    width: 100%;
    height: 400px;
    object-fit: cover;
}
```

The image fills the hero area while maintaining its aspect ratio.

Some parts of the image may be cropped.

### Videos

`object-fit: cover` can also be applied to videos:

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: cover;
}
```

The video fills the specified area while maintaining its aspect ratio.

Some video content may be cropped.

### `cover` Does Not Distort the Content

With:

```css
img {
    object-fit: cover;
}
```

the image's aspect ratio is preserved.

The image is not stretched disproportionately just to match the content box.

Instead:

```text
Aspect ratio
→ Preserved

Content box
→ Completely filled

Excess content
→ May be cropped
```

### When to Use `cover`

Use `cover` when:

- The content box must be completely filled.
- The original aspect ratio should be preserved.
- Some cropping is acceptable.
- Images need consistent dimensions.
- Profile images should fill a fixed shape.
- Gallery thumbnails should have uniform sizes.
- Hero images should cover a defined area.

### When Not to Use `cover`

Avoid `cover` when the entire image must remain visible.

For example, product images or logos may need:

```css
object-fit: contain;
```

instead.

### Important Points

```text
object-fit: cover
│
├── Preserves aspect ratio
│
├── Completely fills the content box
│
├── May crop parts of the content
│
├── Does not distort the content
│
└── Commonly used for
    ├── Profile images
    ├── Image cards
    ├── Gallery thumbnails
    └── Hero images
```

> 💡 **Remember:** `object-fit: cover` prioritizes **filling the entire content box** while preserving the aspect ratio. If the aspect ratios differ, some parts of the image or video may be cropped.


---

## `object-fit: none`

The `none` value prevents the replaced content from being resized to fit the content box.

The content keeps its natural or intrinsic size instead of being scaled to match the dimensions of the element.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: none;
}
```

Here, the image element has a `300px × 200px` content box, but the image content itself is not resized to fit that box.

### Natural Size

Suppose the original image is:

```text
800 × 600
```

and the content box is:

```text
300 × 200
```

With:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: none;
}
```

the image is not scaled down to `300px × 200px`.

Instead, it remains at its natural size.

```text
Original image
800 × 600
        ↓
object-fit: none
        ↓
No resizing
        ↓
Content box
300 × 200
```

### Content Larger Than the Box

When the natural content is larger than the content box, parts of the content may extend beyond the visible area.

For example:

```text
Content box
┌────────────────────┐
│                    │
│    ┌───────────────┼────────
│    │    Image      │
│    │               │
└────┴───────────────┘
         ↑
   Image is larger
   than the box
```

The content is not scaled simply to make it fit.

### Content Smaller Than the Box

If the natural content is already smaller than the content box, `none` keeps it at its natural size.

For example:

```text
Content box
┌────────────────────────────┐
│                            │
│      ┌──────────────┐      │
│      │    Image     │      │
│      └──────────────┘      │
│                            │
└────────────────────────────┘
```

The image does not automatically expand to fill the content box.

### `none` vs `contain`

Compare:

```css
img {
    object-fit: none;
}
```

with:

```css
img {
    object-fit: contain;
}
```

`none`:

```text
Keep natural size
→ Do not resize the content
```

`contain`:

```text
Scale content when necessary
→ Preserve aspect ratio
→ Keep entire content visible
```

### `none` vs `cover`

With:

```css
img {
    object-fit: cover;
}
```

the content is scaled until it completely covers the content box.

With:

```css
img {
    object-fit: none;
}
```

the content is not resized to fit the box.

```text
cover
→ Scale content
→ Fill box
→ May crop

none
→ Do not resize content
→ Natural size
```

### `none` and `object-position`

`object-position` can be used with `object-fit: none` to control where the content is positioned inside the content box.

For example:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: none;
    object-position: center;
}
```

The image remains at its natural size while its position inside the content box is controlled by `object-position`.

### When Is `none` Useful?

`none` can be useful when:

- The natural size of the content should be preserved.
- The content should not be automatically scaled.
- You need to display media at its intrinsic size inside a defined element.
- You want to combine natural sizing with `object-position`.

It is less common than `contain` and `cover` for typical responsive image layouts.

### Important Points

```text
object-fit: none
│
├── Does not resize the content
│
├── Keeps the content at its natural size
│
├── Does not force the content to fill the box
│
├── Content may be larger or smaller
│   than the content box
│
└── Can be combined with object-position
```

> 💡 **Remember:** `object-fit: none` keeps the replaced content at its natural size instead of resizing it to fit the content box. If the content is larger than the box, some of it may not be visible.

---

## `object-fit: scale-down`

The `scale-down` value displays the replaced content using the smaller rendered size between `none` and `contain`.

In other words, the browser compares how the content would appear with:

```css
object-fit: none;
```

and:

```css
object-fit: contain;
```

and uses the smaller result.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: scale-down;
}
```

The image will not be enlarged beyond its natural size.

If the image is too large for the content box, it can be scaled down to fit.

### How `scale-down` Works

Conceptually:

```text
scale-down
    ↓
Compare none and contain
    ↓
Choose the smaller rendered result
```

It behaves like:

```text
smaller of:
    none
    contain
```

### Large Image

Suppose the original image is:

```text
800 × 600
```

and the content box is:

```text
300 × 200
```

With:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: scale-down;
}
```

The image is too large to fit naturally.

Therefore, the `contain` result is smaller than the `none` result.

The image is scaled down while preserving its aspect ratio.

```text
Original
800 × 600
        ↓
Too large for box
        ↓
scale-down
        ↓
Use contain-like scaled size
```

### Small Image

Suppose the original image is:

```text
100 × 80
```

and the content box is:

```text
300 × 200
```

The image already fits inside the content box.

With:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: scale-down;
}
```

the image remains at its natural size instead of being enlarged to fill the box.

```text
Original
100 × 80
        ↓
Already fits
        ↓
scale-down
        ↓
Keep natural size
```

### `scale-down` vs `contain`

Consider a small image:

```text
Image
100 × 80

Content box
300 × 200
```

With:

```css
object-fit: contain;
```

the image can be scaled up to fit the available content box while preserving its aspect ratio.

With:

```css
object-fit: scale-down;
```

the image remains at its natural size because enlarging it would produce a larger result.

```text
contain
→ May enlarge

scale-down
→ Does not enlarge beyond natural size
```

### `scale-down` vs `none`

`none` always keeps the replaced content at its natural size.

```css
img {
    object-fit: none;
}
```

`scale-down` keeps the natural size when it fits, but can scale the content down when necessary.

```text
none
→ Never scale

scale-down
→ Keep natural size when possible
→ Scale down when necessary
```

### Preserving Aspect Ratio

When `scale-down` uses the `contain` behavior, the content is scaled proportionally.

The original aspect ratio is preserved.

```text
Original aspect ratio
        ↓
Preserved
        ↓
Content is scaled only when necessary
```

### Common Use Cases

`scale-down` can be useful when:

- Images should not be enlarged unnecessarily.
- Small images should remain at their natural size.
- Large images should fit inside a fixed content box.
- The original aspect ratio should be preserved.
- Media should adapt to a container without unnecessary upscaling.

### Example With a Product Image

```css
.product-image {
    width: 300px;
    height: 250px;
    object-fit: scale-down;
}
```

A large product image can be reduced to fit the box, while a smaller product image can remain at its natural size.

### Comparison

| Value | Enlarges Small Content | Scales Down Large Content | Preserves Aspect Ratio |
|---|---|---|---|
| `none` | No | No | Yes |
| `contain` | Yes | Yes | Yes |
| `scale-down` | No | Yes | Yes |

### Important Points

```text
object-fit: scale-down
│
├── Compares none and contain
│
├── Uses the smaller rendered result
│
├── Does not unnecessarily enlarge content
│
├── Can scale large content down
│
└── Preserves the aspect ratio
```

> 💡 **Remember:** `scale-down` is useful when you want content to remain at its natural size when it already fits, but scale down when the content is too large for its content box.

---

## Object Fit With Images

The `object-fit` property is most commonly used with images to control how an image fits inside a defined content box.

This is especially useful when images have different dimensions but need to appear in a consistent layout.

### Basic Example

```html
<img
    class="image"
    src="image.jpg"
    alt="Example image"
>
```

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

The image fills the `300px × 200px` content box while preserving its aspect ratio.

### Why Use `object-fit` With Images?

Different images can have different dimensions.

For example:

```text
Image 1
800 × 600

Image 2
1200 × 800

Image 3
600 × 900
```

If all three images are placed inside the same fixed-size card:

```text
300px × 200px
```

they may not naturally fit the same way.

Using `object-fit` provides consistent control over how each image is displayed.

### Image Cards

A common pattern is:

```css
.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

This allows images with different aspect ratios to occupy the same visual area.

```text
Different source images
        ↓
Same image dimensions
        ↓
object-fit: cover
        ↓
Consistent cards
```

### Profile Images

`object-fit` can be used to create consistent profile pictures.

```css
.profile-image {
    width: 150px;
    height: 150px;
    object-fit: cover;
    border-radius: 50%;
}
```

The image fills the square area and is clipped into a circle by `border-radius`.

If the source image is not square, some parts may be cropped.

### Product Images

For product images, `contain` is often useful when the complete product should remain visible.

```css
.product-image {
    width: 300px;
    height: 300px;
    object-fit: contain;
}
```

This preserves the image's aspect ratio and keeps the entire image visible.

Some empty space may remain around the product.

### Gallery Images

For a gallery with consistent thumbnail sizes:

```css
.gallery img {
    width: 250px;
    height: 180px;
    object-fit: cover;
}
```

Every image gets the same content-box dimensions.

Images with different aspect ratios can still be displayed consistently.

### Responsive Images

`object-fit` can also be combined with responsive dimensions.

```css
.card img {
    width: 100%;
    height: 250px;
    object-fit: cover;
}
```

The width adapts to the card while the height remains controlled.

### Using `aspect-ratio`

`object-fit` can be combined with the `aspect-ratio` property.

```css
.card img {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

This creates a consistent media area while allowing the image to fill it without distortion.

### `object-fit: contain` With Images

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: contain;
}
```

Use this when:

```text
Entire image
    ↓
Must remain visible
    ↓
Aspect ratio preserved
    ↓
Empty space is acceptable
```

### `object-fit: cover` With Images

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

Use this when:

```text
Entire content box
    ↓
Must be filled
    ↓
Aspect ratio preserved
    ↓
Cropping is acceptable
```

### Images With Different Aspect Ratios

Consider three images:

```text
Landscape
800 × 500

Square
600 × 600

Portrait
500 × 800
```

Using:

```css
.gallery img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

allows all three images to occupy the same visual area.

The images maintain their proportions, while portions that do not fit may be cropped.

### Image and `object-position`

`object-fit` can be combined with `object-position` to control which part of the image remains visible.

For example:

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
    object-position: center top;
}
```

This is useful when the important part of an image is not centered.

For example, a portrait image may need:

```css
object-position: center top;
```

so that the upper part of the image remains visible.

### Important Points

```text
object-fit + images
│
├── Creates consistent image areas
│
├── Handles different aspect ratios
│
├── Prevents unwanted distortion
│
├── Commonly used with
│   ├── Cards
│   ├── Galleries
│   ├── Profiles
│   └── Product images
│
└── Can be combined with
    ├── aspect-ratio
    └── object-position
```

> 💡 **Remember:** `object-fit` is especially useful for images when different source dimensions need to fit into consistent layouts. Use `contain` when the entire image must remain visible and `cover` when the image should completely fill the available area.

---

## Object Fit With Videos

The `object-fit` property can also be used with `<video>` elements to control how video content fits inside its content box.

This is useful when the video's aspect ratio is different from the dimensions of the video element.

### Basic Example

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

The video fills the `600px × 350px` content box while preserving its aspect ratio.

### Why Use `object-fit` With Videos?

Videos can have different aspect ratios.

For example:

```text
Original video
1920 × 1080
16:9

Video element
600 × 350
```

The aspect ratios are different.

`object-fit` controls how the video content is fitted inside the available area.

### `object-fit: fill`

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: fill;
}
```

The video content fills the entire content box.

The original aspect ratio may not be preserved, so the video can appear stretched or compressed.

### `object-fit: contain`

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: contain;
}
```

The entire video remains visible while preserving its aspect ratio.

Empty space may appear when the video's aspect ratio does not match the content box.

```text
Video content
      ↓
Entire video remains visible
      ↓
Aspect ratio preserved
      ↓
Possible empty space
```

### `object-fit: cover`

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: cover;
}
```

The video fills the entire content box while preserving its aspect ratio.

If the aspect ratios differ, some parts of the video may be cropped.

This is useful when the video must completely fill a defined visual area.

### `object-fit: none`

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: none;
}
```

The video content is not resized to fit the content box.

The content remains at its natural size.

If it is larger than the content box, some parts may not be visible.

### `object-fit: scale-down`

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: scale-down;
}
```

The browser uses the smaller rendered result between `none` and `contain`.

The video is not unnecessarily enlarged, but it can be scaled down when required.

### Video Aspect Ratio

Consider a video:

```text
Original video
16:9
```

and a video element:

```text
600 × 350
```

Different `object-fit` values produce different results:

```text
fill
→ Fill the box
→ May distort

contain
→ Show the entire video
→ May leave empty space

cover
→ Fill the entire box
→ May crop

none
→ Keep natural size

scale-down
→ Keep natural size when possible
→ Scale down when necessary
```

### Responsive Video

`object-fit` can be combined with responsive dimensions.

```css
.video {
    width: 100%;
    height: 400px;
    object-fit: cover;
}
```

The video can adapt to the width of its container while the height remains controlled.

### Video Background-Style Layout

A video can be used as a visual background for a section:

```html
<section class="hero">
    <video
        class="hero-video"
        autoplay
        muted
        loop
        playsinline>
        <source src="background.mp4" type="video/mp4">
    </video>

    <div class="hero-content">
        <h1>Welcome</h1>
    </div>
</section>
```

```css
.hero {
    position: relative;
    width: 100%;
    height: 500px;
    overflow: hidden;
}

.hero-video {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

Here, `object-fit: cover` makes the video fill the entire hero area while preserving its aspect ratio.

### Video With `object-position`

`object-position` can be combined with `object-fit`.

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: cover;
    object-position: center;
}
```

You can also position the video content differently:

```css
.video {
    object-position: center top;
}
```

This can be useful when an important part of the video should remain visible.

### Important Points

```text
object-fit + video
│
├── Controls how video content fits
│   inside the video element
│
├── Handles different aspect ratios
│
├── Commonly used with
│   ├── Responsive videos
│   ├── Hero sections
│   └── Video cards
│
├── cover can crop video content
│
└── contain keeps the entire video visible
```

> 💡 **Remember:** `object-fit` works with videos in much the same way it works with images. Use `contain` when the entire video must remain visible and `cover` when the video must completely fill its container.

---

## Object Fit and Aspect Ratio

The `object-fit` property is closely related to the aspect ratio of replaced content such as images and videos.

When the aspect ratio of the content is different from the aspect ratio of its content box, `object-fit` determines how the content should be fitted.

### What Is Aspect Ratio?

Aspect ratio describes the relationship between the width and height of an element or piece of content.

For example:

```text
800 × 600
```

has an aspect ratio of:

```text
4:3
```

Similarly:

```text
1920 × 1080
```

has an aspect ratio of:

```text
16:9
```

### Different Aspect Ratios

Suppose an image has:

```text
Original image
800 × 600
4:3
```

and its content box has:

```text
Content box
300 × 200
3:2
```

The aspect ratios are different.

This creates a fitting problem:

```text
Original content
      ↓
Different aspect ratio
      ↓
Content box
      ↓
object-fit determines the result
```

### `object-fit: fill`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: fill;
}
```

The image fills the entire content box.

However, the original aspect ratio is not preserved.

```text
Aspect ratio
→ May change

Result
→ Possible distortion
```

### `object-fit: contain`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: contain;
}
```

The image keeps its original aspect ratio and is scaled so that the entire image fits inside the content box.

```text
Aspect ratio
→ Preserved

Entire image
→ Visible

Empty space
→ May remain
```

### `object-fit: cover`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

The image keeps its original aspect ratio and is scaled until the entire content box is covered.

```text
Aspect ratio
→ Preserved

Content box
→ Completely filled

Extra content
→ May be cropped
```

### `object-fit: none`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: none;
}
```

The image is not resized to fit the content box.

Its natural dimensions are preserved.

```text
Natural size
→ Preserved

Scaling
→ None
```

If the image is larger than the content box, some of the image may not be visible.

### `object-fit: scale-down`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: scale-down;
}
```

The browser chooses the smaller rendered result between `none` and `contain`.

This means:

```text
Small content
→ Keep natural size

Large content
→ Scale down when necessary
```

### Visual Comparison

Suppose:

```text
Original image
4:3

Content box
16:9
```

The different values behave approximately like this:

```text
fill
→ Stretch to match the box

contain
→ Keep entire image visible

cover
→ Fill the box and crop excess

none
→ Keep natural dimensions

scale-down
→ Keep natural dimensions when possible
→ Otherwise scale down
```

### Using `aspect-ratio`

The CSS `aspect-ratio` property can be used to define the preferred aspect ratio of an element.

For example:

```css
.image {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

Here:

```text
width
→ Makes the element responsive

aspect-ratio
→ Defines a 16:9 shape

object-fit
→ Controls how the image fits inside that shape
```

### Example: Responsive Card Image

```css
.card-image {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

This creates a consistent 16:9 image area.

Different source images can still be used while maintaining a consistent card layout.

### Why Aspect Ratio Matters

Without considering aspect ratio, images may:

- Become distorted.
- Leave unwanted empty space.
- Be cropped unexpectedly.
- Have inconsistent dimensions.

Using `object-fit` helps control these results.

### Important Points

```text
Aspect ratio
│
├── Describes width-to-height relationship
│
├── Different content and box ratios
│   can require fitting
│
├── object-fit controls the fitting behavior
│
└── aspect-ratio can help define
    a consistent content-box shape
```

> 💡 **Remember:** When the content and its content box have different aspect ratios, `object-fit` determines whether the content is stretched, contained, covered, kept at its natural size, or scaled down.

---

## Object Fit With Width and Height

The `object-fit` property controls how replaced content such as images and videos fits inside the dimensions defined by properties such as `width` and `height`.

`width` and `height` define the size of the element's content box, while `object-fit` controls how the replaced content is displayed inside that box.

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
→ Defines the element width

height: 200px
→ Defines the element height

object-fit: cover
→ Controls how the image fits inside the box
```

### Width and Height With `fill`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: fill;
}
```

The image is resized to exactly match the specified width and height.

The original aspect ratio may be distorted.

```text
Element
300 × 200
      ↓
Image stretched to
300 × 200
```

### Width and Height With `contain`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: contain;
}
```

The image remains inside the `300px × 200px` box while preserving its aspect ratio.

If the aspect ratios differ, empty space may remain.

```text
┌──────────────────────┐
│                      │
│      ┌────────┐      │
│      │ Image  │      │
│      └────────┘      │
│                      │
└──────────────────────┘
```

### Width and Height With `cover`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

The image fills the entire `300px × 200px` box while preserving its aspect ratio.

Some parts of the image may be cropped.

### Width and Height With `none`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: none;
}
```

The image is not resized to fit the specified dimensions.

The content remains at its natural size.

### Width and Height With `scale-down`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: scale-down;
}
```

The browser uses the smaller rendered result between `none` and `contain`.

This means small content is not unnecessarily enlarged, while large content can be scaled down.

### Percentage Width

`object-fit` can be combined with a percentage width.

```css
img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

The image element takes the available width of its parent while maintaining a fixed height.

```text
Parent width
      ↓
width: 100%
      ↓
Image element expands
      ↓
height: 200px
      ↓
object-fit controls the content
```

### Responsive Width and Fixed Height

A common responsive pattern is:

```css
.card img {
    width: 100%;
    height: 250px;
    object-fit: cover;
}
```

This allows the image width to adapt to the card while maintaining a consistent image height.

### Using `max-width`

You can also combine `object-fit` with `max-width`.

```css
img {
    width: 100%;
    max-width: 500px;
    height: 300px;
    object-fit: contain;
}
```

The image element can grow up to `500px` wide while the content is fitted inside the defined dimensions.

### Width and Height Are Independent From `object-fit`

It is important not to confuse these properties.

```css
img {
    width: 400px;
    height: 250px;
    object-fit: cover;
}
```

The browser first establishes the element's dimensions.

Then `object-fit` determines how the replaced content fits inside those dimensions.

```text
width + height
        ↓
Content box
        ↓
object-fit
        ↓
Content fitting behavior
```

### Using `aspect-ratio`

Instead of explicitly defining both width and height, `aspect-ratio` can be used.

```css
img {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

Here:

```text
width
→ Responsive width

aspect-ratio
→ Determines the height

object-fit
→ Controls how the image fits
```

### Example: Responsive Image Card

```css
.card {
    width: 100%;
    max-width: 400px;
}

.card img {
    width: 100%;
    height: 250px;
    object-fit: cover;
}
```

The card can adapt to different screen sizes while the image remains inside a consistent visual area.

### Important Points

```text
width
│
└── Controls element width

height
│
└── Controls element height

object-fit
│
└── Controls how replaced content
    fits inside those dimensions
```

> 💡 **Remember:** `width` and `height` establish the content box. `object-fit` controls how the image or video content fits inside that box.

---

## Object Fit With Overflow

The `object-fit` property controls how replaced content such as images and videos fits inside its content box.

The `overflow` property controls what happens when content extends beyond the boundaries of an element's box.

These properties can work together when the replaced content is larger than its available area.

### Basic Example

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
    overflow: hidden;
}
```

Here:

```text
width + height
→ Define the image element's box

object-fit
→ Controls how the image content fits

overflow
→ Controls content extending outside the box
```

### `object-fit: cover` and Cropping

Consider:

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

If the source image has a different aspect ratio, `cover` scales the image while preserving its aspect ratio.

Some parts of the image may not be visible because they fall outside the content box.

```text
Original image
      ↓
Scaled proportionally
      ↓
Content box
300 × 200
      ↓
Excess image area
      ↓
Not visible
```

This is part of how `object-fit: cover` achieves its fitting behavior.

### Using `overflow: hidden`

`overflow: hidden` is commonly useful when an image is inside a separate container.

For example:

```html
<div class="image-container">
    <img src="image.jpg" alt="Example">
</div>
```

```css
.image-container {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

The container defines the visible area, while the image is fitted inside it.

### Rounded Image Containers

`overflow: hidden` is especially useful when creating rounded image containers.

```css
.image-container {
    width: 300px;
    height: 200px;
    border-radius: 12px;
    overflow: hidden;
}

.image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

The image is clipped to the rounded shape of the container.

```text
┌──────────────────────┐
│      Image           │
│                      │
│                      │
└──────────────────────┘
       rounded
       corners
```

### `overflow: visible`

The default behavior for `overflow` is generally `visible`.

For example:

```css
.image-container {
    overflow: visible;
}
```

Content that extends outside the box may remain visible.

However, with `object-fit: cover`, the replaced content is fitted to the content box, so the visible result is primarily determined by the fitting behavior and the element's rendering area.

### `overflow: hidden`

```css
.image-container {
    overflow: hidden;
}
```

Content extending outside the container is clipped.

This is useful when the image is inside a wrapper and the wrapper should define the visible boundary.

### `overflow: auto`

```css
.image-container {
    overflow: auto;
}
```

The browser can provide scrollbars when content overflows the container.

This is generally less common for decorative image cards but can be useful for other types of replaced content.

### `overflow: scroll`

```css
.image-container {
    overflow: scroll;
}
```

The container provides scrolling mechanisms for overflowing content.

This is usually not needed for normal image-card layouts.

### `object-fit` vs `overflow`

These properties have different responsibilities.

```text
object-fit
→ Controls how replaced content
  is fitted inside its content box

overflow
→ Controls what happens when content
  extends beyond an element's box
```

They should not be treated as interchangeable.

### Example With `object-fit: none`

Consider:

```css
.image-container {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-container img {
    width: 100%;
    height: 100%;
    object-fit: none;
}
```

With `object-fit: none`, the image content is not resized to fit the content box.

The container's `overflow: hidden` can clip content that extends beyond the container.

### Example With `object-fit: contain`

```css
.image-container {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-container img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
```

The entire image is fitted inside the content box while preserving its aspect ratio.

Because the image is contained within the box, there is normally no need to clip the image itself.

### Common Card Pattern

A common pattern is:

```html
<div class="card">
    <div class="card-image">
        <img src="image.jpg" alt="Example">
    </div>

    <div class="card-content">
        <h2>Card Title</h2>
        <p>Card description.</p>
    </div>
</div>
```

```css
.card-image {
    width: 100%;
    height: 200px;
    overflow: hidden;
}

.card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

This creates a consistent image area and clips the image to the container's boundaries.

### Important Points

```text
object-fit + overflow
│
├── object-fit
│   └── Controls how replaced content fits
│
├── overflow
│   └── Controls content extending outside a box
│
├── overflow: hidden
│   └── Clips overflowing content
│
└── Common combination
    ├── Fixed image container
    ├── overflow: hidden
    └── object-fit: cover
```

> 💡 **Remember:** `object-fit` controls **how an image or video fits**, while `overflow` controls **what happens when content extends beyond a box**. They solve different problems but are often used together in image cards and media containers.

---

## Object Fit With Object Position

The `object-position` property controls the position of replaced content, such as an image or video, inside its content box.

It is commonly used together with `object-fit`, especially when `object-fit: cover` crops part of the content.

### Basic Example

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
    object-position: center;
}
```

Here:

```text
width + height
→ Define the content box

object-fit
→ Controls how the image fits

object-position
→ Controls which part of the image is positioned inside the box
```

### Default Position

The default value of `object-position` is:

```css
object-position: 50% 50%;
```

This means the content is positioned at the center of the content box.

You can also write:

```css
object-position: center;
```

### Why Use `object-position`?

Consider:

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

If the image is cropped, the important part of the image may not remain visible.

For example, if a person's face is near the top of the image, centered cropping may cut off part of the face.

You can adjust the position:

```css
img {
    object-fit: cover;
    object-position: center top;
}
```

This keeps the upper part of the image positioned toward the visible area.

### Position Keywords

Common keyword values include:

```css
object-position: center;
object-position: top;
object-position: bottom;
object-position: left;
object-position: right;
```

You can also combine keywords:

```css
object-position: center top;
object-position: center bottom;
object-position: left center;
object-position: right center;
```

### Using Percentages

`object-position` can use percentages.

```css
img {
    object-fit: cover;
    object-position: 50% 50%;
}
```

Here:

```text
50% horizontal
50% vertical
```

means the content is centered.

Another example:

```css
img {
    object-fit: cover;
    object-position: 50% 0%;
}
```

This positions the content toward the top.

### Using Length Values

Length values can also be used.

```css
img {
    object-fit: cover;
    object-position: 20px 10px;
}
```

The first value controls the horizontal position.

The second value controls the vertical position.

### Horizontal and Vertical Position

The two-value syntax follows this pattern:

```css
object-position: horizontal vertical;
```

For example:

```css
object-position: left top;
```

means:

```text
Horizontal → left
Vertical   → top
```

Another example:

```css
object-position: right bottom;
```

means:

```text
Horizontal → right
Vertical   → bottom
```

### `object-fit: cover` With `object-position`

This is one of the most common combinations:

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
    object-position: center top;
}
```

`object-fit: cover` determines how the image is scaled.

`object-position` determines which part of the scaled image is positioned inside the content box.

```text
object-fit
    ↓
Scale and fit content

object-position
    ↓
Position the fitted content
```

### Profile Image Example

Suppose the subject's face is near the top of the image.

```css
.profile-image {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    object-position: center top;
}
```

This can keep the upper portion of the image visible while the image fills the circular area.

### Product Image Example

For a product positioned toward the center:

```css
.product-image {
    width: 300px;
    height: 250px;
    object-fit: cover;
    object-position: center;
}
```

The image is centered within the content box.

### Focal Point Example

If the important part of an image is toward the right:

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
    object-position: right center;
}
```

This changes the visible portion of the image when cropping occurs.

### With Videos

`object-position` also works with videos.

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: cover;
    object-position: center top;
}
```

This can control which part of the video content remains positioned in the visible area.

### Common Values

| Value | Meaning |
|---|---|
| `center` | Center the content |
| `top` | Position toward the top |
| `bottom` | Position toward the bottom |
| `left` | Position toward the left |
| `right` | Position toward the right |
| `center top` | Center horizontally, top vertically |
| `center bottom` | Center horizontally, bottom vertically |
| `left center` | Left horizontally, center vertically |
| `right center` | Right horizontally, center vertically |

### Important Points

```text
object-position
│
├── Controls the position of replaced content
│
├── Commonly used with object-fit
│
├── Especially useful with object-fit: cover
│
├── Helps control which part remains visible
│   when content is cropped
│
├── Supports keywords
│   ├── center
│   ├── top
│   ├── bottom
│   ├── left
│   └── right
│
└── Supports percentages and length values
```

> 💡 **Remember:** `object-fit` controls **how the content fits**, while `object-position` controls **where the fitted content is positioned** inside the content box.

---

## Practical Examples

The `object-fit` property is especially useful when images and videos need to fit into fixed or responsive layouts without unwanted distortion.

### Example 1: Basic Image Card

```html
<div class="card">
    <img src="image.jpg" alt="Example image">
    <h2>Card Title</h2>
</div>
```

```css
.card {
    width: 300px;
}

.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

The image fills the `200px`-high area while preserving its aspect ratio.

---

### Example 2: Product Image

When the entire product image should remain visible:

```html
<div class="product">
    <img src="product.jpg" alt="Product">
</div>
```

```css
.product {
    width: 300px;
    height: 300px;
}

.product img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}
```

`contain` keeps the complete product visible.

Some empty space may remain around the image.

---

### Example 3: Profile Picture

```html
<img
    class="profile"
    src="profile.jpg"
    alt="Profile"
>
```

```css
.profile {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
}
```

`cover` allows the image to completely fill the circular area while preserving its aspect ratio.

---

### Example 4: Profile Picture With Focal Position

If the important part of the image is near the top:

```css
.profile {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    object-position: center top;
}
```

`object-position` changes which part of the image is positioned inside the visible area.

---

### Example 5: Image Gallery

```html
<div class="gallery">
    <img src="image1.jpg" alt="Gallery image 1">
    <img src="image2.jpg" alt="Gallery image 2">
    <img src="image3.jpg" alt="Gallery image 3">
</div>
```

```css
.gallery {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
}

.gallery img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

Different source images can appear in consistent-sized gallery areas.

---

### Example 6: Responsive Image

```css
.responsive-image {
    width: 100%;
    height: 300px;
    object-fit: cover;
}
```

The image adapts to the available width while maintaining a controlled height.

---

### Example 7: Fixed Aspect Ratio Image

The `aspect-ratio` property can be combined with `object-fit`.

```css
.image {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

This creates a consistent `16:9` image area.

---

### Example 8: Rounded Image Card

```html
<div class="image-card">
    <img src="image.jpg" alt="Example">
</div>
```

```css
.image-card {
    width: 300px;
    height: 200px;
    border-radius: 16px;
    overflow: hidden;
}

.image-card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

`overflow: hidden` clips the image to the rounded container.

---

### Example 9: Hero Image

```html
<section class="hero">
    <img src="hero.jpg" alt="Hero image">
</section>
```

```css
.hero {
    width: 100%;
    height: 500px;
}

.hero img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

The image fills the entire hero area while maintaining its aspect ratio.

---

### Example 10: Hero Image With Positioning

If the important content is near the top:

```css
.hero img {
    width: 100%;
    height: 500px;
    object-fit: cover;
    object-position: center top;
}
```

This can keep the upper part of the image visible when cropping occurs.

---

### Example 11: Video Container

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
    object-fit: contain;
}
```

The complete video remains visible while preserving its aspect ratio.

---

### Example 12: Full-Cover Video

```css
.video {
    width: 600px;
    height: 350px;
    object-fit: cover;
}
```

The video fills the entire content box.

Some parts may be cropped when the aspect ratios differ.

---

### Example 13: Background-Style Video

```html
<section class="hero">
    <video
        class="hero-video"
        autoplay
        muted
        loop
        playsinline>
        <source src="background.mp4" type="video/mp4">
    </video>

    <div class="hero-content">
        <h1>Welcome</h1>
    </div>
</section>
```

```css
.hero {
    position: relative;
    width: 100%;
    height: 500px;
    overflow: hidden;
}

.hero-video {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.hero-content {
    position: absolute;
    inset: 0;
    display: grid;
    place-items: center;
}
```

Here, `object-fit: cover` allows the video to fill the entire hero section.

---

### Example 14: Choosing Between `contain` and `cover`

Suppose an image is used inside a product card.

Use:

```css
.product img {
    object-fit: contain;
}
```

when:

```text
The complete product
must remain visible.
```

Use:

```css
.product img {
    object-fit: cover;
}
```

when:

```text
The image area must be completely filled
and some cropping is acceptable.
```

---

### Example 15: Different Image Sizes, Same Layout

Suppose three source images have different dimensions:

```text
Image 1 → 800 × 600
Image 2 → 1200 × 800
Image 3 → 600 × 900
```

A consistent card layout can use:

```css
.card img {
    width: 100%;
    height: 220px;
    object-fit: cover;
}
```

The images will occupy the same visual area while maintaining their aspect ratios.

---

### Example 16: Image With a Custom Focal Point

```css
.image {
    width: 300px;
    height: 200px;
    object-fit: cover;
    object-position: 70% 30%;
}
```

Here:

```text
70%
→ Horizontal position

30%
→ Vertical position
```

This is useful when the important subject of an image is not centered.

---

### Example 17: Complete Media Card

```html
<article class="media-card">
    <div class="media-card-image">
        <img src="image.jpg" alt="Example">
    </div>

    <div class="media-card-content">
        <h2>Media Card</h2>
        <p>A simple card using object-fit.</p>
    </div>
</article>
```

```css
.media-card {
    width: 320px;
    border-radius: 12px;
    overflow: hidden;
}

.media-card-image {
    width: 100%;
    height: 200px;
}

.media-card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.media-card-content {
    padding: 16px;
}
```

This pattern combines:

```text
width
height
object-fit
overflow
border-radius
```

to create a consistent media card.

---

### Example 18: Comparing All Main Values

```css
.fill {
    object-fit: fill;
}

.contain {
    object-fit: contain;
}

.cover {
    object-fit: cover;
}

.none {
    object-fit: none;
}

.scale-down {
    object-fit: scale-down;
}
```

The same content can be displayed differently depending on the selected value.

```text
fill
→ Fill the box, possibly distort

contain
→ Show everything, preserve ratio

cover
→ Fill the box, preserve ratio, may crop

none
→ Keep natural size

scale-down
→ Use the smaller result of none or contain
```

### Practical Selection Guide

```text
Need the entire image visible?
→ contain

Need the entire box filled?
→ cover

Don't care about preserving aspect ratio?
→ fill

Need natural content size?
→ none

Need natural size when possible,
but scale down when necessary?
→ scale-down
```

> 💡 **Remember:** In real-world layouts, `object-fit: cover` is commonly used for consistent image areas, while `object-fit: contain` is useful when the complete image must remain visible. Combine `object-position` with `cover` when you need control over the visible focal area.

---

## Key Takeaways

The CSS `object-fit` property controls how replaced content such as images and videos fits inside its content box.

### Main Concepts

- `object-fit` controls how replaced content is resized and fitted inside its content box.
- It is commonly used with `<img>` and `<video>` elements.
- The `width` and `height` define the element's content box.
- `object-fit` controls how the content fits inside that box.
- The original aspect ratio is important when choosing an `object-fit` value.

### `object-fit` Values

| Value | Main Behavior |
|---|---|
| `fill` | Fills the box and may distort the content |
| `contain` | Keeps the entire content visible and preserves its aspect ratio |
| `cover` | Fills the entire box and preserves the aspect ratio, but may crop |
| `none` | Keeps the content at its natural size |
| `scale-down` | Uses the smaller result of `none` and `contain` |

### `fill`

```css
img {
    object-fit: fill;
}
```

- Fills the entire content box.
- Does not preserve the original aspect ratio.
- Can stretch or compress the content.
- Is the default value.

### `contain`

```css
img {
    object-fit: contain;
}
```

- Preserves the aspect ratio.
- Keeps the entire content visible.
- May leave empty space inside the content box.
- Useful for product images and logos.

### `cover`

```css
img {
    object-fit: cover;
}
```

- Preserves the aspect ratio.
- Completely fills the content box.
- May crop parts of the content.
- Commonly used for cards, galleries, profile images, and hero sections.

### `none`

```css
img {
    object-fit: none;
}
```

- Does not resize the content.
- Keeps the content at its natural size.
- Content may be larger or smaller than the content box.

### `scale-down`

```css
img {
    object-fit: scale-down;
}
```

- Compares the results of `none` and `contain`.
- Uses the smaller rendered result.
- Does not unnecessarily enlarge small content.
- Can scale large content down when required.

### `object-position`

`object-position` controls where the fitted content is positioned inside its content box.

For example:

```css
img {
    object-fit: cover;
    object-position: center top;
}
```

This is especially useful when `cover` crops an image and you want to control which part remains visible.

### `object-fit` and `overflow`

These properties have different purposes:

```text
object-fit
→ Controls how replaced content fits

overflow
→ Controls what happens when content extends
  outside an element's box
```

They can be used together for media containers.

### `object-fit` and Aspect Ratio

When the content and content box have different aspect ratios:

```text
Different aspect ratios
        ↓
object-fit
        ↓
Determines how content is fitted
```

The result depends on the selected value.

### Practical Selection Guide

```text
Need the entire image visible?
→ object-fit: contain;

Need the entire box filled?
→ object-fit: cover;

Stretching is acceptable?
→ object-fit: fill;

Need natural content size?
→ object-fit: none;

Need natural size when possible,
but scale down when necessary?
→ object-fit: scale-down;
```

### Most Important Rule

Remember this distinction:

```text
width + height
        ↓
Define the content box

object-fit
        ↓
Controls how the replaced content
fits inside the box

object-position
        ↓
Controls where the fitted content
is positioned
```

> 💡 **Remember:** `object-fit` is mainly about **how content fits**, while `object-position` is about **where that content is positioned** inside the box.

---

## References

The following resources can be used to learn more about CSS `object-fit`, `object-position`, and related image and video behavior.

### MDN Web Docs

- [MDN — object-fit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
- [MDN — object-position](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position)
- [MDN — `<img>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img)
- [MDN — `<video>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/video)

### CSS Specifications

- [CSS Images Module Level 4 — Object Sizing](https://drafts.csswg.org/css-images-4/#the-object-fit)
- [CSS Images Module Level 4 — Object Position](https://drafts.csswg.org/css-images-4/#the-object-position)

### W3Schools

- [W3Schools — CSS object-fit](https://www.w3schools.com/css/css3_object-fit.asp)
- [W3Schools — CSS object-position](https://www.w3schools.com/css/css3_object-position.asp)

> 💡 **Tip:** MDN and the official CSS specifications are the preferred references for understanding the exact behavior and syntax of CSS properties.

---

## Quick Revision

### What Is `object-fit`?

`object-fit` controls how replaced content such as images and videos fits inside its content box.

### Syntax

```css
img {
    object-fit: value;
}
```

### Main Values

```text
fill
contain
cover
none
scale-down
```

### `fill`

```css
object-fit: fill;
```

- Fills the entire content box.
- May distort the original aspect ratio.
- Default value.

### `contain`

```css
object-fit: contain;
```

- Preserves the aspect ratio.
- Keeps the entire content visible.
- May leave empty space.

### `cover`

```css
object-fit: cover;
```

- Preserves the aspect ratio.
- Completely fills the content box.
- May crop part of the content.

### `none`

```css
object-fit: none;
```

- Keeps the content at its natural size.
- Does not resize the content to fit the box.

### `scale-down`

```css
object-fit: scale-down;
```

- Uses the smaller rendered result of `none` and `contain`.
- Does not unnecessarily enlarge content.
- Can scale large content down.

### `object-position`

`object-position` controls where the fitted content is positioned inside its content box.

```css
img {
    object-fit: cover;
    object-position: center top;
}
```

### `object-fit` vs `object-position`

```text
object-fit
→ How the content fits

object-position
→ Where the content is positioned
```

### `object-fit` vs `overflow`

```text
object-fit
→ Controls how replaced content fits

overflow
→ Controls what happens when content
  extends outside an element's box
```

### Width and Height

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
}
```

```text
width
→ Defines element width

height
→ Defines element height

object-fit
→ Controls content fitting
```

### Aspect Ratio

When the content and content box have different aspect ratios:

```text
Different aspect ratios
        ↓
object-fit
        ↓
Determines the fitting behavior
```

### Quick Selection Guide

```text
Entire image must be visible
→ contain

Entire box must be filled
→ cover

Distortion is acceptable
→ fill

Keep natural size
→ none

Keep natural size when possible,
scale down when necessary
→ scale-down
```

### Common Use Cases

```text
object-fit
│
├── Profile images
├── Product images
├── Image galleries
├── Card thumbnails
├── Hero images
├── Responsive images
└── Videos
```

### One-Line Summary

> `object-fit` controls how an image or video fits inside its content box, while `object-position` controls where that content is positioned.

---

## Best Practices

Following good practices when using `object-fit` makes image and video layouts more consistent, responsive, and easier to maintain.

### 1. Choose the Value Based on the Requirement

Do not use the same `object-fit` value for every situation.

Use:

```css
object-fit: contain;
```

when the entire content must remain visible.

Use:

```css
object-fit: cover;
```

when the content box must be completely filled.

Use:

```css
object-fit: fill;
```

only when changing the original aspect ratio is acceptable.

### 2. Avoid Unnecessary Distortion

For most photographs and videos, preserving the original aspect ratio is important.

Avoid:

```css
object-fit: fill;
```

when distortion would make the content look incorrect.

Prefer:

```css
object-fit: contain;
```

or:

```css
object-fit: cover;
```

depending on the design requirement.

### 3. Define the Content Box Clearly

`object-fit` works inside the element's content box.

For example:

```css
.card-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

Clearly defined dimensions make the fitting behavior predictable.

### 4. Use `cover` for Consistent Image Areas

When multiple images need the same visual dimensions:

```css
.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

This is useful for:

- Card images
- Gallery thumbnails
- Blog images
- Profile images
- Hero images

### 5. Use `contain` When Content Must Stay Visible

For logos, product images, and other content where cropping is undesirable:

```css
.product img {
    width: 300px;
    height: 300px;
    object-fit: contain;
}
```

This keeps the entire image visible.

### 6. Use `object-position` When Cropping Matters

If `cover` crops an important part of an image, adjust its position.

```css
.profile img {
    width: 150px;
    height: 150px;
    object-fit: cover;
    object-position: center top;
}
```

This is useful when the subject is not centered.

### 7. Use `aspect-ratio` for Consistent Media Shapes

Instead of manually setting both dimensions, you can use `aspect-ratio`.

```css
.card img {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

This helps create consistent responsive media areas.

### 8. Use `overflow: hidden` When a Container Defines the Visible Area

For a dedicated image container:

```css
.image-container {
    overflow: hidden;
    border-radius: 12px;
}

.image-container img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

This is particularly useful when the image needs to follow the shape of its container.

### 9. Keep Image Layouts Responsive

Avoid unnecessarily hard-coded widths when a responsive layout is required.

For example:

```css
.image {
    width: 100%;
    height: 250px;
    object-fit: cover;
}
```

The image can adapt to the width of its parent while maintaining a controlled height.

### 10. Consider the Purpose of the Image

Different images have different requirements.

```text
Product image
→ contain

Profile image
→ cover

Gallery thumbnail
→ cover

Logo
→ contain

Hero image
→ cover

Decorative image
→ Depends on the design
```

### 11. Do Not Confuse `object-fit` With `background-size`

`object-fit` is used with replaced elements such as:

```html
<img>
<video>
```

For CSS background images, a different property is used:

```css
background-size: cover;
```

These properties solve similar visual problems but are used in different contexts.

### 12. Test Different Aspect Ratios

Do not test an image layout with only one image.

Try:

```text
Landscape image
Square image
Portrait image
Very wide image
Very tall image
```

This helps identify unexpected cropping or empty space.

### 13. Test Different Screen Sizes

Responsive layouts should be tested at different viewport sizes.

Check:

```text
Desktop
Tablet
Mobile
```

Make sure the media remains visually appropriate at each size.

### 14. Use Meaningful `alt` Text for Images

`object-fit` does not replace accessibility practices.

For meaningful images, provide useful alternative text:

```html
<img
    src="product.jpg"
    alt="Black running shoes">
```

For purely decorative images, an empty `alt` attribute may be appropriate:

```html
<img
    src="decoration.jpg"
    alt="">
```

### 15. Keep the CSS Simple

Avoid unnecessary combinations of properties.

For example, a simple card image may only need:

```css
.card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

Add `object-position`, `overflow`, or other properties only when the design requires them.

### Best Practice Summary

```text
object-fit best practices
│
├── Choose the value based on the design
│
├── Preserve aspect ratio when appropriate
│
├── Use cover for consistent filled areas
│
├── Use contain when the entire content matters
│
├── Use object-position for important focal areas
│
├── Use aspect-ratio for consistent responsive shapes
│
├── Test different image dimensions
│
├── Test different screen sizes
│
└── Keep accessibility in mind
```

> 💡 **Remember:** Good `object-fit` usage starts with deciding what matters most: keeping the entire content visible, completely filling the available area, or preserving the content's natural size.