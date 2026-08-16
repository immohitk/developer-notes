## Table of Contents

1. [Introduction](#introduction)
2. [What Are CSS Pseudo-Classes?](#what-are-css-pseudo-classes)
3. [Why Are Pseudo-Classes Important?](#why-are-pseudo-classes-important)
4. [Pseudo-Class Syntax](#pseudo-class-syntax)
5. [:hover](#hover)
6. [:active](#active)
7. [:focus](#focus)
8. [:visited](#visited)
9. [:link](#link)
10. [:first-child](#first-child)
11. [:last-child](#last-child)
12. [:nth-child()](#nth-child)
13. [:nth-of-type()](#nth-of-type)
14. [:first-of-type](#first-of-type)
15. [:last-of-type](#last-of-type)
16. [:only-child](#only-child)
17. [:not()](#not)
18. [:checked](#checked)
19. [:disabled](#disabled)
20. [:enabled](#enabled)
21. [:required](#required)
22. [:optional](#optional)
23. [:valid](#valid)
24. [:invalid](#invalid)
25. [:focus-visible](#focus-visible)
26. [:focus-within](#focus-within)
27. [Form-Related Pseudo-Classes](#form-related-pseudo-classes)
28. [Combining Pseudo-Classes](#combining-pseudo-classes)
29. [Practical Examples](#practical-examples)
30. [Key Takeaways](#key-takeaways)
31. [References](#references)
32. [Quick Revision](#quick-revision)
33. [Best Practices](#best-practices)
34. [Common Mistakes](#common-mistakes)
35. [Interview Questions](#interview-questions)
36. [Practice Exercises](#practice-exercises)
37. [Related Topics](#related-topics)

---

## Introduction

CSS pseudo-classes are special keywords used with CSS selectors to style an element based on a particular state, condition, or position.

A pseudo-class is written with a single colon (`:`) followed by its name.

For example:

```css
button:hover {
    background-color: steelblue;
}
```

Here:

```text
button
   ↓
Element selector

:hover
   ↓
Pseudo-class
```

The style is applied when the user hovers over the button.

### What Pseudo-Classes Can Represent

Pseudo-classes can represent different situations, such as:

- An element being hovered.
- An element being clicked or activated.
- An element receiving focus.
- A link that has already been visited.
- The first or last element in a group.
- An element at a particular position.
- A checked form control.
- A disabled form control.
- A valid or invalid form input.

### Common Examples

```css
:hover
:active
:focus
:visited
:link
:first-child
:last-child
:nth-child()
:not()
:checked
:disabled
:enabled
:valid
:invalid
```

For example:

```css
a:hover {
    color: red;
}
```

```css
input:focus {
    border-color: steelblue;
}
```

```css
li:first-child {
    font-weight: bold;
}
```

Each selector applies styles under a particular condition.

### Pseudo-Classes Do Not Create New Elements

A pseudo-class does not create an additional HTML element.

For example:

```css
button:hover {
    color: white;
}
```

The `:hover` pseudo-class simply adds a condition to the `button` selector.

```text
button
   +
:hover condition
   ↓
button:hover
```

### Pseudo-Class vs Normal Selector

A normal selector can select an element directly:

```css
button {
    background-color: gray;
}
```

A pseudo-class can select the same element under a specific condition:

```css
button:hover {
    background-color: steelblue;
}
```

Therefore:

```text
button
   ↓
All matching buttons

button:hover
   ↓
Matching buttons currently being hovered
```

### Why Pseudo-Classes Are Useful

Pseudo-classes allow CSS to respond to user interaction and document structure without requiring additional classes in many situations.

For example, instead of adding a special class to the first list item:

```html
<li class="first">One</li>
```

CSS can use:

```css
li:first-child {
    font-weight: bold;
}
```

This allows the browser to determine which element matches the condition.

### Important Point

Pseudo-classes are an important part of CSS selectors because they allow styles to depend on an element's state, condition, or position.

The basic pattern is:

```css
selector:pseudo-class {
    property: value;
}
```

> 💡 **Tip:** Think of a pseudo-class as an additional condition attached to a selector.

> 💡 **Remember:** CSS pseudo-classes use a single colon (`:`), such as `:hover`, `:focus`, and `:first-child`.

---

## What Are CSS Pseudo-Classes?

CSS pseudo-classes are keywords added to selectors to select elements based on a specific state, condition, or position in the document.

They are written using a single colon (`:`) followed by the pseudo-class name.

### Basic Syntax

```css
selector:pseudo-class {
    property: value;
}
```

For example:

```css
button:hover {
    background-color: steelblue;
}
```

Here:

```text
button
   ↓
Normal selector

:hover
   ↓
Pseudo-class

button:hover
   ↓
Button when it is hovered
```

### Pseudo-Classes Represent States

Some pseudo-classes represent the current state of an element.

For example:

```css
input:focus {
    border-color: blue;
}
```

The styles apply when the input has focus.

Another example:

```css
button:disabled {
    opacity: 0.5;
}
```

The styles apply when the button is disabled.

### Pseudo-Classes Represent Positions

Pseudo-classes can also select elements based on their position among their siblings.

For example:

```css
li:first-child {
    font-weight: bold;
}
```

This selects a list item when it is the first child of its parent.

Another example:

```css
li:last-child {
    border-bottom: none;
}
```

This selects the last list item.

### Pseudo-Classes and User Interaction

Pseudo-classes are commonly used for interactive states.

```css
button:hover {
    background-color: blue;
}

button:active {
    transform: scale(0.98);
}

button:focus {
    outline: 2px solid blue;
}
```

These selectors respond to different interaction states.

```text
:hover
   ↓
Pointer is over the element

:active
   ↓
Element is being activated

:focus
   ↓
Element has focus
```

### Pseudo-Classes and Forms

Pseudo-classes can represent form-control states.

For example:

```css
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

They can also select checked or disabled controls:

```css
input:checked {
    accent-color: blue;
}

input:disabled {
    background-color: lightgray;
}
```

### Pseudo-Classes Do Not Add HTML Elements

A pseudo-class does not create a new element.

For example:

```css
p:first-child {
    color: red;
}
```

The `:first-child` part simply adds a condition to the selector.

The HTML remains:

```html
<p>First paragraph</p>
```

There is no additional HTML element created by `:first-child`.

### Pseudo-Class vs Class Selector

A normal class selector uses a period (`.`):

```css
.button {
    color: white;
}
```

A pseudo-class uses a colon (`:`):

```css
.button:hover {
    color: yellow;
}
```

The difference is:

```text
.button
   ↓
Class selector

.button:hover
   ↓
Class selector + pseudo-class
```

### Pseudo-Class vs Pseudo-Element

Pseudo-classes and pseudo-elements are different.

A pseudo-class uses one colon:

```css
:hover
:focus
:first-child
```

A pseudo-element generally uses two colons:

```css
::before
::after
::first-letter
::first-line
```

In general:

```text
Pseudo-class
    ↓
Selects an element based on a state,
condition, or position

Pseudo-element
    ↓
Targets a particular part of an element
```

### Common Categories

Pseudo-classes can be grouped into several categories.

#### User Interaction

```css
:hover
:active
:focus
:focus-visible
:focus-within
```

#### Links

```css
:link
:visited
```

#### Structural

```css
:first-child
:last-child
:nth-child()
:nth-of-type()
:first-of-type
:last-of-type
:only-child
```

#### Form States

```css
:checked
:disabled
:enabled
:required
:optional
:valid
:invalid
```

#### Logical Selection

```css
:not()
```

### Simple Example

HTML:

```html
<ul>
    <li>First</li>
    <li>Second</li>
    <li>Third</li>
</ul>
```

CSS:

```css
li:first-child {
    color: blue;
}

li:last-child {
    color: red;
}
```

The first list item receives the first style, while the last list item receives the second style.

### Important Point

A pseudo-class adds a condition to a selector.

```text
Normal selector
      +
Condition
      ↓
Pseudo-class selector
```

For example:

```css
a:hover
```

means that the `a` element is selected when the `:hover` condition applies.

> 💡 **Tip:** When learning pseudo-classes, first understand the condition represented by the pseudo-class, then look at which elements the selector can match.

> 💡 **Remember:** Pseudo-classes do not create elements. They provide additional conditions for selecting existing elements.

---

## Why Are Pseudo-Classes Important?

CSS pseudo-classes are important because they allow styles to respond to an element's state, condition, or position without requiring additional HTML classes in many situations.

### 1. Style User Interaction

Pseudo-classes make it possible to provide visual feedback when users interact with elements.

For example:

```css
button:hover {
    background-color: steelblue;
}
```

The button changes its appearance when the pointer moves over it.

Other interaction states include:

```css
button:active {
    transform: scale(0.98);
}

button:focus {
    outline: 2px solid steelblue;
}
```

This creates a more responsive interface.

### 2. Style Links Based on Their State

Links can have different styles depending on their state.

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}
```

This allows users to distinguish between links they have and have not visited.

### 3. Select Elements Based on Their Position

Pseudo-classes can select elements based on their position among siblings.

For example:

```css
li:first-child {
    font-weight: bold;
}

li:last-child {
    border-bottom: none;
}
```

This allows the first and last items to be styled differently without adding extra classes to the HTML.

### 4. Select Specific Elements with `:nth-child()`

The `:nth-child()` pseudo-class can select elements according to their position.

```css
li:nth-child(2) {
    color: red;
}
```

This selects the second child.

It can also be used for repeating patterns:

```css
li:nth-child(even) {
    background-color: lightgray;
}
```

This is useful for styling alternating rows in lists and tables.

### 5. Style Form Controls Based on Their State

Pseudo-classes are especially useful for forms.

For example:

```css
input:focus {
    border-color: steelblue;
}

input:disabled {
    background-color: lightgray;
}

input:checked {
    accent-color: steelblue;
}
```

The appearance of the form control changes according to its current state.

### 6. Provide Form Validation Feedback

Pseudo-classes can be used to visually indicate whether an input is valid or invalid.

```css
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

This can provide immediate visual feedback to users.

### 7. Reduce Unnecessary HTML Classes

Without pseudo-classes, you might add extra classes to elements just to identify their state or position.

For example:

```html
<li class="first-item">One</li>
<li>Two</li>
<li class="last-item">Three</li>
```

With pseudo-classes:

```html
<li>One</li>
<li>Two</li>
<li>Three</li>
```

CSS can determine the positions:

```css
li:first-child {
    font-weight: bold;
}

li:last-child {
    font-weight: bold;
}
```

This can keep the HTML simpler.

### 8. Improve User Experience

Pseudo-classes can provide visual feedback for actions such as:

```text
Hover
   ↓
Active
   ↓
Focus
   ↓
Checked
   ↓
Disabled
```

This helps users understand the current state of an interface.

### 9. Support Accessibility

Pseudo-classes such as `:focus` and `:focus-visible` can help make keyboard navigation easier to understand.

For example:

```css
button:focus-visible {
    outline: 3px solid steelblue;
}
```

A visible focus indicator helps users identify which interactive element currently has keyboard focus.

### 10. Create More Flexible CSS

Pseudo-classes allow CSS to respond dynamically to the document and user interaction.

For example:

```css
.card:hover {
    transform: translateY(-5px);
}
```

No JavaScript is required for this simple interaction.

### Important Point

Pseudo-classes make CSS more powerful because they allow selectors to react to:

```text
User interaction
       +
Element state
       +
Element position
       +
Form state
       +
Document structure
```

> 💡 **Tip:** Use pseudo-classes when the styling depends on a condition or state that CSS can already determine.

> 💡 **Remember:** Pseudo-classes can reduce unnecessary HTML classes while making interactive, structural, and form-related styling easier to manage.

---

## Pseudo-Class Syntax

CSS pseudo-classes are written by adding a single colon (`:`) followed by the pseudo-class name to a selector.

### Basic Syntax

```css
selector:pseudo-class {
    property: value;
}
```

For example:

```css
button:hover {
    background-color: steelblue;
}
```

Here:

```text
button
   ↓
CSS selector

:
   ↓
Pseudo-class separator

hover
   ↓
Pseudo-class name
```

Together:

```css
button:hover
```

means that the styles apply to a `button` when the `:hover` condition is active.

### Simple Examples

```css
a:hover {
    color: red;
}
```

```css
input:focus {
    border-color: blue;
}
```

```css
li:first-child {
    font-weight: bold;
}
```

```css
input:checked {
    accent-color: blue;
}
```

Each selector contains:

```text
Element selector
      +
Pseudo-class
      ↓
Conditional selector
```

### Pseudo-Class with a Class Selector

A pseudo-class can be combined with a normal class selector.

```css
.button:hover {
    background-color: blue;
}
```

Here:

```text
.button
   ↓
Class selector

:hover
   ↓
Pseudo-class
```

The selector matches elements with the `button` class when they are hovered.

### Pseudo-Class with an ID Selector

A pseudo-class can also be used with an ID selector.

```css
#submit:focus {
    outline: 2px solid blue;
}
```

This targets the element with the `submit` ID when it has focus.

### Pseudo-Class with an Element Selector

```css
input:disabled {
    opacity: 0.5;
}
```

This targets disabled `<input>` elements.

### Multiple Pseudo-Classes

Multiple pseudo-classes can be combined when their conditions need to apply to the same element.

For example:

```css
button:hover:focus {
    background-color: steelblue;
}
```

The selector applies when the button is both hovered and focused.

Another example:

```css
input:required:invalid {
    border-color: red;
}
```

This targets required inputs that are currently invalid.

### Pseudo-Class with Descendant Selectors

Pseudo-classes can be used as part of larger selectors.

```css
nav a:hover {
    color: red;
}
```

This selects links inside `nav` when they are hovered.

Another example:

```css
ul li:first-child {
    font-weight: bold;
}
```

This selects the first `li` child inside the `ul`.

### Functional Pseudo-Classes

Some pseudo-classes accept arguments inside parentheses.

Examples:

```css
:nth-child(2)
:nth-of-type(odd)
:not(.special)
```

For example:

```css
li:nth-child(2) {
    color: red;
}
```

The `2` is an argument passed to `:nth-child()`.

### Pseudo-Class vs Pseudo-Element Syntax

A pseudo-class generally uses one colon:

```css
:hover
:focus
:first-child
```

A pseudo-element generally uses two colons:

```css
::before
::after
::first-letter
```

For example:

```css
button:hover {
    color: white;
}
```

is a pseudo-class selector.

```css
p::first-letter {
    font-size: 2rem;
}
```

is a pseudo-element selector.

### Important Point

The general structure of a pseudo-class selector is:

```css
selector:pseudo-class
```

For functional pseudo-classes:

```css
selector:pseudo-class(argument)
```

Examples:

```css
button:hover
input:focus
li:first-child
li:nth-child(2)
input:not(.special)
```

> 💡 **Tip:** Read a pseudo-class selector from left to right: first identify the element or class being selected, then identify the condition added by the pseudo-class.

> 💡 **Remember:** Pseudo-classes use a single colon (`:`), while pseudo-elements generally use two colons (`::`).

---

## :hover

The `:hover` pseudo-class applies styles to an element when the user's pointer is positioned over that element.

It is commonly used to provide visual feedback for interactive elements such as links, buttons, cards, and navigation items.

### Basic Syntax

```css
selector:hover {
    property: value;
}
```

### Basic Example

```css
button:hover {
    background-color: steelblue;
    color: white;
}
```

When the pointer moves over the button, the specified styles are applied.

```text
Normal
  ↓
Pointer moves over element
  ↓
:hover becomes active
  ↓
Hover styles are applied
```

### Hover on Links

The `:hover` pseudo-class is commonly used with links.

```css
a:hover {
    color: red;
}
```

HTML:

```html
<a href="#">Visit Page</a>
```

When the pointer moves over the link, its text color changes.

### Hover on Buttons

```css
button {
    background-color: gray;
    color: white;
}

button:hover {
    background-color: steelblue;
}
```

The normal button has one appearance, while the hovered button has another.

### Hover with Background Color

```css
.card:hover {
    background-color: lightblue;
}
```

This changes the card's background when the pointer is over it.

### Hover with Text Color

```css
.title:hover {
    color: steelblue;
}
```

The text color changes while the pointer is over the element.

### Hover with Border

```css
.box:hover {
    border-color: steelblue;
}
```

The border color changes when the element is hovered.

### Hover with Transform

The `:hover` pseudo-class can be combined with `transform`.

```css
.card {
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-5px);
}
```

The card moves slightly upward when hovered.

### Hover with Scale

```css
.button {
    transition: transform 0.2s ease;
}

.button:hover {
    transform: scale(1.05);
}
```

The button becomes slightly larger while hovered.

### Hover with Multiple Properties

Multiple properties can be changed together.

```css
.card {
    background-color: white;
    border: 1px solid lightgray;
}

.card:hover {
    background-color: lightblue;
    border-color: steelblue;
    transform: translateY(-5px);
}
```

The hover state changes:

```text
Background
    +
Border
    +
Position
```

### Hover with a Class Selector

```css
.button:hover {
    background-color: blue;
}
```

This applies only to elements that have the `button` class.

### Hover with a Descendant Selector

`:hover` can also be used to style elements inside a hovered element.

```css
.card:hover .title {
    color: steelblue;
}
```

Here:

```text
.card:hover
     ↓
Card is hovered
     ↓
.title
     ↓
Title receives the style
```

HTML:

```html
<div class="card">
    <h2 class="title">Product</h2>
</div>
```

### Hover and Transition

`:hover` itself does not create a smooth animation.

For a smooth change, `transition` can be used.

```css
.button {
    background-color: gray;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: steelblue;
}
```

Without `transition`, the property changes immediately.

With `transition`, the change happens smoothly.

### Hover on Images

```css
img:hover {
    transform: scale(1.05);
}
```

This can create a zoom effect when the pointer moves over an image.

### Hover on Navigation Items

```css
nav a {
    color: black;
}

nav a:hover {
    color: steelblue;
}
```

This provides visual feedback when the user moves the pointer over navigation links.

### Important Point

The `:hover` pseudo-class represents a pointer-hover state.

```text
selector
   +
:hover
   ↓
Element while pointer is over it
```

It is commonly used for:

```text
Links
Buttons
Cards
Images
Navigation
Interactive controls
```

> 💡 **Tip:** Use `:hover` to provide clear visual feedback, but do not rely on hover alone for essential functionality because hover interactions are not available in the same way on touch devices.

> 💡 **Remember:** `:hover` changes the styling of an element while the pointer is over it. For smooth changes, combine it with `transition`.