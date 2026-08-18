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

---

## Fallback Values

CSS custom properties can use a **fallback value** when the requested custom property is not available or does not provide a usable value for the declaration.

The fallback value is written as the second argument of the `var()` function.

The syntax is:

```css
var(--custom-property, fallback-value)
```

For example:

```css
.button {
    color: var(--button-text-color, white);
}
```

Here:

```text
--button-text-color
        ↓
Try to use this value
        ↓
If unavailable or unusable
        ↓
Use white
```

### Basic Fallback Example

Suppose the variable is not defined:

```css
.button {
    background-color: var(--button-color, blue);
}
```

Because `--button-color` does not provide a usable value, the fallback is used:

```css
background-color: blue;
```

### Fallback When a Variable Is Not Defined

Consider:

```css
.card {
    color: var(--text-color, black);
}
```

If `--text-color` is not available for the element, the browser uses:

```css
black
```

The fallback makes the declaration more robust.

### Fallback With a Defined Variable

If the variable is defined:

```css
:root {
    --text-color: darkblue;
}

.card {
    color: var(--text-color, black);
}
```

the defined value is used:

```text
--text-color
     ↓
darkblue
     ↓
color: darkblue
```

The fallback:

```css
black
```

is not used.

### Fallback Values Can Be Different CSS Values

The fallback does not have to be a simple color.

For example:

```css
.card {
    padding: var(--card-padding, 16px);
}
```

Or:

```css
.card {
    border-radius: var(--card-radius, 8px);
}
```

Or:

```css
body {
    font-family: var(--font-family, Arial, sans-serif);
}
```

### Multiple Fallbacks

A fallback can itself use another custom property.

```css
.card {
    color: var(
        --primary-text,
        var(--secondary-text, black)
    );
}
```

The browser tries the values in order:

```text
--primary-text
      ↓
if unavailable
      ↓
--secondary-text
      ↓
if unavailable
      ↓
black
```

This creates a fallback chain.

### Fallbacks With Local Variables

Fallbacks are particularly useful when working with reusable components.

```css
.button {
    background-color: var(--button-color, blue);
}
```

A component can override the variable:

```css
.button.danger {
    --button-color: red;
}
```

Now:

```text
Normal button
    ↓
--button-color unavailable
    ↓
blue

Danger button
    ↓
--button-color: red
    ↓
red
```

### Fallbacks and Empty Custom Properties

An important detail is that a custom property can exist but still not provide a usable value for a particular declaration.

For example:

```css
:root {
    --primary-color: ;
}
```

and:

```css
.button {
    color: var(--primary-color, blue);
}
```

The fallback behavior depends on whether the custom property can provide a valid value for the declaration.

Therefore, fallback values should not be treated as a general validation system for every possible custom-property value.

### Fallbacks Are Not the Same as Default CSS Values

Compare:

```css
.button {
    color: blue;
}
```

with:

```css
.button {
    color: var(--button-color, blue);
}
```

The first always specifies:

```text
blue
```

The second says:

```text
Use --button-color if it provides a usable value;
otherwise use blue.
```

### Practical Example

```css
:root {
    --primary-color: #2563eb;
}

.button {
    background-color: var(--primary-color, blue);
    color: var(--button-text, white);
    border-radius: var(--button-radius, 8px);
    padding: var(--button-padding, 10px 16px);
}
```

Here:

```text
--primary-color
    ↓
#2563eb

--button-text
    ↓
white fallback

--button-radius
    ↓
8px fallback

--button-padding
    ↓
10px 16px fallback
```

### Why Use Fallback Values?

Fallback values are useful when:

- A component may be customized
- A variable may not be defined in every context
- You want sensible defaults
- You are building reusable components
- You want a safer CSS declaration

A useful component pattern is:

```css
.component {
    color: var(--component-color, #222);
    padding: var(--component-padding, 16px);
    border-radius: var(--component-radius, 8px);
}
```

The component provides defaults while still allowing customization.

> 💡 **Remember:** The second argument of `var()` is a fallback value. It is used when the custom property cannot provide a usable value for the declaration.

---

## Inheritance

CSS custom properties normally **inherit** from their parent element to their descendants.

This is an important feature of CSS Variables because a value defined on a parent can be used by child elements without redefining the variable on every child.

### Basic Example

```css
.card {
    --text-color: #2563eb;
}

.card p {
    color: var(--text-color);
}
```

HTML:

```html
<div class="card">
    <p>Hello CSS</p>
</div>
```

The custom property is defined on:

```text
.card
   ↓
--text-color: #2563eb
```

The `<p>` is a descendant of `.card`, so it inherits the custom property:

```text
.card
   ↓
--text-color
   ↓
<p>
   ↓
var(--text-color)
   ↓
#2563eb
```

### Inheritance From `:root`

A common pattern is to define variables on `:root`:

```css
:root {
    --primary-color: #2563eb;
    --text-color: #222;
}
```

Then descendants can use them:

```css
button {
    background-color: var(--primary-color);
}

p {
    color: var(--text-color);
}
```

The variables are inherited through the document tree.

### Parent and Child Variables

A child can override an inherited custom property.

```css
.parent {
    --color: blue;
}

.child {
    --color: red;
}
```

HTML:

```html
<div class="parent">
    <p>Parent content</p>

    <div class="child">
        <p>Child content</p>
    </div>
</div>
```

The first paragraph can inherit:

```text
blue
```

while the descendants of `.child` can inherit:

```text
red
```

### Inheritance Follows the DOM Tree

Custom properties are inherited according to the document tree.

For example:

```html
<div class="parent">
    <div class="child">
        <p>Text</p>
    </div>
</div>
```

If:

```css
.parent {
    --color: blue;
}
```

then the value can flow down:

```text
.parent
   ↓
.child
   ↓
<p>
```

and the paragraph can use:

```css
color: var(--color);
```

### Local Override

A descendant can provide its own value instead of inheriting the parent's value.

```css
.card {
    --accent-color: blue;
}

.card.warning {
    --accent-color: orange;
}
```

Then:

```css
.card-title {
    color: var(--accent-color);
}
```

A normal card can use blue, while a warning card can use orange.

### Inheritance Is Different From Declaration

Consider:

```css
.parent {
    --color: blue;
}
```

and:

```css
.child {
    color: var(--color);
}
```

The child does not declare:

```css
--color: blue;
```

Instead, it **inherits** the custom property from its parent and then uses it.

```text
Parent
  │
  └── --color: blue
          │
          ↓
       Child
          │
          └── var(--color)
```

### What Happens When a Variable Is Not Defined?

Suppose:

```css
.child {
    color: var(--color);
}
```

and neither the child nor its ancestors provide a usable `--color`.

Then the custom property cannot provide a value for that declaration.

A fallback can be provided:

```css
.child {
    color: var(--color, black);
}
```

If the variable is unavailable, the fallback is used.

### Inheritance With Multiple Levels

