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

---

## What Are CSS Variables?

CSS Variables are officially known as **CSS Custom Properties**.

They allow you to define a reusable CSS value and reference that value in other CSS declarations.

A custom property name begins with two hyphens:

```css
--primary-color: #2563eb;
```

The variable can then be used with the `var()` function:

```css
color: var(--primary-color);
```

For example:

```css
:root {
    --primary-color: #2563eb;
    --text-color: #333;
    --spacing: 16px;
}
```

These values can be reused throughout the stylesheet:

```css
button {
    background-color: var(--primary-color);
    color: white;
    padding: var(--spacing);
}

p {
    color: var(--text-color);
}
```

In this example:

```text
--primary-color
--text-color
--spacing
```

are CSS custom properties.

Their values are:

```text
#2563eb
#333
16px
```

The `var()` function retrieves those values:

```css
var(--primary-color)
var(--text-color)
var(--spacing)
```

### Basic Structure

```css
selector {
    --custom-property: value;
}
```

Then:

```css
selector {
    property: var(--custom-property);
}
```

For example:

```css
.card {
    --card-padding: 20px;
}

.card-content {
    padding: var(--card-padding);
}
```

CSS Variables can contain many kinds of CSS values, including:

```css
:root {
    --main-color: #2563eb;
    --font-size: 18px;
    --spacing: 1rem;
    --border-radius: 8px;
    --font-family: Arial, sans-serif;
}
```

They are useful because the value can be defined once and reused wherever needed.

> 💡 **Remember:** CSS Variables are actually called **CSS Custom Properties**. Custom properties are defined with `--` and are commonly accessed using the `var()` function.

---

## Why Use CSS Variables?

CSS Variables make CSS easier to reuse, maintain, and customize.

Instead of repeating the same values throughout a stylesheet, you can define a value once and reuse it wherever needed.

### 1. Reduce Repetition

Without CSS Variables:

```css
button {
    background-color: #2563eb;
}

a {
    color: #2563eb;
}

.card {
    border-color: #2563eb;
}
```

The same color is repeated multiple times.

With a CSS Variable:

```css
:root {
    --primary-color: #2563eb;
}
```

You can reuse it:

```css
button {
    background-color: var(--primary-color);
}

a {
    color: var(--primary-color);
}

.card {
    border-color: var(--primary-color);
}
```

Now the value is defined in one place.

### 2. Easier Maintenance

Suppose the primary color needs to change.

Without a variable, you may need to find and replace several declarations:

```css
button {
    background-color: #2563eb;
}

a {
    color: #2563eb;
}

.card {
    border-color: #2563eb;
}
```

With a variable, change only:

```css
:root {
    --primary-color: #7c3aed;
}
```

All declarations using:

```css
var(--primary-color)
```

automatically use the new value.

### 3. Maintain Consistent Design

CSS Variables can store common design values.

```css
:root {
    --primary-color: #2563eb;
    --secondary-color: #64748b;
    --text-color: #1e293b;
    --border-radius: 8px;
    --spacing: 16px;
}
```

Components can then reuse the same values:

```css
button {
    background-color: var(--primary-color);
    border-radius: var(--border-radius);
    padding: var(--spacing);
}

.card {
    border-radius: var(--border-radius);
    padding: var(--spacing);
}
```

This helps keep the design consistent.

### 4. Create Themes

CSS Variables make it easier to create different themes.

For example:

```css
:root {
    --background-color: white;
    --text-color: #222;
}
```

A dark theme can override the variables:

```css
.dark-theme {
    --background-color: #222;
    --text-color: white;
}
```

Elements can continue using the same variables:

```css
body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

The component does not need completely different property declarations for each theme.

### 5. Customize Components

Variables can make components easier to customize.

```css
.button {
    --button-color: #2563eb;

    background-color: var(--button-color);
}
```

A different component instance can override the variable:

```css
.button.danger {
    --button-color: #dc2626;
}
```

The same component styles can then produce different results.

### 6. Improve Readability

Compare:

```css
.card {
    padding: 24px;
    border-radius: 8px;
    color: #1e293b;
    border: 1px solid #cbd5e1;
}
```

with:

```css
.card {
    padding: var(--spacing);
    border-radius: var(--border-radius);
    color: var(--text-color);
    border: 1px solid var(--border-color);
}
```

The variable names can communicate the purpose of the values.

### 7. Useful for Responsive Designs

CSS Variables can also be changed inside media queries.

For example:

```css
:root {
    --spacing: 24px;
}

@media (max-width: 600px) {
    :root {
        --spacing: 12px;
    }
}
```

The same variable can then be used throughout the stylesheet:

```css
.card {
    padding: var(--spacing);
}
```

The value changes automatically when the media query matches.

### 8. Useful for Design Systems

Larger projects can define reusable design values such as:

```css
:root {
    --color-primary: #2563eb;
    --color-success: #16a34a;
    --color-danger: #dc2626;

    --space-small: 8px;
    --space-medium: 16px;
    --space-large: 24px;

    --radius-small: 4px;
    --radius-medium: 8px;
}
```

Components can then use these shared values.

```text
Design values
      ↓
CSS Variables
      ↓
Components
      ↓
Consistent interface
```

### Main Benefits

```text
CSS Variables
      │
      ├── Reduce repetition
      │
      ├── Easier maintenance
      │
      ├── Consistent design
      │
      ├── Theme support
      │
      ├── Component customization
      │
      ├── Better readability
      │
      ├── Responsive values
      │
      └── Design systems
```

> 💡 **Remember:** The biggest advantage of CSS Variables is that you can define reusable values once and change those values centrally when needed.