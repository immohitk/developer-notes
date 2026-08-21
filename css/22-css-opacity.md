## Table of Contents

- [Introduction](#introduction)
- [What Is Opacity?](#what-is-opacity)
- [`opacity`](#opacity)
- [Opacity Values](#opacity-values)
- [Fully Opaque Elements](#fully-opaque-elements)
- [Transparent Elements](#transparent-elements)
- [Partially Transparent Elements](#partially-transparent-elements)
- [Opacity and Child Elements](#opacity-and-child-elements)
- [Opacity vs Transparent Colors](#opacity-vs-transparent-colors)
- [Opacity With Images](#opacity-with-images)
- [Opacity With Hover Effects](#opacity-with-hover-effects)
- [Opacity With Transitions](#opacity-with-transitions)
- [Opacity and Visibility](#opacity-and-visibility)
- [Opacity and User Interaction](#opacity-and-user-interaction)
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

CSS `opacity` controls how transparent an element appears.

It allows an element to be displayed at different levels of transparency, from completely visible to completely transparent.

### Basic Example

```css
.box {
    opacity: 0.5;
}
```

The element becomes partially transparent.

Conceptually:

```text
opacity: 1
    ↓
Fully visible

opacity: 0.5
    ↓
50% visible / partially transparent

opacity: 0
    ↓
Fully transparent
```

### Why Use Opacity?

Opacity is useful for creating visual effects such as:

- Faded elements
- Transparent images
- Disabled-looking components
- Hover effects
- Overlays
- Subtle UI elements
- Smooth fade animations

### Basic Syntax

```css
opacity: value;
```

For example:

```css
.box {
    opacity: 0.7;
}
```

The value controls how much of the element is visible.

### Opacity and Transparency

Higher opacity means the element is more visible.

```text
opacity: 1
██████████
Fully visible

opacity: 0.7
███████░░░
Partially transparent

opacity: 0.3
███░░░░░░░
Mostly transparent

opacity: 0
░░░░░░░░░░
Fully transparent
```

### Opacity Applies to the Entire Element

When `opacity` is applied to an element, it affects the element as a whole.

This includes its rendered contents, such as:

```text
Background
Text
Borders
Images
Child elements
```

For example:

```css
.card {
    opacity: 0.5;
}
```

The card and its contents become partially transparent.

### Opacity Is Different From Removing an Element

Setting:

```css
opacity: 0;
```

makes the element fully transparent, but it does not remove the element from the layout.

The element still occupies its space.

```text
opacity: 0
        ↓
Invisible
        ↓
Still exists
        ↓
Still occupies layout space
```

This is different from:

```css
display: none;
```

which removes the element from the layout.

### Opacity With Hover Effects

Opacity is commonly used with `:hover`.

```css
.button {
    opacity: 1;
}

.button:hover {
    opacity: 0.7;
}
```

When the user moves the pointer over the button, it becomes partially transparent.

### Opacity With Transitions

A transition can make opacity changes smoother.

```css
.button {
    opacity: 1;
    transition: opacity 0.3s;
}

.button:hover {
    opacity: 0.7;
}
```

Instead of changing immediately, the opacity changes gradually.

### Important Points

```text
opacity
│
├── Controls transparency
├── 1 → fully opaque
├── 0 → fully transparent
├── Values between 0 and 1
│   → partially transparent
│
└── Common uses
    ├── Fade effects
    ├── Hover effects
    ├── Images
    ├── Overlays
    └── Transitions
```

> 💡 **Remember:** `opacity` controls how transparent an element appears. `opacity: 1` makes it fully opaque, `opacity: 0` makes it fully transparent, and values between them create partial transparency.

---

## What Is Opacity?

Opacity describes how much of an element is visible versus how much of what is behind the element can be seen through it.

In CSS, opacity is controlled using the `opacity` property.

### Basic Concept

```css
.box {
    opacity: 0.5;
}
```

This makes the entire element partially transparent.

Conceptually:

```text
opacity: 1
    ↓
100% opaque
    ↓
Element is fully visible


opacity: 0.5
    ↓
50% opaque
    ↓
Element is partially transparent


opacity: 0
    ↓
0% opaque
    ↓
Element is fully transparent
```

### Understanding the Scale

The normal range of `opacity` is from `0` to `1`.

```text
0        0.25       0.5       0.75       1
│─────────│──────────│──────────│──────────│
Invisible                         Fully visible
```

Examples:

```css
opacity: 1;
```

The element is completely opaque.

```css
opacity: 0.75;
```

The element is mostly opaque.

```css
opacity: 0.5;
```

The element is partially transparent.

```css
opacity: 0.25;
```

The element is mostly transparent.

```css
opacity: 0;
```

The element is fully transparent.

### Opacity and Background Visibility

Consider:

```css
.box {
    background: black;
    opacity: 0.5;
}
```

The black box becomes partially transparent, allowing the background behind the element to contribute to its appearance.

```text
Behind the element
─────────────────────
       ↓
┌───────────────────┐
│   semi-transparent│
│       box         │
└───────────────────┘
       ↓
Behind content can
contribute visually
```

### Opacity Applies to the Whole Element

When you set:

```css
.card {
    opacity: 0.5;
}
```

the opacity affects the rendered element as a whole.

For example:

```html
<div class="card">
    <h2>Title</h2>
    <p>Description</p>
</div>
```

```css
.card {
    opacity: 0.5;
}
```

The card's:

```text
Background
Border
Text
Images
Child content
```

all appear with the element's transparency applied.

### Opacity Does Not Change Layout Size

Changing opacity does not change the element's dimensions or remove it from the layout.

For example:

```css
.box {
    width: 200px;
    height: 100px;
    opacity: 0;
}
```

The element is invisible, but it still occupies:

```text
200px × 100px
```

in the layout.

### Opacity `0` Is Not the Same as `display: none`

Compare:

```css
.box {
    opacity: 0;
}
```

with:

```css
.box {
    display: none;
}
```

`opacity: 0`:

```text
Invisible
↓
Still exists
↓
Still occupies layout space
```

`display: none`:

```text
Not rendered
↓
Removed from layout
```

These properties therefore have very different purposes.

### Opacity and Hover

Opacity is often used to create visual feedback.

```css
.image {
    opacity: 1;
}

.image:hover {
    opacity: 0.7;
}
```

The image becomes partially transparent when hovered.

### Opacity and Transitions

The change can be animated:

```css
.image {
    opacity: 1;
    transition: opacity 0.3s;
}

.image:hover {
    opacity: 0.7;
}
```

This creates a smooth fade instead of an immediate change.

### Opacity and Images

Opacity can be applied directly to an image:

```css
img {
    opacity: 0.6;
}
```

The entire image becomes partially transparent.

This can be useful for:

```text
Background images
Watermark effects
Hover effects
Decorative images
Disabled-looking images
```

### Opacity and Overlays

Opacity is commonly used with overlays.

```css
.overlay {
    background: black;
    opacity: 0.5;
}
```

A semi-transparent overlay can appear over another element.

For example:

```text
┌────────────────────────────┐
│                            │
│       Background           │
│                            │
│   ┌────────────────────┐   │
│   │ Semi-transparent   │   │
│   │ overlay            │   │
│   └────────────────────┘   │
│                            │
└────────────────────────────┘
```

### Important Distinction

`opacity` controls the transparency of the **entire rendered element**.

If you only want to make a particular color transparent while keeping other parts of the element fully opaque, using a color function with an alpha component can be more appropriate.

For example:

```css
.box {
    background-color: rgb(0 0 0 / 50%);
}
```

Here, the background color is transparent while other parts of the element can remain unaffected.

This differs from:

```css
.box {
    opacity: 0.5;
}
```

which affects the entire element.

### Important Points

```text
Opacity
│
├── Controls transparency
├── 1 → fully opaque
├── 0 → fully transparent
├── Values between 0 and 1
│   → partial transparency
│
├── Does not change layout dimensions
├── opacity: 0 does not remove the element
└── Applies to the entire rendered element
```

> 💡 **Remember:** `opacity` controls the transparency of the entire element. It does not change the element's layout size, and `opacity: 0` makes an element invisible without removing it from the layout.

---

## `opacity`

The `opacity` property controls the transparency of an element.

### Syntax

```css
selector {
    opacity: value;
}
```

Example:

```css
.box {
    opacity: 0.5;
}
```

### Basic Example

```html
<div class="box">
    This element is partially transparent.
</div>
```

```css
.box {
    background-color: black;
    color: white;
    opacity: 0.5;
}
```

The entire element becomes partially transparent.

### Property Value

The `opacity` property accepts a number representing the element's opacity.

Common values are:

```css
opacity: 1;
opacity: 0.75;
opacity: 0.5;
opacity: 0.25;
opacity: 0;
```

Conceptually:

```text
1.00 → Fully opaque
0.75 → Mostly opaque
0.50 → 50% opaque
0.25 → Mostly transparent
0.00 → Fully transparent
```

### `opacity: 1`

```css
.box {
    opacity: 1;
}
```

The element is fully opaque.

This is the normal fully visible state.

### `opacity: 0.5`

```css
.box {
    opacity: 0.5;
}
```

The element is partially transparent.

Content behind the element can contribute to its visual appearance.

### `opacity: 0`

```css
.box {
    opacity: 0;
}
```

The element becomes completely transparent.

However, it still exists in the document and continues to occupy its layout space.

### Decimal Values

Opacity is commonly written using decimal values between `0` and `1`.

```css
opacity: 0.1;
opacity: 0.2;
opacity: 0.3;
opacity: 0.4;
opacity: 0.5;
opacity: 0.6;
opacity: 0.7;
opacity: 0.8;
opacity: 0.9;
opacity: 1;
```

For example:

```css
.image {
    opacity: 0.7;
}
```

makes the image mostly opaque with some transparency.

### Percentage Values

CSS also supports percentage notation for opacity.

For example:

```css
.box {
    opacity: 50%;
}
```

is equivalent to:

```css
.box {
    opacity: 0.5;
}
```

Similarly:

```css
opacity: 100%;
```

represents full opacity, while:

```css
opacity: 0%;
```

represents complete transparency.

### Values Outside the Typical Range

Opacity is conceptually bounded between fully transparent and fully opaque.

For practical CSS code, use values from:

```text
0 → 1
```

or:

```text
0% → 100%
```

For example:

```css
opacity: 0.5;
```

is preferable to relying on unusual values outside the normal range.

### Applying Opacity to Different Elements

Opacity can be applied to many elements.

#### Text

```css
p {
    opacity: 0.7;
}
```

#### Image

```css
img {
    opacity: 0.6;
}
```

#### Button

```css
button {
    opacity: 0.8;
}
```

#### Card

```css
.card {
    opacity: 0.9;
}
```

### Opacity Applies to the Entire Element

Consider:

```html
<div class="card">
    <h2>Title</h2>
    <p>Description</p>
</div>
```

```css
.card {
    opacity: 0.5;
}
```

The opacity affects the rendered card as a whole:

```text
Card
├── Background
├── Border
├── Heading
├── Paragraph
└── Other child content
```

All of these appear through the element's opacity.

### Opacity vs Background Transparency

Compare:

```css
.card {
    opacity: 0.5;
}
```

with:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
}
```

The first affects the entire element.

The second makes only the background color transparent.

For example:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
    color: white;
}
```

The text can remain fully opaque while the background is semi-transparent.

### Common Hover Pattern

```css
.image {
    opacity: 1;
}

.image:hover {
    opacity: 0.7;
}
```

The image becomes partially transparent when hovered.

A smoother version uses a transition:

```css
.image {
    opacity: 1;
    transition: opacity 0.3s;
}

.image:hover {
    opacity: 0.7;
}
```

### Important Points

```text
opacity
│
├── Controls element transparency
│
├── 1
│   └── Fully opaque
│
├── 0.5
│   └── Partially transparent
│
├── 0
│   └── Fully transparent
│
└── Can be written using
    ├── Decimal values
    └── Percentage values
```

> 💡 **Remember:** `opacity` controls the transparency of the entire element. `opacity: 1` is fully opaque, `opacity: 0` is fully transparent, and values between them create partial transparency.

---

## Opacity Values

The `opacity` property accepts values that determine how opaque or transparent an element appears.

### Basic Syntax

```css
.element {
    opacity: value;
}
```

The commonly used range is:

```text
0 → 1
```

or equivalently:

```text
0% → 100%
```

### Value `1`

```css
opacity: 1;
```

The element is completely opaque.

```text
opacity: 1
██████████
Fully visible
```

### Value `0`

```css
opacity: 0;
```

The element is completely transparent.

```text
opacity: 0
░░░░░░░░░░
Fully transparent
```

The element still exists and occupies its layout space.

### Values Between `0` and `1`

Values between `0` and `1` create partial transparency.

```css
opacity: 0.8;
```

```css
opacity: 0.6;
```

```css
opacity: 0.4;
```

```css
opacity: 0.2;
```

Conceptually:

```text
1.0  → Fully opaque
0.8  → Slightly transparent
0.6  → Partially transparent
0.4  → More transparent
0.2  → Highly transparent
0.0  → Fully transparent
```

### Common Opacity Values

| Value | Approximate appearance |
|---:|---|
| `1` | Fully opaque |
| `0.9` | Very slightly transparent |
| `0.8` | Slightly transparent |
| `0.7` | Mostly opaque |
| `0.5` | Half opaque |
| `0.3` | Mostly transparent |
| `0.1` | Very transparent |
| `0` | Fully transparent |

The actual visual result also depends on the colors and content behind the element.

### Percentage Values

Opacity can also be expressed as a percentage.

```css
opacity: 50%;
```

is equivalent to:

```css
opacity: 0.5;
```

Similarly:

```css
opacity: 100%;
```

is equivalent to:

```css
opacity: 1;
```

and:

```css
opacity: 0%;
```

is equivalent to:

```css
opacity: 0;
```

### Decimal vs Percentage

Both forms can represent the same opacity:

```css
.box {
    opacity: 0.5;
}
```

and:

```css
.box {
    opacity: 50%;
}
```

Both represent 50% opacity.

For consistency, choose the notation that best matches the style of the project.

### Opacity and Visibility

A value of:

```css
opacity: 0;
```

makes the element fully transparent, but it does not remove the element from the document.

For example:

```css
.box {
    width: 200px;
    height: 100px;
    opacity: 0;
}
```

The element remains part of the layout.

This differs from:

```css
display: none;
```

which removes the element from the layout.

### Opacity Does Not Mean Layout Percentage

An important distinction is that:

```css
opacity: 0.5;
```

does **not** mean:

```text
50% width
50% height
50% size
```

It means the element is rendered with 50% opacity.

For example:

```css
.box {
    width: 400px;
    height: 200px;
    opacity: 0.5;
}
```

The element is still:

```text
400px × 200px
```

Only its transparency changes.

### Opacity With Hover

Different values can be used for interactive states.

```css
.button {
    opacity: 1;
}

.button:hover {
    opacity: 0.7;
}
```

The button becomes slightly transparent when hovered.

### Opacity With Transitions

```css
.button {
    opacity: 1;
    transition: opacity 0.3s;
}

.button:hover {
    opacity: 0.7;
}
```

The opacity changes smoothly between the two values.

### Important Points

```text
Opacity Values
│
├── 1 / 100%
│   └── Fully opaque
│
├── Between 0 and 1
│   └── Partially transparent
│
└── 0 / 0%
    └── Fully transparent
```

> 💡 **Remember:** Opacity values control transparency, not size. `1` means fully opaque, `0` means fully transparent, and values between them create partial transparency. Percentage notation can also be used.

---

## Fully Opaque Elements

An element is fully opaque when its `opacity` value is `1`.

At this value, the element is rendered without transparency.

### Basic Example

```css
.box {
    opacity: 1;
}
```

This is equivalent to the normal fully opaque state.

```text
opacity: 1

┌──────────────────────┐
│                      │
│      Fully visible   │
│                      │
└──────────────────────┘
```

### `opacity: 1` Is the Default

For an element that does not have a different opacity applied, the normal opacity is fully opaque.

For example:

```css
.box {
    background-color: blue;
}
```

and:

```css
.box {
    background-color: blue;
    opacity: 1;
}
```

have the same opacity behavior.

Therefore, explicitly writing:

```css
opacity: 1;
```

is usually unnecessary unless you are intentionally setting or resetting the opacity.

### Resetting Opacity

`opacity: 1` can be useful when changing opacity between different states.

For example:

```css
.button {
    opacity: 0.7;
}

.button:hover {
    opacity: 1;
}
```

The button starts partially transparent and becomes fully opaque when hovered.

### Opacity With Transitions

A common pattern is to transition from a partially transparent state to full opacity.

```css
.button {
    opacity: 0.7;
    transition: opacity 0.3s;
}

.button:hover {
    opacity: 1;
}
```

The change happens smoothly.

```text
Normal
opacity: 0.7
      ↓
Partially transparent

Hover
opacity: 1
      ↓
Fully opaque
```

### Fully Opaque Images

An image can be explicitly made fully opaque:

```css
img {
    opacity: 1;
}
```

This is useful when the same image has another state with reduced opacity.

For example:

```css
.gallery-image {
    opacity: 0.6;
}

.gallery-image:hover {
    opacity: 1;
}
```

### Fully Opaque Buttons

```css
.button {
    opacity: 1;
}
```

This makes the button fully opaque.

A hover state can then use a different value:

```css
.button {
    opacity: 1;
    transition: opacity 0.2s;
}

.button:hover {
    opacity: 0.8;
}
```

### Opacity Does Not Affect Size

An opaque element can have any dimensions.

For example:

```css
.box {
    width: 300px;
    height: 150px;
    opacity: 1;
}
```

The element remains:

```text
300px × 150px
```

Opacity controls transparency, not width or height.

### Opacity Does Not Remove an Element

Using:

```css
opacity: 1;
```

obviously keeps the element visible.

More importantly, the opacity property itself does not control whether an element participates in layout.

For example:

```css
.box {
    opacity: 0;
}
```

makes the element transparent but does not remove it from the layout.

Changing it back to:

```css
.box {
    opacity: 1;
}
```

makes the element fully visible again.

### `opacity: 1` in Interactive States

Opacity is often used for different visual states:

```css
.button {
    opacity: 0.6;
}

.button:hover {
    opacity: 1;
}
```

Conceptually:

```text
Normal
──────
60% opacity

Hover
─────
100% opacity
```

### Important Points

```text
opacity: 1
│
├── Fully opaque
├── No transparency from the opacity property
├── Normal default opacity
├── Does not change element dimensions
└── Commonly used for resetting or interactive states
```

> 💡 **Remember:** `opacity: 1` means the element is fully opaque. It is the normal fully visible state and is particularly useful when restoring full opacity after another state has reduced it.

---

## Transparent Elements

An element is transparent when its `opacity` value is less than `1`.

The lower the opacity value, the more transparent the element becomes.

### Basic Example

```css
.box {
    opacity: 0.5;
}
```

The element becomes partially transparent.

```text
opacity: 1
██████████
Fully opaque

opacity: 0.5
█████░░░░░
Partially transparent

opacity: 0
░░░░░░░░░░
Fully transparent
```

### Fully Transparent Element

To make an element fully transparent:

```css
.box {
    opacity: 0;
}
```

The element becomes visually invisible.

However, it still:

- Exists in the document.
- Occupies layout space.
- Can still affect the layout.
- Is not the same as `display: none`.

### `opacity: 0` vs `display: none`

These properties behave differently.

```css
.box {
    opacity: 0;
}
```

The element is:

```text
Invisible
↓
Still in the layout
↓
Still has its dimensions
```

While:

```css
.box {
    display: none;
}
```

means:

```text
Not rendered
↓
Removed from layout
```

### Different Transparency Levels

You can choose different opacity values depending on the desired visual effect.

```css
.box {
    opacity: 0.9;
}
```

Almost fully opaque.

```css
.box {
    opacity: 0.7;
}
```

Slightly transparent.

```css
.box {
    opacity: 0.5;
}
```

Clearly transparent.

```css
.box {
    opacity: 0.3;
}
```

Mostly transparent.

```css
.box {
    opacity: 0.1;
}
```

Very transparent.

```css
.box {
    opacity: 0;
}
```

Fully transparent.

### Transparent Text

Opacity can be applied to text:

```css
.description {
    opacity: 0.7;
}
```

The entire element, including its text and other rendered content, receives the opacity effect.

For text color specifically, a color with an alpha component can be more appropriate when only the text color should become translucent.

For example:

```css
.description {
    color: rgb(0 0 0 / 70%);
}
```

This affects the text color rather than the opacity of the entire element.

### Transparent Images

Opacity can be applied to images:

```css
img {
    opacity: 0.5;
}
```

The image becomes partially transparent.

This can be useful for:

```text
Watermarks
Background images
Decorative images
Hover effects
Faded thumbnails
```

### Transparent Backgrounds

If only the background should be transparent, avoid applying opacity to the whole element when the text should remain fully opaque.

Instead of:

```css
.card {
    opacity: 0.5;
}
```

you can use a background color with an alpha component:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
    color: white;
}
```

Conceptually:

```text
opacity
→ Entire element becomes transparent

background alpha
→ Only the background color becomes transparent
```

### Transparent Overlay

Opacity is commonly used for overlays:

```css
.overlay {
    background-color: black;
    opacity: 0.5;
}
```

This creates a semi-transparent layer through which the content underneath can be seen.

### Hover Effect

A common transparent hover effect is:

```css
.image {
    opacity: 1;
}

.image:hover {
    opacity: 0.6;
}
```

The image becomes partially transparent when hovered.

### Smooth Transparency

Combine opacity with `transition`:

```css
.image {
    opacity: 1;
    transition: opacity 0.3s;
}

.image:hover {
    opacity: 0.6;
}
```

The opacity changes smoothly instead of immediately.

### Important Points

```text
Transparent Elements
│
├── opacity < 1
│   └── Element becomes transparent
│
├── opacity: 0
│   └── Fully transparent
│
├── opacity does not remove the element
│
├── opacity affects the entire element
│
└── For individual colors
    └── Consider alpha colors instead
```

> 💡 **Remember:** `opacity: 0` makes an element completely transparent, but it does not remove the element from the layout. If only a particular color needs transparency, use a color with an alpha component instead of reducing the opacity of the entire element.

---

## Partially Transparent Elements

An element is partially transparent when its `opacity` value is greater than `0` and less than `1`.

Partial transparency allows some of the background behind an element to contribute to its appearance.

### Basic Example

```css
.box {
    opacity: 0.5;
}
```

The element is partially transparent.

```text
opacity: 1
██████████
Fully opaque

opacity: 0.75
███████░░░
Mostly opaque

opacity: 0.5
█████░░░░░
Partially transparent

opacity: 0.25
██░░░░░░░░
Mostly transparent
```

### Common Values

```css
opacity: 0.9;
opacity: 0.8;
opacity: 0.7;
opacity: 0.6;
opacity: 0.5;
opacity: 0.4;
opacity: 0.3;
opacity: 0.2;
opacity: 0.1;
```

All of these create some degree of transparency.

The lower the value, the more transparent the element becomes.

### `opacity: 0.9`

```css
.box {
    opacity: 0.9;
}
```

The element is almost fully opaque.

This is useful when you want a subtle transparency effect.

### `opacity: 0.7`

```css
.box {
    opacity: 0.7;
}
```

The element is mostly opaque but has noticeable transparency.

This can work well for:

```text
Secondary UI elements
Faded images
Hover states
Subtle overlays
```

### `opacity: 0.5`

```css
.box {
    opacity: 0.5;
}
```

The element is significantly transparent.

This is a common value for overlays and visual effects.

### `opacity: 0.3`

```css
.box {
    opacity: 0.3;
}
```

The element is mostly transparent.

This can be useful for decorative elements or subtle background effects.

### Opacity With an Image

```css
.image {
    opacity: 0.6;
}
```

The image becomes partially transparent.

For example:

```text
Normal image
████████████

opacity: 0.6
██████░░░░░░
```

### Opacity With a Card

```css
.card {
    opacity: 0.8;
}
```

The entire card becomes partially transparent.

This includes its rendered:

```text
Background
Border
Text
Images
Child content
```

### Opacity With a Hover Effect

Partial transparency is commonly used for hover feedback.

```css
.image {
    opacity: 1;
}

.image:hover {
    opacity: 0.7;
}
```

Normal state:

```text
opacity: 1
→ Fully opaque
```

Hover state:

```text
opacity: 0.7
→ Partially transparent
```

### Smooth Partial Transparency

Use a transition:

```css
.image {
    opacity: 1;
    transition: opacity 0.3s;
}

.image:hover {
    opacity: 0.7;
}
```

The opacity gradually changes from `1` to `0.7`.

### Partial Transparency vs Transparent Color

Consider:

```css
.card {
    opacity: 0.5;
}
```

This affects the entire card.

If only the background should be transparent, use an alpha color instead:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
}
```

The difference is:

```text
opacity: 0.5
→ Entire element becomes transparent

background-color: rgb(... / 50%)
→ Background color becomes transparent
→ Other content can remain fully opaque
```

### Percentage Values

Partial opacity can also be written using percentages.

```css
opacity: 50%;
```

is equivalent to:

```css
opacity: 0.5;
```

Similarly:

```css
opacity: 75%;
```

represents:

```css
opacity: 0.75;
```

### Opacity Does Not Change Layout

Consider:

```css
.box {
    width: 300px;
    height: 150px;
    opacity: 0.5;
}
```

The element is still:

```text
300px × 150px
```

Opacity only changes its transparency.

### Practical Example

HTML:

```html
<div class="overlay">
    <h2>Overlay</h2>
</div>
```

CSS:

```css
.overlay {
    background: black;
    color: white;
    opacity: 0.5;
}
```

The overlay becomes partially transparent, allowing content behind it to contribute visually.

### Choosing an Opacity Value

Use the value based on the intended visual effect:

```text
0.9
→ Very subtle transparency

0.7
→ Mild transparency

0.5
→ Clearly transparent

0.3
→ Strong transparency

0.1
→ Very faint element
```

Do not assume that a particular value will always look the same because the final appearance also depends on the background behind the element.

### Important Points

```text
Partial Transparency
│
├── 0 < opacity < 1
│
├── Lower value
│   └── More transparent
│
├── Higher value
│   └── More opaque
│
├── opacity affects the whole element
│
└── Alpha colors can be used when
    only a specific color should be transparent
```

> 💡 **Remember:** Partial transparency uses an opacity value between `0` and `1` (or `0%` and `100%`). Use `opacity` when the entire element should become transparent, and use alpha colors when only a particular color needs transparency.

---

## Opacity and Child Elements

When `opacity` is applied to a parent element, the transparency affects the parent and its rendered child content as part of the parent's rendering.

### Basic Example

HTML:

```html
<div class="parent">
    <h2>Title</h2>
    <p>Some content</p>
</div>
```

CSS:

```css
.parent {
    opacity: 0.5;
}
```

The parent and its contents appear partially transparent.

```text
Parent
┌──────────────────────┐
│ Title                │
│ Some content         │
│                      │
└──────────────────────┘
        ↓
   opacity: 0.5
        ↓
Everything appears
partially transparent
```

### Parent Opacity Affects Child Content

Consider:

```css
.parent {
    opacity: 0.5;
}

.child {
    opacity: 1;
}
```

The child does **not** become fully opaque relative to the page simply because it has:

```css
opacity: 1;
```

The parent's opacity still affects the final rendered result.

Conceptually:

```text
Parent opacity
      ↓
Child rendered inside parent
      ↓
Final result is affected by
the parent's transparency
```

### Example

HTML:

```html
<div class="card">
    <h2>Card Title</h2>

    <button class="button">
        Click Me
    </button>
</div>
```

CSS:

```css
.card {
    opacity: 0.5;
}

.button {
    opacity: 1;
}
```

The button remains part of the semi-transparent card rendering.

Setting:

```css
.button {
    opacity: 1;
}
```

does not cancel:

```css
.card {
    opacity: 0.5;
}
```

### Why This Happens

The parent's opacity is applied to the rendered result of the element and its descendants.

Conceptually:

```text
Parent
│
├── Background
├── Text
├── Child
│   └── Content
│
└── Entire rendered result
        ↓
     opacity
```

Therefore, applying opacity to a parent is different from applying transparency independently to each child.

### Parent vs Child Opacity

Consider:

```css
.parent {
    opacity: 0.8;
}

.child {
    opacity: 0.5;
}
```

Both opacity settings contribute to the final appearance.

The child is first rendered with its own opacity, and the resulting content is then affected by the parent's opacity.

Conceptually:

```text
Child opacity
      ↓
Child rendered
      ↓
Parent opacity
      ↓
Final result
```

### Avoiding Unwanted Child Transparency

Suppose you want:

```text
Semi-transparent background
+
Fully opaque text
```

Do not use:

```css
.card {
    opacity: 0.5;
}
```

because this affects the whole card rendering.

Instead, make only the background color transparent.

For example:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
    color: white;
}
```

Now the background can be translucent while the text remains fully opaque.

### Overlay Example

A common mistake is:

```css
.overlay {
    background: black;
    opacity: 0.5;
}

.overlay h2 {
    opacity: 1;
}
```

The heading will still be affected by the parent's opacity.

A better approach is to use an alpha background:

```css
.overlay {
    background-color: rgb(0 0 0 / 50%);
}

.overlay h2 {
    opacity: 1;
}
```

This allows the heading to remain fully opaque.

### Opacity on an Image Container

Consider:

```html
<div class="image-box">
    <img src="image.jpg" alt="Example">
</div>
```

If you use:

```css
.image-box {
    opacity: 0.5;
}
```

the image inside the container is also affected by the parent's opacity.

If only the image should be transparent, apply opacity directly to the image:

```css
.image-box img {
    opacity: 0.5;
}
```

### Opacity on a Parent vs Individual Children

Parent:

```css
.parent {
    opacity: 0.5;
}
```

means the parent and its rendered contents are affected.

Individual child:

```css
.child {
    opacity: 0.5;
}
```

means only that child receives the opacity setting.

This distinction is important when designing interfaces.

### Practical Example

HTML:

```html
<div class="card">
    <div class="background"></div>

    <div class="content">
        <h2>Product</h2>
        <p>Product description.</p>
    </div>
</div>
```

Instead of:

```css
.card {
    opacity: 0.5;
}
```

use a transparent background layer when only the background should be translucent:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
}

.content {
    color: white;
}
```

### Important Points

```text
Parent opacity
│
├── Affects the parent's rendered result
├── Child content is part of that result
├── Child opacity: 1 does not cancel parent opacity
│
└── If only a background should be transparent
    └── Use an alpha color or separate background layer
```

> 💡 **Remember:** Applying `opacity` to a parent affects its rendered child content as well. If you need a transparent background while keeping text or other children fully opaque, use an alpha color or a separate background layer instead of reducing the parent's overall opacity.

---

## Opacity vs Transparent Colors

`opacity` and transparent colors can both create transparency, but they affect different parts of an element.

The main difference is:

```text
opacity
→ Affects the entire element

Transparent color
→ Affects the specific color where transparency is defined
```

### Using `opacity`

```css
.card {
    opacity: 0.5;
}
```

The entire rendered element becomes partially transparent.

This can affect:

```text
Background
Text
Border
Images
Child content
```

### Using a Transparent Background Color

Instead of:

```css
.card {
    opacity: 0.5;
}
```

you can make only the background transparent:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
}
```

The background is translucent, while the text and other content can remain fully opaque.

### Example

HTML:

```html
<div class="card">
    <h2>Product</h2>
    <p>This text should remain fully visible.</p>
</div>
```

Using `opacity`:

```css
.card {
    background-color: black;
    color: white;
    opacity: 0.5;
}
```

The entire card becomes transparent.

Conceptually:

```text
Background → transparent
Text       → transparent
Content    → transparent
```

### Using an Alpha Background

Instead:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
    color: white;
}
```

Now:

```text
Background → transparent
Text       → fully opaque
Content    → fully opaque
```

This is often the better approach when only the background needs transparency.

### Alpha Colors

Modern CSS color functions can specify an alpha component.

For example:

```css
background-color: rgb(0 0 0 / 50%);
```

The last value controls the alpha.

You can also use:

```css
background-color: rgb(0 0 0 / 0.5);
```

These represent the same 50% alpha value.

### Transparent Text Color

If only the text should be partially transparent:

```css
.text {
    color: rgb(0 0 0 / 60%);
}
```

The text color becomes translucent without applying opacity to the entire element.

### Transparent Border

You can also make a border translucent:

```css
.box {
    border: 2px solid rgb(0 0 0 / 30%);
}
```

The border is partially transparent while other parts of the element can remain fully opaque.

### Background, Text, and Border Separately

You can control transparency independently:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
    color: rgb(255 255 255 / 90%);
    border: 1px solid rgb(255 255 255 / 30%);
}
```

This provides more precise control than:

```css
.card {
    opacity: 0.5;
}
```

### `opacity` With Child Elements

Consider:

```css
.card {
    opacity: 0.5;
}
```

The card's rendered child content is affected as well.

Setting:

```css
.card h2 {
    opacity: 1;
}
```

does not make the heading fully opaque relative to the page because the parent is still rendered with reduced opacity.

### Alpha Background Avoids This Problem

Instead:

```css
.card {
    background-color: rgb(0 0 0 / 50%);
}

.card h2 {
    opacity: 1;
}
```

The heading can remain fully opaque because the parent's overall opacity has not been reduced.

### When to Use `opacity`

Use `opacity` when the **entire element** should become transparent.

Common examples:

```text
Fading an image
Hover effects
Fading a complete card
Disabled-looking visual states
Fade animations
```

Example:

```css
.image:hover {
    opacity: 0.7;
}
```

### When to Use Transparent Colors

Use transparent colors when only a particular part of an element should be transparent.

Common examples:

```text
Semi-transparent backgrounds
Transparent text colors
Transparent borders
Overlays
Layered UI components
```

Example:

```css
.overlay {
    background-color: rgb(0 0 0 / 50%);
}
```

### Comparison

| Feature | `opacity` | Transparent Color |
|---|---|---|
| Affects entire element | Yes | No |
| Affects child content | Yes | No, unless separately styled |
| Transparent background | Yes | Yes |
| Transparent text | Yes | Yes |
| Transparent border | Yes | Yes |
| Precise control | Lower | Higher |
| Useful for whole-element fade | Yes | Usually not |

### Practical Example

Suppose you want a dark overlay with fully visible white text.

Avoid:

```css
.overlay {
    background: black;
    color: white;
    opacity: 0.5;
}
```

because the text also becomes transparent.

Prefer:

```css
.overlay {
    background-color: rgb(0 0 0 / 50%);
    color: white;
}
```

Now the result is:

```text
Dark semi-transparent background
            +
Fully opaque white text
```

### Important Points

```text
opacity: 0.5
        ↓
Entire element becomes transparent

rgb(0 0 0 / 50%)
        ↓
Only that particular color becomes translucent
```

Use:

```css
opacity
```

when you want a **whole-element transparency effect**.

Use:

```css
rgb(... / alpha)
```

or another appropriate alpha-enabled color when you want **specific color transparency**.

> 💡 **Remember:** `opacity` affects the entire element and its rendered contents, while alpha-enabled colors let you control transparency for a specific background, text color, border, or other color independently.

---

## Opacity With Images

The `opacity` property can be applied to images to control how transparent they appear.

### Basic Example

```html
<img src="image.jpg" alt="Example image">
```

```css
img {
    opacity: 0.5;
}
```

The image becomes partially transparent.

```text
opacity: 1
→ Fully visible

opacity: 0.5
→ Partially transparent

opacity: 0
→ Fully transparent
```

### Fully Opaque Image

```css
img {
    opacity: 1;
}
```

The image is fully opaque.

Since `1` is the normal opacity value, this declaration is usually unnecessary unless you are explicitly setting or restoring the image's opacity.

### Partially Transparent Image

```css
img {
    opacity: 0.6;
}
```

The image becomes partially transparent, allowing the content behind it to contribute to its appearance.

### Fully Transparent Image

```css
img {
    opacity: 0;
}
```

The image becomes completely transparent.

The image element still exists and continues to occupy its layout space.

### Hover Effect

A common use of opacity with images is a hover effect.

```css
.image {
    opacity: 1;
}

.image:hover {
    opacity: 0.7;
}
```

When the pointer moves over the image, it becomes partially transparent.

### Smooth Image Fade

Combine `opacity` with `transition` for a smooth effect:

```css
.image {
    opacity: 1;
    transition: opacity 0.3s;
}

.image:hover {
    opacity: 0.7;
}
```

The image gradually changes from fully opaque to partially transparent.

### Gallery Example

```html
<div class="gallery">
    <img class="gallery-image" src="image1.jpg" alt="Image 1">
    <img class="gallery-image" src="image2.jpg" alt="Image 2">
    <img class="gallery-image" src="image3.jpg" alt="Image 3">
</div>
```

```css
.gallery-image {
    opacity: 0.7;
    transition: opacity 0.3s;
}

.gallery-image:hover {
    opacity: 1;
}
```

The images appear slightly faded normally and become fully opaque when hovered.

### Image Overlay

Opacity can also be used with an image overlay.

```html
<div class="image-container">
    <img src="image.jpg" alt="Example image">

    <div class="overlay">
        <span>View Image</span>
    </div>
</div>
```

```css
.image-container {
    position: relative;
}

.overlay {
    position: absolute;
    inset: 0;
    background-color: black;
    opacity: 0.5;
}
```

The black overlay becomes partially transparent, allowing the image underneath to remain visible.

### Overlay With Fully Visible Text

If the overlay contains text, applying opacity to the overlay itself also affects that text.

For example:

```css
.overlay {
    background: black;
    color: white;
    opacity: 0.5;
}
```

The text also becomes transparent.

If only the background should be transparent, use an alpha color instead:

```css
.overlay {
    background-color: rgb(0 0 0 / 50%);
    color: white;
}
```

Now:

```text
Background → semi-transparent
Text       → fully opaque
```

### Disabled-Looking Images

Opacity can create a faded visual appearance:

```css
.disabled-image {
    opacity: 0.4;
}
```

This can communicate that an image or visual option is unavailable.

However, opacity alone should not be relied upon to communicate the actual state or functionality.

### Watermark Effect

A partially transparent image can be used as a watermark:

```css
.watermark {
    opacity: 0.2;
}
```

The image becomes faint and allows the background behind it to remain visible.

### Opacity Does Not Resize an Image

Consider:

```css
.image {
    width: 500px;
    opacity: 0.5;
}
```

The image is still:

```text
500px wide
```

Opacity changes transparency, not dimensions.

If you need to control image size, use properties such as:

```css
width
height
max-width
object-fit
```

### Responsive Images and Opacity

Opacity can be combined with responsive image sizing:

```css
img {
    max-width: 100%;
    height: auto;
    opacity: 0.8;
}
```

Here:

```text
max-width
→ Controls image sizing

height
→ Maintains proportional scaling

opacity
→ Controls transparency
```

Each property has a separate responsibility.

### Important Points

```text
Opacity With Images
│
├── opacity: 1
│   └── Fully opaque
│
├── 0 < opacity < 1
│   └── Partially transparent
│
├── opacity: 0
│   └── Fully transparent
│
├── opacity + transition
│   └── Smooth fade effects
│
└── Alpha background color
    └── Useful when only an overlay/background
        should be transparent
```

> 💡 **Remember:** `opacity` can fade an entire image, and it works especially well with `transition` for hover effects. If an overlay contains text that should remain fully opaque, use an alpha-enabled background color instead of applying opacity to the entire overlay.

---

## Opacity With Hover Effects

The `opacity` property is commonly used with the `:hover` pseudo-class to create visual feedback when the user moves the pointer over an element.

### Basic Example

```css
.button {
    opacity: 1;
}

.button:hover {
    opacity: 0.7;
}
```

The button changes from fully opaque to partially transparent when hovered.

```text
Normal
opacity: 1
    ↓
Fully opaque

Hover
opacity: 0.7
    ↓
Partially transparent
```

### Image Hover Effect

Opacity is frequently used with images:

```css
.image {
    opacity: 1;
}

.image:hover {
    opacity: 0.7;
}
```

When the image is hovered, it becomes slightly transparent.

### Smooth Hover Effect

Without a transition:

```css
.image:hover {
    opacity: 0.7;
}
```

the opacity changes immediately.

Add a transition:

```css
.image {
    opacity: 1;
    transition: opacity 0.3s;
}

.image:hover {
    opacity: 0.7;
}
```

Now the change happens gradually.

### Different Hover Opacity Values

You can choose the value based on the desired effect.

```css
.card:hover {
    opacity: 0.9;
}
```

Very subtle effect.

```css
.card:hover {
    opacity: 0.7;
}
```

Noticeable effect.

```css
.card:hover {
    opacity: 0.5;
}
```

Strong transparency.

Avoid making interactive elements excessively transparent if it makes them difficult to see.

### Link Hover Effect

```css
a {
    opacity: 1;
    transition: opacity 0.2s;
}

a:hover {
    opacity: 0.7;
}
```

This provides visual feedback when the link is hovered.

### Button Hover Effect

```css
.button {
    opacity: 1;
    transition: opacity 0.2s;
}

.button:hover {
    opacity: 0.8;
}
```

The button becomes slightly transparent on hover.

### Gallery Example

HTML:

```html
<div class="gallery">
    <img src="image1.jpg" alt="Image 1">
    <img src="image2.jpg" alt="Image 2">
    <img src="image3.jpg" alt="Image 3">
</div>
```

CSS:

```css
.gallery img {
    opacity: 0.7;
    transition: opacity 0.3s;
}

.gallery img:hover {
    opacity: 1;
}
```

The images appear slightly faded until the user hovers over one.

### Card Hover Effect

```css
.card {
    opacity: 0.85;
    transition: opacity 0.3s;
}

.card:hover {
    opacity: 1;
}
```

The card becomes fully opaque when hovered.

### Combining Opacity With Other Hover Effects

Opacity can be combined with transforms:

```css
.card {
    opacity: 0.8;
    transition:
        opacity 0.3s,
        transform 0.3s;
}

.card:hover {
    opacity: 1;
    transform: translateY(-4px);
}
```

This creates two visual changes:

```text
Hover
│
├── opacity → 1
└── transform → moves upward
```

### Important: Hover Is Not Available Everywhere

The `:hover` state is primarily associated with pointer interaction.

Do not rely on hover alone to communicate important information or functionality, especially for touch-based devices.

For important interactive states, also consider:

```css
:focus
:focus-visible
:active
```

### Hover and Accessibility

Avoid reducing opacity so much that text or controls become difficult to see.

For example, this may be too faint depending on the design:

```css
.button:hover {
    opacity: 0.2;
}
```

Prefer a value that maintains sufficient visual clarity.

### Hover vs Disabled State

Do not use opacity alone to determine whether an element is actually disabled.

For example:

```css
.button {
    opacity: 0.5;
}
```

only changes its appearance.

If a button should actually be disabled, use the appropriate HTML state:

```html
<button disabled>Submit</button>
```

Then style it:

```css
button:disabled {
    opacity: 0.5;
}
```

Here:

```text
disabled
→ Controls functionality/state

opacity
→ Controls visual appearance
```

### Practical Example

```html
<a class="card-link" href="#">
    <img src="image.jpg" alt="Example">
    <h2>Learn CSS</h2>
</a>
```

```css
.card-link {
    display: block;
    opacity: 0.8;
    transition: opacity 0.3s;
}

.card-link:hover {
    opacity: 1;
}

.card-link:focus-visible {
    outline: 2px solid currentColor;
    outline-offset: 4px;
}
```

This provides:

```text
Normal
→ Slightly transparent

Hover
→ Fully opaque

Keyboard focus
→ Visible focus indicator
```

### Important Points

```text
Opacity + :hover
│
├── Creates visual feedback
├── Can fade images
├── Can fade buttons
├── Can fade links
├── Can fade cards
│
└── transition
    └── Makes the change smooth
```

> 💡 **Remember:** `opacity` is useful for hover feedback, especially when combined with `transition`. However, opacity should control appearance—not functionality—and important interaction states should not depend on hover alone.

---

## Opacity With Transitions

The `transition` property can be combined with `opacity` to create smooth fade effects.

Without a transition, an opacity change happens immediately.

With a transition, the browser gradually changes the opacity over the specified duration.

### Basic Example

```css
.box {
    opacity: 1;
    transition: opacity 0.3s;
}

.box:hover {
    opacity: 0.5;
}
```

The element smoothly changes from:

```text
opacity: 1
    ↓
opacity: 0.5
```

when it is hovered.

### Without a Transition

```css
.box {
    opacity: 1;
}

.box:hover {
    opacity: 0.5;
}
```

The change happens immediately:

```text
Normal
opacity: 1

        ↓ hover

Hover
opacity: 0.5
```

### With a Transition

```css
.box {
    opacity: 1;
    transition: opacity 0.3s;
}

.box:hover {
    opacity: 0.5;
}
```

The browser gradually changes the opacity:

```text
1.0
 ↓
0.9
 ↓
0.8
 ↓
0.7
 ↓
0.6
 ↓
0.5
```

The actual intermediate values are handled by the browser.

### Transition Duration

The duration determines how long the opacity change takes.

```css
transition: opacity 0.2s;
```

Short transition.

```css
transition: opacity 0.5s;
```

Longer transition.

```css
transition: opacity 1s;
```

Slow transition.

For small UI interactions, shorter durations are often appropriate.

### Using `transition-property`

You can explicitly specify the property:

```css
.box {
    transition-property: opacity;
    transition-duration: 0.3s;
}
```

This is equivalent in intent to:

```css
.box {
    transition: opacity 0.3s;
}
```

### Transition Timing Function

You can also control how the transition progresses over time.

```css
.box {
    transition: opacity 0.3s ease;
}
```

Common timing functions include:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

Example:

```css
.box {
    transition: opacity 0.3s ease-in-out;
}
```

### Transition Delay

A delay can be added:

```css
.box {
    transition: opacity 0.3s ease 0.1s;
}
```

Conceptually:

```text
0.1s
↓
Wait

0.3s
↓
Perform opacity transition
```

### Image Fade Effect

```css
.image {
    opacity: 1;
    transition: opacity 0.3s ease;
}

.image:hover {
    opacity: 0.7;
}
```

The image smoothly fades when hovered.

### Button Fade Effect

```css
.button {
    opacity: 1;
    transition: opacity 0.2s ease;
}

.button:hover {
    opacity: 0.8;
}
```

The button becomes slightly transparent on hover.

### Card Fade Effect

```css
.card {
    opacity: 0.8;
    transition: opacity 0.3s ease;
}

.card:hover {
    opacity: 1;
}
```

The card becomes fully opaque when hovered.

### Combining Opacity With Other Transitions

Opacity can be transitioned together with other properties.

```css
.card {
    opacity: 0.8;
    transform: translateY(0);

    transition:
        opacity 0.3s ease,
        transform 0.3s ease;
}

.card:hover {
    opacity: 1;
    transform: translateY(-5px);
}
```

Now the card:

```text
Becomes more opaque
        +
Moves upward
```

### Transition Should Usually Be on the Normal State

Prefer:

```css
.button {
    opacity: 1;
    transition: opacity 0.3s;
}

.button:hover {
    opacity: 0.7;
}
```

rather than placing the transition only inside `:hover`:

```css
.button:hover {
    opacity: 0.7;
    transition: opacity 0.3s;
}
```

Putting the transition on the normal state allows the effect to work smoothly in both directions:

```text
Normal → Hover
Hover  → Normal
```

### Fade-In Example

An element can start transparent and become visible:

```css
.message {
    opacity: 0;
    transition: opacity 0.5s ease;
}

.message.visible {
    opacity: 1;
}
```

When the `visible` class is added:

```text
opacity: 0
    ↓
fade
    ↓
opacity: 1
```

### Fade-Out Example

The reverse can be used to fade an element out:

```css
.message {
    opacity: 1;
    transition: opacity 0.5s ease;
}

.message.hidden {
    opacity: 0;
}
```

The element becomes visually transparent.

Remember that:

```css
opacity: 0;
```

does not remove the element from layout.

### Opacity Transition vs `display: none`

Opacity can be transitioned:

```css
.element {
    opacity: 1;
    transition: opacity 0.3s;
}

.element.hidden {
    opacity: 0;
}
```

But `display` does not behave like a normal interpolated opacity transition:

```css
display: none;
```

If you need a visual fade, animate opacity or another suitable visual property rather than expecting `display` itself to gradually change.

### Accessibility and Reduced Motion

Some users prefer reduced motion.

You can respect that preference:

```css
.button {
    opacity: 1;
    transition: opacity 0.3s ease;
}

.button:hover {
    opacity: 0.7;
}

@media (prefers-reduced-motion: reduce) {
    .button {
        transition: none;
    }
}
```

This removes the transition for users who have requested reduced motion.

### Important Points

```text
Opacity + Transition
│
├── opacity
│   └── Controls transparency
│
├── transition
│   └── Makes the change gradual
│
├── duration
│   └── Controls how long it takes
│
├── timing-function
│   └── Controls the transition's pace
│
└── delay
    └── Delays the start
```

> 💡 **Remember:** Put the transition on the normal state so the opacity change works smoothly both when entering and leaving the interactive state. Use a duration and timing function appropriate for the UI, and consider `prefers-reduced-motion` for accessibility.