Custom properties can be inherited through several levels.

```css
:root {
    --main-color: blue;
}

.container {
    /* inherits --main-color */
}

.card {
    /* inherits --main-color */
}

.title {
    color: var(--main-color);
}
```

The value can flow through:

```text
:root
  ↓
.container
  ↓
.card
  ↓
.title
```

The `.title` can therefore use the value defined on `:root`.

### Overriding at Different Levels

Different components can override the same variable.

```css
:root {
    --main-color: blue;
}

.card {
    --main-color: green;
}

.card.danger {
    --main-color: red;
}
```

This creates a hierarchy:

```text
:root
--main-color: blue
       ↓
.card
--main-color: green
       ↓
.card.danger
--main-color: red
```

Elements inside each scope use the applicable value.

### Custom Properties and Normal CSS Properties

CSS custom properties inherit by default.

However, not every normal CSS property inherits.

For example:

```css
:root {
    --primary-color: blue;
}
```

The custom property can be inherited by descendants.

Then:

```css
button {
    color: var(--primary-color);
}
```

uses the inherited custom property to set the normal `color` property.

This distinction is important:

```text
Custom property
      ↓
Inherited through the element tree

Normal CSS property
      ↓
May or may not inherit depending on the property
```

### Practical Component Example

```css
.card {
    --card-color: #2563eb;
    --card-padding: 16px;

    padding: var(--card-padding);
}

.card-title {
    color: var(--card-color);
}

.card-text {
    color: var(--card-color);
}
```

Both descendants can use the variables defined on `.card`.

A variant can override them:

```css
.card.warning {
    --card-color: #d97706;
}
```

Now both:

```text
.card-title
.card-text
```

inside the warning card can use the new color.

### Important Point

Inheritance makes CSS Variables especially useful for component-level configuration.

Instead of writing separate values for every descendant:

```css
.card-title {
    color: blue;
}

.card-text {
    color: blue;
}

.card-link {
    color: blue;
}
```

you can define one variable:

```css
.card {
    --card-color: blue;
}

.card-title {
    color: var(--card-color);
}

.card-text {
    color: var(--card-color);
}

.card-link {
    color: var(--card-color);
}
```

A parent-level override can then change the value for all applicable descendants.

> 💡 **Remember:** CSS custom properties normally inherit. A value defined on a parent can therefore be used by descendants unless a descendant overrides the custom property or the value cannot provide a usable result.

---

## CSS Variables and the Cascade

CSS Variables, or custom properties, participate in the **CSS cascade**.

This means that when the same custom property is declared in multiple places, the browser determines which value applies to an element based on the normal cascade rules.

### Basic Example

```css
:root {
    --primary-color: blue;
}

.card {
    --primary-color: green;
}

.card-title {
    color: var(--primary-color);
}
```

If `.card-title` is inside `.card`:

```text
:root
--primary-color: blue
       ↓
.card
--primary-color: green
       ↓
.card-title
var(--primary-color)
       ↓
green
```

The value defined on `.card` applies because it is the custom property inherited by the descendants of that element.

### Cascade Determines Which Declaration Applies

Consider:

```css
.card {
    --color: blue;
}

.card {
    --color: red;
}
```

Both rules have the same selector and therefore the same specificity.

The second declaration wins because it appears later in the stylesheet.

```text
--color: blue
       ↓
--color: red
       ↓
Winner: red
```

This is the same source-order principle that applies to other CSS declarations.

### Specificity Can Affect Custom Properties

Consider:

```css
.card {
    --color: blue;
}

.card.featured {
    --color: red;
}
```

The second selector is more specific:

```text
.card
        ↓
1 class

.card.featured
        ↓
2 classes
```

Therefore, for an element matching both selectors:

```css
--color: red;
```

wins.

### Custom Properties Can Be Overridden

A custom property can be redefined in a more specific or more local context.

```css
:root {
    --primary-color: blue;
}

.card {
    --primary-color: green;
}

.card.danger {
    --primary-color: red;
}
```

The applicable value depends on where the element exists in the document and which declaration wins through the cascade.

```text
Global default
     ↓
blue

.card
     ↓
green

.card.danger
     ↓
red
```

### Cascade and Inheritance Work Together

The cascade determines which custom-property declaration applies to an element.

The resulting custom property can then be inherited by descendants.

For example:

```css
:root {
    --color: blue;
}

.card {
    --color: green;
}

.card-title {
    color: var(--color);
}
```

If `.card-title` is inside `.card`:

```text
Cascade
   ↓
.card gets --color: green
   ↓
Inheritance
   ↓
.card-title receives --color: green
   ↓
var(--color)
   ↓
green
```

This distinction is important.

```text
Cascade
   ↓
Chooses the applicable declaration

Inheritance
   ↓
Passes the custom property to descendants
```

### Custom Properties and Source Order

When competing declarations have the same relevant cascade priority and specificity, source order can determine the winner.

Example:

```css
.theme {
    --color: blue;
}

.theme {
    --color: green;
}
```

The later declaration wins:

```css
--color: green;
```

### Custom Properties and `!important`

Custom-property declarations can also use `!important`.

```css
.card {
    --color: blue !important;
}

.card.special {
    --color: red;
}
```

The important declaration has higher cascade priority than the normal declaration.

However, `!important` should not be used unnecessarily.

### Cascade Layers

Custom properties also participate in cascade layers.

For example:

```css
@layer base {
    :root {
        --primary-color: blue;
    }
}

@layer theme {
    :root {
        --primary-color: purple;
    }
}
```

The ordering of the cascade layers affects which declaration wins.

This can be useful when organizing large stylesheets.

### Custom Property Values Are Not Simply Text Replacements

Consider:

```css
:root {
    --size: 20px;
}

.box {
    width: calc(var(--size) * 2);
}
```

The custom property participates in CSS value processing.

The browser evaluates:

```text
var(--size)
     ↓
20px

calc(20px * 2)
     ↓
40px
```

Therefore, custom properties should be understood as CSS values that participate in the cascade and are substituted when used.

### Changing a Variable Changes Dependent Styles

Suppose:

```css
:root {
    --primary-color: blue;
}

button {
    background-color: var(--primary-color);
}

a {
    color: var(--primary-color);
}
```

If the applicable value changes:

```css
:root {
    --primary-color: purple;
}
```

both declarations using the variable now use the new value.

```text
--primary-color
       ↓
     purple
       ↓
 ┌─────┴─────┐
 ↓           ↓
button       a
 ↓           ↓
purple      purple
```

### Practical Example

```css
:root {
    --color: blue;
}

.card {
    color: var(--color);
}

.card.warning {
    --color: orange;
}

.card.error {
    --color: red;
}
```

HTML:

```html
<div class="card">
    Normal card
</div>

<div class="card warning">
    Warning card
</div>

<div class="card error">
    Error card
</div>
```

The same:

```css
color: var(--color);
```

