## Table of Contents

- [Introduction](#introduction)
- [Basic HTML Structure](#basic-html-structure)
- [Components of an HTML Document](#components-of-an-html-document)
  - [`<!DOCTYPE html>`](#doctype-html)
  - [`<html>`](#html)
  - [`<head>`](#head)
  - [`<title>`](#title)
  - [`<body>`](#body)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


# HTML Page Structure

## Introduction

Every HTML document follows a standard structure that helps web browsers understand and display web pages correctly.

A proper HTML structure improves readability, maintainability, browser compatibility, and provides a solid foundation for building websites.

Whether you're creating a simple webpage or a large web application, every HTML document should follow this basic structure.


---


## Basic HTML Structure

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Web Page</title>
</head>
<body>
    <h1>Welcome to HTML</h1>
    <p>This is my first web page.</p>
</body>
</html>
```

The above template represents the basic structure of an HTML5 document. Each element has a specific purpose and together they form the foundation of every web page.


---


## Components of an HTML Document

Every HTML document is made up of several important elements. Each element has a specific role in defining the structure and behavior of a web page.

### `<!DOCTYPE html>`

The `<!DOCTYPE html>` declaration tells the web browser that the document is written using **HTML5**.

Although it is not an HTML tag, it is required at the beginning of every HTML document to ensure the browser renders the page in **standards mode**.

---

### `<html>`

The `<html>` element is the **root element** of an HTML document.

All other HTML elements are placed inside the `<html>` element, making it the parent of the entire webpage.

---

### `<head>`

The `<head>` element contains information **about the webpage** that is not directly displayed in the browser.

It commonly includes:

- The page title
- Metadata
- Links to CSS files
- JavaScript files
- Icons and other resources

---

### `<title>`

The `<title>` element defines the title of the webpage.

The title is displayed:

- In the browser tab
- In bookmarks
- In search engine results

Every webpage should have a meaningful and descriptive title.

---

### `<body>`

The `<body>` element contains all the **visible content** displayed on a webpage.

Examples of content inside the `<body>` include:

- Headings
- Paragraphs
- Images
- Links
- Lists
- Tables
- Forms
- Videos
- Buttons

Everything that users see and interact with belongs inside the `<body>` element.


---


## Key Takeaways

- Every HTML document follows a standard structure.
- `<!DOCTYPE html>` tells the browser that the document uses HTML5.
- The `<html>` element is the root element of the document.
- The `<head>` section contains metadata and resources that are not displayed on the webpage.
- The `<title>` element defines the title shown in the browser tab.
- The `<body>` element contains all the visible content displayed to users.
- A well-structured HTML document improves readability, maintainability, and browser compatibility.


---


## References

To learn more about HTML document structure, refer to the following resources:

- **MDN Web Docs** – HTML Document Structure
- **WHATWG HTML Living Standard**
- **W3Schools HTML Tutorial**


---


## Quick Revision

| Element | Purpose |
|---------|---------|
| `<!DOCTYPE html>` | Declares that the document uses HTML5. |
| `<html>` | The root element that contains the entire HTML document. |
| `<head>` | Stores metadata, links to CSS, scripts, and the page title. |
| `<title>` | Sets the title displayed in the browser tab. |
| `<body>` | Contains all the visible content shown on the webpage. |

### Basic HTML Template

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Web Page</title>
</head>
<body>
    <h1>Welcome to HTML</h1>
    <p>This is my first web page.</p>
</body>
</html>
```

### Remember

- Every HTML page starts with `<!DOCTYPE html>`.
- There should be only one `<html>`, `<head>`, and `<body>` element in a document.
- Everything visible to users belongs inside the `<body>` element.
- Keep the document structure clean and properly indented for better readability.


---


## Best Practices

- Always start every HTML document with `<!DOCTYPE html>`.
- Use proper indentation to improve readability.
- Write meaningful titles for every webpage.
- Place metadata, CSS links, and JavaScript references inside the `<head>` element.
- Keep all visible content inside the `<body>` element.
- Close all HTML elements properly when required.
- Organize the document structure consistently across your project.
- Use semantic HTML elements whenever possible.


---


## Common Mistakes

❌ Forgetting to include `<!DOCTYPE html>`.

✅ Always declare the document type to ensure browsers render the page correctly.

---

❌ Placing visible content inside the `<head>` element.

✅ Only metadata and resources belong inside `<head>`.

---

❌ Forgetting the `<title>` element.

✅ Every webpage should have a descriptive title.

---

❌ Writing content outside the `<body>` element.

✅ All visible webpage content belongs inside `<body>`.

---

❌ Poor indentation.

✅ Proper indentation makes HTML easier to read and maintain.


---


## Interview Questions

### Basic

1. What is the purpose of `<!DOCTYPE html>`?
2. What is the root element of an HTML document?
3. What is the difference between `<head>` and `<body>`?
4. What information is stored inside the `<head>` element?
5. What is the purpose of the `<title>` element?

### Intermediate

6. What happens if `<!DOCTYPE html>` is omitted?
7. Can a webpage have multiple `<head>` elements?
8. Why is the `<title>` important for SEO?
9. Which HTML element contains the visible content?
10. Explain the basic structure of an HTML5 document.


---


## Practice Exercises

### Exercise 1

Create a basic HTML document containing:

- `<!DOCTYPE html>`
- `<html>`
- `<head>`
- `<title>`
- `<body>`

---

### Exercise 2

Create a webpage with:

- A heading
- Two paragraphs
- A descriptive page title

---

### Exercise 3

Identify and correct errors in an HTML document with missing structural elements.

---

### Challenge

Build a personal profile webpage using the correct HTML document structure.


---

## Related Topics

Continue learning with the following topics:

- [HTML Basics](01-html-basics.md)
- [HTML Comments](03-comments.md)
- [HTML Tags](04-tags.md)
- [HTML Elements](05-elements.md)
- [HTML Attributes](06-attributes.md)
- [HTML ID and Classes](07-id-classes.md)
- [Inline and Block Elements](08-inline-block-elements.md)