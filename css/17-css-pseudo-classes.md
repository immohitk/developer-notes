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