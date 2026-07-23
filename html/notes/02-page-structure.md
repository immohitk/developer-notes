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