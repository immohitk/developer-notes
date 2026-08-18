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

---

## The `var()` Function

The `var()` function is used to access the value stored in a CSS custom property.

The basic syntax is:

```css
var(--custom-property)
```

For example:

```css
:root {
    --primary-color: #2563eb;
}

button {
    background-color: var(--primary-color);
}
```

Here:

```text
--primary-color
       ↓
CSS custom property

var(--primary-color)
       ↓
Retrieves its value
```

### Basic Syntax

The general syntax is:

```css
var(--name)
```

For example:

```css
:root {
    --spacing: 16px;
}

.card {
    padding: var(--spacing);
}
```

The browser uses the value stored in `--spacing`:

```text
--spacing: 16px
       ↓
var(--spacing)
       ↓
16px
```

### Using `var()` with Different Properties

A custom property can be used in different declarations when its value is valid for those declarations.

```css
:root {
    --primary-color: #2563eb;
    --spacing: 16px;
    --radius: 8px;
}

.button {
    background-color: var(--primary-color);
    padding: var(--spacing);
    border-radius: var(--radius);
}
```

### Using `var()` Inside `calc()`

The `var()` function can be combined with other CSS functions.

For example:

```css
:root {
    --spacing: 16px;
}

.card {
    padding: calc(var(--spacing) * 2);
}
```

The calculation becomes:

```text
var(--spacing)
      ↓
16px
      ↓
16px × 2
      ↓
32px
```

### Using `var()` as Part of a Larger Value

A variable does not always have to represent an entire declaration value.

For example:

```css
:root {
    --border-color: #ccc;
}

.card {
    border: 1px solid var(--border-color);
}
```

Here, the final value is effectively:

```css
border: 1px solid #ccc;
```

The variable supplies only the border color.

### Fallback Values

The `var()` function can optionally provide a fallback value.

The syntax is:

```css
var(--custom-property, fallback-value)
```

Example:

```css
.button {
    color: var(--button-text-color, white);
}
```

If `--button-text-color` provides a usable value, that value is used.

Otherwise, the fallback:

```css
white
```

is used.

### Multiple Fallback Values

Fallback values can also contain another `var()` function.

```css
color: var(--text-color, var(--fallback-color, black));
```

The browser first attempts to use:

```css
--text-color
```

If that is not usable, it tries:

```css
--fallback-color
```

and finally:

```css
black
```

### `var()` Does Not Mean String Replacement

CSS custom properties are not simply text macros.

For example:

```css
:root {
    --size: 10px;
}
```

and:

```css
.box {
    width: calc(var(--size) * 2);
}
```

allows the value to participate in CSS value processing.

This is different from a simple textual find-and-replace operation.

### Variables Are Resolved Where They Are Used

Consider:

```css
:root {
    --main-color: blue;
}

.card {
    color: var(--main-color);
}
```

The custom property is inherited and resolved according to the element where the variable is used.

This becomes especially important when variables are overridden on different elements.

### Undefined Custom Property

Suppose:

```css
.button {
    color: var(--button-color);
}
```

but no usable `--button-color` is available for that element.

The declaration can become invalid at computed-value time.

A fallback can make the rule safer:

```css
.button {
    color: var(--button-color, black);
}
```

### Fallback Does Not Mean "If the Value Is Invalid in Every Situation"

The fallback in:

```css
var(--color, black)
```

is used when the custom property cannot provide a usable value for that declaration.

It is not simply a general-purpose validation mechanism for every possible CSS value.

### Practical Example

```css
:root {
    --primary-color: #2563eb;
    --text-color: #222;
    --spacing: 16px;
}

.card {
    color: var(--text-color, black);
    padding: var(--spacing, 16px);
    border: 1px solid var(--primary-color, blue);
}
```

The variables provide the preferred values, while the second arguments provide fallbacks.

### Important Point

The `var()` function is the normal way to consume a CSS custom property:

```css
--name: value;
```

defines the custom property, while:

```css
var(--name)
```

uses its value.

> 💡 **Remember:** The first argument of `var()` is the custom property name. The optional second argument is a fallback value used when the custom property cannot provide a usable value.

---

## Global CSS Variables

Global CSS Variables are custom properties that are defined in a scope where they can be accessed throughout the document.

A common way to create globally available custom properties is to define them on `:root`.

### Defining Variables on `:root`

```css
:root {
    --primary-color: #2563eb;
    --text-color: #222;
    --spacing: 16px;
}
```

These variables can then be used by elements throughout the document:

