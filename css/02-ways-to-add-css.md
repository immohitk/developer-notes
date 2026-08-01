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