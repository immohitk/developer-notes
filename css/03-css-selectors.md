# CSS Selectors

## Table of Contents

- [Introduction](#introduction)
- [What is a CSS Selector?](#what-is-a-css-selector)
- [Universal Selector](#universal-selector)
- [Element Selector](#element-selector)
- [Class Selector](#class-selector)
- [ID Selector](#id-selector)
- [Grouping Selector](#grouping-selector)
- [Descendant Selector](#descendant-selector)
- [Child Selector](#child-selector)
- [Adjacent Sibling Selector](#adjacent-sibling-selector)
- [General Sibling Selector](#general-sibling-selector)
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

CSS selectors are one of the most fundamental concepts in CSS. Before applying any style, you must first tell the browser **which HTML element or elements should receive that style**. This is the job of a CSS selector.

Selectors allow you to target specific elements based on their name, class, ID, relationship with other elements, or other criteria. Choosing the correct selector helps you write cleaner, more efficient, and easier-to-maintain stylesheets.

In this chapter, you'll learn the different types of CSS selectors, understand how they work, and discover when to use each one in real-world projects.


---


## What is a CSS Selector?

A **CSS selector** is a pattern used to select one or more HTML elements that you want to style.

Before CSS can apply a style, it must know **which element or group of elements** the style should affect. Selectors make this possible by identifying the target elements.

### Basic Syntax

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
}
```

In this example:

- `h1` is the **selector**.
- `color` is the **property**.
- `blue` is the **value**.

The browser first finds all `<h1>` elements and then applies the specified styles.

### Why Are Selectors Important?

Selectors help you:

- Apply styles to specific HTML elements.
- Reuse the same styles across multiple elements.
- Write cleaner and more organized CSS.
- Reduce duplicate styling code.
- Build scalable and maintainable websites.

Without selectors, CSS would not know which HTML elements should receive a particular style.


---


## Universal Selector

The **Universal Selector** is represented by an asterisk (`*`). It selects **every HTML element** on the page.

It is commonly used to apply common styles to all elements or to reset the browser's default spacing.

### Syntax

```css
* {
    property: value;
}
```

### Example

```css
* {
    margin: 0;
    padding: 0;
}
```

```html
<h1>Developer Notes</h1>
<p>Learning CSS Selectors</p>
<div>This is a container.</div>
```

In this example, the `margin` and `padding` of every HTML element are set to `0`.

### Common Use Cases

- Reset default browser spacing.
- Apply a common style to every element.
- Create a consistent starting point before adding custom styles.

### Note

Although the Universal Selector is useful, avoid applying unnecessary styles to every element. Overusing it may affect performance and make your stylesheet harder to understand.


---


## Element Selector

The **Element Selector** (also called the **Type Selector**) selects HTML elements based on their **tag name**.

It applies the specified styles to **every occurrence** of that HTML element on the page.

### Syntax

```css
element {
    property: value;
}
```

### Example

```css
h1 {
    color: blue;
}

p {
    font-size: 18px;
    color: gray;
}
```

```html
<h1>Developer Notes</h1>

<p>Learning CSS Selectors.</p>
<p>This paragraph also receives the same styles.</p>
```

In this example:

- The `h1` selector styles **all** `<h1>` elements.
- The `p` selector styles **all** `<p>` elements.

### Common Use Cases

- Applying common styles to headings (`h1`–`h6`).
- Styling all paragraphs consistently.
- Setting default styles for lists, tables, buttons, and other HTML elements.

### Note

Since the Element Selector affects **every matching element**, avoid using it when only specific elements need different styles. In such cases, use **class** or **ID** selectors instead.