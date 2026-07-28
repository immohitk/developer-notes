## Table of Contents

- [Introduction](#introduction)
- [What is an HTML Element?](#what-is-an-html-element)
- [Structure of an HTML Element](#structure-of-an-html-element)
- [Types of HTML Elements](#types-of-html-elements)
- [Nested HTML Elements](#nested-html-elements)
- [Empty HTML Elements](#empty-html-elements)
- [HTML Tags vs HTML Elements](#html-tags-vs-html-elements)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


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


---


## Empty HTML Elements

Empty HTML elements, also known as **void elements**, are elements that do not contain any content. Since they have nothing to enclose, they do not require a closing tag.

Unlike container elements, empty elements perform a specific function without wrapping any text or other HTML elements.

### Syntax

```html
<tagname>
```

### Example

```html
<br>

<hr>

<img src="profile.jpg" alt="Profile Image">

<input type="text">
```

---

### Common Empty HTML Elements

| Element | Purpose |
|---------|---------|
| `<br>` | Inserts a line break. |
| `<hr>` | Inserts a horizontal rule. |
| `<img>` | Displays an image. |
| `<input>` | Creates an input field. |
| `<meta>` | Provides metadata about the webpage. |
| `<link>` | Links external resources such as CSS files. |

---

### Example

```html
<h1>Student Profile</h1>

<img src="student.jpg" alt="Student Photo">

<br>

<input type="text" placeholder="Enter your name">

<hr>

<p>Thank you for visiting.</p>
```

---

### Important Points

- Empty elements do not have closing tags.
- They cannot contain text or other HTML elements.
- They are used to perform specific tasks such as inserting images, creating input fields, or adding line breaks.
- Some code editors may automatically write empty elements as `<br />` or `<img />`. Both styles are commonly accepted in HTML5.


---


## HTML Tags vs HTML Elements

Although the terms **HTML tags** and **HTML elements** are often used interchangeably, they have different meanings.

### HTML Tag

An HTML tag is the markup enclosed within angle brackets (`< >`). Tags tell the browser where an element begins or ends.

Examples:

```html
<p>

</p>

<h1>

</h1>
```

The examples above are **HTML tags**.

---

### HTML Element

An HTML element is the complete structure formed by:

- Opening tag
- Content
- Closing tag

Example:

```html
<p>This is a paragraph.</p>
```

In this example:

- `<p>` is the opening tag.
- `This is a paragraph.` is the content.
- `</p>` is the closing tag.

Together, they form an **HTML element**.

---

### Comparison

| HTML Tag | HTML Element |
|----------|--------------|
| A tag is enclosed within angle brackets (`< >`). | An element is the complete unit consisting of tags and content. |
| Tags define the beginning or end of an element. | Elements define the structure and content of a webpage. |
| Tags alone do not display content. | Elements can display content on a webpage. |
| Example: `<h1>` or `</h1>` | Example: `<h1>Welcome</h1>` |

---

### Quick Example

```html
<h2>HTML Tutorial</h2>
```

Here:

- `<h2>` → Opening tag
- `HTML Tutorial` → Content
- `</h2>` → Closing tag
- `<h2>HTML Tutorial</h2>` → HTML element

---

### Remember

- Every HTML element is created using HTML tags.
- A tag is only a part of an HTML element.
- Most HTML elements consist of an opening tag, content, and a closing tag.
- Empty (void) elements contain only a single tag because they do not have any content.


---


## Key Takeaways

- HTML elements are the building blocks of every HTML document.
- An HTML element usually consists of an opening tag, content, and a closing tag.
- HTML elements define the structure and content of a webpage.
- HTML elements are classified into container (normal) elements and empty (void) elements.
- Nested elements create a hierarchical structure that improves organization and readability.
- Empty elements do not contain content and therefore do not require closing tags.
- HTML tags and HTML elements are related but are not the same thing.
- Proper nesting and indentation make HTML code easier to read and maintain.


---


## References

To learn more about HTML elements, refer to the following resources:

- **MDN Web Docs** – HTML Elements
- **WHATWG HTML Living Standard**
- **W3Schools HTML Elements Tutorial**


---


## Quick Revision

### HTML Elements at a Glance

- HTML elements are the building blocks of a webpage.
- A typical HTML element consists of:
  - Opening tag
  - Content
  - Closing tag
- Some elements are **container (normal) elements**, while others are **empty (void) elements**.
- Empty elements do not contain content and therefore do not have closing tags.
- HTML elements can be nested inside one another to create a hierarchical document structure.
- Proper nesting improves code readability and ensures correct rendering by browsers.
- An **HTML tag** is part of an HTML element, whereas an **HTML element** is the complete structure.

### Example

```html
<p>Hello, World!</p>
```

| Part | Description |
|------|-------------|
| `<p>` | Opening tag |
| `Hello, World!` | Content |
| `</p>` | Closing tag |
| `<p>Hello, World!</p>` | HTML element |

### Revision Checklist

- ✅ Understand what an HTML element is.
- ✅ Know the structure of an HTML element.
- ✅ Differentiate between container and empty elements.
- ✅ Understand nested HTML elements.
- ✅ Distinguish HTML tags from HTML elements.


---


## Best Practices

Follow these best practices when working with HTML elements:

### 1. Use Proper Nesting

Always close the innermost element before closing its parent element.

✅ Correct

```html
<p>This is <strong>important</strong> text.</p>
```

❌ Incorrect

```html
<p>This is <strong>important</p></strong>
```

---

### 2. Use Semantic HTML Elements

Choose elements based on their meaning instead of their appearance.

✅ Good

```html
<header>
<nav>
<main>
<section>
<footer>
```

Instead of using multiple generic `<div>` elements everywhere.

---

### 3. Write Properly Indented Code

Indent nested elements consistently to improve readability.

```html
<div>
    <h2>Profile</h2>
    <p>Welcome to my website.</p>
</div>
```

---

### 4. Provide Required Attributes

Some HTML elements require important attributes.

Example:

```html
<img src="profile.jpg" alt="Profile Picture">
```

Always include the `alt` attribute for images to improve accessibility.

---

### 5. Avoid Unnecessary Nesting

Keep your HTML structure as simple as possible.

❌ Avoid

```html
<div>
    <div>
        <div>
            <p>Hello</p>
        </div>
    </div>
</div>
```

✅ Better

```html
<div>
    <p>Hello</p>
</div>
```

---

### 6. Keep HTML Clean and Readable

- Use meaningful indentation.
- Remove unused elements.
- Keep related elements grouped together.
- Write consistent and well-formatted code.

Following these practices makes HTML easier to understand, debug, and maintain.


---


## Common Mistakes

Below are some common mistakes beginners make when working with HTML elements.

### 1. Incorrect Nesting

❌ Incorrect

```html
<p>This is <strong>important</p></strong>
```

✅ Correct

```html
<p>This is <strong>important</strong></p>
```

Always close the innermost element before closing its parent element.

---

### 2. Forgetting Closing Tags

❌ Incorrect

```html
<h1>Welcome
<p>This is a paragraph.
```

✅ Correct

```html
<h1>Welcome</h1>
<p>This is a paragraph.</p>
```

Most HTML elements require both opening and closing tags.

---

### 3. Adding Closing Tags to Empty Elements

❌ Incorrect

```html
<br></br>

<img src="image.jpg"></img>
```

✅ Correct

```html
<br>

<img src="image.jpg" alt="Sample Image">
```

Empty (void) elements do not have closing tags.

---

### 4. Confusing Tags with Elements

❌ Incorrect Statement

> "`<p>` is an HTML element."

✅ Correct Statement

> "`<p>` is an HTML tag, while `<p>Hello</p>` is an HTML element."

Understanding this distinction helps you use HTML terminology correctly.

---

### 5. Poor Code Formatting

❌ Difficult to Read

```html
<div><h2>About</h2><p>Welcome</p></div>
```

✅ Better

```html
<div>
    <h2>About</h2>
    <p>Welcome</p>
</div>
```

Proper indentation improves readability and makes debugging easier.

---

### 6. Overusing Generic Elements

❌ Avoid using `<div>` for everything.

Whenever appropriate, use semantic HTML elements such as:

```html
<header>
<nav>
<main>
<section>
<article>
<footer>
```

Semantic elements make your HTML more meaningful and easier to understand.


---


## Interview Questions

### Beginner Level

1. What is an HTML element?

2. What are the parts of an HTML element?

3. What is the difference between an HTML tag and an HTML element?

4. What are container (normal) elements?

5. What are empty (void) elements?

6. Why don't empty elements have closing tags?

7. What is meant by nested HTML elements?

8. Why is proper nesting important in HTML?

9. Name five commonly used empty HTML elements.

10. Which part of an HTML element can contain attributes?

---

### Intermediate Level

1. Explain the difference between container elements and empty elements with examples.

2. What happens if HTML elements are not properly nested?

3. Why is indentation important when writing HTML?

4. How does the browser handle incorrectly nested HTML elements?

5. Why is the `alt` attribute important for the `<img>` element?

6. What is the purpose of semantic HTML elements?

7. Can an HTML element exist without content? Explain with an example.

8. Why are HTML elements considered the building blocks of a webpage?

---

### Practical Questions

1. Write an HTML element that displays a heading.

2. Create a paragraph element containing any text.

3. Write an HTML example demonstrating nested elements.

4. Add an image using the `<img>` element.

5. Create a simple HTML snippet that contains both container and empty elements.

6. Explain the difference between the following:

```html
<p>
```

and

```html
<p>Hello World!</p>
```


---


## Practice Exercises

Try the following exercises to strengthen your understanding of HTML elements.

### Exercise 1: Create Basic Elements

Create an HTML page that contains:

- A heading
- A paragraph
- A horizontal line
- A line break

**Expected elements:**

- `<h1>`
- `<p>`
- `<hr>`
- `<br>`

---

### Exercise 2: Practice Nested Elements

Create the following structure:

```html
<div>
    <h2>My Profile</h2>
    <p>I am learning HTML.</p>
</div>
```

Identify:

- Parent element
- Child elements

---

### Exercise 3: Container vs Empty Elements

Classify the following as **Container** or **Empty** elements:

- `<p>`
- `<img>`
- `<hr>`
- `<div>`
- `<input>`
- `<section>`
- `<br>`

---

### Exercise 4: Identify the Mistakes

Find and correct the errors in the following code:

```html
<p>This is <strong>important</p></strong>

<img src="photo.jpg"></img>
```

---

### Exercise 5: Tag or Element?

Identify whether each of the following is an **HTML Tag** or an **HTML Element**.

| Example | Answer |
|---------|--------|
| `<p>` | ? |
| `</h1>` | ? |
| `<h2>Welcome</h2>` | ? |
| `<img>` | ? |
| `<div><p>Hello</p></div>` | ? |

---

### Exercise 6: Build a Simple Webpage

Create a webpage that includes:

- One heading
- Two paragraphs
- One image
- One horizontal rule
- One line break
- A nested `<div>` containing a heading and a paragraph

Ensure your HTML code is:

- Properly nested
- Well-indented
- Easy to read


---


## Related Topics

If you've understood HTML elements, the following topics are the natural next steps in your HTML learning journey:

### Previously Covered

- HTML Basics
- HTML Page Structure
- HTML Comments
- HTML Tags

### Continue Learning

- HTML Attributes
- HTML ID and Class Attributes
- Inline vs Block Elements
- Lists (`<ul>`, `<ol>`, `<li>`)
- Links (`<a>`)
- Images (`<img>`)
- Tables
- Forms
- Semantic HTML
- HTML Entities

---

### Learning Path

```text
HTML Basics
        ↓
HTML Page Structure
        ↓
HTML Comments
        ↓
HTML Tags
        ↓
HTML Elements
        ↓
HTML Attributes
        ↓
ID & Class
        ↓
Inline vs Block Elements
        ↓
Lists, Links & Images
        ↓
Tables & Forms
        ↓
Semantic HTML
```

> **Tip:** A strong understanding of HTML elements makes learning attributes, forms, tables, and semantic HTML much easier because almost every HTML feature is built around elements.