## Table of Contents

- [Introduction](#introduction)
- [HTML Tag Syntax](#html-tag-syntax)
- [Types of HTML Tags](#types-of-html-tags)
  - [Container (Paired) Tags](#1-container-paired-tags)
  - [Empty (Void) Tags](#2-empty-void-tags)
- [Nested HTML Tags](#nested-html-tags)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


# HTML Tags

## Introduction

HTML tags are special keywords enclosed in angle brackets (`< >`) that define the structure and content of a webpage. Web browsers read these tags to understand how different parts of a webpage should be displayed.

Almost everything in an HTML document is created using HTML tags. They define elements such as headings, paragraphs, images, links, lists, tables, and many other components.


---


## HTML Tag Syntax

Most HTML tags consist of:

- An opening tag
- Content
- A closing tag

### Syntax

```html
<tagname>Content</tagname>
```

### Example

```html
<h1>Welcome to HTML</h1>

<p>This is a paragraph.</p>
```

In the example above:

- `<h1>` is the opening tag.
- `</h1>` is the closing tag.
- `Welcome to HTML` is the content.

Similarly,

- `<p>` starts a paragraph.
- `</p>` ends the paragraph.
- The text between them is the paragraph content.


---


## Types of HTML Tags

HTML tags can be categorized into two main types.

### 1. Container (Paired) Tags

Container tags have both an opening tag and a closing tag.

### Syntax

```html
<tagname>Content</tagname>
```

### Example

```html
<p>This is a paragraph.</p>

<h1>Welcome</h1>
```

Examples of paired tags:

- `<html></html>`
- `<head></head>`
- `<title></title>`
- `<body></body>`
- `<p></p>`
- `<h1></h1>`

---

### 2. Empty (Void) Tags

Empty tags do not have closing tags because they do not contain any content.

### Examples

```html
<br>
<hr>
<img src="image.jpg" alt="Image">
<input type="text">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```


---


## Nested HTML Tags

HTML allows tags to be placed inside other tags. This is called **nesting**.

### Example

```html
<div>
    <h1>Welcome</h1>
    <p>This is a paragraph.</p>
</div>
```

In this example:

- `<div>` is the parent element.
- `<h1>` and `<p>` are child elements.

Proper nesting improves readability and ensures browsers interpret HTML correctly.


---


## Key Takeaways

- HTML tags define the structure of a webpage.
- Most tags consist of opening and closing tags.
- Empty (void) tags do not require closing tags.
- HTML tags can be nested inside one another.
- Proper nesting and indentation improve code readability and maintainability.


---


## References

- MDN Web Docs – HTML Elements
- WHATWG HTML Living Standard
- W3Schools HTML Tags Tutorial


---


## Quick Revision

| Topic | Description |
|--------|-------------|
| HTML Tag | A keyword enclosed in angle brackets used to define webpage structure. |
| Opening Tag | Marks the beginning of an element. |
| Closing Tag | Marks the end of an element. |
| Empty Tag | A tag that has no closing tag. |
| Nested Tags | Tags placed inside other tags. |

### Remember

- Most HTML tags have opening and closing tags.
- Empty tags do not contain content.
- Always close paired tags properly.
- Maintain proper nesting and indentation.


---


## Best Practices

- Use lowercase tag names.
- Properly indent nested elements.
- Always close paired tags.
- Write semantic HTML whenever possible.
- Keep HTML code organized and readable.
- Validate your HTML regularly.


---


## Common Mistakes

### Forgetting Closing Tags

❌ Incorrect

```html
<p>Hello World
```

✅ Correct

```html
<p>Hello World</p>
```

---

### Improper Nesting

❌ Incorrect

```html
<p><strong>Hello</p></strong>
```

✅ Correct

```html
<p><strong>Hello</strong></p>
```

---

### Using Deprecated Tags

❌ Incorrect

```html
<center>Hello</center>
```

✅ Correct

Use CSS for styling and alignment instead of deprecated HTML tags.


---


## Interview Questions

### Basic

1. What is an HTML tag?
2. What is the difference between an opening and closing tag?
3. What are empty (void) tags?
4. Give examples of paired tags.
5. Why are HTML tags important?

### Intermediate

6. What is nested HTML?
7. Why is proper nesting important?
8. What happens if closing tags are omitted?
9. Name five HTML empty tags.
10. What are deprecated HTML tags?


---


## Practice Exercises

### Exercise 1

Create a webpage using:

- `<html>`
- `<head>`
- `<title>`
- `<body>`

---

### Exercise 2

Write HTML using:

- One heading
- Two paragraphs
- One horizontal rule
- One line break

---

### Exercise 3

Create a nested structure using:

```html
<div>
    <h2>Heading</h2>
    <p>Paragraph</p>
</div>
```

---

### Challenge

Build a simple webpage that demonstrates:

- Paired tags
- Empty tags
- Proper nesting
- Correct indentation


---


## Related Topics

### Previous Topics

- [HTML Basics](01-html-basics.md)
- [HTML Page Structure](02-page-structure.md)
- [HTML Comments](03-comments.md)

### Next Topics

- [HTML Elements](05-elements.md)
- [HTML Attributes](06-attributes.md)
- [HTML ID and Classes](07-id-classes.md)
- [Inline and Block Elements](08-inline-block-elements.md)