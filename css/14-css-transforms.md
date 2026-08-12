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

CSS Transforms allow you to visually move, resize, rotate, or distort an element without changing the normal document flow.

Transforms are commonly used for:

- Moving elements
- Scaling elements
- Rotating elements
- Skewing elements
- Creating hover effects
- Creating interactive UI effects
- Building 2D and 3D visual effects

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

This increases the visual size of the element.

CSS Transforms are especially useful when creating interactive interfaces because they can be combined with CSS transitions and animations to create smooth visual effects.