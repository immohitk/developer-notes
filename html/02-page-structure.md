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