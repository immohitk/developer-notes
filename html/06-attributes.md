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


---


## Syntax of HTML Attributes

HTML attributes are written inside the **opening tag** of an HTML element. They are usually written as **name-value pairs**, where the attribute name is followed by an equals sign (`=`) and the value is enclosed in quotation marks.

### General Syntax

```html
<tagname attribute="value">Content</tagname>
```

### Example

```html
<a href="https://example.com">Visit Website</a>
```

In this example:

- `<a>` is the opening tag.
- `href` is the attribute name.
- `"https://example.com"` is the attribute value.
- `Visit Website` is the content of the element.

---

### Multiple Attributes

An HTML element can have more than one attribute.

```html
<img src="profile.jpg" alt="Profile Picture" width="200" height="200">
```

In this example:

- `src` specifies the image location.
- `alt` provides alternative text.
- `width` specifies the image width.
- `height` specifies the image height.

Attributes are separated by spaces.

---

### Rules for Writing Attributes

- Attributes are always written in the opening tag.
- Most attributes are written as **name-value pairs**.
- Attribute values should be enclosed in double quotation marks (`"`).
- An element can have multiple attributes.
- Each attribute should appear only once unless explicitly allowed by HTML.

---

### Example

```html
<input type="text" placeholder="Enter your name" required>
```

Here:

- `type="text"` defines the type of input.
- `placeholder="Enter your name"` displays a hint inside the input field.
- `required` is a boolean attribute that makes the field mandatory.

> **Note:** While quotation marks are optional for some simple attribute values in HTML5, it is considered a best practice to always enclose attribute values in quotation marks for better readability and consistency.


---


## Common HTML Attributes

HTML provides many attributes that add extra information and functionality to elements. Below are some of the most commonly used HTML attributes.

### `href`

The `href` attribute specifies the destination URL of a hyperlink.

**Example**

```html
<a href="https://example.com">Visit Website</a>
```

---

### `src`

The `src` attribute specifies the path or URL of an external resource, such as an image.

**Example**

```html
<img src="profile.jpg" alt="Profile Picture">
```

---

### `alt`

The `alt` attribute provides alternative text for an image if it cannot be displayed. It also improves accessibility for users who rely on screen readers.

**Example**

```html
<img src="profile.jpg" alt="Profile Picture">
```

---

### `id`

The `id` attribute assigns a unique identifier to an HTML element.

**Example**

```html
<h1 id="main-heading">Welcome</h1>
```

> The value of an `id` attribute must be unique within a webpage.

---

### `class`

The `class` attribute assigns one or more class names to an element. It is commonly used for applying CSS styles and selecting elements with JavaScript.

**Example**

```html
<p class="highlight">Learning HTML is fun!</p>
```

---

### `title`

The `title` attribute provides additional information about an element. This information is typically displayed as a tooltip when the user hovers over the element.

**Example**

```html
<p title="This is additional information.">
    Hover over this text.
</p>
```

---

### `style`

The `style` attribute is used to apply inline CSS styles directly to an element.

**Example**

```html
<p style="color: blue;">This text is blue.</p>
```

---

### `width` and `height`

The `width` and `height` attributes specify the dimensions of certain elements, such as images.

**Example**

```html
<img
    src="profile.jpg"
    alt="Profile Picture"
    width="200"
    height="200"
>
```

---

### Summary

| Attribute | Purpose | Commonly Used With |
|-----------|---------|--------------------|
| `href` | Specifies a hyperlink destination | `<a>` |
| `src` | Specifies the source of a resource | `<img>`, `<script>` |
| `alt` | Provides alternative text for images | `<img>` |
| `id` | Assigns a unique identifier | Most HTML elements |
| `class` | Assigns one or more class names | Most HTML elements |
| `title` | Provides additional information | Most HTML elements |
| `style` | Applies inline CSS | Most HTML elements |
| `width` | Specifies the width of an element | `<img>`, `<iframe>` |
| `height` | Specifies the height of an element | `<img>`, `<iframe>` |


---


## Global HTML Attributes

