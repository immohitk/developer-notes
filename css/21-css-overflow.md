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