can produce different results because the custom property is changed by the cascade and inheritance rules.

```text
Normal
    ↓
blue

Warning
    ↓
orange

Error
    ↓
red
```

### Important Mental Model

When working with CSS Variables, think about these steps:

```text
Custom property declarations
          ↓
CSS Cascade
          ↓
Winning custom-property value
          ↓
Inheritance to descendants
          ↓
var(--custom-property)
          ↓
Used CSS value
```

> 💡 **Remember:** CSS Variables are part of the CSS cascade. When a custom property is declared in multiple places, cascade rules determine the applicable value, and that value can then be inherited by descendants.

---

## Changing Variables with Pseudo-Classes

CSS Variables can be changed inside pseudo-class states such as `:hover`, `:focus`, `:active`, and `:checked`.

This allows the same CSS declarations to use different values depending on the current state of an element.

### Basic `:hover` Example

Define a variable for a button:

```css
.button {
    --button-color: #2563eb;

    background-color: var(--button-color);
}
```

Change the variable when the button is hovered:

```css
.button:hover {
    --button-color: #1d4ed8;
}
```

The button's existing declaration:

```css
background-color: var(--button-color);
```

automatically uses the new value.

Conceptually:

```text
Normal
    ↓
--button-color: #2563eb
    ↓
background-color: #2563eb

Hover
    ↓
--button-color: #1d4ed8
    ↓
background-color: #1d4ed8
```

### Using `:focus`

Variables can also change when an element receives focus.

```css
.input {
    --border-color: #ccc;

    border: 2px solid var(--border-color);
}

.input:focus {
    --border-color: #2563eb;
}
```

When the input receives focus, the variable changes and the border becomes blue.

For keyboard-friendly focus styling, `:focus-visible` can also be used:

```css
.button:focus-visible {
    --button-color: #1d4ed8;
}
```

### Using `:active`

The `:active` pseudo-class represents an element while it is being activated.

```css
.button {
    --button-color: #2563eb;

    background-color: var(--button-color);
}

.button:active {
    --button-color: #1e40af;
}
```

While the button is active, the darker value is used.

### Using `:checked`

Variables can also be changed based on the checked state of form controls.

```css
.checkbox {
    --check-color: gray;
}

.checkbox:checked {
    --check-color: green;
}
```

The variable can then be used by related styles:

```css
.checkbox {
    accent-color: var(--check-color);
}
```

### Using Variables With a Parent State

A parent element can change a variable that is inherited by its descendants.

```css
.card {
    --accent-color: blue;
}

.card:hover {
    --accent-color: red;
}

.card-title {
    color: var(--accent-color);
}
```

When the card is hovered:

```text
.card
    ↓
--accent-color: red
    ↓
.card-title
    ↓
color: red
```

This is useful when several child elements should change together.

### Changing Multiple Properties Through One Variable

A single variable can control several declarations.

```css
.button {
    --button-color: #2563eb;

    background-color: var(--button-color);
    border-color: var(--button-color);
    color: white;
}

.button:hover {
    --button-color: #1d4ed8;
}
```

Only the variable changes:

```css
--button-color
```

but multiple properties respond to that change.

### Creating Component States

Variables are useful for defining different component states.

```css
.button {
    --button-background: #2563eb;
    --button-text: white;

    background-color: var(--button-background);
    color: var(--button-text);
}

.button:hover {
    --button-background: #1d4ed8;
}

.button:disabled {
    --button-background: #94a3b8;
    --button-text: #e2e8f0;
}
```

The main component styles remain unchanged.

Only the variables change according to the state.

### Combining Pseudo-Classes With Transitions

Variables can also be used with transitions when the resulting property supports interpolation.

For example:

```css
.button {
    --button-color: #2563eb;

    background-color: var(--button-color);
    transition: background-color 0.2s ease;
}

.button:hover {
    --button-color: #1d4ed8;
}
```

The `background-color` transition can animate between the two resulting colors.

### Important Distinction

Changing a custom property does not automatically create an animation.

For example:

```css
.button {
    --button-color: blue;
}

.button:hover {
    --button-color: red;
}
```

The variable changes between states.

A transition must be applied to the actual property whose computed value changes:

```css
.button {
    background-color: var(--button-color);
    transition: background-color 0.2s ease;
}
```

### Practical Example

```css
.button {
    --button-background: #2563eb;
    --button-border: #2563eb;

    background-color: var(--button-background);
    border: 2px solid var(--button-border);
    color: white;
    padding: 10px 16px;
    transition:
        background-color 0.2s ease,
        border-color 0.2s ease;
}

.button:hover {
    --button-background: #1d4ed8;
    --button-border: #1d4ed8;
}

.button:active {
    --button-background: #1e40af;
    --button-border: #1e40af;
}
```

The same component can therefore have:

```text
Normal
    ↓
Primary color

Hover
    ↓
Darker color

Active
    ↓
Even darker color
```

> 💡 **Remember:** Pseudo-classes can change custom-property values. Because other declarations use those variables, changing one variable can update several visual properties at once.

---

## CSS Variables with Media Queries

CSS Variables can be changed inside media queries.

This makes it possible to use the same CSS declarations while changing values based on the screen size or other media conditions.

### Basic Example

Define a variable for spacing:

```css
:root {
    --spacing: 24px;
}

.card {
    padding: var(--spacing);
}
```

Change the variable for smaller screens:

```css
@media (max-width: 600px) {
    :root {
        --spacing: 12px;
    }
}
```

The `.card` declaration does not need to change:

```css
.card {
    padding: var(--spacing);
}
```

The value changes depending on the active media query.

```text
Large screen
    ↓
--spacing: 24px
    ↓
padding: 24px

Small screen
    ↓
--spacing: 12px
    ↓
padding: 12px
```

### Responsive Typography

CSS Variables can also control font sizes.

```css
:root {
    --heading-size: 2.5rem;
}

h1 {
    font-size: var(--heading-size);
}
```

On smaller screens:

```css
@media (max-width: 600px) {
    :root {
        --heading-size: 2rem;
    }
}
```

The same `h1` rule uses the appropriate value.

### Responsive Spacing

You can create a small responsive spacing system:

```css
:root {
    --space-small: 8px;
    --space-medium: 16px;
    --space-large: 32px;
}

@media (max-width: 600px) {
    :root {
        --space-medium: 12px;
        --space-large: 20px;
    }
}
```

Components can continue using:

```css
.card {
    padding: var(--space-medium);
    margin-bottom: var(--space-large);
}
```

### Responsive Container Width

A variable can also control layout dimensions.

```css
:root {
    --container-width: 1200px;
}

.container {
    width: min(100% - 32px, var(--container-width));
    margin-inline: auto;
}
```

For smaller screens, the value can be changed if needed:

```css
@media (max-width: 768px) {
    :root {
        --container-width: 100%;
    }
}
```

### Changing Colors With Media Queries

Media queries do not have to be used only for dimensions.

