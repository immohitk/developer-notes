# CSS Basics

## Introduction

After learning how to structure web pages with HTML, the next step is learning how to style them using **CSS (Cascading Style Sheets)**.

CSS is a stylesheet language that controls the appearance and presentation of HTML elements. While HTML provides the structure and content of a webpage, CSS is responsible for its visual design.

Using CSS, you can style web pages by changing colors, fonts, spacing, layouts, borders, backgrounds, animations, and much more.

Separating content (HTML) from presentation (CSS) makes websites easier to maintain, improves code readability, and allows a consistent design across multiple pages.

In this section, you'll learn the fundamentals of CSS, understand how it works with HTML, and build the foundation needed for creating modern, responsive websites.


---


## What is CSS?

**CSS (Cascading Style Sheets)** is a stylesheet language used to describe the presentation and appearance of HTML documents.

It controls how HTML elements are displayed on a webpage by defining styles such as:

- Text color
- Font family and size
- Background colors and images
- Borders
- Spacing (margin and padding)
- Layout and positioning
- Animations and transitions

CSS allows developers to separate the content of a webpage from its design. Instead of adding styles to every HTML element individually, a single CSS file can control the appearance of multiple web pages, making websites easier to maintain and update.

Without CSS, web pages would display using the browser's default styles, resulting in plain and less visually appealing websites.

### Example

**HTML**

```html
<h1>Welcome to Developer Notes</h1>
<p>Learning CSS is fun!</p>
```

**CSS**

```css
h1 {
    color: blue;
}

p {
    font-size: 18px;
}
```

In this example:

- HTML creates the webpage content.
- CSS changes the appearance of the heading and paragraph.


---


## Why CSS?

CSS plays a vital role in modern web development. It improves the appearance of web pages, enhances user experience, and makes websites easier to maintain.

### Creates Attractive Web Pages

CSS transforms plain HTML pages into visually appealing websites by adding colors, fonts, spacing, borders, layouts, and animations.

### Separates Content from Design

HTML is responsible for the structure and content of a webpage, while CSS handles its presentation.

This separation makes the code cleaner, easier to read, and simpler to maintain.

### Reusability

A single CSS file can be linked to multiple HTML pages. Any changes made to the stylesheet are automatically applied wherever it is used, reducing duplicate code.

### Easier Maintenance

Instead of editing the design on every individual page, developers can update one stylesheet to apply changes across the entire website.

### Responsive Web Design

CSS provides features such as media queries, flexible layouts, and relative units that allow websites to adapt to different screen sizes and devices.

### Better User Experience

Well-designed websites are easier to read, navigate, and interact with. CSS helps create interfaces that are both functional and visually engaging.

### Industry Standard

CSS is one of the three core technologies of web development, alongside HTML and JavaScript. Every modern website relies on CSS for styling and layout.


---


## How CSS Works

CSS works together with HTML to create visually appealing web pages.

- **HTML** provides the structure and content of a webpage.
- **CSS** controls how that content is displayed.

When a web browser loads a webpage, it first reads the HTML document to understand its structure. It then reads the CSS rules and applies the matching styles to the corresponding HTML elements.

This allows developers to change the appearance of a webpage without modifying its content.

### Example

**HTML**

```html
<h1>Developer Notes</h1>
<p>Welcome to CSS Basics.</p>
```

**CSS**

```css
h1 {
    color: blue;
}

p {
    color: gray;
    font-size: 18px;
}
```

### Result

- The heading is displayed in **blue**.
- The paragraph is displayed in **gray** with a font size of **18 pixels**.

This demonstrates how HTML creates the content while CSS controls its presentation.


---


## Basic CSS Syntax

A CSS stylesheet is made up of one or more **CSS rules**. Each rule tells the browser which HTML element to style and how it should look.

### Syntax

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
    font-size: 32px;
}
```

In this example:

- The selector is `h1`.
- The `color` property changes the text color to blue.
- The `font-size` property changes the text size to 32 pixels.

Every declaration ends with a semicolon (`;`), and all declarations are enclosed within curly braces (`{ }`).

---

## CSS Rule Components

Every CSS rule consists of three main parts.

### Selector

A **selector** specifies which HTML element(s) the style should be applied to.

Example:

```css
h1
```

This selector targets all `<h1>` elements.

### Property

A **property** defines what aspect of the selected element should be changed.

Examples of common properties:

- `color`
- `background-color`
- `font-size`
- `margin`
- `padding`

### Value

A **value** specifies how the property should be applied.

Example:

```css
color: blue;
```

Here:

- **Property:** `color`
- **Value:** `blue`

A property and its value together form a **CSS declaration**.

```css
color: blue;
```

A CSS rule can contain multiple declarations.

```css
p {
    color: black;
    font-size: 18px;
    line-height: 1.6;
}
```


---


## CSS Comments

Comments are used to explain CSS code or leave notes for yourself and other developers. Browsers ignore comments, so they do not affect how a webpage is displayed.

Comments improve code readability and make large stylesheets easier to understand and maintain.

### Syntax

CSS comments start with `/*` and end with `*/`.

```css
/* This is a CSS comment */
```

### Example

```css
/* Style the main heading */
h1 {
    color: blue;
}

