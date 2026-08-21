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