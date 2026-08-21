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