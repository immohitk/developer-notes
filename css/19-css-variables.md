# CSS Variables

## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Variables?](#what-are-css-variables)
- [Why Use CSS Variables?](#why-use-css-variables)
- [Declaring CSS Variables](#declaring-css-variables)
- [Using CSS Variables](#using-css-variables)
- [The `var()` Function](#the-var-function)
- [Global CSS Variables](#global-css-variables)
- [Local CSS Variables](#local-css-variables)
- [Fallback Values](#fallback-values)
- [Inheritance](#inheritance)
- [CSS Variables and the Cascade](#css-variables-and-the-cascade)
- [Changing Variables with Pseudo-Classes](#changing-variables-with-pseudo-classes)
- [CSS Variables with Media Queries](#css-variables-with-media-queries)
- [CSS Variables with JavaScript](#css-variables-with-javascript)
- [CSS Variables for Themes](#css-variables-for-themes)
- [Practical Examples](#practical-examples)
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

CSS Variables, officially called **CSS Custom Properties**, allow you to store reusable values in CSS and use those values throughout your stylesheet.

Instead of repeatedly writing the same value:

```css
button {
    background-color: #2563eb;
}

.link {
    color: #2563eb;
}

.badge {
    border-color: #2563eb;
}
```

you can define the value once:

```css
:root {
    --primary-color: #2563eb;
}
```

and reuse it:

```css
button {
    background-color: var(--primary-color);
}

.link {
    color: var(--primary-color);
}

.badge {
    border-color: var(--primary-color);
}
```

Here:

```css
--primary-color
```

is the **custom property**, and:

```css
var(--primary-color)
```

is used to retrieve its value.

CSS Variables are useful for:

- Reusing common values
- Maintaining consistent designs
- Creating themes
- Reducing repetition
- Making styles easier to update
- Sharing values between related components
- Creating responsive designs with reusable values

A simple mental model is:

```text
Define a value
      ↓
--primary-color: #2563eb
      ↓
Reuse the value
      ↓
var(--primary-color)
      ↓
Multiple CSS rules
```

> 💡 **Remember:** CSS Variables are officially called **CSS Custom Properties**. Their values participate in the CSS cascade and inheritance system.