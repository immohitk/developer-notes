## Table of Contents

- [Introduction](#introduction)
- [What Is Overflow?](#what-is-overflow)
- [`overflow`](#overflow)
- [`overflow-x`](#overflow-x)
- [`overflow-y`](#overflow-y)
- [`overflow: visible`](#overflow-visible)
- [`overflow: hidden`](#overflow-hidden)
- [`overflow: scroll`](#overflow-scroll)
- [`overflow: auto`](#overflow-auto)
- [`overflow: clip`](#overflow-clip)
- [Two-Value Overflow](#two-value-overflow)
- [`text-overflow`](#text-overflow)
- [Overflow With Text](#overflow-with-text)
- [Overflow With Images](#overflow-with-images)
- [Overflow With Border Radius](#overflow-with-border-radius)
- [Overflow With Positioning](#overflow-with-positioning)
- [Overflow in CSS Grid](#overflow-in-css-grid)
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

CSS Overflow controls what happens when the content of an element is **larger than the space available inside its box**.

Normally, content fits inside an element:

```text
┌──────────────────────┐
│      Content         │
│      Content         │
└──────────────────────┘
```

When the content becomes larger than the available space, it can overflow:

```text
┌──────────────────────┐
│      Content         │
│      Content         │
└──────────────────────┘
      Content continues
      outside the box
```

CSS provides overflow properties that allow you to control this behavior.

### Why Overflow Matters

Overflow commonly occurs when:

- An element has a fixed width or height.
- Text is too long to fit.
- An image is larger than its container.
- A child element extends beyond its parent.
- Content does not wrap as expected.
- A layout needs a scrollable region.

For example:

```css
.box {
    width: 200px;
    height: 100px;
}
```

If the content requires more than the available:

```text
Width  → 200px
Height → 100px
```

the extra content needs to be handled somehow.

### Controlling Overflow

The main property is:

```css
overflow
```

Example:

```css
.box {
    overflow: hidden;
}
```

Other related properties include:

```css
overflow-x
overflow-y
```

These allow horizontal and vertical overflow to be controlled independently.

### Common Overflow Values

The most commonly used values are:

```css
visible
hidden
scroll
auto
clip
```

They provide different behaviors when content exceeds the available space.

### Simple Example

HTML:

```html
<div class="box">
    This is some content that is larger than the available space.
</div>
```

CSS:

```css
.box {
    width: 200px;
    height: 100px;
    overflow: auto;
}
```

If the content fits, no scrolling is needed.

If the content does not fit, the browser can provide scrolling.

### Overflow and the Box

It is useful to think of an element as having a visible area:

```text
┌──────────────────────────┐
│      Visible Area        │
│                          │
│      Content             │
│                          │
└──────────────────────────┘
            ↓
      Overflow handling
```

CSS determines what happens to content outside that available area.

### Horizontal and Vertical Overflow

Overflow can occur in two directions:

```text
Horizontal
←────────────────────────→

Vertical
        ↓
        ↓
        ↓
```

You can control them separately:

```css
.box {
    overflow-x: auto;
    overflow-y: hidden;
}
```

Here:

```text
Horizontal → scrolling when necessary
Vertical   → clipped
```

### Overflow Is Not Always a Problem

Overflow is not necessarily an error.

Sometimes overflow is intentional.

For example, a code editor, table, or horizontally scrollable container may intentionally allow content to extend beyond its visible area.

```css
.code {
    overflow-x: auto;
}
```

The important point is to choose the behavior that matches the design.

> 💡 **Remember:** CSS Overflow controls what happens when content is larger than the available space inside an element. The main properties are `overflow`, `overflow-x`, and `overflow-y`, while values such as `visible`, `hidden`, `scroll`, `auto`, and `clip` determine how that overflow is handled.

---

## What Is Overflow?

**Overflow** occurs when the content inside an element is larger than the space available within that element's box.

For example:

```css
.box {
    width: 200px;
    height: 100px;
}
```

If the content requires more than `200px` of width or `100px` of height, the content can extend beyond the element's available area.

### Simple Example

HTML:

```html
<div class="box">
    This is a very long piece of content that may not fit inside the box.
</div>
```

CSS:

```css
.box {
    width: 200px;
    height: 100px;
}
```

Conceptually:

```text
┌──────────────────────┐
│ Content that fits    │
│ inside the box       │
└──────────────────────┘
        ↓
   Extra content
   may overflow
```

### Why Does Overflow Happen?

Overflow commonly happens when:

- Content is too wide.
- Content is too tall.
- An element has fixed dimensions.
- An image is larger than its container.
- Text does not wrap.
- A child element extends outside its parent.
- A layout contains content that cannot shrink enough.

### Horizontal Overflow

Horizontal overflow occurs when content is wider than the available width.

```text
Available width:

┌──────────────────────┐
│ Content               │
└──────────────────────┘
              ────────────────→
              Extra width
```

For example:

```css
.box {
    width: 200px;
}
```

If the content needs `400px`, it can overflow horizontally.

### Vertical Overflow

Vertical overflow occurs when content is taller than the available height.

```text
┌──────────────────────┐
│ Content              │
│ Content              │
│ Content              │
└──────────────────────┘
          ↓
          ↓
     Extra content
```

For example:

```css
.box {
    height: 100px;
}
```

If the content requires `300px` of height, it can overflow vertically.

### Overflow Is Related to Available Space

Think of an element as having a limited visible area:

```text
Element
┌─────────────────────────┐
│                         │
│    Available Space      │
│                         │
└─────────────────────────┘
            ↓
      Content exceeds
      available space
            ↓
         Overflow
```

The browser then applies the overflow behavior specified by CSS.

### Controlling Overflow

The main property used to control overflow is:

```css
overflow
```

For example:

```css
.box {
    width: 200px;
    height: 100px;
    overflow: hidden;
}
```

Here, content that extends outside the box is clipped.

Other related properties are:

```css
overflow-x
overflow-y
```

These control horizontal and vertical overflow separately.

### Overflow Is Not Necessarily an Error

Overflow can be intentional.

For example, a horizontally scrollable code block can use:

```css
.code {
    overflow-x: auto;
}
```

A large table can also require horizontal scrolling on smaller screens.

```text
Small screen

┌──────────────────────┐
│ Table                │
│ ────────────────────→│
└──────────────────────┘
       scroll
```

In these situations, overflow is part of the intended design.

### Overflow vs Normal Content Flow

Normally, browsers try to lay out content inside the available space.

When content cannot fit, the browser must determine what happens to the extra content.

CSS gives you control over this behavior through:

```css
overflow
overflow-x
overflow-y
```

The specific value determines whether the content remains visible, is clipped, or becomes scrollable.

### Important Points

```text
Overflow
│
├── Content is larger than available space
│
├── Horizontal overflow
│   └── Content is too wide
│
├── Vertical overflow
│   └── Content is too tall
│
└── Controlled using
    ├── overflow
    ├── overflow-x
    └── overflow-y
```

> 💡 **Remember:** Overflow simply means that content does not fit within the available space of its element. It can happen horizontally, vertically, or in both directions, and CSS provides properties to control what happens to that extra content.