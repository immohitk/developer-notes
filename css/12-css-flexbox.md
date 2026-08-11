## Table of Contents

1. [Introduction](#introduction)
2. [What Is Flexbox?](#what-is-flexbox)
3. [Why Is Flexbox Important?](#why-is-flexbox-important)
4. [Flex Container and Flex Items](#flex-container-and-flex-items)
5. [Creating a Flex Container](#creating-a-flex-container)
6. [Flex Direction](#flex-direction)
7. [Main Axis and Cross Axis](#main-axis-and-cross-axis)
8. [Flex Wrap](#flex-wrap)
9. [Flex Flow](#flex-flow)
10. [Justify Content](#justify-content)
11. [Align Items](#align-items)
12. [Align Content](#align-content)
13. [Gap](#gap)
14. [Row Gap and Column Gap](#row-gap-and-column-gap)
15. [Flex Item Properties](#flex-item-properties)
16. [Order](#order)
17. [Flex Grow](#flex-grow)
18. [Flex Shrink](#flex-shrink)
19. [Flex Basis](#flex-basis)
20. [Flex Shorthand](#flex-shorthand)
21. [Align Self](#align-self)
22. [Nested Flex Containers](#nested-flex-containers)
23. [Centering with Flexbox](#centering-with-flexbox)
24. [Common Flexbox Layouts](#common-flexbox-layouts)
25. [Flexbox vs Grid](#flexbox-vs-grid)
26. [Common Use Cases](#common-use-cases)
27. [Key Takeaways](#key-takeaways)
28. [References](#references)
29. [Quick Revision](#quick-revision)
30. [Best Practices](#best-practices)
31. [Common Mistakes](#common-mistakes)
32. [Interview Questions](#interview-questions)
33. [Practice Exercises](#practice-exercises)
34. [Related Topics](#related-topics)

---

# Introduction

**Flexbox**, short for **Flexible Box Layout**, is a CSS layout system designed to arrange elements efficiently within a container.

It provides a convenient way to control:

- The direction of elements
- Alignment
- Spacing
- Distribution of available space
- Sizing of elements
- Responsive layouts

A basic Flexbox container is created using:

```css
.container {
    display: flex;
}
```

When an element becomes a flex container, its **direct children** become flex items.

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

The structure becomes:

```text
Flex Container
      │
      ├── Flex Item
      ├── Flex Item
      └── Flex Item
```

---

## Why Was Flexbox Introduced?

Before Flexbox, developers commonly used techniques such as:

- Floats
- Inline-block
- Tables
- Positioning

These techniques could make common layout tasks unnecessarily complicated.

For example, vertically and horizontally centering an element often required additional CSS techniques.

Flexbox provides dedicated properties for these types of layout problems.

---

## One-Dimensional Layout

Flexbox is primarily a **one-dimensional layout system**.

This means it handles layout in one direction at a time:

```text
Horizontal
→ Row

Vertical
→ Column
```

For example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

arranges items horizontally.

While:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

arranges items vertically.

---

## Basic Visual Example

With:

```css
.container {
    display: flex;
}
```

the default layout is:

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│ Item 1  │  │ Item 2  │  │ Item 3  │
└─────────┘  └─────────┘  └─────────┘
```

With:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

the layout becomes:

```text
┌─────────┐
│ Item 1  │
└─────────┘
     ↓
┌─────────┐
│ Item 2  │
└─────────┘
     ↓
┌─────────┐
│ Item 3  │
└─────────┘
```

---

## Flexbox Is Controlled by the Parent

One important concept is that many Flexbox properties are applied to the **parent container**.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

These properties control how the child elements are positioned and aligned within the container.

Individual flex items also have their own properties, which will be covered later.

---

## Common Uses of Flexbox

Flexbox is commonly used for:

- Navigation bars
- Button groups
- Card layouts
- Toolbars
- Form layouts
- Headers
- Footers
- Centering content
- Aligning icons and text
- Responsive components

---

> 💡 **Pro Tip:** Don't try to memorize every Flexbox property at once. First understand the relationship between the **container and its items**, then learn how the main axis and cross axis control their layout.

---

> 💡 **Remember:** `display: flex` turns an element into a **flex container**, and its direct children become **flex items**. Flexbox is designed primarily for arranging items in a single direction at a time.