Global attributes are attributes that can be used with **most HTML elements**. They provide common functionality regardless of the element on which they are used.

### Common Global Attributes

| Attribute | Description |
|-----------|-------------|
| `id` | Assigns a unique identifier to an element. |
| `class` | Assigns one or more class names to an element. |
| `style` | Applies inline CSS styles to an element. |
| `title` | Provides additional information about an element, usually displayed as a tooltip. |
| `hidden` | Hides an element from the webpage. |
| `tabindex` | Controls the order in which elements receive keyboard focus. |
| `draggable` | Specifies whether an element can be dragged. |

---

### `id`

The `id` attribute uniquely identifies an HTML element within a webpage.

```html
<h1 id="main-heading">Welcome</h1>
```

> Each `id` value should be unique within a webpage.

---

### `class`

The `class` attribute assigns one or more class names to an element.

```html
<p class="highlight">Learning HTML is fun!</p>
```

Multiple elements can share the same class name.

---

### `style`

The `style` attribute applies inline CSS directly to an element.

```html
<p style="color: blue;">This text is blue.</p>
```

---

### `title`

The `title` attribute provides additional information about an element.

```html
<button title="Click to submit the form">
    Submit
</button>
```

The information is usually displayed as a tooltip when the user hovers over the element.

---

### `hidden`

The `hidden` attribute hides an element from the webpage.

```html
<p hidden>This paragraph is hidden.</p>
```

---

### `tabindex`

The `tabindex` attribute specifies the keyboard navigation order.

```html
<input type="text" tabindex="1">
<button tabindex="2">Submit</button>
```

---

### `draggable`

The `draggable` attribute specifies whether an element can be dragged.

```html
<img
    src="logo.png"
    alt="Company Logo"
    draggable="true"
>
```

---

### Example

```html
<p
    id="intro"
    class="highlight"
    title="Introduction"
    style="color: green;"
>
    Welcome to HTML!
</p>
```

This example demonstrates how multiple global attributes can be applied to a single HTML element.


---


## Boolean HTML Attributes

Boolean attributes are HTML attributes whose presence indicates that the attribute is **true**. Unlike most HTML attributes, they do not require a value.

If a boolean attribute is present, the browser treats it as enabled. If it is omitted, the browser treats it as disabled or false.

### Syntax

```html
<element attribute>
```

or

```html
<element attribute="attribute">
```

Both forms are valid in HTML.

---

### Common Boolean Attributes

| Attribute | Description |
|-----------|-------------|
| `required` | Makes a form field mandatory. |
| `disabled` | Disables an element, preventing user interaction. |
| `checked` | Pre-selects a checkbox or radio button. |
| `readonly` | Makes an input field read-only. |
| `selected` | Pre-selects an option in a dropdown list. |
| `autofocus` | Automatically focuses an element when the page loads. |

---

### `required`

The `required` attribute makes a form field mandatory.

```html
<input type="text" required>
```

The user must provide a value before submitting the form.

---

### `disabled`

The `disabled` attribute prevents the user from interacting with an element.

```html
<button disabled>Submit</button>
```

The button cannot be clicked.

---

### `checked`

The `checked` attribute pre-selects a checkbox or radio button.

```html
<input type="checkbox" checked>
```

The checkbox is selected when the page loads.

---

### `readonly`

The `readonly` attribute allows users to view an input field but prevents them from modifying its value.

```html
<input type="text" value="John Doe" readonly>
```

---

### `selected`

The `selected` attribute pre-selects an option in a dropdown list.

```html
<select>
    <option>HTML</option>
    <option selected>CSS</option>
    <option>JavaScript</option>
</select>
```

The **CSS** option is selected by default.

---

### `autofocus`

The `autofocus` attribute automatically places the cursor inside an element when the page loads.

```html
<input type="text" autofocus>
```

---

### Example

```html
<form>
    <input
        type="text"
        placeholder="Enter your name"
        required
        autofocus
    >

    <input
        type="checkbox"
        checked
    >

    <button disabled>
        Submit
    </button>
</form>
```

This example demonstrates several boolean attributes used together in a form.