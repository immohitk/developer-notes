# HTML Attributes

## Introduction

HTML attributes provide additional information about HTML elements. They modify an element's behavior, appearance, or functionality by supplying extra details that are not part of the element's content.

Attributes are written inside an element's opening tag as **name-value pairs**. Different HTML elements support different attributes depending on their purpose.

For example, an `<img>` element uses the `src` attribute to specify the image location, while an `<a>` element uses the `href` attribute to specify the destination of a hyperlink.

Understanding HTML attributes is essential because they enable developers to create interactive, accessible, and well-structured web pages.


---


## What are HTML Attributes?

HTML attributes provide additional information about HTML elements. They define or modify an element's behavior, appearance, or functionality.

Attributes are always specified in the **opening tag** of an HTML element and are usually written as **name-value pairs**.

### Example

```html
<a href="https://example.com">Visit Website</a>
```

In this example:

- `<a>` is the opening tag.
- `href` is the attribute name.
- `https://example.com` is the attribute value.
- `Visit Website` is the content of the element.

The `href` attribute tells the browser where the hyperlink should navigate when clicked.

---

### Another Example

```html
<img src="profile.jpg" alt="Profile Picture">
```

Here:

- `src` specifies the path of the image.
- `alt` provides alternative text if the image cannot be displayed and improves accessibility.

---

### Why Do We Use HTML Attributes?

HTML attributes are used to:

- Provide additional information about an element.
- Configure an element's behavior.
- Improve accessibility.
- Add styling, identification, or functionality to elements.
- Supply values required by certain HTML elements.

Without attributes, many HTML elements would not function as intended.