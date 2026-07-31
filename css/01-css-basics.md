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