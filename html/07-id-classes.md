# HTML ID and Classes

## Introduction

The `id` and `class` attributes are two of the most commonly used global attributes in HTML. They help identify and organize HTML elements, making it easier to apply styles with CSS and interact with elements using JavaScript.

The `id` attribute uniquely identifies a single HTML element within a webpage, while the `class` attribute groups one or more elements that share similar characteristics or styles.

Understanding the difference between `id` and `class` is important because both attributes play a significant role in creating well-structured, maintainable, and reusable web pages.


---


## What is the `id` Attribute?

The `id` attribute is a **global HTML attribute** that assigns a **unique identifier** to an HTML element.

Each `id` value must be unique within a webpage, meaning no two elements should have the same `id`.

The `id` attribute is commonly used for:

- Identifying a specific HTML element.
- Applying CSS styles to a single element.
- Selecting an element using JavaScript.
- Creating internal page links.

### Syntax

```html
<element id="unique-id">
    Content
</element>
```

### Example

```html
<h1 id="main-heading">
    Welcome to My Website
</h1>
```

In this example:

- `id` is the attribute name.
- `main-heading` is the unique identifier.
- The `<h1>` element can now be uniquely referenced using CSS or JavaScript.

---

### Another Example

```html
<section id="about">
    <h2>About Me</h2>
    <p>I am learning HTML.</p>
</section>
```

Here, the `section` element has a unique identifier named `about`.

---

### Characteristics of the `id` Attribute

- An `id` value must be unique within a webpage.
- An element can have only one `id` attribute.
- Different elements cannot share the same `id` value.
- The `id` attribute can be used with most HTML elements because it is a global attribute.

---

### Example with CSS

```html
<h1 id="title">HTML Tutorial</h1>
```

```css
#title {
    color: blue;
}
```

The `#` symbol is used in CSS to select an element by its `id`.

---

### Example with JavaScript

```html
<p id="message">Hello!</p>
```

```javascript
document.getElementById("message");
```

The `getElementById()` method selects an element using its `id` value.


---


## What is the `class` Attribute?

The `class` attribute is a **global HTML attribute** used to assign one or more class names to an HTML element.

Unlike the `id` attribute, multiple HTML elements can share the same class name. This makes the `class` attribute useful for grouping elements that have similar styles or behavior.

The `class` attribute is commonly used for:

- Applying the same CSS styles to multiple elements.
- Selecting multiple elements using JavaScript.
- Organizing HTML elements into logical groups.

### Syntax

```html
<element class="class-name">
    Content
</element>
```

### Example

```html
<p class="highlight">
    Learning HTML is fun!
</p>
```

In this example:

- `class` is the attribute name.
- `highlight` is the class name.
- The paragraph can now be styled or selected using its class name.

---

### Multiple Elements with the Same Class

Multiple HTML elements can use the same class name.

```html
<h2 class="title">Introduction</h2>

<p class="title">
    Welcome to the HTML tutorial.
</p>
```

Both elements belong to the same class and can share the same CSS styles.

---

### Multiple Classes

An HTML element can have more than one class.

```html
<p class="highlight important">
    This is an important note.
</p>
```

Here, the paragraph belongs to both the `highlight` and `important` classes.

Multiple class names are separated by spaces.

---

### Example with CSS

```html
<p class="message">
    Welcome!
</p>
```

```css
.message {
    color: green;
}
```

The `.` (dot) symbol is used in CSS to select elements by their class name.

---

### Example with JavaScript

```html
<p class="message">Hello!</p>
```

```javascript
document.getElementsByClassName("message");
```

The `getElementsByClassName()` method selects all elements that have the specified class name.

---

### Characteristics of the `class` Attribute

- Multiple elements can share the same class name.
- An element can have one or more class names.
- Class names are separated by spaces.
- The `class` attribute can be used with most HTML elements because it is a global attribute.