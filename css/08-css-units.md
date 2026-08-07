# CSS Units

## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Units?](#what-are-css-units)
- [Why Are CSS Units Important?](#why-are-css-units-important)
- [Absolute Units](#absolute-units)
  - [Pixels (`px`)](#pixels-px)
  - [Centimeters (`cm`)](#centimeters-cm)
  - [Millimeters (`mm`)](#millimeters-mm)
  - [Inches (`in`)](#inches-in)
  - [Points (`pt`)](#points-pt)
  - [Picas (`pc`)](#picas-pc)
- [Relative Units](#relative-units)
  - [Percentage (`%`)](#percentage-)
  - [`em`](#em)
  - [`rem`](#rem)
  - [`vw`](#vw)
  - [`vh`](#vh)
  - [`vmin`](#vmin)
  - [`vmax`](#vmax)
  - [`ch`](#ch)
  - [`ex`](#ex)
- [Viewport Units](#viewport-units)
- [Font-Relative Units](#font-relative-units)
- [Unit Comparison Table](#unit-comparison-table)
- [Real-World Examples](#real-world-examples)
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

CSS units define **how the browser measures lengths and sizes**.

Every visual property that represents size uses a CSS unit.

Examples include:

- Width
- Height
- Margin
- Padding
- Font size
- Border width
- Position offsets
- Grid tracks
- Flexbox sizing

Choosing the correct unit is just as important as choosing the correct CSS property.

For example:

```css
.box {
    width: 300px;
}
```

uses a fixed pixel value, while:

```css
.box {
    width: 50%;
}
```

creates a responsive width based on its parent element.

Similarly,

```css
font-size: 2rem;
```

behaves very differently from:

```css
font-size: 2em;
```

Understanding these differences helps you build layouts that adapt to different screen sizes, user preferences, and devices.

In this chapter, you'll learn the most common CSS units, how they work, when to use them, and which units are recommended for modern web development.

> 💡 **Pro Tip:** There is no single "best" CSS unit. The right choice depends on what you're sizing and how you want it to respond to different screen sizes and user settings.


---


# What Are CSS Units?

**CSS units** define **how the browser measures lengths and sizes**.

Whenever you specify a size in CSS, you use a unit to tell the browser how that value should be interpreted.

For example:

```css
.box {
    width: 300px;
}
```

Here:

- `300` is the numeric value.
- `px` (pixels) is the unit.

Together they form a CSS measurement.

---

## Syntax

A CSS measurement consists of:

```text
Value + Unit
```

Example:

```css
font-size: 16px;
margin: 2rem;
width: 75%;
height: 100vh;
```

Each declaration combines a numeric value with a unit.

---

## Where Are CSS Units Used?

CSS units are used in many properties, including:

| Property | Example |
|----------|---------|
| `width` | `300px` |
| `height` | `50vh` |
| `font-size` | `1.2rem` |
| `margin` | `20px` |
| `padding` | `1em` |
| `gap` | `24px` |
| `border-width` | `2px` |
| `top`, `left`, `right`, `bottom` | `10%` |

Almost every CSS layout uses units.

---

## Types of CSS Units

CSS units are divided into two main categories.

### 1. Absolute Units

Absolute units represent fixed measurements.

Examples:

- `px`
- `cm`
- `mm`
- `in`
- `pt`
- `pc`

These units generally do not change based on the surrounding layout.

---

### 2. Relative Units

Relative units are calculated relative to another value.

Examples:

- `%`
- `em`
- `rem`
- `vw`
- `vh`
- `vmin`
- `vmax`
- `ch`
- `ex`

These units are commonly used for responsive layouts and scalable typography.

---

## Visual Overview

```text
CSS Units
│
├── Absolute Units
│     ├── px
│     ├── cm
│     ├── mm
│     ├── in
│     ├── pt
│     └── pc
│
└── Relative Units
      ├── %
      ├── em
      ├── rem
      ├── vw
      ├── vh
      ├── vmin
      ├── vmax
      ├── ch
      └── ex
```

---

## Why CSS Units Matter

Different units produce different behaviors.

For example:

```css
width: 300px;
```

creates a fixed width.

Whereas:

```css
width: 50%;
```

creates a width relative to the parent element.

Likewise:

```css
font-size: 2rem;
```

behaves differently from:

```css
font-size: 2em;
```

Choosing the correct unit has a direct impact on responsiveness and usability.

---

## Advantages

- Control element sizing.
- Enable responsive layouts.
- Improve typography.
- Support scalable designs.
- Adapt layouts to different devices.

---

## Limitations

- Some units are better suited for specific situations than others.
- Using the wrong unit can make layouts difficult to maintain or less responsive.
- Relative units require understanding what they are relative to.

> 💡 **Pro Tip:** Before choosing a unit, ask yourself: *Should this size stay fixed, or should it adapt to its parent, the viewport, or the user's font settings?* The answer usually determines the best unit to use.

### 🌍 Real-World Usage

Modern websites typically combine several units:

- `px` for borders and fine details.
- `rem` for typography.
- `%` for flexible widths.
- `vw` and `vh` for viewport-based layouts.
- `em` for component-level scaling.

Using the appropriate unit for each situation creates layouts that are both flexible and maintainable.

### 📌 Did You Know?

CSS supports many units, but in everyday frontend development you'll primarily use:

- `px`
- `%`
- `em`
- `rem`
- `vw`
- `vh`

Mastering these six units covers the majority of sizing tasks in modern web applications.

### ⚠️ Important

A numeric value alone is **not** enough for most CSS length properties.

For example:

❌ Incorrect

```css
width: 300;
```

✅ Correct

```css
width: 300px;
```

Without an appropriate unit, most length values are considered invalid in CSS.