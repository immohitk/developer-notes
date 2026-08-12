## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Transforms?](#what-are-css-transforms)
- [Why Are CSS Transforms Important?](#why-are-css-transforms-important)
- [Transform Syntax](#transform-syntax)
- [Translate](#translate)
- [Translate X](#translate-x)
- [Translate Y](#translate-y)
- [Translate 3D](#translate-3d)
- [Scale](#scale)
- [Scale X](#scale-x)
- [Scale Y](#scale-y)
- [Rotate](#rotate)
- [Rotate X](#rotate-x)
- [Rotate Y](#rotate-y)
- [Rotate Z](#rotate-z)
- [Skew](#skew)
- [Skew X](#skew-x)
- [Skew Y](#skew-y)
- [Transform Origin](#transform-origin)
- [Multiple Transforms](#multiple-transforms)
- [2D Transforms](#2d-transforms)
- [3D Transforms](#3d-transforms)
- [Perspective](#perspective)
- [Transform Style](#transform-style)
- [Backface Visibility](#backface-visibility)
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

CSS Transforms are used to visually modify an element without changing its normal position in the document flow.

They allow you to **move, resize, rotate, and distort elements** using the CSS `transform` property.

For example:

```css
.box {
    transform: rotate(45deg);
}
```

This rotates the element by `45deg`.

Another example:

```css
.box {
    transform: scale(1.2);
}
```

This makes the element visually larger.

CSS Transforms are commonly used to create:

- Hover effects
- Interactive UI elements
- Smooth visual effects
- Card effects
- Image effects
- 2D transformations
- 3D transformations
- Animation effects

> 💡 **Tip:** CSS Transforms are especially useful when you want to visually change an element while keeping its original place in the document layout.

In this chapter, you will learn how to use different CSS transform functions, control the transformation point, combine multiple transformations, and create both 2D and 3D effects.

---

### Example

```html
<div class="box">Transform Me</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: rotate(10deg);
}
```

The element is visually rotated without changing the normal document flow around it.

---

### Basic Syntax

The basic syntax for CSS transforms is:

```css
selector {
    transform: function(value);
}
```

For example:

```css
.box {
    transform: translateX(50px);
}
```

Here:

- `transform` is the CSS property.
- `translateX()` is the transform function.
- `50px` is the value applied to the transformation.

> 💡 **Remember:** The `transform` property can contain one or multiple transform functions.