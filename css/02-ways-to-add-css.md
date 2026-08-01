# Ways to Add CSS

## Table of Contents

- [Introduction](#introduction)
- [Inline CSS](#inline-css)
- [Internal CSS](#internal-css)
- [External CSS](#external-css)
- [Comparison of CSS Methods](#comparison-of-css-methods)
- [When to Use Each Method](#when-to-use-each-method)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


## Introduction

After learning the basics of CSS, the next step is understanding how CSS can be applied to an HTML document.

There are **three ways to add CSS** to a webpage:

1. Inline CSS
2. Internal CSS
3. External CSS

Each method serves a different purpose and is suitable for different scenarios. While all three achieve the same goal of styling HTML elements, they differ in terms of maintainability, reusability, and ease of use.

In this chapter, you'll learn each method in detail, understand their advantages and disadvantages, and discover which approach is recommended for modern web development.


---


## Inline CSS

**Inline CSS** is a method of applying CSS directly to an HTML element using the `style` attribute.

The styles written inside the `style` attribute affect **only that specific element**.

### Syntax

```html
<tag style="property: value;">Content</tag>
```

### Example

```html
<h1 style="color: blue;">Welcome to CSS</h1>

<p style="font-size: 18px;">
    This paragraph uses inline CSS.
</p>
```

In the example above:

- The `<h1>` element is displayed in **blue**.
- The paragraph has a **font size of 18 pixels**.
- The styles apply only to those individual elements.


---


### Advantages

- Easy to use for small changes.
- Applies styles directly to a specific HTML element.
- Useful for testing or making quick style changes.
- Does not require a separate CSS file.

### Disadvantages

- Styles cannot be reused across multiple elements.
- Mixing HTML and CSS makes the code harder to read and maintain.
- Increases code duplication when the same styles are used repeatedly.
- Not recommended for large websites or production projects.

### When to Use Inline CSS

Inline CSS is suitable for:

- Testing small styling changes.
- Applying a unique style to a single element.
- Email templates where inline styles are often required.

For most websites, **External CSS** is the recommended approach because it keeps HTML and CSS separate, making projects easier to maintain and scale.


---


## Internal CSS

**Internal CSS** is a method of adding CSS directly inside an HTML document using the `<style>` element.

The `<style>` element is placed inside the `<head>` section of the HTML document. All the styles written within it apply only to that specific webpage.

### Syntax

```html
<head>
    <style>
        selector {
            property: value;
        }
    </style>
</head>
```

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        h1 {
            color: blue;
        }

        p {
            font-size: 18px;
            color: gray;
        }
    </style>
</head>

<body>
    <h1>Welcome to CSS</h1>
    <p>This paragraph uses internal CSS.</p>
</body>
</html>
```

In this example:

- The `<style>` element contains all the CSS rules.
- The styles apply only to this HTML page.
- Multiple HTML elements can share the same styles.


---


### Advantages

- Styles are written in one place within the HTML document.
- Multiple elements on the same page can share the same styles.
- Keeps styling separate from the HTML content better than Inline CSS.
- Useful for styling a single webpage without creating a separate CSS file.

### Disadvantages

- Styles cannot be reused across multiple HTML pages.
- As the stylesheet grows, the HTML file becomes larger and harder to maintain.
- Updating styles across multiple pages requires editing each file individually.
- Not suitable for large websites with many pages.

### When to Use Internal CSS

Internal CSS is suitable for:

- Single-page websites.
- Small projects.
- Prototypes and demonstrations.
- Testing styles before moving them to an external stylesheet.

For websites with multiple pages, **External CSS** is the preferred approach because it allows styles to be shared across the entire project.