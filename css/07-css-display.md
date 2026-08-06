## Table of Contents

- [Introduction](#introduction)
- [What is the `display` Property?](#what-is-the-display-property)
- [Block Elements](#block-elements)
- [Inline Elements](#inline-elements)
- [Inline-Block Elements](#inline-block-elements)
- [`display: none`](#display-none)
- [`display: contents`](#display-contents)
- [`display: flex`](#display-flex)
- [`display: grid`](#display-grid)
- [Other Common Display Values](#other-common-display-values)
- [Display Comparison Table](#display-comparison-table)
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


## Introduction

Every HTML element has a **display type** that determines **how it appears and behaves within a webpage layout**.

Some elements naturally occupy an entire line, while others only take up as much space as their content requires. Some elements can be completely hidden, while others become flexible containers for advanced layouts.

The CSS **`display`** property allows you to control this behavior.

By changing an element's display type, you can completely alter how it interacts with surrounding elements without changing the HTML itself.

For example, you can:

- Make an inline element behave like a block element.
- Place multiple block elements on the same line.
- Hide elements from the page.
- Create flexible layouts with Flexbox.
- Build two-dimensional layouts with Grid.

Because of its versatility, the `display` property is one of the most frequently used properties in modern CSS.

In this chapter, you'll learn the most common display values, when to use them, how they affect layout, and how they serve as the foundation for advanced layout systems.

> 💡 **Pro Tip:** Before reaching for Flexbox or Grid, first ask yourself: *"How should this element behave?"* The answer often begins with choosing the correct `display` value.


---


## What is the `display` Property?

The **`display`** property determines **how an HTML element is displayed and participates in the page layout**.

Every HTML element has a default display type assigned by the browser.

For example:

- `<div>` is a **block** element.
- `<span>` is an **inline** element.
- `<img>` is an **inline** element (often treated as a replaced inline element).
- `<button>` commonly behaves as an **inline-block** element in browsers.

By changing the `display` property, you can completely change how an element behaves without modifying the HTML structure.

---

## Syntax

```css
selector {
    display: value;
}
```

---

## Common Values

| Value | Purpose |
|--------|---------|
| `block` | Displays the element as a block-level element. |
| `inline` | Displays the element inline with surrounding content. |
| `inline-block` | Combines features of inline and block elements. |
| `none` | Removes the element from the layout. |
| `flex` | Creates a Flexbox container. |
| `grid` | Creates a Grid container. |
| `contents` | Removes the element's own box while keeping its children. |

---

## Why is `display` Important?

The `display` property controls:

- Whether an element starts on a new line.
- Whether width and height can be applied.
- How much horizontal space an element occupies.
- How child elements are laid out.
- Whether an element participates in the document layout.

Changing `display` often changes the entire behavior of an element.

---

## Example

### HTML

```html
<div class="box">
    Hello CSS
</div>
```

### CSS

```css
.box {
    display: inline;
}
```

Although `<div>` is normally a block element, it now behaves like an inline element.

---

## Default Behavior

Different HTML elements have different default display values.

Examples:

| Element | Default Display |
|----------|-----------------|
| `<div>` | `block` |
| `<p>` | `block` |
| `<h1>`–`<h6>` | `block` |
| `<span>` | `inline` |
| `<a>` | `inline` |
| `<strong>` | `inline` |
| `<img>` | `inline` |
| `<button>` | Usually `inline-block` |

These defaults can be changed using CSS.

---

## Layout Behavior

Think of `display` as answering one question:

> **How should this element behave inside the layout?**

Possible answers include:

```text
Take the whole row?

↓

display: block
```

```text
Stay within surrounding text?

↓

display: inline
```

```text
Stay inline but allow width and height?

↓

display: inline-block
```

```text
Become a flexible layout container?

↓

display: flex
```

```text
Become a two-dimensional layout?

↓

display: grid
```

---

## Advantages

- Controls element layout behavior.
- Makes layouts flexible without changing HTML.
- Enables modern layout systems.
- Works with every HTML element.

---

## Limitations

- Some display values affect which CSS properties have an effect (for example, `width` and `height` on inline elements).
- Choosing the wrong display type can produce unexpected layouts.
- Advanced values such as `contents` have specific use cases and should be used carefully.

> 💡 **Pro Tip:** Before changing margins, widths, or positioning, first verify that the element has the correct `display` value. Many layout issues are caused by using the wrong display type.

### 🌍 Real-World Usage

The `display` property is used on virtually every website to:

- Build navigation menus
- Create cards
- Align buttons
- Hide and show content
- Build dashboards
- Create responsive layouts
- Enable Flexbox and Grid

### 📌 Did You Know?

Modern CSS layout begins with one property:

```css
display
```

Both **Flexbox** and **Grid** are enabled simply by changing the `display` value.

### ⚠️ Important

The `display` property changes **how an element behaves**, not what the element is.

For example:

```html
<div></div>
```

will always remain a `<div>` element, even if you apply:

```css
display: inline;
```

Only its layout behavior changes.