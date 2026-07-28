# HTML Elements

## Introduction

HTML elements are the fundamental building blocks of an HTML document. They define the structure and content of a webpage, such as headings, paragraphs, links, images, tables, forms, and more.

An HTML element is created using HTML tags. While tags mark the beginning and end of an element, the element itself includes the opening tag, the content, and the closing tag (when applicable).

Understanding HTML elements is essential because every webpage is made up of different elements working together to display information in a structured and meaningful way.


---


## What is an HTML Element?

An HTML element is a complete unit of an HTML document. It is created using HTML tags and usually consists of:

- An opening tag
- The content
- A closing tag

### Syntax

```html
<tagname>Content</tagname>
```

### Example

```html
<p>This is a paragraph.</p>
```

In the example above:

- `<p>` is the opening tag.
- `This is a paragraph.` is the content.
- `</p>` is the closing tag.

Together, they form a complete **HTML element**.

Some HTML elements do not contain content and therefore do not require a closing tag. These are called **empty (void) elements**, which will be discussed later in this document.


---


## Structure of an HTML Element

A typical HTML element consists of three main parts:

1. Opening Tag
2. Content
3. Closing Tag

### Structure

```html
<tagname>Content</tagname>
```

### Example

```html
<h1>Welcome to HTML</h1>
```

Let's break it down:

| Part | Description |
|------|-------------|
| `<h1>` | Opening tag that marks the beginning of the element. |
| `Welcome to HTML` | The content displayed on the webpage. |
| `</h1>` | Closing tag that marks the end of the element. |

Together, these three parts form a complete HTML element.

### Another Example

```html
<a href="https://example.com">Visit Website</a>
```

Here:

- `<a href="https://example.com">` is the opening tag.
- `Visit Website` is the content.
- `</a>` is the closing tag.

The opening tag can also contain **attributes**, which provide additional information about the element. Attributes will be covered in a later topic.


---


## Types of HTML Elements

HTML elements can be broadly classified into two types:

1. Container (Normal) Elements
2. Empty (Void) Elements

### 1. Container (Normal) Elements

Container elements have:

- An opening tag
- Content
- A closing tag

These elements are used to wrap and display content on a webpage.

#### Syntax

```html
<tagname>Content</tagname>
```

#### Example

```html
<h1>Welcome</h1>

<p>This is a paragraph.</p>
```

In these examples:

- `<h1>` and `</h1>` form a heading element.
- `<p>` and `</p>` form a paragraph element.

---

### 2. Empty (Void) Elements

Empty elements do not contain any content and therefore do not require a closing tag.

These elements perform a specific task without enclosing any text or other elements.

#### Examples

```html
<br>
<hr>
<img src="image.jpg" alt="Sample Image">
<input type="text">
```

Common empty elements include:

- `<br>` – Inserts a line break.
- `<hr>` – Creates a horizontal line.
- `<img>` – Displays an image.
- `<input>` – Creates an input field.

> **Note:** Although empty elements do not have closing tags, some editors may display them as `<br />` or `<img />`. Both forms are commonly accepted in HTML5.


---


## Nested HTML Elements

HTML allows one element to be placed inside another element. This is called **nesting**.

Nested elements help organize webpage content into a hierarchical structure, making the HTML document easier to read, maintain, and understand.

### Example

```html
<div>
    <h1>Welcome</h1>
    <p>This is a paragraph inside a div element.</p>
</div>
```

In this example:

- `<div>` is the parent element.
- `<h1>` and `<p>` are child elements nested inside the `<div>` element.

---

### Multiple Levels of Nesting

HTML elements can be nested through multiple levels.

```html
<html>
    <body>
        <div>
            <p>Hello World!</p>
        </div>
    </body>
</html>
```

Here:

- `<html>` contains `<body>`.
- `<body>` contains `<div>`.
- `<div>` contains `<p>`.

This creates a parent-child relationship between elements.

---

### Rules for Proper Nesting

Always close the innermost element before closing its parent element.

✅ Correct

```html
<p>This is <strong>important</strong> text.</p>
```

❌ Incorrect

```html
<p>This is <strong>important</p></strong>
```

Improper nesting can lead to unexpected rendering and makes the code difficult to understand and maintain.