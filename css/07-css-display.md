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


---


## Block Elements

A **block element** starts on a **new line** and, by default, expands to occupy the **full available width** of its parent container.

Block elements are primarily used to structure the layout of a webpage.

### Default Behavior

When multiple block elements appear one after another, each starts on its own line.

```text
+-----------------------------+
|         Header              |
+-----------------------------+

+-----------------------------+
|        Paragraph            |
+-----------------------------+

+-----------------------------+
|         Footer              |
+-----------------------------+
```

Each element occupies its own row.

---

## Syntax

```css
selector {
    display: block;
}
```

---

## Common Block Elements

The following HTML elements are block-level by default:

| Element | Purpose |
|----------|---------|
| `<div>` | Generic container |
| `<p>` | Paragraph |
| `<h1>`–`<h6>` | Headings |
| `<section>` | Content section |
| `<article>` | Independent content |
| `<header>` | Header section |
| `<footer>` | Footer section |
| `<main>` | Main page content |
| `<nav>` | Navigation |
| `<aside>` | Sidebar |

---

## Characteristics

Block elements:

- Start on a new line.
- Expand to the available width by default.
- Respect `width` and `height`.
- Support `margin` and `padding` on all sides.
- Can contain both block and inline elements (subject to HTML content rules).

---

## Example

### HTML

```html
<div>First Box</div>
<div>Second Box</div>
<div>Third Box</div>
```

### CSS

```css
div {
    border: 2px solid royalblue;
    padding: 10px;
}
```

Result:

```text
+---------------------+
| First Box           |
+---------------------+

+---------------------+
| Second Box          |
+---------------------+

+---------------------+
| Third Box           |
+---------------------+
```

Each `<div>` automatically begins on a new line.

---

## Changing an Inline Element to Block

Even inline elements can become block elements.

```html
<span>HTML</span>
<span>CSS</span>
<span>JavaScript</span>
```

```css
span {
    display: block;
}
```

Result:

```text
HTML

CSS

JavaScript
```

Each `<span>` now occupies its own line.

---

## Width Behavior

Without specifying a width:

```css
div {
    display: block;
}
```

The element stretches across the available horizontal space.

To limit its width:

```css
div {
    width: 300px;
}
```

---

## Advantages

- Easy to build page layouts.
- Supports explicit width and height.
- Ideal for sections, containers, and structural elements.
- Works naturally with the Box Model.

---

## Limitations

- Always starts on a new line.
- Cannot sit beside another block element without additional layout techniques (such as Flexbox, Grid, or other positioning methods).
- May occupy more horizontal space than necessary if no width is specified.

> 💡 **Pro Tip:** Use block elements for the main structure of your webpage—headers, sections, articles, sidebars, and containers are all natural candidates.

### 🌍 Real-World Usage

Block elements are commonly used for:

- Page headers
- Navigation sections
- Hero banners
- Content containers
- Blog posts
- Cards
- Footers

Almost every webpage begins with a hierarchy of block elements.

### 📌 Did You Know?

Even though block elements usually occupy the full available width, you can control their size using properties such as:

```css
width
max-width
min-width
```

This makes them highly flexible for responsive layouts.

### ⚠️ Important

A block element's default width is typically **`auto`**, which means it expands to fill the available horizontal space in its containing block.

It does **not** automatically become `100%`; instead, the browser calculates the width based on the available space.

### 🎯 Interview Insight

A common interview question is:

> **What are the characteristics of a block element?**

A strong answer is:

- Starts on a new line.
- Occupies the available width by default.
- Supports width and height.
- Supports margins and padding.
- Commonly used for page structure and layout.


---


## Inline Elements

An **inline element** flows **within a line of text** and occupies **only the space required by its content**.

Unlike block elements, inline elements do **not** start on a new line.

They are commonly used to style or mark up small portions of text within a larger block of content.

---

## Default Behavior

Multiple inline elements appear on the same line if there is enough horizontal space.

```text
HTML   CSS   JavaScript
```

Instead of:

```text
HTML

CSS

JavaScript
```

---

## Syntax

```css
selector {
    display: inline;
}
```

---

## Common Inline Elements

The following HTML elements are inline by default:

| Element | Purpose |
|----------|---------|
| `<span>` | Generic inline container |
| `<a>` | Hyperlink |
| `<strong>` | Strong importance |
| `<em>` | Emphasized text |
| `<b>` | Bold text |
| `<i>` | Italic text |
| `<code>` | Inline code |
| `<small>` | Smaller text |
| `<mark>` | Highlighted text |
| `<label>` | Form label |

---

## Characteristics

Inline elements:

- Stay on the same line whenever possible.
- Occupy only the space required by their content.
- Do **not** start on a new line.
- Ignore `width` and `height` in normal layout.
- Support horizontal padding and margins.
- Can have vertical padding and borders, but they generally do not affect line placement the way block elements do.

---

## Example

### HTML

```html
<span>HTML</span>
<span>CSS</span>
<span>JavaScript</span>
```

### CSS

```css
span {
    border: 1px solid royalblue;
    padding: 5px;
}
```

Result:

```text
+----+  +---+  +-----------+
|HTML|  |CSS|  |JavaScript |
+----+  +---+  +-----------+
```

All three elements remain on the same line.

---

## Width and Height

Consider:

```css
span {
    width: 300px;
    height: 100px;
}
```

These properties generally have **no effect** on a normal inline element's layout.

This is one of the biggest differences between **block** and **inline** elements.

---

## Converting a Block Element to Inline

Even block elements can become inline.

```html
<div>HTML</div>
<div>CSS</div>
<div>JavaScript</div>
```

```css
div {
    display: inline;
}
```

Result:

```text
HTML CSS JavaScript
```

The `<div>` elements now flow on the same line.

---

## Advantages

- Ideal for styling text within paragraphs.
- Occupies only the required space.
- Flows naturally with surrounding content.
- Useful for links, labels, and inline formatting.

---

## Limitations

- Does not start on a new line.
- `width` and `height` generally do not affect normal inline layout.
- Not suitable for building larger page structures.

> 💡 **Pro Tip:** Use inline elements for **content inside a sentence**, not for creating page sections or containers.

### 🌍 Real-World Usage

Inline elements are commonly used for:

- Hyperlinks
- Highlighted words
- Bold and italic text
- Inline code snippets
- Form labels
- Icons placed within text

They enhance or annotate content without interrupting the flow of the document.

### 📌 Did You Know?

Many interactive elements, such as links (`<a>`), are inline by default. Developers often change them to `inline-block` or `block` when they need additional layout control, such as setting dimensions or creating larger clickable areas.

### ⚠️ Important

Although inline elements can have padding and borders, using large vertical values may affect the appearance of surrounding text because they remain part of the same line formatting context.

### 🎯 Interview Insight

A common interview question is:

> **What are the characteristics of an inline element?**

A strong answer is:

- Does not start on a new line.
- Occupies only the space required by its content.
- Flows with surrounding text.
- Generally ignores `width` and `height`.
- Commonly used for styling or marking up text within larger content.