You can change theme-related values as well.

```css
:root {
    --background-color: white;
    --text-color: #222;
}

@media (prefers-color-scheme: dark) {
    :root {
        --background-color: #111;
        --text-color: white;
    }
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

The variables provide different values depending on the user's preferred color scheme.

### Responsive Component Variables

Variables can also be changed at the component level.

```css
.card {
    --card-padding: 24px;

    padding: var(--card-padding);
}

@media (max-width: 600px) {
    .card {
        --card-padding: 16px;
    }
}
```

Only the component's variable changes.

The main declaration remains:

```css
.card {
    padding: var(--card-padding);
}
```

### Multiple Breakpoints

Different breakpoints can provide different values.

```css
:root {
    --spacing: 24px;
}

@media (max-width: 900px) {
    :root {
        --spacing: 20px;
    }
}

@media (max-width: 600px) {
    :root {
        --spacing: 12px;
    }
}
```

Conceptually:

```text
> 900px
    ↓
24px

601px – 900px
    ↓
20px

≤ 600px
    ↓
12px
```

The applicable media-query rules participate in the cascade.

### Combining Variables With `calc()`

Variables can also be used with `calc()` for responsive values.

```css
:root {
    --base-spacing: 16px;
}

.card {
    padding: calc(var(--base-spacing) * 1.5);
}
```

The variable can be changed at a breakpoint:

```css
@media (max-width: 600px) {
    :root {
        --base-spacing: 12px;
    }
}
```

The calculation automatically uses the new value.

### Why Use Variables With Media Queries?

This approach can reduce repeated responsive declarations.

Instead of:

```css
.card {
    padding: 24px;
    font-size: 20px;
}

@media (max-width: 600px) {
    .card {
        padding: 12px;
        font-size: 16px;
    }
}
```

you can use:

```css
:root {
    --card-padding: 24px;
    --card-font-size: 20px;
}

.card {
    padding: var(--card-padding);
    font-size: var(--card-font-size);
}

@media (max-width: 600px) {
    :root {
        --card-padding: 12px;
        --card-font-size: 16px;
    }
}
```

The component declaration remains unchanged.

### Practical Example

```css
:root {
    --page-padding: 32px;
    --heading-size: 2.5rem;
    --card-gap: 24px;
}

.page {
    padding: var(--page-padding);
}

h1 {
    font-size: var(--heading-size);
}

.cards {
    gap: var(--card-gap);
}

@media (max-width: 768px) {
    :root {
        --page-padding: 20px;
        --heading-size: 2rem;
        --card-gap: 16px;
    }
}

@media (max-width: 480px) {
    :root {
        --page-padding: 12px;
        --heading-size: 1.75rem;
        --card-gap: 12px;
    }
}
```

The same component rules automatically adapt to different screen sizes.

### Important Point

CSS Variables do not replace media queries.

Instead, they work **with** media queries.

```text
Media Query
     ↓
Changes custom-property value
     ↓
Existing CSS declarations
     ↓
Use var(--property)
     ↓
Responsive result
```

> 💡 **Remember:** A powerful responsive pattern is to keep component declarations stable and change the custom-property values inside media queries.

---

## CSS Variables with JavaScript

CSS Variables can be read and modified with JavaScript.

This is useful when a web application needs to dynamically change colors, spacing, sizes, themes, or other CSS values.

JavaScript can interact with CSS custom properties through the DOM.

### Defining a CSS Variable

Start with a custom property:

```css
:root {
    --primary-color: #2563eb;
}
```

Use it in CSS:

```css
button {
    background-color: var(--primary-color);
}
```

JavaScript can then access or modify the variable.

### Setting a CSS Variable With JavaScript

Use:

```javascript
document.documentElement.style.setProperty(
    "--primary-color",
    "#dc2626"
);
```

Here:

```text
document.documentElement
        ↓
<html> element

style.setProperty()
        ↓
Changes the custom property

--primary-color
        ↓
#dc2626
```

The CSS:

```css
button {
    background-color: var(--primary-color);
}
```

automatically uses the new value.

### Reading a CSS Variable

JavaScript can read a custom property using `getComputedStyle()`.

```css
:root {
    --primary-color: #2563eb;
}
```

JavaScript:

```javascript
const styles = getComputedStyle(document.documentElement);

const primaryColor = styles
    .getPropertyValue("--primary-color")
    .trim();