```css
button {
    background-color: var(--primary-color);
}

p {
    color: var(--text-color);
}

.card {
    padding: var(--spacing);
}
```

The basic pattern is:

```text
:root
  ↓
Global custom properties
  ↓
var(--property-name)
  ↓
Different elements
```

### Why Use `:root`?

`:root` represents the root element of the document.

In an HTML document, this is normally the `<html>` element.

For example:

```css
:root {
    --primary-color: #2563eb;
}
```

Using `:root` is a common pattern for defining design values that should be available throughout the page.

### Global Color Variables

A common use is to define a color palette:

```css
:root {
    --primary-color: #2563eb;
    --secondary-color: #64748b;
    --success-color: #16a34a;
    --danger-color: #dc2626;
    --text-color: #1e293b;
    --background-color: #ffffff;
}
```

These values can then be reused:

```css
body {
    background-color: var(--background-color);
    color: var(--text-color);
}

.button-primary {
    background-color: var(--primary-color);
}

.button-danger {
    background-color: var(--danger-color);
}
```

### Global Spacing Variables

You can also create a reusable spacing system:

```css
:root {
    --spacing-small: 8px;
    --spacing-medium: 16px;
    --spacing-large: 24px;
}
```

Then:

```css
.card {
    padding: var(--spacing-medium);
}

.section {
    margin-bottom: var(--spacing-large);
}

.badge {
    padding: var(--spacing-small);
}
```

### Global Typography Variables

Global variables can store typography values:

```css
:root {
    --font-family: Arial, sans-serif;
    --font-size-base: 16px;
    --heading-size: 2rem;
}
```

They can then be reused:

```css
body {
    font-family: var(--font-family);
    font-size: var(--font-size-base);
}

h1 {
    font-size: var(--heading-size);
}
```

### Global Border Variables

For consistent borders:

```css
:root {
    --border-color: #d1d5db;
    --border-radius: 8px;
}
```

Then:

```css
.card {
    border: 1px solid var(--border-color);
    border-radius: var(--border-radius);
}

.button {
    border: 1px solid var(--border-color);
    border-radius: var(--border-radius);
}
```

### Creating a Design Token System

Global CSS Variables can act as design tokens.

```css
:root {
    --color-primary: #2563eb;
    --color-secondary: #64748b;
    --color-success: #16a34a;

    --space-1: 4px;
    --space-2: 8px;
    --space-3: 16px;
    --space-4: 24px;

    --radius-small: 4px;
    --radius-medium: 8px;
    --radius-large: 12px;
}
```

Components can then use these shared values:

```css
.card {
    padding: var(--space-3);
    border-radius: var(--radius-medium);
}

.button {
    padding: var(--space-2) var(--space-3);
    border-radius: var(--radius-small);
    background-color: var(--color-primary);
}
```

This creates a consistent visual system.

### Overriding a Global Variable

A globally declared variable can be overridden in a more specific scope.

For example:

```css
:root {
    --primary-color: #2563eb;
}

.dark-theme {
    --primary-color: #60a5fa;
}
```

An element inside `.dark-theme` can use the overridden value:

```css
.button {
    background-color: var(--primary-color);
}
```

The value of `--primary-color` depends on the element's applicable scope.

This is one of the features that makes CSS Variables useful for themes and component customization.

### Global Does Not Mean Immutable

A variable declared on `:root` can still be overridden.

For example:

```css
:root {
    --spacing: 16px;
}

.card {
    --spacing: 24px;
}
```

Inside `.card`, descendants that inherit `--spacing` can receive the overridden value.

Therefore, a global variable provides a default value; it does not mean that the value can never change.

### Practical Structure

A stylesheet might organize global variables like this:

```css
:root {
    /* Colors */
    --color-primary: #2563eb;
    --color-text: #1e293b;
    --color-background: #ffffff;

    /* Spacing */
    --space-small: 8px;
    --space-medium: 16px;
    --space-large: 24px;

    /* Typography */
    --font-size-base: 16px;
    --font-size-heading: 2rem;

    /* Borders */
    --border-radius: 8px;
    --border-color: #d1d5db;
}
```

Components can then consume these values without redefining them.

> 💡 **Remember:** A common pattern for global CSS Variables is to declare custom properties on `:root` and reuse them throughout the document with `var()`.

---

## Local CSS Variables

Local CSS Variables are custom properties defined within a specific element or component rather than at the root level.

They are useful when a value should apply only to a particular part of the page.

For example:

```css
.card {
    --card-padding: 20px;
}
```

