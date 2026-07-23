# HTML Page Structure

## Introduction

Every HTML document follows a standard structure that helps web browsers understand and render the page correctly.

## Basic HTML Structure

```html
<!DOCTYPE html>
<html>
<head>
    <title>Document</title>
</head>
<body>
    <!-- Content goes here -->
</body>
</html>
```


## Components of an HTML Document

### 1. `<!DOCTYPE html>`

- Declares that the document uses HTML5.
- Helps browsers render the page in standards mode.

### 2. `<html>`

- The root element of an HTML document.
- Contains all other HTML elements.

### 3. `<head>`

- Stores metadata about the document.
- Includes links to CSS, JavaScript, icons, and other resources.

### 4. `<title>`

- Defines the page title displayed in the browser tab.

### 5. `<body>`

- Contains all visible content such as headings, paragraphs, images, links, tables, forms, and more.


## 📑 Table of Contents

- Introduction
- Basic HTML Structure
- Components of an HTML Document
  - `<!DOCTYPE html>`
  - `<html>`
  - `<head>`
  - `<title>`
  - `<body>`
- Key Takeaways
- References



---

## ✅ Best Practices

- Always start an HTML document with `<!DOCTYPE html>`.
- Keep the document structure in the correct order: `html` → `head` → `body`.
- Include a meaningful `<title>` for every web page.
- Store metadata, stylesheets, and scripts inside the `<head>` section.
- Place only visible content inside the `<body>` section.
- Use proper indentation to improve readability and maintenance.



---

## ❌ Common Mistakes

- Forgetting to include `<!DOCTYPE html>`, which may cause browsers to use quirks mode.
- Placing visible content inside the `<head>` section instead of the `<body>`.
- Omitting the `<title>` tag, making the page less user-friendly and less SEO-friendly.
- Incorrectly nesting HTML elements.
- Forgetting to close elements that require closing tags.
- Writing poorly indented HTML, making the code difficult to read and maintain.



---

## 📝 Quick Revision

- Every HTML document begins with `<!DOCTYPE html>`.
- The `<html>` element is the root of the document.
- The `<head>` section contains metadata and resources.
- The `<title>` element defines the text shown in the browser tab.
- The `<body>` section contains all visible content displayed on the web page.
- A proper document structure improves readability, maintainability, and browser compatibility.



---

## 💼 Interview Questions

### 1. Why is `<!DOCTYPE html>` important?
**Answer:** It tells the browser that the document uses HTML5 and helps render the page in standards mode.

### 2. What is the purpose of the `<head>` element?
**Answer:** It contains metadata, links to stylesheets, scripts, the page title, and other resources that are not directly displayed.

### 3. What is the difference between the `<head>` and `<body>` elements?
**Answer:** The `<head>` contains document metadata, while the `<body>` contains the visible content shown to users.

### 4. What is the purpose of the `<title>` tag?
**Answer:** It defines the title displayed in the browser tab and is also used by search engines and bookmarks.

### 5. Which element is the root element of an HTML document?
**Answer:** The `<html>` element.



---

## 💻 Practice Exercises

### Exercise 1
Write the basic structure of an HTML5 document from memory.

---

### Exercise 2
Explain the purpose of each of these elements:
- `<!DOCTYPE html>`
- `<html>`
- `<head>`
- `<title>`
- `<body>`

---

### Exercise 3
Create an HTML page with:
- A meaningful page title
- One heading
- One paragraph

---

### Exercise 4
Identify and correct the errors in an HTML document with misplaced elements.

---

### Exercise 5
Why should visible content be placed inside the `<body>` element instead of the `<head>` element?



---

## 🔗 Related Topics

Build on your understanding of HTML with these topics:

### Previous
- [HTML Basics](01-html-basics.md)

### Next
- [HTML Comments](03-comments.md)
- [HTML Tags](04-tags.md)
- [HTML Elements](05-elements.md)
- [HTML Attributes](06-attributes.md)
- [HTML ID and Classes](07-id-classes.md)
- [Inline vs Block Elements](08-inline-block-elements.md)