console.log(primaryColor);
```

The result is:

```text
#2563eb
```

### Changing a Variable Dynamically

Consider:

```css
:root {
    --background-color: white;
    --text-color: #222;
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

JavaScript can change the values:

```javascript
document.documentElement.style.setProperty(
    "--background-color",
    "#111"
);

document.documentElement.style.setProperty(
    "--text-color",
    "white"
);
```

The page updates without changing the individual CSS declarations.

### Theme Switching

CSS Variables and JavaScript are commonly used together for theme switching.

CSS:

```css
:root {
    --background-color: white;
    --text-color: #222;
}

.dark-theme {
    --background-color: #111;
    --text-color: white;
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

JavaScript can toggle the theme class:

```javascript
document.documentElement.classList.toggle("dark-theme");
```

This changes the variables inherited by the page.

### Using JavaScript to Control Component Values

Suppose a component uses:

```css
.card {
    --card-radius: 8px;

    border-radius: var(--card-radius);
}
```

JavaScript can change the value:

```javascript
const card = document.querySelector(".card");

card.style.setProperty("--card-radius", "20px");
```

The card now uses:

```text
--card-radius: 20px
```

without changing the main CSS rule.

### Setting Multiple Variables

JavaScript can update several custom properties:

```javascript
const root = document.documentElement;

root.style.setProperty("--primary-color", "#2563eb");
root.style.setProperty("--text-color", "#222");
root.style.setProperty("--spacing", "16px");
```

This can be useful when dynamically updating a design system.

### Removing a CSS Variable

A custom property set through inline styles can be removed using:

```javascript
document.documentElement.style.removeProperty(
    "--primary-color"
);
```

After removal, the browser can fall back to another applicable declaration or inherited value.

### Reading a Variable From a Specific Element

Suppose:

```css
.card {
    --card-color: blue;
}
```

You can read the computed value from that element:

```javascript
const card = document.querySelector(".card");

const styles = getComputedStyle(card);

const color = styles
    .getPropertyValue("--card-color")
    .trim();

console.log(color);
```

The result is:

```text
blue
```

### JavaScript and CSS Separation

CSS Variables allow JavaScript to change values without requiring JavaScript to rewrite complete CSS rules.

Instead of JavaScript doing something like:

```javascript
element.style.backgroundColor = "#2563eb";
```

you can use a CSS Variable:

```css
.element {
    background-color: var(--primary-color);
}
```

and let JavaScript change:

```javascript
document.documentElement.style.setProperty(
    "--primary-color",
    "#2563eb"
);
```

This keeps the styling logic in CSS while JavaScript controls the dynamic value.

### Practical Example — Color Picker

CSS:

```css
:root {
    --user-color: #2563eb;
}

.box {
    width: 200px;
    height: 100px;
    background-color: var(--user-color);
}
```

HTML:

```html
<input type="color" id="colorPicker">

<div class="box"></div>
```

JavaScript:

```javascript
const colorPicker = document.querySelector("#colorPicker");

colorPicker.addEventListener("input", () => {
    document.documentElement.style.setProperty(
        "--user-color",
        colorPicker.value
    );
});
```

Now the selected color is stored in:

```css
--user-color
```

and the `.box` automatically updates.

### Practical Example — Dynamic Spacing

CSS:

```css
:root {
    --spacing: 16px;
}

.card {
    padding: var(--spacing);
}
```

HTML:

```html
<button id="increase">Increase</button>
<button id="decrease">Decrease</button>

<div class="card">
    Content
</div>
```

JavaScript can change the variable:

```javascript
const root = document.documentElement;

document.querySelector("#increase").addEventListener("click", () => {
    root.style.setProperty("--spacing", "32px");
});

document.querySelector("#decrease").addEventListener("click", () => {
    root.style.setProperty("--spacing", "8px");
});
```

The card responds because its padding uses:

```css
padding: var(--spacing);
```

### Important Point

JavaScript does not need to know every CSS property that uses the variable.

It only changes:

```text
CSS Variable
     ↓
--spacing
     ↓
CSS declarations using var(--spacing)
     ↓
Updated appearance
```

This makes CSS Variables a useful bridge between JavaScript behavior and CSS presentation.

> 💡 **Remember:** JavaScript can read custom properties with `getComputedStyle()` and modify them with `style.setProperty()`. This allows dynamic styling while keeping reusable presentation rules in CSS.

---

## CSS Variables for Themes

CSS Variables are very useful for creating **light and dark themes** because the same CSS declarations can use different custom-property values depending on the active theme.

Instead of creating completely separate styles for every theme, define the design values as variables and change those variables when the theme changes.

### Basic Theme Structure

A simple light theme can be defined on `:root`:

```css
:root {
    --background-color: #ffffff;
    --text-color: #222222;
    --primary-color: #2563eb;
}
```

Use the variables in the page:

```css
body {
    background-color: var(--background-color);
    color: var(--text-color);
}

button {
    background-color: var(--primary-color);
}
```

Now the actual component styles do not need to know which theme is active.

### Creating a Dark Theme

A dark theme can override the same variables:

```css
.dark-theme {
    --background-color: #111827;
    --text-color: #f9fafb;
    --primary-color: #60a5fa;
}
```

The existing CSS remains unchanged:

```css
body {
    background-color: var(--background-color);
    color: var(--text-color);
}

button {
    background-color: var(--primary-color);
}
```

When `.dark-theme` applies to an ancestor of these elements, the inherited variable values change.

Conceptually:

```text
Light theme
    ↓
--background-color: white
--text-color: #222
--primary-color: #2563eb

Dark theme
    ↓
--background-color: #111827
--text-color: #f9fafb
--primary-color: #60a5fa
```

### Theme Using a Class

A common approach is to place the theme class on the root element:

```html
<html class="dark-theme">
```

Then:

```css
:root {
    --background-color: white;
    --text-color: #222;
}

.dark-theme {
    --background-color: #111827;
    --text-color: white;
}
```

The page automatically uses the values inherited from the active theme.

### Theme Switching With JavaScript

JavaScript can switch the theme by adding or removing the class.

HTML:

```html
<button id="theme-toggle">
    Toggle Theme
</button>
```

CSS:

```css
:root {
    --background-color: white;
    --text-color: #222;
}

.dark-theme {
    --background-color: #111827;
    --text-color: white;
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

JavaScript:

```javascript
const button = document.querySelector("#theme-toggle");

button.addEventListener("click", () => {
    document.documentElement.classList.toggle("dark-theme");
});
```

The JavaScript changes only the theme state.

The actual colors remain controlled by CSS Variables.

### Multiple Theme Variables

A complete theme can define many design values:

```css
:root {
    --background-color: #ffffff;
    --surface-color: #f8fafc;
    --text-color: #1e293b;
    --muted-text-color: #64748b;
    --border-color: #cbd5e1;
    --primary-color: #2563eb;
}

.dark-theme {
    --background-color: #0f172a;
    --surface-color: #1e293b;
    --text-color: #f8fafc;
    --muted-text-color: #94a3b8;
    --border-color: #475569;
    --primary-color: #60a5fa;
}
```

Components can then use these variables:

```css
body {
    background-color: var(--background-color);
    color: var(--text-color);
}

.card {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
}

.card p {
    color: var(--muted-text-color);
}

.button {
    background-color: var(--primary-color);
}
```

The same component rules work for both themes.

### Using `prefers-color-scheme`

CSS can also respond to the user's operating-system color-scheme preference.

```css
:root {
    --background-color: white;
    --text-color: #222;
}

@media (prefers-color-scheme: dark) {
    :root {
        --background-color: #111827;
        --text-color: white;
    }
}
```

Then:

```css
body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

If the user's system prefers dark mode, the dark values are used.

### Automatic Theme vs Manual Theme

There are two common approaches.

#### Automatic Theme

Use:

```css
@media (prefers-color-scheme: dark) {
    :root {
        --background-color: #111827;
        --text-color: white;
    }
}
```

The browser follows the user's system preference.

#### Manual Theme

Use a class or attribute:

```html
<html class="dark-theme">
```

or:

```html
<html data-theme="dark">
```

Then override the variables:

```css
[data-theme="dark"] {
    --background-color: #111827;
    --text-color: white;
}
```

Manual themes allow the user to explicitly select a theme.

### Using Data Attributes for Themes

A data attribute is another clean approach:

```html
<html data-theme="dark">
```

CSS:

```css
:root {
    --background-color: white;
    --text-color: #222;
}

[data-theme="dark"] {
    --background-color: #111827;
    --text-color: white;
}
```

JavaScript can change the attribute:

```javascript
document.documentElement.dataset.theme = "dark";
```

To switch back:

```javascript
document.documentElement.dataset.theme = "light";
```

### Theme-Specific Component Values

Themes can also change component-specific variables.

```css
.card {
    --card-background: white;
    --card-border: #ddd;

    background-color: var(--card-background);
    border: 1px solid var(--card-border);
}

.dark-theme {
    --card-background: #1e293b;
    --card-border: #475569;
}
```

This allows the component to automatically adapt to the active theme.

### Theme Variables and Inheritance

The theme works particularly well because custom properties inherit.

For example:

```html
<html class="dark-theme">
    <body>
        <div class="card">
            <p>Hello</p>
        </div>
    </body>
</html>
```

The theme variables defined on the root element can flow down:

```text
<html>
   ↓
<body>
   ↓
.card
   ↓
<p>
```

The descendants can use:

```css
var(--background-color)
var(--text-color)
```

without defining the variables again.

### Practical Theme Example

```css
:root {
    --background-color: #ffffff;
    --surface-color: #f8fafc;
    --text-color: #1e293b;
    --border-color: #cbd5e1;
    --primary-color: #2563eb;
}

[data-theme="dark"] {
    --background-color: #0f172a;
    --surface-color: #1e293b;
    --text-color: #f8fafc;
    --border-color: #475569;
    --primary-color: #60a5fa;
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}

.card {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
}

.button {
    background-color: var(--primary-color);
}
```

The component styles remain the same.

Only the values change:

```text
Theme
  ↓
Custom Properties
  ↓
Components
  ↓
Different appearance
```

### Why CSS Variables Are Ideal for Themes

Without CSS Variables, you might need to write separate declarations:

```css
.card {
    background: white;
    color: black;
}

.dark .card {
    background: #1e293b;
    color: white;
}
```

With variables:

```css
.card {
    background: var(--surface-color);
    color: var(--text-color);
}
```

and only the variables change:

```css
:root {
    --surface-color: white;
    --text-color: black;
}

.dark-theme {
    --surface-color: #1e293b;
    --text-color: white;
}
```

This keeps theme logic centralized and reduces duplicated component styles.

> 💡 **Remember:** A theme can be implemented by changing a set of CSS Variables while keeping the component declarations unchanged. This is one of the most practical uses of CSS Custom Properties.

---

## Practical Examples

CSS Variables become especially useful when they are used to build reusable and maintainable components.

The following examples demonstrate common real-world uses.

### Example 1 — Reusable Color

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

.icon {
    color: var(--primary-color);
}
```

One variable controls the primary color used by multiple elements.

Changing:

```css
--primary-color: #7c3aed;
```

updates all elements using the variable.

### Example 2 — Reusable Spacing

```css
:root {
    --spacing: 16px;
}

.card {
    padding: var(--spacing);
}

.section {
    margin-bottom: var(--spacing);
}

.button {
    padding: var(--spacing);
}
```

A single variable can provide consistent spacing throughout a design.

### Example 3 — Button Variants

CSS Variables can simplify component variants.

```css
.button {
    --button-background: #2563eb;
    --button-text: white;

    background-color: var(--button-background);
    color: var(--button-text);
    padding: 10px 16px;
    border: none;
    border-radius: 8px;
}

.button.success {
    --button-background: #16a34a;
}

.button.danger {
    --button-background: #dc2626;
}
```

HTML:

```html
<button class="button">
    Primary
</button>

<button class="button success">
    Success
</button>

<button class="button danger">
    Delete
</button>
```

The main button styles remain unchanged.

Only the custom-property values change.

### Example 4 — Card Component

```css
.card {
    --card-background: white;
    --card-text: #222;
    --card-border: #ddd;
    --card-radius: 8px;
    --card-padding: 20px;

    background-color: var(--card-background);
    color: var(--card-text);
    border: 1px solid var(--card-border);
    border-radius: var(--card-radius);
    padding: var(--card-padding);
}
```

A variant can override the variables:

```css
.card.featured {
    --card-background: #eff6ff;
    --card-border: #2563eb;
}
```

This creates a different card appearance without duplicating the component's main styles.

### Example 5 — Responsive Design

```css
:root {
    --page-padding: 32px;
    --card-gap: 24px;
}

.page {
    padding: var(--page-padding);
}

.cards {
    display: flex;
    gap: var(--card-gap);
}

@media (max-width: 600px) {
    :root {
        --page-padding: 16px;
        --card-gap: 12px;
    }
}
```

The same component declarations work at different screen sizes.

### Example 6 — Dark Mode

```css
:root {
    --background-color: white;
    --text-color: #222;
    --surface-color: #f8fafc;
}

.dark-theme {
    --background-color: #0f172a;
    --text-color: #f8fafc;
    --surface-color: #1e293b;
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}

.card {
    background-color: var(--surface-color);
}
```

The theme changes the values while the component rules remain the same.

### Example 7 — CSS Variable With `calc()`

```css
:root {
    --base-spacing: 16px;
}

.card {
    padding: calc(var(--base-spacing) * 2);
}
```

The resulting padding is:

```text
16px × 2
   ↓
32px
```

This is useful when several values need to be derived from a common base value.

### Example 8 — Customizing a Component

A reusable component can expose variables for customization:

```css
.alert {
    --alert-background: #eff6ff;
    --alert-color: #1e40af;
    --alert-border: #93c5fd;

    background-color: var(--alert-background);
    color: var(--alert-color);
    border: 1px solid var(--alert-border);
    padding: 16px;
}
```

Variants can customize the component:

```css
.alert.warning {
    --alert-background: #fffbeb;
    --alert-color: #92400e;
    --alert-border: #fcd34d;
}

.alert.error {
    --alert-background: #fef2f2;
    --alert-color: #991b1b;
    --alert-border: #fca5a5;
}
```

The component structure stays the same.

### Example 9 — Navigation Theme

```css
.navbar {
    --nav-background: #ffffff;
    --nav-text: #222222;

    background-color: var(--nav-background);
    color: var(--nav-text);
}

.navbar.dark {
    --nav-background: #111827;
    --nav-text: #ffffff;
}
```

The navigation component can switch appearance by changing its variables.

### Example 10 — Form Controls

```css
.form-control {
    --input-border: #cbd5e1;
    --input-focus: #2563eb;

    border: 2px solid var(--input-border);
    padding: 10px;
}

.form-control:focus {
    --input-border: var(--input-focus);
    outline: none;
}
```

The same variable controls the border in different states.

### Example 11 — Theme With Data Attributes

HTML:

```html
<html data-theme="light">
```

CSS:

```css
:root {
    --background-color: white;
    --text-color: #222;
}

[data-theme="dark"] {
    --background-color: #111827;
    --text-color: white;
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

JavaScript can switch the theme:

```javascript
document.documentElement.dataset.theme = "dark";
```

### Example 12 — JavaScript-Controlled Color

CSS:

```css
:root {
    --user-color: #2563eb;
}

.preview {
    width: 200px;
    height: 100px;
    background-color: var(--user-color);
}
```

JavaScript:

```javascript
document.documentElement.style.setProperty(
    "--user-color",
    "#16a34a"
);
```

The preview automatically changes because it uses:

```css
background-color: var(--user-color);
```

### Example 13 — Reusable Design Tokens

A small design system can be created with variables:

```css
:root {
    /* Colors */
    --color-primary: #2563eb;
    --color-success: #16a34a;
    --color-danger: #dc2626;

    /* Spacing */
    --space-1: 4px;
    --space-2: 8px;
    --space-3: 16px;
    --space-4: 24px;

    /* Border Radius */
    --radius-small: 4px;
    --radius-medium: 8px;
    --radius-large: 12px;
}
```

Components can use these shared values:

```css
.button {
    padding: var(--space-2) var(--space-3);
    border-radius: var(--radius-medium);
    background-color: var(--color-primary);
}

.card {
    padding: var(--space-4);
    border-radius: var(--radius-large);
}
```

This creates consistency across the application.

### Example 14 — Complete Mini Example

HTML:

```html
<div class="card">
    <h2 class="card-title">CSS Variables</h2>
    <p class="card-text">
        Reusable CSS values make styles easier to maintain.
    </p>
    <button class="button">Learn More</button>
</div>
```

CSS:

```css
:root {
    --primary-color: #2563eb;
    --text-color: #1e293b;
    --surface-color: #ffffff;
    --border-color: #cbd5e1;
    --spacing: 16px;
    --radius: 8px;
}

.card {
    background-color: var(--surface-color);
    color: var(--text-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius);
    padding: var(--spacing);
}

.card-title {
    color: var(--primary-color);
}

.button {
    background-color: var(--primary-color);
    color: white;
    border: none;
    border-radius: var(--radius);
    padding: 10px 16px;
}
```

The design values are centralized:

```text
CSS Variables
     ↓
Colors
Spacing
Radius
Borders
     ↓
Components
     ↓
Consistent design
```

> 💡 **Remember:** The real power of CSS Variables comes from combining them with inheritance, the cascade, media queries, pseudo-classes, themes, and reusable components.

---

## Key Takeaways

- **CSS Variables** are officially called **CSS Custom Properties**.
- Custom property names begin with two hyphens, such as `--primary-color`.
- CSS Variables are commonly used with the `var()` function.
- A custom property is declared using:
  ```css
  --property-name: value;
  ```
- A custom property is used with:
  ```css
  var(--property-name);
  ```
- CSS Variables help reduce repetition and make CSS easier to maintain.
- Variables can store colors, sizes, spacing, fonts, borders, shadows, and other CSS values.
- Variables declared on `:root` are commonly used as global design values.
- Variables can also be declared locally on specific components.
- CSS custom properties normally **inherit** from parent elements to descendants.
- Custom properties participate in the **CSS cascade**.
- A local declaration can override an inherited custom property.
- The `var()` function supports fallback values:
  ```css
  var(--primary-color, blue);
  ```
- CSS Variables can be changed inside pseudo-classes such as `:hover`, `:focus`, and `:active`.
- CSS Variables work well with media queries for responsive designs.
- JavaScript can read custom properties with `getComputedStyle()`.
- JavaScript can modify custom properties with `style.setProperty()`.
- CSS Variables are useful for implementing light and dark themes.
- Variables can simplify reusable and customizable components.
- CSS Variables can be combined with functions such as `calc()`.
- CSS Variables are useful for creating consistent design systems and design tokens.

### Core Syntax

```css
:root {
    --primary-color: #2563eb;
    --spacing: 16px;
}

.button {
    background-color: var(--primary-color);
    padding: var(--spacing);
}
```

### Fallback Syntax

```css
.button {
    color: var(--text-color, black);
}
```

### Responsive Example

```css
:root {
    --spacing: 24px;
}

@media (max-width: 600px) {
    :root {
        --spacing: 12px;
    }
}

.card {
    padding: var(--spacing);
}
```

### Theme Example

```css
:root {
    --background-color: white;
    --text-color: #222;
}

.dark-theme {
    --background-color: #111827;
    --text-color: white;
}

body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

### Overall Mental Model

```text
Define
  ↓
--custom-property: value
  ↓
Store a reusable CSS value
  ↓
Use
  ↓
var(--custom-property)
  ↓
Apply the value to CSS properties
```

> 💡 **Remember:** CSS Variables make styles more reusable, maintainable, customizable, and consistent by allowing values to be defined once and reused throughout a stylesheet.

---

## References

- [MDN Web Docs — CSS Custom Properties for Cascading Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cascading_variables/Using_custom_properties)
- [MDN Web Docs — `var()` CSS Function](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Values/var)
- [MDN Web Docs — CSS `:root` Pseudo-Class](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors/:root)
- [MDN Web Docs — CSS `@media` Rule](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media)
- [MDN Web Docs — `prefers-color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media/prefers-color-scheme)
- [MDN Web Docs — CSS Cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cascade)
- [MDN Web Docs — CSS Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cascade/Inheritance)
- [MDN Web Docs — CSSOM](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)
- [MDN Web Docs — `getComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
- [MDN Web Docs — `CSSStyleDeclaration.setProperty()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/setProperty)
- [W3C — CSS Custom Properties for Cascading Variables Module](https://www.w3.org/TR/css-variables-1/)

---

## Quick Revision

### What Are CSS Variables?

CSS Variables, officially called **CSS Custom Properties**, are reusable CSS values defined with names beginning with two hyphens.

```css
--primary-color: #2563eb;
```

### How Are CSS Variables Used?

Use the `var()` function:

```css
color: var(--primary-color);
```

### Where Can Variables Be Declared?

They can be declared globally:

```css
:root {
    --primary-color: #2563eb;
}
```

or locally:

```css
.card {
    --card-color: #2563eb;
}
```

### Do CSS Variables Inherit?

Yes. Custom properties normally inherit from parent elements to descendants.

```css
.card {
    --text-color: blue;
}

.card p {
    color: var(--text-color);
}
```

### What Is a Fallback Value?

A fallback is used when a custom property cannot provide a usable value.

```css
color: var(--text-color, black);
```

Here, `black` is the fallback.

### Do CSS Variables Participate in the Cascade?

Yes. Custom properties participate in the CSS cascade.

```css
.card {
    --color: blue;
}

.card.special {
    --color: red;
}
```

The applicable declaration is determined by the cascade.

### Can Variables Change on Interaction?

Yes. Variables can be changed with pseudo-classes.

```css
.button {
    --button-color: blue;
}

.button:hover {
    --button-color: darkblue;
}
```

### Can Variables Be Used With Media Queries?

Yes.

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

### Can JavaScript Change CSS Variables?

Yes.

```javascript
document.documentElement.style.setProperty(
    "--primary-color",
    "red"
);
```

A variable can also be read with:

```javascript
const styles = getComputedStyle(document.documentElement);

const color = styles
    .getPropertyValue("--primary-color")
    .trim();
```

### Can CSS Variables Be Used for Themes?

Yes. Theme-specific values can override the same variables.

```css
:root {
    --background-color: white;
    --text-color: #222;
}

.dark-theme {
    --background-color: #111827;
    --text-color: white;
}
```

### Important Syntax

```css
/* Declaration */
--name: value;

/* Usage */
var(--name);

/* Usage with fallback */
var(--name, fallback);
```

### Quick Mental Model

```text
CSS Custom Property
        ↓
--property: value
        ↓
var(--property)
        ↓
CSS declaration
        ↓
Rendered result
```

### Remember These Points

```text
CSS Variables
│
├── Start with --
├── Use var() to access values
├── Can be global or local
├── Normally inherit
├── Participate in the cascade
├── Support fallback values
├── Work with pseudo-classes
├── Work with media queries
├── Can be controlled by JavaScript
└── Are useful for themes and design systems
```

> 💡 **One-line revision:** CSS Variables let you define reusable custom properties once and use, override, and dynamically change those values throughout a stylesheet.

---

## Best Practices

### 1. Use Meaningful Variable Names

Choose names that describe the purpose of the value.

Good:

```css
:root {
    --primary-color: #2563eb;
    --text-color: #222;
    --card-radius: 8px;
}
```

Avoid unclear names:

```css
:root {
    --x: #2563eb;
    --value1: #222;
    --thing: 8px;
}
```

Meaningful names make CSS easier to understand and maintain.

### 2. Use a Consistent Naming Convention

Keep variable names consistent throughout the project.

For example:

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

A consistent naming system makes variables easier to find and reuse.

### 3. Define Global Design Values in `:root`

Values that are shared throughout the application can be defined on `:root`.

```css
:root {
    --color-primary: #2563eb;
    --color-text: #222;
    --color-background: #fff;
    --spacing-medium: 16px;
    --radius-medium: 8px;
}
```

This provides a central location for common design values.

### 4. Keep Component-Specific Variables Local

Not every variable needs to be global.

If a value belongs only to one component, define it locally.

```css
.card {
    --card-padding: 20px;
    --card-radius: 8px;

    padding: var(--card-padding);
    border-radius: var(--card-radius);
}
```

This keeps the global variable namespace smaller and makes the component easier to customize.

### 5. Use Variables for Repeated Values

If the same design value appears repeatedly, consider creating a variable.

Instead of:

```css
.button {
    border-radius: 8px;
}

.card {
    border-radius: 8px;
}

.input {
    border-radius: 8px;
}
```

use:

```css
:root {
    --radius-medium: 8px;
}

.button {
    border-radius: var(--radius-medium);
}

.card {
    border-radius: var(--radius-medium);
}

.input {
    border-radius: var(--radius-medium);
}
```

### 6. Use Fallback Values When Appropriate

Reusable components can provide sensible defaults:

```css
.button {
    color: var(--button-text, white);
    background-color: var(--button-color, #2563eb);
}
```

This allows customization while maintaining a default appearance.

### 7. Avoid Excessive Variables

CSS Variables are useful, but not every value needs to become a variable.

For example, creating variables for values that are used only once can add unnecessary complexity:

```css
:root {
    --button-width: 137px;
}
```

If the value has no meaningful reuse or customization purpose, a normal CSS value may be clearer:

```css
.button {
    width: 137px;
}
```

Use variables where they provide real value.

### 8. Use Variables to Build Design Tokens

For larger projects, group reusable values into categories.

```css
:root {
    /* Colors */
    --color-primary: #2563eb;
    --color-success: #16a34a;
    --color-danger: #dc2626;

    /* Spacing */
    --space-small: 8px;
    --space-medium: 16px;
    --space-large: 24px;

    /* Radius */
    --radius-small: 4px;
    --radius-medium: 8px;
    --radius-large: 12px;
}
```

This creates a simple design-token system.

### 9. Use Variables for Theme Values

Keep theme-dependent values in variables.

```css
:root {
    --background-color: white;
    --text-color: #222;
}

.dark-theme {
    --background-color: #111827;
    --text-color: white;
}
```

Components can then remain unchanged:

```css
body {
    background-color: var(--background-color);
    color: var(--text-color);
}
```

### 10. Use Variables for Component Variants

Instead of duplicating entire component styles, override the variables that change.

```css
.button {
    --button-color: #2563eb;

    background-color: var(--button-color);
}

.button.success {
    --button-color: #16a34a;
}

.button.danger {
    --button-color: #dc2626;
}
```

This keeps variants concise.

### 11. Keep Variable Definitions Organized

Group related variables together.

```css
:root {
    /* Colors */
    --color-primary: #2563eb;
    --color-text: #222;

    /* Spacing */
    --space-small: 8px;
    --space-medium: 16px;

    /* Typography */
    --font-size-base: 16px;
    --font-size-heading: 2rem;

    /* Borders */
    --radius-medium: 8px;
    --border-color: #ddd;
}
```

Good organization makes large stylesheets easier to navigate.

### 12. Prefer Variables Over Repeated Magic Values

A magic value is a value whose purpose is not obvious.

For example:

```css
.card {
    padding: 23px;
}

.button {
    margin: 17px;
}
```

If these values represent a design system, define meaningful variables:

```css
:root {
    --space-medium: 16px;
    --space-large: 24px;
}
```

Then use the appropriate design values:

```css
.card {
    padding: var(--space-medium);
}

.button {
    margin: var(--space-large);
}
```

Do not create variables simply to hide arbitrary numbers; give variables meaningful design purposes.

### 13. Be Careful With `!important`

Avoid using `!important` with custom properties unless there is a specific reason.

Prefer organizing the cascade and variable scopes clearly:

```css
:root {
    --primary-color: blue;
}

.card {
    --primary-color: green;
}
```

Use `!important` only when it is genuinely necessary.

### 14. Use Comments for Complex Variable Systems

If a variable's purpose is not obvious, a comment can help.

```css
:root {
    /* Main brand color used by primary actions */
    --color-primary: #2563eb;

    /* Spacing unit used to build component spacing */
    --space-unit: 4px;
}
```

Avoid comments that merely repeat the variable name.

### 15. Keep the Variable System Simple

A good CSS Variable system should make the stylesheet easier to understand, not harder.

Prefer:

```css
.button {
    background-color: var(--color-primary);
}
```

over unnecessarily complicated chains when they do not provide meaningful benefits.

### 16. Use CSS Variables to Separate Design From Components

A useful structure is:

```text
Design values
      ↓
CSS Variables
      ↓
Components
      ↓
Rendered interface
```

For example:

```css
:root {
    --color-primary: #2563eb;
    --radius-medium: 8px;
    --space-medium: 16px;
}

.button {
    background-color: var(--color-primary);
    border-radius: var(--radius-medium);
    padding: var(--space-medium);
}
```

The component describes how the values are used, while the variables define the reusable design values.

### Best-Practice Checklist

```text
CSS Variables
│
├── Use meaningful names
├── Follow a consistent naming convention
├── Use :root for shared values
├── Keep component values local when appropriate
├── Reuse repeated design values
├── Provide fallbacks when useful
├── Avoid unnecessary variables
├── Organize design tokens
├── Use variables for themes
├── Use variables for component variants
├── Keep definitions organized
├── Avoid unnecessary !important
└── Keep the overall system simple
```

> 💡 **Remember:** Good CSS Variable usage is not about creating the maximum number of variables. It is about creating a clear, reusable, and maintainable system of values that makes the CSS easier to manage.