The variable is available to the `.card` element and, through inheritance, to its descendants.

```css
.card {
    --card-padding: 20px;
}

.card-content {
    padding: var(--card-padding);
}
```

### Global vs Local Variables

A global variable is commonly defined on `:root`:

```css
:root {
    --primary-color: #2563eb;
}
```

A local variable can be defined on a specific component:

```css
.card {
    --card-padding: 20px;
}
```

The difference can be visualized as:

```text
Global Variable
      ↓
:root
      ↓
Available throughout the document

Local Variable
      ↓
Specific element
      ↓
Available to that element and applicable descendants
```

### Component-Specific Variables

Local variables are useful for component-specific values.

```css
.card {
    --card-background: white;
    --card-padding: 20px;
    --card-radius: 8px;

    background-color: var(--card-background);
    padding: var(--card-padding);
    border-radius: var(--card-radius);
}
```

The variables belong to the `.card` scope.

### Local Variables for Variants

Local variables are especially useful for creating component variants.

For example:

```css
.button {
    --button-color: #2563eb;

    background-color: var(--button-color);
}

.button-danger {
    --button-color: #dc2626;
}
```

HTML:

```html
<button class="button">
    Save
</button>

<button class="button button-danger">
    Delete
</button>
```

The base component uses the default value:

```text
.button
   ↓
--button-color: #2563eb
```

The danger variant overrides it:

```text
.button-danger
   ↓
--button-color: #dc2626
```

The actual `background-color` declaration does not need to change.

### Local Variables and Descendants

Custom properties normally inherit.

For example:

```css
.card {
    --text-color: blue;
}

.card p {
    color: var(--text-color);
}
```

The paragraph can use the variable because it is a descendant of `.card`.

HTML:

```html
<div class="card">
    <p>Hello CSS</p>
</div>
```

The paragraph receives:

```text
--text-color
     ↓
blue
     ↓
color: blue
```

### Different Values for Different Components

Local variables allow the same CSS rule to behave differently for different elements.

```css
.card {
    --card-color: blue;
}

.card.warning {
    --card-color: orange;
}

.card.error {
    --card-color: red;
}

.card-title {
    color: var(--card-color);
}
```

HTML:

```html
<div class="card">
    <h2 class="card-title">Normal</h2>
</div>

<div class="card warning">
    <h2 class="card-title">Warning</h2>
</div>

<div class="card error">
    <h2 class="card-title">Error</h2>
</div>
```

The same `.card-title` rule can produce different colors depending on the variable inherited from its parent.

### Local Variables Without Immediate Usage

A custom property can be declared for descendants even if the element itself does not directly use it.

```css
.card {
    --accent-color: blue;
}

.card-title {
    color: var(--accent-color);
}

.card-link {
    border-color: var(--accent-color);
}
```

Both descendants can access the locally defined variable.

### Local Variables for Theming Components

A component can define its own defaults:

```css
.card {
    --card-background: white;
    --card-text: #222;
    --card-border: #ddd;

    background: var(--card-background);
    color: var(--card-text);
    border: 1px solid var(--card-border);
}
```

Another class can override those values:

```css
.card.dark {
    --card-background: #222;
    --card-text: white;
    --card-border: #444;
}
```

The component structure remains the same.

### Local Variables Can Override Global Variables

Suppose a global variable exists:

```css
:root {
    --primary-color: blue;
}
```

A component can override it:

```css
.card {
    --primary-color: red;
}
```

Then:

```css
.card-title {
    color: var(--primary-color);
}
```

Inside `.card`, the local value is used.

Conceptually:

```text
:root
--primary-color: blue
       ↓
     .card
--primary-color: red
       ↓
  .card-title
       ↓
      red
```

### Why Local Variables Are Useful

Local CSS Variables are useful when:

- A value belongs to one component
- Components need different variants
- A component needs configurable values
- Descendants should share a value
- You want to avoid creating many globally named variables
- A component should have its own styling defaults

### Practical Example

```css
.button {
    --button-background: #2563eb;
    --button-text: white;
    --button-radius: 8px;

    background-color: var(--button-background);
    color: var(--button-text);
    border-radius: var(--button-radius);
}

.button.success {
    --button-background: #16a34a;
}

.button.danger {
    --button-background: #dc2626;
}
```

The component's main CSS remains unchanged while variants override only the variables they need.

> 💡 **Remember:** Local CSS Variables are useful for component-level customization. Define the variable where the value belongs, then let the element and its descendants use the inherited custom property.