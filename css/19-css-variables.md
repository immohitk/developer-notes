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

---

## Declaring CSS Variables

CSS Variables are declared by creating a **custom property** whose name begins with two hyphens (`--`).

The basic syntax is:

```css
--property-name: value;
```

For example:

```css
--primary-color: #2563eb;
```

A custom property can then be declared inside a CSS rule:

```css
.card {
    --card-color: #2563eb;
}
```

Here:

```text
--card-color
     ↓
Custom property name

#2563eb
     ↓
Custom property value
```

### Naming CSS Variables

Custom property names must begin with two hyphens:

```css
--primary-color
--text-color
--font-size
--spacing
--border-radius
```

Names can contain letters, numbers, hyphens, and underscores according to CSS custom-property naming rules.

For example:

```css
:root {
    --main-color: #2563eb;
    --font-size: 16px;
    --border-radius: 8px;
}
```

### Declaring Multiple Variables

Multiple custom properties can be declared in the same rule:

```css
:root {
    --primary-color: #2563eb;
    --secondary-color: #64748b;
    --text-color: #222;
    --spacing: 16px;
    --border-radius: 8px;
}
```

Each declaration follows the same pattern:

```text
--name: value;
```

### Variables Can Store Different Values

CSS Variables are not limited to colors.

They can store values such as:

```css
:root {
    --primary-color: #2563eb;
    --font-size: 18px;
    --spacing: 1rem;
    --border-width: 2px;
    --border-radius: 8px;
    --font-family: Arial, sans-serif;
}
```

They can also contain more complex CSS token sequences:

```css
:root {
    --box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}
```

### Declaring a Variable on `:root`

A common pattern is to declare reusable variables on `:root`:

```css
:root {
    --primary-color: #2563eb;
    --text-color: #222;
}
```

The variables can then be used elsewhere:

```css
button {
    background-color: var(--primary-color);
}

p {
    color: var(--text-color);
}
```

Using `:root` is common when the variables are intended to be available throughout the document.

### Declaring a Variable on a Specific Element

A custom property can also be declared on a specific element or component:

```css
.card {
    --card-padding: 20px;
}
```

The variable can then be used by that element and, where inheritance applies, by its descendants:

```css
.card {
    --card-padding: 20px;
}

.card-content {
    padding: var(--card-padding);
}
```

This makes it possible to create component-specific values.

### Declaration vs Usage

It is important to distinguish between declaring and using a variable.

Declaration:

```css
:root {
    --primary-color: #2563eb;
}
```

Usage:

```css
button {
    background-color: var(--primary-color);
}
```

The first statement creates the custom property.

The second retrieves its value using `var()`.

```text
Declaration
    ↓
--primary-color: #2563eb;

Usage
    ↓
var(--primary-color)
```

> 💡 **Remember:** A CSS custom property is declared with `--name: value;`. The `var()` function is used later when you want to use that value.

---

## Using CSS Variables

After declaring a CSS Variable, you can use its value in CSS declarations with the `var()` function.

For example, declare a variable:

```css
:root {
    --primary-color: #2563eb;
}
```

Then use it:

```css
button {
    background-color: var(--primary-color);
}
```

The browser replaces:

```css
var(--primary-color)
```

with the value stored in:

```css
--primary-color
```

So conceptually:

```text
--primary-color: #2563eb
          ↓
var(--primary-color)
          ↓
#2563eb
```

### Using a Variable Multiple Times

A single CSS Variable can be used in multiple declarations:

```css
:root {
    --primary-color: #2563eb;
}

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

This allows one value to control multiple parts of a design.

### Using Variables for Different Properties

A CSS Variable can be used as the value of different CSS properties when the stored value is valid for those properties.

For example:

```css
:root {
    --spacing: 16px;
}

.card {
    padding: var(--spacing);
    margin: var(--spacing);
}
```

Another example:

```css
:root {
    --radius: 8px;
}

.card {
    border-radius: var(--radius);
}

.button {
    border-radius: var(--radius);
}
```

### Using Variables in Shorthand Properties

CSS Variables can also be used in shorthand declarations.

```css
:root {
    --spacing: 16px;
}

.card {
    padding: var(--spacing);
}
```

You can also use a variable as part of a larger declaration:

```css
:root {
    --border-color: #ccc;
}

.card {
    border: 1px solid var(--border-color);
}
```

Here, the variable supplies only the color value.

### Using Variables in Calculations

CSS Variables can be combined with CSS functions such as `calc()`.

```css
:root {
    --spacing: 16px;
}

.card {
    padding: calc(var(--spacing) * 2);
}
```

The value becomes:

```text
16px × 2
   ↓
32px
```

Another example:

```css
:root {
    --base-size: 20px;
}

.title {
    font-size: calc(var(--base-size) * 1.5);
}
```

### Using Variables in Multiple Components

Variables are especially useful when several components share the same design values.

```css
:root {
    --primary-color: #2563eb;
    --border-radius: 8px;
    --spacing: 16px;
}

.button {
    background-color: var(--primary-color);
    border-radius: var(--border-radius);
    padding: var(--spacing);
}

.card {
    border-radius: var(--border-radius);
    padding: var(--spacing);
}

.badge {
    background-color: var(--primary-color);
}
```

Changing the variable can update all components that use it.

### Variable Names Are Case-Sensitive

Custom property names are case-sensitive.

These are different variables:

```css
--primary-color: blue;
--Primary-Color: red;
```

Therefore:

```css
color: var(--primary-color);
```

and:

```css
color: var(--Primary-Color);
```

can produce different results.

It is good practice to use a consistent naming convention.

### Using Variables in Media Queries

Variables can be used inside media-query declarations and declarations affected by media queries.

For example:

```css
:root {
    --spacing: 24px;
}

.card {
    padding: var(--spacing);
}

@media (max-width: 600px) {
    :root {
        --spacing: 12px;
    }
}
```

The same `.card` rule can then use the appropriate value depending on the active media-query rules.

### Using Variables in Pseudo-Classes

Variables can also be used in states such as `:hover`.

```css
:root {
    --primary-color: #2563eb;
    --hover-color: #1d4ed8;
}

button {
    background-color: var(--primary-color);
}

button:hover {
    background-color: var(--hover-color);
}
```

### Using Variables with Pseudo-Elements

CSS Variables can also be used with pseudo-elements.

```css
:root {
    --icon: "→";
}

.link::after {
    content: var(--icon);
}
```

This allows the generated content to be controlled by a custom property.

### Important Point

Declaring a variable does not automatically apply its value to an element.

For example:

```css
:root {
    --primary-color: blue;
}
```

does not make all text blue.

You must explicitly use the variable:

```css
p {
    color: var(--primary-color);
}
```

> 💡 **Remember:** Declaring a CSS Variable stores a value; using `var(--name)` retrieves that value and applies it to a CSS declaration.