/* Style all paragraphs */
p {
    font-size: 18px;
    color: #333;
}
```

### Why Use Comments?

- Explain the purpose of a block of CSS.
- Organize large stylesheets into sections.
- Make code easier to understand during future revisions.
- Improve collaboration when working with other developers.

### Best Practices for Comments

- Write clear and meaningful comments.
- Use comments to separate major sections of your stylesheet.
- Avoid commenting obvious or self-explanatory code.
- Remove outdated comments that no longer match the code.


---


## Key Takeaways

- CSS stands for **Cascading Style Sheets**.
- CSS is used to control the appearance and presentation of HTML documents.
- HTML provides the structure, while CSS is responsible for the design.
- CSS rules are made up of **selectors**, **properties**, and **values**.
- A single CSS rule can contain multiple declarations.
- CSS comments improve readability and help organize stylesheets.
- Separating content (HTML) from presentation (CSS) makes websites easier to maintain.


---


## References

The following resources provide detailed documentation and additional examples for learning CSS:

- **MDN Web Docs** – Comprehensive documentation and guides for CSS.
- **W3Schools** – Beginner-friendly CSS tutorials and examples.
- **W3C CSS Specifications** – Official CSS standards and specifications.

---

## Quick Revision

- **CSS** stands for **Cascading Style Sheets**.
- CSS is used to style HTML elements.
- HTML defines the **structure**, while CSS defines the **presentation**.
- Basic CSS syntax:

```css
selector {
    property: value;
}
```

- A CSS rule contains:
  - **Selector** – Selects the HTML element(s).
  - **Property** – Specifies what to style.
  - **Value** – Specifies how the property should be styled.
- CSS comments are written using:

```css
/* This is a comment */
```


---


## Best Practices

Following good CSS practices makes your code easier to read, maintain, and scale as your projects grow.

- Keep your CSS code properly indented and consistently formatted.
- Use meaningful and descriptive class names.
- Separate HTML structure from CSS styling by using external stylesheets whenever possible.
- Group related CSS rules together to improve readability.
- Add comments to organize large stylesheets into sections.
- Avoid writing duplicate CSS rules; reuse existing classes whenever possible.
- Use consistent naming conventions throughout your project.
- Write simple and readable CSS before trying advanced techniques.


---


## Common Mistakes

Beginners often make small mistakes that can prevent CSS from working correctly.

- Forgetting the semicolon (`;`) after a CSS declaration.
- Misspelling property names such as `colour` instead of `color`.
- Forgetting opening `{` or closing `}` curly braces.
- Using incorrect property values.
- Mixing HTML structure with inline styles unnecessarily.
- Writing duplicate or conflicting CSS rules.
- Using overly complex selectors when simpler ones would work.
- Forgetting to save the CSS file before refreshing the browser.


---


## Interview Questions

Here are some common interview questions related to CSS Basics:

1. What does CSS stand for?
2. What is the purpose of CSS in web development?
3. Explain the difference between HTML and CSS.
4. What are the three main components of a CSS rule?
5. What is a CSS selector?
6. What is the difference between a property and a value?
7. How do you write comments in CSS?
8. Why is it recommended to separate HTML and CSS?
9. What are the advantages of using external CSS?
10. What happens if a CSS declaration is missing a semicolon?


---


## Practice Exercises

Try these exercises to strengthen your understanding of CSS Basics.

### Beginner

1. Create a CSS rule that changes the text color of an `<h1>` element.
2. Set the font size of all `<p>` elements to `18px`.
3. Add comments to organize different sections of your stylesheet.
4. Write a CSS rule with at least three declarations.

### Intermediate

1. Create a simple webpage and style the heading, paragraphs, and buttons using CSS.
2. Organize your stylesheet using meaningful comments and proper formatting.
3. Create separate HTML and CSS files and link them together.
4. Experiment with different properties such as `color`, `background-color`, `font-size`, and `margin` to observe how they affect the page.