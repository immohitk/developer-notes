# HTML Inline and Block Elements

## Introduction

When building web pages with HTML, it is important to understand how elements are displayed by default. Some elements occupy the entire available width of a page, while others only take up the space required by their content.

HTML elements are generally categorized into two display types:

- **Block elements**
- **Inline elements**

Knowing the difference between these two types helps you create well-structured layouts, apply CSS effectively, and build more readable and maintainable web pages.

In this chapter, you will learn:

- What block elements are.
- What inline elements are.
- The differences between block and inline elements.
- Common examples of each type.
- Best practices for using them appropriately.


---


## What are Block Elements?

A **block element** is an HTML element that starts on a new line and, by default, occupies the full width available within its parent container.

Because block elements take up the entire available width, the next element is displayed on a new line.

### Characteristics of Block Elements

- Always start on a new line.
- Occupy the full available width by default.
- Can contain inline elements and, in many cases, other block elements.
- Commonly used to define the structure and layout of a webpage.

### Basic Syntax

```html
<tag>
    Content
</tag>
```

### Example

```html
<h1>Welcome to My Website</h1>

<p>This is a paragraph.</p>

<div>This is a division.</div>
```

**Output Behavior:**

- The `<h1>` appears on its own line.
- The `<p>` starts on a new line below the heading.
- The `<div>` starts on a new line below the paragraph.

Each element is displayed one after another vertically.

### Common Block Elements

Some commonly used block elements include:

- `<div>`
- `<p>`
- `<h1>` to `<h6>`
- `<section>`
- `<article>`
- `<header>`
- `<footer>`
- `<main>`
- `<nav>`
- `<aside>`
- `<form>`
- `<ul>`
- `<ol>`
- `<li>`
- `<table>`
- `<hr>`

### Example with Multiple Block Elements

```html
<header>
    Website Header
</header>

<main>
    <section>
        <h2>About Us</h2>

        <p>
            Welcome to our website.
        </p>
    </section>
</main>

<footer>
    Copyright © 2026
</footer>
```

Each block element begins on a new line, creating a clear vertical structure for the webpage.


---


## What are Inline Elements?

An **inline element** is an HTML element that does not start on a new line and only occupies the width required by its content.

Unlike block elements, multiple inline elements can appear on the same line if there is enough horizontal space.

### Characteristics of Inline Elements

- Do not start on a new line.
- Occupy only the width required by their content.
- Appear side by side when space is available.
- Commonly used to format or emphasize text within block elements.
- Generally cannot contain block elements.

### Basic Syntax

```html
<tag>Content</tag>
```

### Example

```html
<p>
    This is <strong>important</strong> and
    <em>emphasized</em> text.
</p>
```

**Output Behavior:**

- The paragraph (`<p>`) is a block element.
- The `<strong>` element appears within the same line as the surrounding text.
- The `<em>` element also remains on the same line.
- None of the inline elements force a new line.

### Common Inline Elements

Some commonly used inline elements include:

- `<span>`
- `<a>`
- `<strong>`
- `<em>`
- `<b>`
- `<i>`
- `<u>`
- `<small>`
- `<mark>`
- `<code>`
- `<sup>`
- `<sub>`
- `<br>`
- `<img>`

### Example with Multiple Inline Elements

```html
<p>
    Learn <strong>HTML</strong>,
    <em>CSS</em>, and
    <a href="#">JavaScript</a>
    to become a web developer.
</p>
```

In this example, the `<strong>`, `<em>`, and `<a>` elements all appear within the same line of text because they are inline elements.


---


## Difference Between Block and Inline Elements

Although both block and inline elements are used to create HTML documents, they behave differently when displayed in a web browser.

### Comparison Table

| Feature | Block Elements | Inline Elements |
|---------|----------------|-----------------|
| Starts on a new line | Yes | No |
| Width | Occupies the full available width by default | Occupies only the width required by its content |
| Layout | Stacks vertically | Appears side by side when space is available |
| Can contain other elements | Can contain inline elements and, in many cases, other block elements | Generally contains text or other inline elements |
| Common Use | Structure and layout | Formatting and styling content within a line |

---

### Example

```html
<h1>Welcome</h1>

<p>
    Learn <strong>HTML</strong> and
    <a href="#">CSS</a>.
</p>

<div>This is a block element.</div>
```

In this example:

- `<h1>`, `<p>`, and `<div>` are **block elements**, so each starts on a new line.
- `<strong>` and `<a>` are **inline elements**, so they appear within the same line as the surrounding text.

---

### Visual Representation

```text
Block Elements

+------------------------------+
| Heading                      |
+------------------------------+

+------------------------------+
| Paragraph                    |
+------------------------------+

+------------------------------+
| Division                     |
+------------------------------+


Inline Elements

This is <strong>important</strong> and <a>click here</a>.
```

Block elements create the overall structure of a webpage, while inline elements are used to format or enhance content within that structure.

---

### When to Use Block Elements

Use block elements when you want to:

- Create sections of a webpage.
- Organize content into distinct areas.
- Build the overall layout of a document.
- Separate content vertically.

---

### When to Use Inline Elements

Use inline elements when you want to:

- Format text.
- Add links.
- Highlight or emphasize content.
- Display images within text.
- Modify a small portion of existing content.

---

### Summary

- Block elements create the structural layout of a webpage.
- Inline elements format or enhance content within that layout.
- Understanding the difference helps you write cleaner, more organized, and maintainable HTML.