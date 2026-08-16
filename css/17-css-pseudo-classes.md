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

---

## :active

The `:active` pseudo-class applies styles to an element while it is being activated by the user.

For a typical mouse interaction, this usually means the short period while the mouse button is being pressed on the element.

### Basic Syntax

```css
selector:active {
    property: value;
}
```

### Basic Example

```css
button:active {
    background-color: steelblue;
    color: white;
}
```

When the button is being pressed, the `:active` styles are applied.

```text
Normal
   ↓
User presses the button
   ↓
:active becomes active
   ↓
User releases the button
   ↓
Normal state returns
```

### Active State on Links

The `:active` pseudo-class can be used with links.

```css
a:active {
    color: red;
}
```

The style applies while the link is being activated.

### Active State on Buttons

```css
button {
    background-color: gray;
}

button:active {
    background-color: darkgray;
}
```

The button changes appearance while it is being pressed.

### Active with Transform

A common use is creating a pressed effect with `transform`.

```css
button {
    transition: transform 0.1s ease;
}

button:active {
    transform: scale(0.95);
}
```

The button becomes slightly smaller while being pressed.

### Active with Multiple Properties

Multiple properties can be changed together.

```css
.button {
    background-color: steelblue;
    color: white;
}

.button:active {
    background-color: darkblue;
    transform: scale(0.98);
}
```

The active state can provide immediate visual feedback that the interaction has been triggered.

### `:active` vs `:hover`

These pseudo-classes represent different states.

```text
:hover
   ↓
Pointer is over the element

:active
   ↓
Element is being activated
```

Example:

```css
button:hover {
    background-color: steelblue;
}

button:active {
    background-color: darkblue;
}
```

The first style applies while hovering, while the second applies during activation.

### `:active` vs `:focus`

`:active` and `:focus` are also different.

```text
:active
   ↓
Element is currently being activated

:focus
   ↓
Element currently has focus
```

For example:

```css
button:active {
    transform: scale(0.95);
}

button:focus {
    outline: 2px solid steelblue;
}
```

A button can be focused without being active.

### Using `:active` with Links and Buttons

```css
a:active,
button:active {
    transform: scale(0.98);
}
```

This gives both links and buttons a temporary pressed effect.

### Important Point

The `:active` pseudo-class represents an element while it is being activated.

```text
:hover
    ↓
Pointer is over element

:active
    ↓
Element is being activated

:focus
    ↓
Element has focus
```

> 💡 **Tip:** `:active` is useful for giving users immediate feedback when they press or activate an interactive element.

> 💡 **Remember:** `:active` is a temporary state. The styles normally stop applying when the activation ends.

---

## :focus

The `:focus` pseudo-class applies styles to an element when it has focus.

An element can receive focus when the user interacts with it, for example by clicking a form control or navigating through interactive elements with the keyboard.

### Basic Syntax

```css
selector:focus {
    property: value;
}
```

### Basic Example

```css
input:focus {
    border-color: steelblue;
}
```

When the input receives focus, its border changes.

```text
Normal
   ↓
Element receives focus
   ↓
:focus becomes active
   ↓
Focus moves away
   ↓
Normal state returns
```

### Focus on Input Fields

`:focus` is commonly used with form controls.

```css
input {
    border: 1px solid gray;
}

input:focus {
    border-color: steelblue;
}
```

HTML:

```html
<input type="text" placeholder="Enter your name">
```

When the user clicks inside the input, it receives focus and the focus styles are applied.

### Focus on Buttons

Buttons can also receive focus.

```css
button:focus {
    outline: 2px solid steelblue;
}
```

This makes the focused button visually identifiable.

### Focus on Links

Links can receive focus as well.

```css
a:focus {
    color: steelblue;
}
```

This is particularly useful when navigating links with the keyboard.

### Focus and Keyboard Navigation

Keyboard users can move focus between interactive elements using the `Tab` key.

For example:

```html
<a href="#">Home</a>
<a href="#">About</a>
<button>Contact</button>
```

When the user presses `Tab`, focus moves between the interactive elements.

A visible focus style helps the user know which element is currently focused.

### Focus vs Hover

`:focus` and `:hover` represent different states.

```text
:hover
   ↓
Pointer is over the element

:focus
   ↓
Element has focus
```

For example:

```css
button:hover {
    background-color: steelblue;
}

button:focus {
    outline: 2px solid blue;
}
```

An element can be focused without being hovered.

### Focus vs Active

`:focus` and `:active` also represent different states.

```text
:focus
   ↓
Element has focus

:active
   ↓
Element is currently being activated
```

For example:

```css
button:focus {
    outline: 2px solid steelblue;
}

button:active {
    transform: scale(0.98);
}
```

A button may remain focused after the user releases the mouse button, while `:active` is only active during the activation.

### Focus with Multiple Properties

Multiple properties can be changed when an element receives focus.

```css
input:focus {
    border-color: steelblue;
    background-color: lightblue;
    outline: none;
}
```

However, removing the default focus outline should only be done when a clear replacement focus indicator is provided.

### Focus on Form Controls

`:focus` can be used with different form controls.

```css
input:focus {
    border-color: steelblue;
}

textarea:focus {
    border-color: steelblue;
}

select:focus {
    border-color: steelblue;
}
```

### Focus and Accessibility

A visible focus indicator is important for keyboard accessibility.

For example:

```css
button:focus {
    outline: 3px solid steelblue;
}
```

This allows keyboard users to see which interactive element currently has focus.

A better approach for many interfaces is to use `:focus-visible` when the visual indicator should specifically respond to focus that needs to be shown to the user.

```css
button:focus-visible {
    outline: 3px solid steelblue;
}
```

### Important Point

The `:focus` pseudo-class represents an element that currently has focus.

```text
Element
   ↓
Receives focus
   ↓
:focus becomes active
   ↓
Focus moves away
   ↓
:focus no longer applies
```

Common elements that can receive focus include:

```text
Inputs
Buttons
Links
Select elements
Textareas
Other focusable controls
```

> 💡 **Tip:** Always make sure interactive elements have a clear visible focus state, especially when designing for keyboard users.

> 💡 **Remember:** `:focus` is about the element having focus, while `:hover` is about the pointer being over the element and `:active` is about the element being activated.

---

## :visited

The `:visited` pseudo-class applies styles to links that the user has already visited.

It is mainly used with `<a>` elements that have a valid `href` attribute.

### Basic Syntax

```css
a:visited {
    property: value;
}
```

### Basic Example

```css
a:visited {
    color: purple;
}
```

After a user visits a link, the link can be displayed with the specified visited style.

```text
Unvisited link
      ↓
User opens the link
      ↓
Link becomes visited
      ↓
:visited styles can apply
```

### Using `:link` and `:visited`

`:link` represents an unvisited link, while `:visited` represents a visited link.

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}
```

This creates a visual difference between links that have not been visited and links that have been visited.

### Example

HTML:

```html
<a href="https://example.com">Example</a>
```

CSS:

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}
```

Before visiting the link:

```text
Blue
 ↓
Unvisited
```

After visiting the link:

```text
Purple
 ↓
Visited
```

### `:visited` with Other Link Styles

Link pseudo-classes are often used together.

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}

a:hover {
    color: red;
}

a:active {
    color: orange;
}
```

These represent different link states:

```text
:link
   ↓
Unvisited

:visited
   ↓
Visited

:hover
   ↓
Pointer over link

:active
   ↓
Link is being activated
```

### `:visited` and Privacy Restrictions

Browsers place restrictions on what CSS can do with visited links for privacy reasons.

For example, CSS cannot freely use `:visited` to reveal a user's browsing history.

The browser restricts which properties can produce observable differences for visited links.

Therefore, use `:visited` primarily for simple visual styling.

### `:visited` Does Not Apply to Every Element

The `:visited` pseudo-class is specifically related to visited links.

For example:

```css
a:visited {
    color: purple;
}
```

It should not be treated as a general state selector for arbitrary elements such as:

```css
div:visited
```

### `:visited` vs `:link`

These two pseudo-classes represent opposite link states.

```text
:link
   ↓
Link has not been visited

:visited
   ↓
Link has been visited
```

Example:

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}
```

### Important Point

The `:visited` pseudo-class is used to style links that the browser considers visited.

```css
a:visited {
    color: purple;
}
```

It is useful for helping users distinguish previously visited links from unvisited links.

> 💡 **Tip:** Use `:visited` for simple visual differences, such as changing link color, and remember that browsers restrict visited-link styling for privacy.

> 💡 **Remember:** `:link` represents an unvisited link, while `:visited` represents a visited link.

---

## :link

The `:link` pseudo-class applies styles to links that have not yet been visited.

It is mainly used with `<a>` elements that have an `href` attribute.

### Basic Syntax

```css
a:link {
    property: value;
}
```

### Basic Example

```css
a:link {
    color: blue;
}
```

This styles unvisited links.

```text
Link
 ↓
Not visited
 ↓
:link applies
```

### `:link` vs `:visited`

The two pseudo-classes represent different link states.

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}
```

Here:

```text
:link
   ↓
Unvisited link

:visited
   ↓
Visited link
```

### Example

HTML:

```html
<a href="https://example.com">Example</a>
```

CSS:

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}
```

Before visiting the link, the `:link` styles can apply.

After visiting the link, the browser can apply the `:visited` styles instead.

### Using `:link` with Other Link States

Link pseudo-classes can be combined to style different interaction states.

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}

a:hover {
    color: red;
}

a:active {
    color: orange;
}
```

The states represent:

```text
:link
   ↓
Unvisited

:visited
   ↓
Visited

:hover
   ↓
Pointer is over the link

:active
   ↓
Link is being activated
```

### `:link` Applies to Unvisited Links

The `:link` pseudo-class is specifically for links that have not been visited.

For example:

```css
a:link {
    text-decoration: none;
}
```

This applies to unvisited links.

### `:link` and Normal `a` Selector

A normal selector:

```css
a {
    color: blue;
}
```

selects matching links generally.

A `:link` selector:

```css
a:link {
    color: blue;
}
```

specifically targets unvisited links.

This allows different styles to be defined for different link states.

### Link State Example

```css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}

a:hover {
    color: red;
}

a:active {
    color: orange;
}
```

This provides four different visual states:

```text
Unvisited
    ↓
:link

Visited
    ↓
:visited

Hovered
    ↓
:hover

Activated
    ↓
:active
```

### Important Point

The `:link` pseudo-class represents an unvisited link.

```css
a:link {
    color: blue;
}
```

It is useful when you want to style links differently depending on whether they have already been visited.

> 💡 **Tip:** `:link` and `:visited` are specifically related to link history, while `:hover`, `:active`, and `:focus` represent interaction states.

> 💡 **Remember:** `:link` selects unvisited links, while `:visited` selects links that have been visited.

---

## :first-child

The `:first-child` pseudo-class selects an element when it is the first child of its parent.

It is useful when you want to style the first element in a group without adding a separate class to the HTML.

### Basic Syntax

```css
selector:first-child {
    property: value;
}
```

### Basic Example

```css
li:first-child {
    font-weight: bold;
}
```

HTML:

```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

The first `<li>` is selected because it is the first child of the `<ul>`.

```text
<ul>
 ├── First item    ← :first-child
 ├── Second item
 └── Third item
</ul>
```

### Styling the First Paragraph

```css
p:first-child {
    color: steelblue;
}
```

This selects a `<p>` only when that paragraph is the first child of its parent.

For example:

```html
<div>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

The first paragraph matches:

```css
p:first-child
```

### Important Detail

`:first-child` is based on the element's position among **all of its siblings**, not simply the first element of the same type.

For example:

```html
<div>
    <h2>Title</h2>
    <p>Paragraph</p>
</div>
```

This selector:

```css
p:first-child {
    color: red;
}
```

does **not** match the paragraph because the `<h2>` is the first child.

The structure is:

```text
<div>
 ├── h2       ← First child
 └── p        ← Second child
</div>
```

Therefore, the paragraph is not the `:first-child`.

### `:first-child` with Classes

It can be combined with a class selector.

```css
.item:first-child {
    background-color: lightblue;
}
```

HTML:

```html
<div class="item">First</div>
<div class="item">Second</div>
<div class="item">Third</div>
```

The first `.item` is selected.

### `:first-child` with Descendant Selectors

```css
ul li:first-child {
    color: blue;
}
```

This selects an `<li>` when it is the first child of its parent `<ul>`.

### Common Use: Lists

```css
.menu li:first-child {
    border-top: none;
}
```

This can be useful for removing a top border from the first menu item.

### Common Use: Cards

```css
.card:first-child {
    margin-top: 0;
}
```

This can be used when the first card needs different spacing from the other cards.

### `:first-child` vs `:first-of-type`

These selectors are different.

`:first-child` checks whether the element is the first child of its parent.

`:first-of-type` checks whether the element is the first element of its specific type among its siblings.

Example:

```html
<div>
    <h2>Title</h2>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

This does not match:

```css
p:first-child {
    color: red;
}
```

because the `<p>` is not the first child.

But this does match:

```css
p:first-of-type {
    color: red;
}
```

because it is the first `<p>` among its sibling `<p>` elements.

### Important Point

The key idea is:

```text
:first-child
      ↓
Is this element the first child
of its parent?
```

It does not mean:

```text
Is this the first element of this type?
```

That is what `:first-of-type` is used for.

> 💡 **Tip:** When using `:first-child`, check the complete order of the parent's children, including elements of different types.

> 💡 **Remember:** `:first-child` selects an element only when it is the first child of its parent.

---

## :last-child

The `:last-child` pseudo-class selects an element when it is the last child of its parent.

It is useful when the final element in a group needs different styling.

### Basic Syntax

```css
selector:last-child {
    property: value;
}
```

### Basic Example

```css
li:last-child {
    font-weight: bold;
}
```

HTML:

```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

The last `<li>` is selected.

```text
<ul>
 ├── First item
 ├── Second item
 └── Third item    ← :last-child
</ul>
```

### Styling the Last Paragraph

```css
p:last-child {
    margin-bottom: 0;
}
```

This can be useful for removing unnecessary bottom spacing from the final paragraph.

### Important Detail

Like `:first-child`, `:last-child` considers **all children** of the parent.

For example:

```html
<div>
    <p>Paragraph</p>
    <button>Submit</button>
</div>
```

This selector:

```css
p:last-child {
    color: red;
}
```

does not match the paragraph because the `<button>` is the last child.

The structure is:

```text
<div>
 ├── p
 └── button     ← Last child
</div>
```

### `:last-child` with Classes

```css
.item:last-child {
    background-color: lightblue;
}
```

HTML:

```html
<div class="item">First</div>
<div class="item">Second</div>
<div class="item">Third</div>
```

Only the final `.item` is selected.

### `:last-child` with Descendant Selectors

```css
ul li:last-child {
    border-bottom: none;
}
```

This selects the last `<li>` child of the list.

### Common Use: Navigation

```css
nav li:last-child {
    margin-right: 0;
}
```

This can remove the right margin from the final navigation item.

### Common Use: Lists

```css
.menu li:last-child {
    border-bottom: none;
}
```

This is useful when list items have separators and the final item should not have one.

### `:last-child` vs `:last-of-type`

These selectors are different.

`:last-child` checks whether the element is the last child of its parent.

`:last-of-type` checks whether the element is the last element of its specific type among its siblings.

Example:

```html
<div>
    <p>First paragraph</p>
    <p>Last paragraph</p>
    <button>Submit</button>
</div>
```

This does not match:

```css
p:last-child {
    color: red;
}
```

because the `<button>` is the last child.

But this matches:

```css
p:last-of-type {
    color: red;
}
```

because it is the last `<p>` among the `<p>` elements.

### Comparing `:first-child` and `:last-child`

```text
:first-child
      ↓
First child of parent

:last-child
      ↓
Last child of parent
```

Example:

```css
li:first-child {
    color: blue;
}

li:last-child {
    color: red;
}
```

The first and final list items receive different styles.

### Important Point

The key idea is:

```text
:last-child
      ↓
Is this element the last child
of its parent?
```

It does not mean:

```text
Is this the last element of this type?
```

For that purpose, use:

```css
:last-of-type
```

> 💡 **Tip:** When using `:last-child`, check all of the parent's children, including elements of different types.

> 💡 **Remember:** `:last-child` selects an element only when it is the last child of its parent.

---

## :nth-child()

The `:nth-child()` pseudo-class selects an element based on its position among the children of its parent.

It is useful when you need to select a specific child or create repeating patterns without adding separate classes to the HTML.

### Basic Syntax

```css
selector:nth-child(value) {
    property: value;
}
```

### Selecting a Specific Child

For example:

```css
li:nth-child(2) {
    color: red;
}
```

This selects the second child of its parent when that child is an `<li>`.

HTML:

```html
<ul>
    <li>First</li>
    <li>Second</li>
    <li>Third</li>
</ul>
```

The result is:

```text
<ul>
 ├── First
 ├── Second    ← :nth-child(2)
 └── Third
</ul>
```

### Selecting the First Child

The first child can be selected with:

```css
li:nth-child(1) {
    font-weight: bold;
}
```

This is equivalent in this situation to:

```css
li:first-child {
    font-weight: bold;
}
```

### Selecting the Third Child

```css
li:nth-child(3) {
    color: steelblue;
}
```

This selects the third child if it is an `<li>`.

### Using `even`

The `even` keyword selects even-numbered children.

```css
li:nth-child(even) {
    background-color: lightgray;
}
```

For example:

```text
1 → Normal
2 → Styled
3 → Normal
4 → Styled
5 → Normal
6 → Styled
```

This is commonly used for alternating rows.

### Using `odd`

The `odd` keyword selects odd-numbered children.

```css
li:nth-child(odd) {
    background-color: lightblue;
}
```

The pattern is:

```text
1 → Styled
2 → Normal
3 → Styled
4 → Normal
5 → Styled
```

### Using `2n`

`2n` selects every second child.

```css
li:nth-child(2n) {
    background-color: lightgray;
}
```

This produces an even-child pattern.

### Using `2n + 1`

```css
li:nth-child(2n + 1) {
    background-color: lightblue;
}
```

This selects odd-numbered children.

```text
2n + 1

1 → Styled
2 → Normal
3 → Styled
4 → Normal
5 → Styled
```

### Using Other Formulas

The `:nth-child()` function can use formulas.

For example:

```css
li:nth-child(3n) {
    color: red;
}
```

This selects:

```text
3
6
9
12
...
```

Another example:

```css
li:nth-child(3n + 1) {
    color: blue;
}
```

This selects:

```text
1
4
7
10
...
```

### Selecting the First Few Children

A formula can be used to select an initial range.

For example:

```css
li:nth-child(-n + 3) {
    font-weight: bold;
}
```

This selects the first three children.

```text
1 → Styled
2 → Styled
3 → Styled
4 → Normal
5 → Normal
```

### Important Detail

Like `:first-child`, `:nth-child()` counts **all children**, not only elements of the same type.

Consider:

```html
<div>
    <h2>Title</h2>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

The children are:

```text
1 → h2
2 → p
3 → p
```

Therefore:

```css
p:nth-child(2) {
    color: red;
}
```

matches the first paragraph because it is the second child overall.

### `:nth-child()` vs `:nth-of-type()`

These selectors work differently.

`:nth-child()` counts all child elements.

`:nth-of-type()` counts only elements of the same type.

Example:

```html
<div>
    <h2>Title</h2>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

For:

```css
p:nth-child(2) {
    color: red;
}
```

the first paragraph matches because it is the second child.

For:

```css
p:nth-of-type(2) {
    color: blue;
}
```

the second paragraph matches because it is the second `<p>` element.

### Practical Example: Zebra Striping

A table can use `:nth-child()` to create alternating row colors.

```css
tr:nth-child(even) {
    background-color: lightgray;
}
```

HTML:

```html
<table>
    <tr>
        <td>Mohit</td>
        <td>85</td>
    </tr>
    <tr>
        <td>Rahul</td>
        <td>90</td>
    </tr>
    <tr>
        <td>Aman</td>
        <td>88</td>
    </tr>
    <tr>
        <td>Ravi</td>
        <td>92</td>
    </tr>
</table>
```

The second and fourth rows receive the style.

### Practical Example: Grid Items

```css
.card:nth-child(3n) {
    margin-right: 0;
}
```

This can be useful when styling repeating groups of cards.

### Important Point

The basic idea is:

```text
:nth-child()
      ↓
Count the children
      ↓
Find the requested position or pattern
      ↓
Apply the style
```

Common values include:

```css
:nth-child(1)
:nth-child(2)
:nth-child(3)
:nth-child(even)
:nth-child(odd)
:nth-child(2n)
:nth-child(2n + 1)
:nth-child(3n)
```

> 💡 **Tip:** When using `:nth-child()`, always count all child elements of the parent before deciding which number to use.

> 💡 **Remember:** `:nth-child()` is based on the element's position among all siblings, while `:nth-of-type()` counts elements of the same type.

---

## :nth-of-type()

The `:nth-of-type()` pseudo-class selects an element based on its position among its siblings of the same element type.

Unlike `:nth-child()`, which counts all child elements, `:nth-of-type()` counts only elements of the same type.

### Basic Syntax

```css
selector:nth-of-type(value) {
    property: value;
}
```

### Basic Example

```css
p:nth-of-type(2) {
    color: red;
}
```

This selects the second `<p>` element among its sibling `<p>` elements.

### `:nth-child()` vs `:nth-of-type()`

Consider:

```html
<div>
    <h2>Title</h2>
    <p>First paragraph</p>
    <p>Second paragraph</p>
    <p>Third paragraph</p>
</div>
```

The child positions are:

```text
1 → h2
2 → p
3 → p
4 → p
```

Using:

```css
p:nth-child(2) {
    color: red;
}
```

selects the first paragraph because it is the second child overall.

Using:

```css
p:nth-of-type(2) {
    color: blue;
}
```

selects the second paragraph because it is the second `<p>` element.

### Selecting the First Element of a Type

```css
p:nth-of-type(1) {
    font-weight: bold;
}
```

This is equivalent to:

```css
p:first-of-type {
    font-weight: bold;
}
```

### Selecting the Third Element of a Type

```css
p:nth-of-type(3) {
    color: steelblue;
}
```

This selects the third `<p>` among its sibling `<p>` elements.

### Using `even`

The `even` keyword selects even-numbered elements of the same type.

```css
p:nth-of-type(even) {
    background-color: lightgray;
}
```

The pattern is:

```text
1 → Normal
2 → Styled
3 → Normal
4 → Styled
5 → Normal
```

### Using `odd`

The `odd` keyword selects odd-numbered elements of the same type.

```css
p:nth-of-type(odd) {
    background-color: lightblue;
}
```

The pattern is:

```text
1 → Styled
2 → Normal
3 → Styled
4 → Normal
5 → Styled
```

### Using Formulas

`:nth-of-type()` also supports formulas.

For example:

```css
p:nth-of-type(2n) {
    color: red;
}
```

This selects:

```text
2nd
4th
6th
8th
...
```

Another example:

```css
p:nth-of-type(3n) {
    color: blue;
}
```

This selects:

```text
3rd
6th
9th
12th
...
```

### Using `2n + 1`

```css
p:nth-of-type(2n + 1) {
    font-weight: bold;
}
```

This selects odd-numbered `<p>` elements:

```text
1st → Styled
2nd → Normal
3rd → Styled
4th → Normal
5th → Styled
```

### Practical Example

HTML:

```html
<div class="content">
    <h2>Introduction</h2>
    <p>First paragraph</p>
    <p>Second paragraph</p>
    <p>Third paragraph</p>
    <p>Fourth paragraph</p>
</div>
```

CSS:

```css
.content p:nth-of-type(even) {
    background-color: lightgray;
}
```

Only the second and fourth paragraphs are styled.

```text
h2

p 1 → Normal
p 2 → Styled
p 3 → Normal
p 4 → Styled
```

### Another Example

Different element types can exist together:

```html
<div>
    <h2>Title</h2>
    <p>Paragraph 1</p>
    <span>Span</span>
    <p>Paragraph 2</p>
    <p>Paragraph 3</p>
</div>
```

For:

```css
p:nth-of-type(2) {
    color: red;
}
```

the second `<p>` is selected.

The `<span>` does not affect the `<p>` count.

```text
p 1 → Counted
span → Not counted
p 2 → Counted and selected
p 3 → Counted
```

### `:nth-of-type()` vs `:nth-child()`

| Selector | What It Counts |
| --- | --- |
| `:nth-child()` | All child elements |
| `:nth-of-type()` | Siblings of the same element type |

Example:

```html
<div>
    <h2>Title</h2>
    <p>First</p>
    <p>Second</p>
</div>
```

```css
p:nth-child(2) {
    color: red;
}
```

The first paragraph matches because it is child number `2`.

```css
p:nth-of-type(2) {
    color: blue;
}
```

The second paragraph matches because it is the second `<p>`.

### Important Point

The key difference is:

```text
:nth-child()
      ↓
Counts all siblings

:nth-of-type()
      ↓
Counts siblings of the same type
```

> 💡 **Tip:** Use `:nth-of-type()` when the position you care about is specifically among elements of the same HTML type.

> 💡 **Remember:** `:nth-of-type()` ignores other element types when calculating the position.

---

## :first-of-type

The `:first-of-type` pseudo-class selects an element when it is the first element of its type among its siblings.

Unlike `:first-child`, it does not require the element to be the first child overall.

### Basic Syntax

```css
selector:first-of-type {
    property: value;
}
```

### Basic Example

```css
p:first-of-type {
    color: steelblue;
}
```

HTML:

```html
<div>
    <h2>Title</h2>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

The first `<p>` is selected because it is the first `<p>` among its siblings.

```text
<div>
 ├── h2
 ├── p    ← :first-of-type
 └── p
</div>
```

### `:first-of-type` vs `:first-child`

These pseudo-classes are different.

```css
p:first-child {
    color: red;
}
```

checks whether the `<p>` is the **first child overall**.

```css
p:first-of-type {
    color: blue;
}
```

checks whether the `<p>` is the **first `<p>` element among its siblings**.

Consider:

```html
<div>
    <h2>Title</h2>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

The structure is:

```text
1 → h2
2 → p
3 → p
```

This does not match:

```css
p:first-child {
    color: red;
}
```

because the `<h2>` is the first child.

But this does match:

```css
p:first-of-type {
    color: blue;
}
```

because it is the first `<p>`.

### Another Example

```html
<div>
    <p>First paragraph</p>
    <span>Some text</span>
    <p>Second paragraph</p>
</div>
```

The first `<p>` matches:

```css
p:first-of-type {
    font-weight: bold;
}
```

The `<span>` does not affect the `<p>` count.

```text
p 1       ← First <p>
span      ← Different type
p 2
```

### Using `:first-of-type` with Different Elements

The pseudo-class can be used with different element types.

```css
h2:first-of-type {
    color: blue;
}

p:first-of-type {
    color: green;
}

li:first-of-type {
    font-weight: bold;
}
```

Each selector finds the first element of its specified type.

### Practical Example

HTML:

```html
<article>
    <h2>Introduction</h2>
    <p>First paragraph.</p>
    <p>Second paragraph.</p>
    <p>Third paragraph.</p>
</article>
```

CSS:

```css
article p:first-of-type {
    font-weight: bold;
}
```

Only the first paragraph is styled.

### Common Use

`:first-of-type` is useful when different types of elements are mixed together and you want to select the first element of a particular type.

For example:

```css
article p:first-of-type {
    margin-top: 0;
}
```

This can remove the top margin from the first paragraph without requiring an additional class.

### Important Point

The key difference is:

```text
:first-child
      ↓
First child overall

:first-of-type
      ↓
First element of its type
```

> 💡 **Tip:** Use `:first-of-type` when the element's position matters only among siblings of the same HTML element type.

> 💡 **Remember:** Other element types do not affect the position calculated by `:first-of-type`.

---

## :last-of-type

The `:last-of-type` pseudo-class selects an element when it is the last element of its type among its siblings.

Unlike `:last-child`, it does not require the element to be the final child overall.

### Basic Syntax

```css
selector:last-of-type {
    property: value;
}
```

### Basic Example

```css
p:last-of-type {
    color: steelblue;
}
```

HTML:

```html
<div>
    <p>First paragraph</p>
    <p>Second paragraph</p>
    <button>Submit</button>
</div>
```

The second `<p>` is selected because it is the last `<p>` among its siblings.

```text
<div>
 ├── p
 ├── p          ← :last-of-type
 └── button
</div>
```

### `:last-of-type` vs `:last-child`

These pseudo-classes work differently.

```css
p:last-child {
    color: red;
}
```

checks whether the `<p>` is the **last child overall**.

```css
p:last-of-type {
    color: blue;
}
```

checks whether the `<p>` is the **last `<p>` element among its siblings**.

Consider:

```html
<div>
    <p>First paragraph</p>
    <p>Last paragraph</p>
    <button>Submit</button>
</div>
```

The structure is:

```text
1 → p
2 → p
3 → button
```

This does not match:

```css
p:last-child {
    color: red;
}
```

because the `<button>` is the last child.

But this matches:

```css
p:last-of-type {
    color: blue;
}
```

because the second `<p>` is the last `<p>`.

### Different Element Types

Other element types do not affect the `:last-of-type` count.

For example:

```html
<div>
    <p>First paragraph</p>
    <span>Some text</span>
    <p>Last paragraph</p>
    <button>Submit</button>
</div>
```

This selector:

```css
p:last-of-type {
    font-weight: bold;
}
```

selects the second `<p>`.

The `<span>` and `<button>` do not affect which `<p>` is the last `<p>`.

### Using `:last-of-type` with Classes

```css
.card p:last-of-type {
    margin-bottom: 0;
}
```

This can remove the bottom margin from the final paragraph inside a card.

### Practical Example

HTML:

```html
<article>
    <h2>Article Title</h2>

    <p>First paragraph.</p>
    <p>Second paragraph.</p>
    <p>Final paragraph.</p>

    <button>Read More</button>
</article>
```

CSS:

```css
article p:last-of-type {
    margin-bottom: 0;
}
```

The final paragraph is selected even though the button comes after it.

### Comparing Related Pseudo-Classes

```text
:first-child
    ↓
First child overall

:last-child
    ↓
Last child overall

:first-of-type
    ↓
First element of a specific type

:last-of-type
    ↓
Last element of a specific type
```

### Important Point

The key idea is:

```text
:last-of-type
      ↓
Find the last element
of the specified type
      ↓
Apply the style
```

For example:

```css
p:last-of-type {
    color: blue;
}
```

means:

```text
Find the last <p>
among its siblings
```

> 💡 **Tip:** Use `:last-of-type` when other element types may appear after the element you want to select.

> 💡 **Remember:** `:last-child` looks at the final child overall, while `:last-of-type` looks at the final element of a particular type.

---

## :only-child

The `:only-child` pseudo-class selects an element when it is the only child of its parent.

It matches an element that has no siblings.

### Basic Syntax

```css
selector:only-child {
    property: value;
}
```

### Basic Example

```css
p:only-child {
    color: steelblue;
}
```

HTML:

```html
<div>
    <p>Only paragraph</p>
</div>
```

The `<p>` is selected because it is the only child of the `<div>`.

```text
<div>
 └── p    ← :only-child
</div>
```

### Element with Multiple Children

Consider:

```html
<div>
    <p>First paragraph</p>
    <p>Second paragraph</p>
</div>
```

This selector:

```css
p:only-child {
    color: red;
}
```

does not match either paragraph because each paragraph has a sibling.

```text
<div>
 ├── p
 └── p
```

Neither `<p>` is the only child.

### Different Element Types

`:only-child` does not require the parent to contain only one element of the same type.

It requires the parent to have only **one child overall**.

For example:

```html
<div>
    <p>Only child</p>
</div>
```

This matches:

```css
p:only-child {
    font-weight: bold;
}
```

But:

```html
<div>
    <h2>Title</h2>
    <p>Paragraph</p>
</div>
```

does not match:

```css
p:only-child {
    font-weight: bold;
}
```

because the `<p>` has an `<h2>` sibling.

### `:only-child` vs `:first-child`

These pseudo-classes are different.

`:first-child` selects an element when it is the first child.

```css
p:first-child {
    color: blue;
}
```

`:only-child` selects an element when it is the only child.

```css
p:only-child {
    color: red;
}
```

For example:

```html
<div>
    <p>Paragraph</p>
    <p>Another paragraph</p>
</div>
```

The first paragraph matches:

```css
p:first-child
```

but neither paragraph matches:

```css
p:only-child
```

### `:only-child` vs `:first-of-type`

`:first-of-type` selects the first element of a particular type among its siblings.

```css
p:first-of-type {
    color: blue;
}
```

`:only-child` requires there to be only one child overall.

Example:

```html
<div>
    <h2>Title</h2>
    <p>Paragraph</p>
</div>
```

The `<p>` can match:

```css
p:first-of-type {
    color: blue;
}
```

because it is the first `<p>`.

But it does not match:

```css
p:only-child {
    color: red;
}
```

because the `<h2>` is another child.

### Practical Example

HTML:

```html
<div class="message">
    <p>No messages available.</p>
</div>
```

CSS:

```css
.message p:only-child {
    text-align: center;
    font-style: italic;
}
```

The paragraph receives the styles because it is the only child inside `.message`.

### Another Example

```css
.card:only-child {
    width: 100%;
}
```

This can be useful when a container contains only one card and that card needs different styling.

### Important Point

The key idea is:

```text
:only-child
      ↓
Does this element have
any siblings?
      ↓
No
      ↓
Match
```

It is based on the number of children of the parent, not on the element's type.

> 💡 **Tip:** Remember that `:only-child` means exactly one child exists under the parent.

> 💡 **Remember:** `:only-child` is stricter than `:first-child`. An element can be the first child without being the only child.

---

## :not()

The `:not()` pseudo-class selects elements that do **not** match a specified selector.

It is useful when you want to apply a style to most elements while excluding specific elements.

### Basic Syntax

```css
selector:not(selector) {
    property: value;
}
```

### Basic Example

```css
p:not(.special) {
    color: gray;
}
```

This selects `<p>` elements that do not have the `special` class.

HTML:

```html
<p>Normal paragraph</p>
<p class="special">Special paragraph</p>
<p>Another paragraph</p>
```

The result is:

```text
Normal paragraph       ← Styled
Special paragraph      ← Not styled
Another paragraph      ← Styled
```

### Excluding a Class

A common use of `:not()` is excluding elements with a particular class.

```css
.button:not(.primary) {
    background-color: gray;
}
```

This selects `.button` elements that do not have the `.primary` class.

### Excluding an ID

```css
div:not(#main) {
    padding: 10px;
}
```

This selects `<div>` elements except the one with the `main` ID.

### Excluding an Element Type

`:not()` can also be used with different selectors.

```css
.container > *:not(p) {
    margin-bottom: 10px;
}
```

This selects direct children of `.container` that are not `<p>` elements.

### Using `:not()` with `:first-child`

Pseudo-classes can be combined.

```css
li:not(:first-child) {
    border-top: 1px solid gray;
}
```

This selects every list item except the first one.

```text
First item
    ↓
Not selected

Second item
    ↓
Selected

Third item
    ↓
Selected
```

This can be useful for adding separators between items without adding a separator before the first item.

### Using `:not()` with `:last-child`

```css
li:not(:last-child) {
    margin-bottom: 10px;
}
```

This applies the margin to every list item except the last one.

### Multiple Conditions

Modern CSS allows `:not()` to contain a selector list.

For example:

```css
button:not(.primary, .secondary) {
    background-color: gray;
}
```

This selects buttons that are neither `.primary` nor `.secondary`.

### `:not()` Does Not Select the Excluded Element

Consider:

```css
p:not(.special) {
    color: blue;
}
```

The logic is:

```text
Find <p>
   ↓
Does it have .special?
   ↓
Yes → Do not select
No  → Select
```

### Practical Example

HTML:

```html
<ul>
    <li>Home</li>
    <li class="active">Products</li>
    <li>About</li>
    <li>Contact</li>
</ul>
```

CSS:

```css
li:not(.active) {
    color: gray;
}
```

Only the non-active list items receive the style.

```text
Home       → Styled
Products   → Not styled
About      → Styled
Contact    → Styled
```

### Practical Example: Form Controls

```css
input:not([type="submit"]) {
    border: 1px solid gray;
}
```

This selects inputs whose type is not `submit`.

### `:not()` vs Normal Selector

Normal selector:

```css
p {
    color: blue;
}
```

selects all matching paragraphs.

Using `:not()`:

```css
p:not(.special) {
    color: blue;
}
```

selects only paragraphs that do not have the `special` class.

### Important Point

The key idea is:

```text
:not()
   ↓
Exclude elements matching
the specified selector
```

For example:

```css
li:not(:first-child)
```

means:

```text
Select li elements
+
Exclude the first child
```

> 💡 **Tip:** `:not()` is useful when it is simpler to describe what should be excluded than to list every element that should be included.

> 💡 **Remember:** `:not()` selects elements that do not match the selector inside its parentheses.

---

## :checked

The `:checked` pseudo-class selects form controls that are currently selected or checked.

It is commonly used with:

- Checkboxes
- Radio buttons
- Other checkable form controls

### Basic Syntax

```css
selector:checked {
    property: value;
}
```

### Basic Checkbox Example

HTML:

```html
<label>
    <input type="checkbox">
    Accept the terms
</label>
```

CSS:

```css
input:checked {
    accent-color: steelblue;
}
```

The style applies when the checkbox is checked.

```text
Unchecked
    ↓
:checked does not match

Checked
    ↓
:checked matches
```

### Styling a Checked Checkbox

```css
input[type="checkbox"]:checked {
    accent-color: green;
}
```

This specifically targets checked checkboxes.

### Radio Button Example

`:checked` also works with radio buttons.

HTML:

```html
<label>
    <input type="radio" name="plan" value="basic">
    Basic
</label>

<label>
    <input type="radio" name="plan" value="pro">
    Pro
</label>
```

CSS:

```css
input[type="radio"]:checked {
    accent-color: steelblue;
}
```

The pseudo-class applies to whichever radio button is currently selected.

### Styling a Related Element

`:checked` can be combined with the sibling combinator to style another element when a checkbox is checked.

HTML:

```html
<input type="checkbox" id="toggle">
<label for="toggle">Show details</label>

<p class="details">Additional information</p>
```

CSS:

```css
#toggle:checked + label {
    color: steelblue;
}
```

Here:

```text
#toggle
   ↓
:checked
   ↓
+
   ↓
Adjacent sibling
   ↓
label is styled
```

### Checkbox and `~` Sibling Combinator

The general sibling combinator can also be used.

HTML:

```html
<input type="checkbox" id="menu">
<div class="content">Menu content</div>
```

CSS:

```css
#menu:checked ~ .content {
    display: block;
}
```

When the checkbox is checked, the `.content` element is selected.

### `:checked` vs `:enabled` and `:disabled`

These pseudo-classes represent different form states.

```text
:checked
    ↓
Checkbox/radio is selected

:enabled
    ↓
Form control can be used

:disabled
    ↓
Form control cannot be used
```

For example:

```css
input:checked {
    accent-color: green;
}

input:disabled {
    opacity: 0.5;
}
```

### `:checked` vs `:focus`

A checked control does not necessarily have focus.

```text
:checked
    ↓
Control is selected

:focus
    ↓
Control currently has focus
```

For example:

```css
input:checked {
    accent-color: green;
}

input:focus {
    outline: 2px solid steelblue;
}
```

A checkbox can remain checked after focus moves to another element.

### Practical Example

HTML:

```html
<label>
    <input type="checkbox" class="task">
    Complete task
</label>
```

CSS:

```css
.task:checked {
    accent-color: green;
}
```

The checkbox changes its appearance when selected.

### Important Point

The key idea is:

```text
Form control
      ↓
Checked / selected
      ↓
:checked
      ↓
Apply CSS styles
```

> 💡 **Tip:** `:checked` is especially useful for styling checkboxes and radio buttons based on their current selected state.

> 💡 **Remember:** `:checked` represents a selected or checked state; it is different from `:focus`, which represents the element currently having focus.

---

## :disabled

The `:disabled` pseudo-class selects form controls that are currently disabled.

A disabled form control cannot normally be interacted with or edited by the user.

### Basic Syntax

```css
selector:disabled {
    property: value;
}
```

### Basic Example

HTML:

```html
<button disabled>Submit</button>
```

CSS:

```css
button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
}
```

The styles apply because the button has the `disabled` attribute.

```text
Enabled
   ↓
User can interact with control

Disabled
   ↓
User cannot normally interact with control
```

### Disabled Input

```html
<input type="text" disabled>
```

CSS:

```css
input:disabled {
    background-color: lightgray;
}
```

The input receives the disabled styles.

### Disabled Button

```css
button:disabled {
    background-color: gray;
    color: white;
}
```

This can make a disabled button visually different from an enabled button.

### Disabled Select

The pseudo-class also works with `<select>` elements.

```html
<select disabled>
    <option>Choose an option</option>
</select>
```

CSS:

```css
select:disabled {
    opacity: 0.6;
}
```

### Disabled Textarea

```html
<textarea disabled></textarea>
```

CSS:

```css
textarea:disabled {
    background-color: lightgray;
}
```

### `:disabled` vs `:enabled`

These pseudo-classes represent opposite states.

```text
:enabled
    ↓
Control can normally be used

:disabled
    ↓
Control is disabled
```

Example:

```css
input:enabled {
    background-color: white;
}

input:disabled {
    background-color: lightgray;
}
```

### Using `:disabled` with Other Pseudo-Classes

Pseudo-classes can be combined.

For example:

```css
button:disabled:hover {
    cursor: not-allowed;
}
```

However, disabled controls generally do not behave like normal interactive controls, so hover behavior can vary depending on the browser and element.

### `:disabled` vs Attribute Selector

You can also select an element using the attribute selector:

```css
button[disabled] {
    opacity: 0.5;
}
```

But `:disabled` specifically represents the disabled state of a form control.

```css
button:disabled {
    opacity: 0.5;
}
```

This makes the intent clearer when you want to style disabled controls.

### Practical Example

HTML:

```html
<form>
    <input type="text" placeholder="Username">

    <input type="email" placeholder="Email">

    <button disabled>Submit</button>
</form>
```

CSS:

```css
button:disabled {
    background-color: gray;
    color: white;
    opacity: 0.6;
}
```

The submit button is visually shown as disabled.

### Important Point

The key idea is:

```text
Form control
      ↓
Disabled state
      ↓
:disabled
      ↓
Apply disabled styles
```

Common elements that support disabled states include:

```text
<button>
<input>
<select>
<textarea>
<option>
<optgroup>
<fieldset>
```

> 💡 **Tip:** Use `:disabled` to make disabled controls visually distinguishable from controls that users can interact with.

> 💡 **Remember:** `:disabled` selects controls that are actually disabled; `:enabled` represents controls that are enabled.

---

## :enabled

The `:enabled` pseudo-class selects form controls that are currently enabled and can normally be interacted with by the user.

It is the opposite state of `:disabled`.

### Basic Syntax

```css
selector:enabled {
    property: value;
}
```

### Basic Example

HTML:

```html
<input type="text" placeholder="Username">
<input type="text" placeholder="Disabled" disabled>
```

CSS:

```css
input:enabled {
    border-color: steelblue;
}

input:disabled {
    border-color: gray;
}
```

The first input matches `:enabled`, while the second matches `:disabled`.

```text
Enabled
   ↓
Can normally be interacted with
   ↓
:enabled

Disabled
   ↓
Cannot normally be interacted with
   ↓
:disabled
```

### Enabled Buttons

```html
<button>Submit</button>
<button disabled>Disabled</button>
```

CSS:

```css
button:enabled {
    background-color: steelblue;
    color: white;
}

button:disabled {
    background-color: gray;
}
```

The first button is enabled, while the second button is disabled.

### Enabled Form Controls

`:enabled` can be used with form controls such as:

```text
<input>
<button>
<select>
<textarea>
<option>
<optgroup>
```

For example:

```css
input:enabled {
    background-color: white;
}
```

### `:enabled` vs `:disabled`

These pseudo-classes represent opposite states.

```text
:enabled
    ↓
Form control is enabled

:disabled
    ↓
Form control is disabled
```

Example:

```css
input:enabled {
    opacity: 1;
}

input:disabled {
    opacity: 0.5;
}
```

### Combining `:enabled` with Other Selectors

`:enabled` can be combined with classes and other selectors.

```css
.form-control:enabled {
    border-color: steelblue;
}
```

This selects enabled elements with the `form-control` class.

### Combining `:enabled` with `:focus`

Pseudo-classes can also be combined.

```css
input:enabled:focus {
    border-color: green;
}
```

This selects an input when it is both enabled and focused.

This can be useful when you want focused styles to apply only to controls that users can interact with.

### Attribute Selector Comparison

You may see:

```css
input:not([disabled]) {
    border-color: steelblue;
}
```

But:

```css
input:enabled {
    border-color: steelblue;
}
```

directly expresses the enabled state of the form control.

### Practical Example

HTML:

```html
<form>
    <input type="text" placeholder="Name">

    <input type="email" placeholder="Email">

    <input type="text" placeholder="Disabled field" disabled>
</form>
```

CSS:

```css
input:enabled {
    background-color: white;
    border: 1px solid steelblue;
}

input:disabled {
    background-color: lightgray;
    border: 1px solid gray;
}
```

The enabled inputs receive the interactive styling, while the disabled input receives the disabled styling.

### Important Point

The key idea is:

```text
Form control
      ↓
Enabled state
      ↓
:enabled
      ↓
Apply styles
```

`:enabled` is useful when the styling should specifically apply to controls that users can interact with.

> 💡 **Tip:** Use `:enabled` when you need to distinguish usable form controls from disabled ones.

> 💡 **Remember:** `:enabled` selects enabled form controls, while `:disabled` selects controls that are disabled.

---

## :required

The `:required` pseudo-class selects form controls that have the `required` attribute.

It is commonly used to style fields that users must complete before submitting a form.

### Basic Syntax

```css
selector:required {
    property: value;
}
```

### Basic Example

HTML:

```html
<input type="text" required>
```

CSS:

```css
input:required {
    border-color: steelblue;
}
```

The input matches `:required` because it has the `required` attribute.

```text
required attribute
       ↓
Field must be completed
       ↓
:required matches
```

### Required Input

```html
<label>
    Name:
    <input type="text" required>
</label>
```

CSS:

```css
input:required {
    background-color: lightyellow;
}
```

This can visually indicate that the field is required.

### Required Email Field

```html
<input type="email" required>
```

CSS:

```css
input:required {
    border: 2px solid steelblue;
}
```

The same pseudo-class can be used with different form-control types.

### `:required` vs `:optional`

These pseudo-classes represent opposite states.

```text
:required
    ↓
Control is required

:optional
    ↓
Control is not required
```

Example:

```css
input:required {
    border-color: steelblue;
}

input:optional {
    border-color: gray;
}
```

### Combining `:required` with `:invalid`

`:required` can be combined with other pseudo-classes.

```css
input:required:invalid {
    border-color: red;
}
```

This targets a required input that is currently invalid.

For example:

```html
<input type="email" required>
```

If the field is empty or contains an invalid email value, the selector can match.

### Combining `:required` with `:valid`

```css
input:required:valid {
    border-color: green;
}
```

This can style a required input when its current value satisfies its validation constraints.

### Practical Example

HTML:

```html
<form>
    <label>
        Name:
        <input type="text" required>
    </label>

    <label>
        Email:
        <input type="email" required>
    </label>

    <label>
        Phone:
        <input type="tel">
    </label>
</form>
```

CSS:

```css
input:required {
    background-color: lightyellow;
}
```

The name and email fields match `:required`, while the phone field does not.

### `:required` vs Attribute Selector

You can also select an element using:

```css
input[required] {
    border-color: steelblue;
}
```

But:

```css
input:required {
    border-color: steelblue;
}
```

directly represents the required state of the form control.

### Important Point

The key idea is:

```text
Form control
      ↓
Has required constraint
      ↓
:required
      ↓
Apply styles
```

`:required` is useful when you want to visually distinguish fields that users must complete.

> 💡 **Tip:** Combine `:required` with validation pseudo-classes such as `:valid` and `:invalid` when you need more specific form-state styling.

> 💡 **Remember:** `:required` selects form controls that are required, while `:optional` selects controls that are not required.

---

## :optional

The `:optional` pseudo-class selects form controls that do not have the `required` constraint.

It is commonly used to style fields that users are not required to complete.

### Basic Syntax

```css
selector:optional {
    property: value;
}
```

### Basic Example

HTML:

```html
<input type="text">
```

CSS:

```css
input:optional {
    border-color: gray;
}
```

The input matches `:optional` because it is not marked as required.

```text
No required constraint
        ↓
     :optional
        ↓
Apply styles
```

### Required vs Optional

Consider:

```html
<input type="text" required>
<input type="text">
```

CSS:

```css
input:required {
    border-color: steelblue;
}

input:optional {
    border-color: gray;
}
```

The first input matches `:required`.

The second input matches `:optional`.

```text
required attribute
        ↓
     :required

No required attribute
        ↓
     :optional
```

### Optional Email Field

```html
<label>
    Website:
    <input type="url">
</label>
```

CSS:

```css
input:optional {
    background-color: #f5f5f5;
}
```

The field can be left empty because it does not have the `required` constraint.

### Optional Textarea

```html
<textarea></textarea>
```

CSS:

```css
textarea:optional {
    border-color: gray;
}
```

### Optional Select

```html
<select>
    <option>Choose an option</option>
    <option>Option 1</option>
</select>
```

CSS:

```css
select:optional {
    border-color: gray;
}
```

### Combining `:optional` with `:valid`

`:optional` can be combined with other pseudo-classes.

```css
input:optional:valid {
    border-color: green;
}
```

This selects an optional input whose current value satisfies its validation constraints.

### Combining `:optional` with `:invalid`

```css
input:optional:invalid {
    border-color: orange;
}
```

This can be useful when an optional field has been filled in but its value does not satisfy its validation constraints.

### Practical Example

HTML:

```html
<form>
    <label>
        Name:
        <input type="text" required>
    </label>

    <label>
        Phone:
        <input type="tel">
    </label>

    <label>
        Website:
        <input type="url">
    </label>
</form>
```

CSS:

```css
input:required {
    border: 2px solid steelblue;
}

input:optional {
    border: 1px solid gray;
}
```

The name field is required, while the phone and website fields are optional.

### `:optional` vs `:required`

These pseudo-classes represent opposite requiredness states.

```text
:required
    ↓
Control has a required constraint

:optional
    ↓
Control does not have a required constraint
```

### Important Point

The `:optional` pseudo-class is based on whether a form control has a required constraint.

```css
input:optional {
    /* styles */
}
```

It does not mean that the field currently contains an empty value. An optional field can still contain a value.

> 💡 **Tip:** Remember that `:optional` describes the validation requirement of the control, not whether the user has left the field empty.

> 💡 **Remember:** `:required` selects required form controls, while `:optional` selects controls that are not required.

---

## :valid

The `:valid` pseudo-class selects form controls whose current value satisfies the validation rules applied to them.

It is commonly used with form controls such as:

- Text inputs
- Email inputs
- URL inputs
- Number inputs
- Other controls with validation constraints

### Basic Syntax

```css
selector:valid {
    property: value;
}
```

### Basic Example

```html
<input type="email" required>
```

CSS:

```css
input:valid {
    border-color: green;
}
```

When the value satisfies the input's validation requirements, the `:valid` styles can apply.

```text
Input value
    ↓
Validation rules checked
    ↓
Value satisfies rules
    ↓
:valid matches
```

### Valid Email Input

```html
<input type="email" required>
```

CSS:

```css
input:valid {
    border-color: green;
}
```

A valid email value such as:

```text
mohit@example.com
```

can satisfy the email validation requirement.

### Invalid Email Input

Compare:

```css
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

The browser can apply different styles depending on whether the current value satisfies the validation constraints.

### Using `:valid` with `:required`

These pseudo-classes can be combined.

```css
input:required:valid {
    border-color: green;
}
```

This selects a required input whose current value is valid.

For example:

```html
<input type="email" required>
```

### Using `:valid` with `:optional`

An optional field can also be valid.

```css
input:optional:valid {
    border-color: green;
}
```

Remember:

```text
:required
    ↓
Describes whether the field is required

:valid
    ↓
Describes whether its current value satisfies validation
```

These are different concepts.

### Pattern Validation

The `pattern` attribute can define a validation pattern.

```html
<input
    type="text"
    pattern="[A-Za-z]+"
    required
>
```

CSS:

```css
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

The input can match `:valid` when its value satisfies the specified pattern and other applicable constraints.

### Minimum and Maximum Values

Number inputs can also use validation constraints.

```html
<input
    type="number"
    min="1"
    max="100"
>
```

CSS:

```css
input:valid {
    border-color: green;
}
```

A value within the specified range can satisfy the validation constraint.

### Minimum Length

Text inputs can use `minlength`.

```html
<input
    type="text"
    minlength="5"
    required
>
```

CSS:

```css
input:valid {
    border-color: green;
}
```

The value can match `:valid` when it satisfies the applicable requirements.

### Practical Form Example

HTML:

```html
<form>
    <label>
        Email:
        <input type="email" required>
    </label>

    <label>
        Username:
        <input type="text" minlength="3" required>
    </label>

    <button type="submit">Submit</button>
</form>
```

CSS:

```css
input:valid {
    border: 2px solid green;
}

input:invalid {
    border: 2px solid red;
}
```

The border changes according to the current validity state.

### `:valid` vs `:invalid`

These pseudo-classes represent opposite validation states.

```text
:valid
    ↓
Current value satisfies
the applicable constraints

:invalid
    ↓
Current value does not satisfy
the applicable constraints
```

### Important Point

`:valid` does not simply mean that a field contains text.

It means the current value satisfies the validation constraints that apply to that form control.

For example:

```html
<input type="email">
```

The browser can evaluate whether the entered value satisfies the email input's validity requirements.

> 💡 **Tip:** Use `:valid` together with `:invalid` when providing visual feedback for form validation.

> 💡 **Remember:** `:valid` describes the current validation state of a form control, while `:required` describes whether the control is required.

---

## :invalid

The `:invalid` pseudo-class selects form controls whose current value does not satisfy the validation rules that apply to them.

It is commonly used to provide visual feedback when a form value is invalid.

### Basic Syntax

```css
selector:invalid {
    property: value;
}
```

### Basic Example

```html
<input type="email" required>
```

CSS:

```css
input:invalid {
    border-color: red;
}
```

When the current value does not satisfy the input's validation constraints, the `:invalid` styles can apply.

```text
Input value
    ↓
Validation rules checked
    ↓
Value does not satisfy rules
    ↓
:invalid matches
```

### Invalid Email Input

```html
<input type="email" required>
```

CSS:

```css
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

An invalid email value can receive the `:invalid` styling.

### Using `:invalid` with `:required`

These pseudo-classes can be combined:

```css
input:required:invalid {
    border-color: red;
}
```

This targets a required input whose current value does not satisfy its validation constraints.

### Using `:invalid` with `:optional`

Optional controls can also become invalid when a value has been entered that violates their constraints.

```css
input:optional:invalid {
    border-color: orange;
}
```

For example:

```html
<input type="email">
```

The field is optional, but if a value is entered, that value can still be invalid.

### Pattern Validation

The `pattern` attribute can define a validation pattern.

```html
<input
    type="text"
    pattern="[A-Za-z]+"
>
```

CSS:

```css
input:invalid {
    border-color: red;
}
```

If the value does not satisfy the specified pattern, the input can match `:invalid`.

### Minimum and Maximum Values

Number inputs can have range constraints.

```html
<input
    type="number"
    min="1"
    max="100"
>
```

CSS:

```css
input:invalid {
    border-color: red;
}
```

A value outside the specified range can cause the control to match `:invalid`.

### Minimum Length

Text inputs can use `minlength`.

```html
<input
    type="text"
    minlength="5"
    required
>
```

CSS:

```css
input:invalid {
    border-color: red;
}
```

A value that does not satisfy the applicable length requirement can match `:invalid`.

### Practical Form Example

HTML:

```html
<form>
    <label>
        Email:
        <input type="email" required>
    </label>

    <label>
        Username:
        <input type="text" minlength="3" required>
    </label>

    <button type="submit">Submit</button>
</form>
```

CSS:

```css
input:valid {
    border: 2px solid green;
}

input:invalid {
    border: 2px solid red;
}
```

The input border can change according to its current validation state.

### `:invalid` vs `:valid`

These pseudo-classes represent opposite validation states.

```text
:valid
    ↓
Current value satisfies
the applicable constraints

:invalid
    ↓
Current value does not satisfy
the applicable constraints
```

### Important Point

`:invalid` does not simply mean that a field is empty.

It means that the current state or value of the form control does not satisfy the validation constraints that apply to it.

For example:

```html
<input type="email" required>
```

can be invalid when the required value is missing or when the entered value does not satisfy the email constraint.

> 💡 **Tip:** Use `:invalid` together with `:valid` when providing visual feedback for form validation.

> 💡 **Remember:** `:invalid` describes the current validation state of a form control, while `:required` describes whether the control is required.

---

## :focus-visible

The `:focus-visible` pseudo-class applies styles when an element has focus and the browser determines that a visible focus indicator should be shown.

It is especially useful for improving keyboard accessibility while avoiding unnecessary focus styling in situations where the browser does not consider a visible indicator necessary.

### Basic Syntax

```css
selector:focus-visible {
    property: value;
}
```

### Basic Example

```css
button:focus-visible {
    outline: 3px solid steelblue;
}
```

When the button receives focus in a context where a visible focus indicator is appropriate, the specified styles are applied.

### `:focus` vs `:focus-visible`

Both pseudo-classes are related to focus, but they have different purposes.

```text
:focus
   ↓
Element currently has focus

:focus-visible
   ↓
Element has focus and the browser determines
that a visible focus indicator should be shown
```

For example:

```css
button:focus {
    outline: 2px solid steelblue;
}
```

styles every matching focused button.

```css
button:focus-visible {
    outline: 3px solid steelblue;
}
```

provides a visible focus style when appropriate according to the browser's focus indication behavior.

### Keyboard Navigation

`:focus-visible` is particularly useful for keyboard navigation.

Consider:

```html
<button>Home</button>
<button>About</button>
<button>Contact</button>
```

CSS:

```css
button:focus-visible {
    outline: 3px solid steelblue;
}
```

When a user navigates through the buttons using the keyboard, the focus indicator can make the currently focused button easy to identify.

```text
Tab
 ↓
Button receives focus
 ↓
:focus-visible
 ↓
Visible focus indicator
```

### Accessibility

A visible focus indicator is important for users who navigate a page using a keyboard.

For example:

```css
button:focus-visible {
    outline: 3px solid steelblue;
    outline-offset: 2px;
}
```

This provides a clear visual indication of which interactive element currently has focus.

### Using `:focus-visible` with Links

```css
a:focus-visible {
    outline: 2px solid steelblue;
    outline-offset: 2px;
}
```

This can provide a visible focus indicator for keyboard users navigating links.

### Using `:focus-visible` with Form Controls

```css
input:focus-visible {
    border-color: steelblue;
    outline: 2px solid steelblue;
}
```

The focus styling can be applied to form controls when visible focus indication is appropriate.

### `:focus` and `:focus-visible` Together

A common approach is to use general focus behavior while providing a stronger visible indicator through `:focus-visible`.

```css
button:focus {
    outline: none;
}

button:focus-visible {
    outline: 3px solid steelblue;
    outline-offset: 2px;
}
```

However, removing the default focus indicator should be done carefully. The `:focus-visible` rule should provide a clear and accessible replacement.

### Important Point

The key idea is:

```text
Element receives focus
        ↓
Browser determines whether
visible focus indication is appropriate
        ↓
:focus-visible
        ↓
Apply visible focus styles
```

`:focus-visible` is designed to help developers provide accessible focus indicators without necessarily showing the same focus styling in every interaction scenario.

> 💡 **Tip:** Prefer `:focus-visible` when you want a strong visible focus indicator that is especially helpful for keyboard navigation.

> 💡 **Remember:** `:focus` represents an element having focus, while `:focus-visible` is intended for focus states where a visible focus indicator should be presented.

---

## :focus-within

The `:focus-within` pseudo-class selects an element when that element itself has focus or when one of its descendants has focus.

It is especially useful when you want to style a parent element based on the focus state of an input, button, link, or another focusable element inside it.

### Basic Syntax

```css
selector:focus-within {
    property: value;
}
```

### Basic Example

HTML:

```html
<div class="form-group">
    <label for="name">Name</label>
    <input id="name" type="text">
</div>
```

CSS:

```css
.form-group:focus-within {
    border-color: steelblue;
}
```

When the input receives focus, the `.form-group` parent also matches `:focus-within`.

```text
.form-group
    ↓
    input receives focus
    ↓
:focus-within matches the parent
```

### `:focus` vs `:focus-within`

These pseudo-classes have different purposes.

`:focus` selects the element that currently has focus.

```css
input:focus {
    border-color: steelblue;
}
```

`:focus-within` can select a parent when it or one of its descendants has focus.

```css
.form-group:focus-within {
    border-color: steelblue;
}
```

The difference is:

```text
:focus
   ↓
This element has focus

:focus-within
   ↓
This element or a descendant has focus
```

### Styling a Form Group

HTML:

```html
<div class="form-group">
    <label for="email">Email</label>
    <input id="email" type="email">
</div>
```

CSS:

```css
.form-group {
    padding: 10px;
    border: 1px solid gray;
}

.form-group:focus-within {
    border-color: steelblue;
}
```

When the input receives focus, the border of the entire form group changes.

### Styling a Parent Based on a Link

HTML:

```html
<nav class="menu">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
</nav>
```

CSS:

```css
.menu:focus-within {
    background-color: lightgray;
}
```

When one of the links inside `.menu` receives focus, the `.menu` element matches `:focus-within`.

### Styling a Card

HTML:

```html
<div class="card">
    <h2>Product</h2>
    <a href="#">View Product</a>
</div>
```

CSS:

```css
.card:focus-within {
    border-color: steelblue;
}
```

The card can receive a visual focus state when its link receives focus.

### Using `:focus-within` with Form Controls

It can be useful when several controls belong to the same container.

```css
.form-row:focus-within {
    background-color: lightblue;
}
```

HTML:

```html
<div class="form-row">
    <input type="text" placeholder="First name">
    <input type="text" placeholder="Last name">
</div>
```

When either input receives focus, the `.form-row` matches `:focus-within`.

```text
.form-row
 ├── input → focus
 └── input
      ↓
:focus-within matches .form-row
```

### `:focus-within` and Accessibility

`:focus-within` can help create clear visual grouping for keyboard users.

For example:

```css
.form-group:focus-within {
    outline: 2px solid steelblue;
    outline-offset: 2px;
}
```

When a user navigates through the controls using the keyboard, the surrounding group can visually indicate where the focus is located.

### Combining `:focus-within` with Other Selectors

`:focus-within` can be combined with classes and descendant selectors.

```css
.card:focus-within .title {
    color: steelblue;
}
```

When any focusable descendant inside `.card` receives focus, the `.title` inside that card is styled.

### `:focus-within` vs `:focus-visible`

These pseudo-classes solve different problems.

```text
:focus-visible
      ↓
Focus state where a visible focus indicator
should be shown

:focus-within
      ↓
Element contains the focused element
or is itself focused
```

They can also be used together:

```css
.form-group:focus-within {
    border-color: steelblue;
}

.form-group input:focus-visible {
    outline: 2px solid steelblue;
}
```

Here, the parent responds to focus within the group, while the input receives its own visible focus indicator.

### Important Point

The key idea is:

```text
Element
   ↓
Itself or a descendant receives focus
   ↓
:focus-within matches
   ↓
Parent/container styles can change
```

> 💡 **Tip:** Use `:focus-within` when the visual state of a container should depend on focus inside that container.

> 💡 **Remember:** `:focus` targets the element that has focus, while `:focus-within` can target an element when it or any descendant has focus.

---

## Form-Related Pseudo-Classes

CSS provides several pseudo-classes specifically useful for styling form controls according to their state or validation requirements.

These pseudo-classes allow forms to respond visually to conditions such as whether a field is required, valid, invalid, enabled, disabled, checked, or focused.

### Common Form-Related Pseudo-Classes

Some commonly used form-related pseudo-classes are:

```css
:checked
:disabled
:enabled
:required
:optional
:valid
:invalid
:focus
:focus-visible
```

They can be grouped by purpose.

### Selection State

The `:checked` pseudo-class applies to selected checkboxes and radio buttons.

```css
input:checked {
    accent-color: steelblue;
}
```

Example:

```html
<input type="checkbox" checked>
```

The checkbox matches `:checked`.

### Enabled and Disabled State

`:enabled` selects controls that are enabled.

```css
input:enabled {
    background-color: white;
}
```

`:disabled` selects controls that are disabled.

```css
input:disabled {
    background-color: lightgray;
}
```

Example:

```html
<input type="text">
<input type="text" disabled>
```

The first control is enabled and the second is disabled.

### Required and Optional Fields

`:required` selects controls that have a required constraint.

```css
input:required {
    border-color: steelblue;
}
```

`:optional` selects controls that are not required.

```css
input:optional {
    border-color: gray;
}
```

Example:

```html
<input type="text" required>
<input type="text">
```

The first field is required, while the second is optional.

### Valid and Invalid Fields

`:valid` selects controls whose current value satisfies their applicable validation constraints.

```css
input:valid {
    border-color: green;
}
```

`:invalid` selects controls whose current value does not satisfy their applicable validation constraints.

```css
input:invalid {
    border-color: red;
}
```

Example:

```html
<input type="email" required>
```

The browser can determine whether the current value satisfies the email and required constraints.

### Focused Form Controls

`:focus` can style a form control while it has focus.

```css
input:focus {
    border-color: steelblue;
}
```

For a visible focus indicator:

```css
input:focus-visible {
    outline: 2px solid steelblue;
}
```

### Combining Form Pseudo-Classes

Multiple pseudo-classes can be combined to describe more specific states.

For example:

```css
input:required:invalid {
    border-color: red;
}
```

This targets a required input that is currently invalid.

Another example:

```css
input:required:valid {
    border-color: green;
}
```

This targets a required input whose current value satisfies its validation constraints.

An enabled and focused input can be selected with:

```css
input:enabled:focus {
    border-color: steelblue;
}
```

### Practical Form Example

HTML:

```html
<form>
    <label>
        Name:
        <input type="text" required>
    </label>

    <label>
        Email:
        <input type="email" required>
    </label>

    <label>
        Phone:
        <input type="tel">
    </label>

    <label>
        Country:
        <select>
            <option>India</option>
            <option>USA</option>
        </select>
    </label>

    <label>
        <input type="checkbox">
        Subscribe
    </label>

    <button type="submit">Submit</button>
</form>
```

CSS:

```css
input:required,
select:required {
    border-color: steelblue;
}

input:focus,
select:focus {
    outline: 2px solid steelblue;
}

input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}

input:disabled {
    opacity: 0.5;
}

input:checked {
    accent-color: steelblue;
}
```

Each pseudo-class responds to a different state of the form controls.

### Form State Overview

```text
:checked
    ↓
Selected checkbox/radio

:enabled
    ↓
Control is enabled

:disabled
    ↓
Control is disabled

:required
    ↓
Control is required

:optional
    ↓
Control is not required

:valid
    ↓
Value satisfies validation constraints

:invalid
    ↓
Value does not satisfy validation constraints

:focus
    ↓
Control currently has focus

:focus-visible
    ↓
Visible focus indication is appropriate
```

### Important Point

Form-related pseudo-classes allow CSS to reflect the current state of form controls without requiring separate classes for every state.

```text
Form control
     ↓
Browser determines its state
     ↓
Pseudo-class matches
     ↓
CSS applies the corresponding style
```

> 💡 **Tip:** Combine form pseudo-classes when you need to represent a specific state, such as `:required:invalid` or `:enabled:focus`.

> 💡 **Remember:** Each pseudo-class represents a different condition. `:required` describes a requirement, while `:valid` and `:invalid` describe the current validation state.

---

## Combining Pseudo-Classes

CSS pseudo-classes can be combined to create more specific selectors.

Combining pseudo-classes is useful when an element needs to match more than one condition before a style is applied.

### Basic Syntax

Multiple pseudo-classes can be placed one after another:

```css
selector:pseudo-class:pseudo-class {
    property: value;
}
```

For example:

```css
button:hover:focus {
    background-color: steelblue;
}
```

This targets a button when it is both hovered and focused.

### Combining `:hover` and `:focus`

```css
button:hover:focus {
    outline: 2px solid blue;
}
```

Both conditions must apply:

```text
button
  ↓
:hover
  +
:focus
  ↓
Selector matches
```

### Combining `:required` and `:invalid`

This is useful for form validation.

```css
input:required:invalid {
    border-color: red;
}
```

The selector targets an input that is:

```text
Required
   +
Invalid
   ↓
Apply red border
```

### Combining `:required` and `:valid`

```css
input:required:valid {
    border-color: green;
}
```

This targets required inputs whose current values satisfy their validation constraints.

### Combining `:enabled` and `:focus`

```css
input:enabled:focus {
    border-color: steelblue;
}
```

The input must be both enabled and focused.

### Combining `:checked` and `:disabled`

```css
input:checked:disabled {
    opacity: 0.5;
}
```

This targets a control that is both checked and disabled.

### Combining `:not()` with Other Pseudo-Classes

`:not()` can also be combined with other pseudo-classes.

For example:

```css
li:not(:first-child) {
    border-top: 1px solid gray;
}
```

This selects list items except the first child.

Another example:

```css
button:not(:disabled):hover {
    background-color: steelblue;
}
```

This targets buttons that are not disabled and are currently hovered.

### Combining Structural Pseudo-Classes

Structural pseudo-classes can also be combined.

```css
li:first-child:hover {
    color: red;
}
```

This targets the first list item while it is being hovered.

Another example:

```css
li:last-child:hover {
    color: blue;
}
```

This targets the last list item while it is being hovered.

### Combining Pseudo-Classes with Classes

Pseudo-classes can be combined with normal class selectors.

```css
.button.primary:hover {
    background-color: steelblue;
}
```

This selects an element that has both:

```text
.button
   +
.primary
   +
:hover
```

### Combining Pseudo-Classes with Descendant Selectors

Pseudo-classes can also be used inside larger selectors.

```css
.card:hover .title {
    color: steelblue;
}
```

Here, the `.title` is styled when its parent `.card` is hovered.

Another example:

```css
.form-group:focus-within input:focus {
    border-color: steelblue;
}
```

This combines focus-related conditions within a larger selector.

### Conditions Must Be Satisfied

When pseudo-classes are placed together on the same element:

```css
button:hover:focus {
    color: white;
}
```

the element must satisfy both conditions.

```text
Hovered?
   ↓
Yes
   ↓
Focused?
   ↓
Yes
   ↓
Apply style
```

If either condition is not satisfied, the selector does not match.

### Practical Example

HTML:

```html
<button class="button">Save</button>
<button class="button" disabled>Delete</button>
```

CSS:

```css
.button:not(:disabled):hover {
    background-color: steelblue;
    color: white;
}
```

The hover style applies to enabled buttons but excludes disabled buttons.

```text
Enabled + Hovered
       ↓
Styled

Disabled + Hovered
       ↓
Not selected
```

### Important Point

Combining pseudo-classes allows CSS to describe more specific states.

```text
Element
   +
Condition 1
   +
Condition 2
   +
Condition 3
   ↓
More specific selector
```

Examples:

```css
button:hover:focus
input:required:invalid
input:required:valid
input:enabled:focus
button:not(:disabled):hover
li:not(:first-child)
```

> 💡 **Tip:** Combine pseudo-classes when a style should apply only when multiple conditions are true.

> 💡 **Remember:** Multiple pseudo-classes written on the same element create combined conditions. The element must satisfy all of those conditions for the selector to match.

---

## Practical Examples

CSS pseudo-classes become especially useful when they are combined with normal selectors to create interactive, structural, and form-related styles.

### Example 1: Button Hover Effect

HTML:

```html
<button class="button">Click Me</button>
```

CSS:

```css
.button {
    background-color: gray;
    color: white;
    padding: 10px 20px;
    border: none;
}

.button:hover {
    background-color: steelblue;
}
```

The button changes its background color when the pointer moves over it.

---

### Example 2: Button Pressed Effect

```css
.button:active {
    transform: scale(0.98);
}
```

The button becomes slightly smaller while it is being activated.

---

### Example 3: Keyboard Focus

```css
.button:focus-visible {
    outline: 3px solid steelblue;
    outline-offset: 2px;
}
```

This provides a visible focus indicator when appropriate, especially during keyboard navigation.

---

### Example 4: Styling the First and Last List Items

HTML:

```html
<ul class="menu">
    <li>Home</li>
    <li>About</li>
    <li>Services</li>
    <li>Contact</li>
</ul>
```

CSS:

```css
.menu li:first-child {
    font-weight: bold;
}

.menu li:last-child {
    color: steelblue;
}
```

The first and last list items receive different styles.

---

### Example 5: Alternating List Items

```css
.menu li:nth-child(even) {
    background-color: lightgray;
}
```

This styles every even-numbered list item.

```text
1 → Normal
2 → Styled
3 → Normal
4 → Styled
```

---

### Example 6: Excluding an Element

```css
.menu li:not(:last-child) {
    border-bottom: 1px solid gray;
}
```

Every list item except the last one receives a bottom border.

This is useful for creating separators without adding a separator after the final item.

---

### Example 7: Styling a Checked Checkbox

HTML:

```html
<label>
    <input type="checkbox" class="task">
    Complete task
</label>
```

CSS:

```css
.task:checked {
    accent-color: green;
}
```

The checkbox receives the style when it is checked.

---

### Example 8: Styling Required Fields

HTML:

```html
<input type="text" required>
<input type="text">
```

CSS:

```css
input:required {
    border: 2px solid steelblue;
}

input:optional {
    border: 1px solid gray;
}
```

The first field is required, while the second is optional.

---

### Example 9: Valid and Invalid Form Fields

HTML:

```html
<input type="email" required>
```

CSS:

```css
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

The border changes according to the current validation state.

---

### Example 10: Disabled Form Control

HTML:

```html
<button>Enabled</button>
<button disabled>Disabled</button>
```

CSS:

```css
button:enabled {
    opacity: 1;
}

button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
}
```

The enabled and disabled buttons receive different styles.

---

### Example 11: Focus Within a Form Group

HTML:

```html
<div class="form-group">
    <label for="username">Username</label>
    <input id="username" type="text">
</div>
```

CSS:

```css
.form-group {
    padding: 10px;
    border: 1px solid gray;
}

.form-group:focus-within {
    border-color: steelblue;
}
```

When the input receives focus, the parent `.form-group` also receives the `:focus-within` styling.

---

### Example 12: Combining Pseudo-Classes

A button can be styled only when it is enabled and hovered.

```css
button:not(:disabled):hover {
    background-color: steelblue;
    color: white;
}
```

The selector means:

```text
button
   ↓
:not(:disabled)
   ↓
Button is enabled
   ↓
:hover
   ↓
Pointer is over the button
   ↓
Apply styles
```

---

### Example 13: Required and Invalid

```css
input:required:invalid {
    border-color: red;
}
```

This targets inputs that are both required and currently invalid.

A valid required input can be styled separately:

```css
input:required:valid {
    border-color: green;
}
```

---

### Example 14: Navigation Links

HTML:

```html
<nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
</nav>
```

CSS:

```css
nav a:hover {
    color: steelblue;
}

nav a:focus-visible {
    outline: 2px solid steelblue;
}
```

The navigation links respond to pointer and keyboard interaction.

---

### Example 15: Complete Interactive Card

HTML:

```html
<div class="card">
    <h2>CSS</h2>
    <p>Learn CSS pseudo-classes.</p>
    <a href="#">Read More</a>
</div>
```

CSS:

```css
.card {
    padding: 20px;
    border: 1px solid gray;
}

.card:hover {
    transform: translateY(-5px);
}

.card:focus-within {
    border-color: steelblue;
}

.card a:focus-visible {
    outline: 2px solid steelblue;
}
```

Here, several pseudo-classes work together:

```text
.card:hover
      ↓
Card responds to pointer interaction

.card:focus-within
      ↓
Card responds when its link receives focus

a:focus-visible
      ↓
Link receives a visible focus indicator
```

### Important Point

Pseudo-classes can be used for many common CSS tasks:

```text
User interaction
      ↓
:hover
:active
:focus
:focus-visible

Document structure
      ↓
:first-child
:last-child
:nth-child()
:nth-of-type()

Form states
      ↓
:checked
:disabled
:enabled
:required
:optional
:valid
:invalid

Conditional selection
      ↓
:not()
:focus-within
```

> 💡 **Tip:** Start with simple pseudo-classes such as `:hover`, `:focus`, `:first-child`, and `:checked`, then combine them when more specific conditions are needed.

> 💡 **Remember:** Pseudo-classes let CSS respond to element state, position, interaction, and validation without requiring a separate class for every condition.
## Key Takeaways

- CSS pseudo-classes are keywords added to selectors to style elements based on their state, condition, or position.

- Pseudo-classes use a single colon (`:`).

```css
selector:pseudo-class {
    property: value;
}
```

- Common interaction pseudo-classes include:

```css
:hover
:active
:focus
:focus-visible
:focus-within
```

- Link-related pseudo-classes include:

```css
:link
:visited
```

- Structural pseudo-classes include:

```css
:first-child
:last-child
:nth-child()
:nth-of-type()
:first-of-type
:last-of-type
:only-child
```

- The `:not()` pseudo-class is used to exclude elements matching a specified selector.

```css
li:not(:first-child) {
    border-top: 1px solid gray;
}
```

- Form-related pseudo-classes allow CSS to respond to form-control states:

```css
:checked
:disabled
:enabled
:required
:optional
:valid
:invalid
```

- `:first-child` selects an element only when it is the first child of its parent.

- `:last-child` selects an element only when it is the last child of its parent.

- `:nth-child()` selects elements based on their position among all children.

- `:nth-of-type()` selects elements based on their position among siblings of the same type.

- `:first-of-type` selects the first element of a particular type.

- `:last-of-type` selects the last element of a particular type.

- `:only-child` selects an element when it is the only child of its parent.

- `:hover` represents a pointer-hover state.

- `:active` represents an element while it is being activated.

- `:focus` represents an element that currently has focus.

- `:focus-visible` is useful for providing visible focus indicators when appropriate, especially for keyboard navigation.

- `:focus-within` allows a parent or container to be styled when it or one of its descendants has focus.

- `:checked` is commonly used with selected checkboxes and radio buttons.

- `:disabled` selects disabled form controls.

- `:enabled` selects enabled form controls.

- `:required` selects form controls with a required constraint.

- `:optional` selects form controls that are not required.

- `:valid` selects controls whose current value satisfies their applicable validation constraints.

- `:invalid` selects controls whose current value does not satisfy their applicable validation constraints.

- Multiple pseudo-classes can be combined to create more specific selectors.

```css
input:required:invalid {
    border-color: red;
}
```

- Pseudo-classes can reduce the need for additional HTML classes when styling based on states or positions.

- Pseudo-classes do not create new HTML elements. They add conditions to selectors.

### Quick Comparison

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

:visited
    ↓
Link has been visited

:first-child
    ↓
First child overall

:last-child
    ↓
Last child overall

:nth-child()
    ↓
Specific position among all children

:nth-of-type()
    ↓
Specific position among the same element type

:checked
    ↓
Checkbox/radio is selected

:disabled
    ↓
Form control is disabled

:valid
    ↓
Value satisfies validation constraints

:invalid
    ↓
Value does not satisfy validation constraints
```

> 💡 **Remember:** CSS pseudo-classes allow selectors to respond to user interaction, element position, form state, and other conditions without requiring a separate class for every state.

---

## References

The following references can be used to learn more about CSS pseudo-classes, selectors, and related CSS concepts.

### MDN Web Docs

- [CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
- [CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors)
- [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)
- [`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active)
- [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)
- [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited)
- [`:first-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child)
- [`:last-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child)
- [`:nth-child()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
- [`:nth-of-type()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type)
- [`:not()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)
- [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked)
- [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled)
- [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled)
- [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)
- [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)
- [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)
- [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
- [`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible)
- [`:focus-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within)

### W3C CSS Specifications

- [Selectors Level 4](https://www.w3.org/TR/selectors-4/)
- [CSS Basic User Interface Module](https://www.w3.org/TR/css-ui-4/)

### Reference Purpose

These resources can be used to:

- Verify CSS pseudo-class syntax.
- Understand pseudo-class behavior.
- Explore browser compatibility.
- Learn about selector combinations.
- Study form validation states.
- Understand focus and accessibility-related pseudo-classes.

> 💡 **Tip:** MDN is a useful practical reference for examples and browser behavior, while W3C specifications provide the formal standards behind CSS selectors.

---

## Quick Revision

### What Are CSS Pseudo-Classes?

Pseudo-classes are keywords added to CSS selectors to style elements based on their state, condition, or position.

```css
selector:pseudo-class {
    property: value;
}
```

### Interaction Pseudo-Classes

```css
:hover
:active
:focus
:focus-visible
:focus-within
```

- `:hover` — applies when the pointer is over an element.
- `:active` — applies while an element is being activated.
- `:focus` — applies when an element has focus.
- `:focus-visible` — provides a visible focus state when appropriate.
- `:focus-within` — applies when an element or one of its descendants has focus.

### Link Pseudo-Classes

```css
:link
:visited
```

- `:link` — selects unvisited links.
- `:visited` — selects visited links.

### Structural Pseudo-Classes

```css
:first-child
:last-child
:nth-child()
:nth-of-type()
:first-of-type
:last-of-type
:only-child
```

- `:first-child` — selects the first child of a parent.
- `:last-child` — selects the last child of a parent.
- `:nth-child()` — selects children according to their position.
- `:nth-of-type()` — selects elements according to their position among elements of the same type.
- `:first-of-type` — selects the first element of its type.
- `:last-of-type` — selects the last element of its type.
- `:only-child` — selects an element when it is the only child of its parent.

### Conditional Selection

```css
:not()
```

`:not()` selects elements that do not match the selector inside its parentheses.

Example:

```css
li:not(:first-child) {
    border-top: 1px solid gray;
}
```

### Form Pseudo-Classes

```css
:checked
:disabled
:enabled
:required
:optional
:valid
:invalid
```

- `:checked` — selects checked or selected controls.
- `:disabled` — selects disabled controls.
- `:enabled` — selects enabled controls.
- `:required` — selects controls with a required constraint.
- `:optional` — selects controls without a required constraint.
- `:valid` — selects controls whose current value satisfies applicable validation constraints.
- `:invalid` — selects controls whose current value does not satisfy applicable validation constraints.

### Common Combinations

Pseudo-classes can be combined:

```css
input:required:invalid {
    border-color: red;
}
```

```css
input:required:valid {
    border-color: green;
}
```

```css
button:not(:disabled):hover {
    background-color: steelblue;
}
```

### Key Differences

```text
:first-child
    ↓
First child overall

:first-of-type
    ↓
First element of its type
```

```text
:last-child
    ↓
Last child overall

:last-of-type
    ↓
Last element of its type
```

```text
:nth-child()
    ↓
Counts all children

:nth-of-type()
    ↓
Counts elements of the same type
```

```text
:focus
    ↓
Element has focus

:focus-within
    ↓
Element or a descendant has focus
```

```text
:required
    ↓
Control is required

:valid
    ↓
Current value satisfies validation constraints
```

### Basic Pattern

```css
selector:pseudo-class {
    property: value;
}
```

Multiple pseudo-classes:

```css
selector:pseudo-class:pseudo-class {
    property: value;
}
```

Functional pseudo-class:

```css
selector:nth-child(value) {
    property: value;
}
```

### Final Revision

Remember the main purpose of pseudo-classes:

```text
User interaction
        +
Element state
        +
Element position
        +
Form validation
        +
Conditional selection
        ↓
CSS Pseudo-Classes
```

> 💡 **Remember:** Pseudo-classes add conditions to CSS selectors. They do not create new HTML elements.

---

## Best Practices

Following good practices when using CSS pseudo-classes makes styles easier to understand, maintain, and use.

### 1. Use Pseudo-Classes for States and Conditions

Use pseudo-classes when styling depends on an element's state or condition.

```css
button:hover {
    background-color: steelblue;
}
```

Avoid adding unnecessary classes for simple interactive states.

### 2. Keep Selectors Simple

Prefer simple selectors when possible.

Good:

```css
button:hover {
    color: white;
}
```

Avoid unnecessarily complicated selectors:

```css
div.container ul li button.primary:hover {
    color: white;
}
```

Simple selectors are easier to maintain.

### 3. Use `:focus-visible` for Visible Focus Indicators

Provide clear focus indicators for keyboard users.

```css
button:focus-visible {
    outline: 3px solid steelblue;
    outline-offset: 2px;
}
```

Do not remove focus indicators without providing an accessible replacement.

### 4. Use `:focus-within` for Focused Containers

When a container should respond to focus inside it, use `:focus-within`.

```css
.form-group:focus-within {
    border-color: steelblue;
}
```

This avoids adding extra classes just to track focus inside a group.

### 5. Use Structural Pseudo-Classes Instead of Extra Classes

For simple positional styling, structural pseudo-classes can avoid unnecessary HTML classes.

Instead of:

```html
<li class="first">Home</li>
<li>About</li>
<li>Contact</li>
```

you can use:

```css
li:first-child {
    font-weight: bold;
}
```

### 6. Understand the Difference Between `:nth-child()` and `:nth-of-type()`

Use `:nth-child()` when the position among all children matters.

```css
li:nth-child(2) {
    color: red;
}
```

Use `:nth-of-type()` when the position among elements of the same type matters.

```css
p:nth-of-type(2) {
    color: blue;
}
```

Understanding this difference prevents unexpected selections.

### 7. Use `:not()` Carefully

`:not()` is useful for excluding elements.

```css
li:not(:last-child) {
    border-bottom: 1px solid gray;
}
```

Avoid creating overly complicated `:not()` conditions that make selectors difficult to understand.

### 8. Combine Pseudo-Classes When Necessary

Multiple pseudo-classes can describe a specific state.

```css
input:required:invalid {
    border-color: red;
}
```

Use combinations when each condition is meaningful.

### 9. Use Form Pseudo-Classes for Visual Feedback

Pseudo-classes such as:

```css
:valid
:invalid
:required
:optional
:disabled
:enabled
```

can provide useful visual feedback.

Example:

```css
input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}
```

Make sure the visual feedback is clear and does not rely only on color.

### 10. Do Not Rely Only on Color

Avoid communicating important states using color alone.

Instead of:

```css
input:invalid {
    border-color: red;
}
```

consider combining the styling with other visual cues when appropriate.

```css
input:invalid {
    border: 2px solid red;
    outline: 1px solid red;
}
```

For production forms, also provide meaningful text or other accessible feedback.

### 11. Preserve Keyboard Accessibility

Interactive elements should remain usable with the keyboard.

For example:

```css
a:focus-visible,
button:focus-visible {
    outline: 2px solid steelblue;
    outline-offset: 2px;
}
```

Do not remove focus styles simply because they are visually inconvenient.

### 12. Use Appropriate Specificity

Avoid unnecessarily high-specificity selectors.

Prefer:

```css
button:hover {
    color: white;
}
```

over unnecessarily long selectors.

Lower specificity makes styles easier to override and maintain.

### 13. Use Semantic HTML

Pseudo-classes work best when used with meaningful HTML elements.

For example:

```html
<button>Submit</button>
```

is preferable to using a generic element for button behavior.

Then CSS can naturally style its states:

```css
button:hover {
    background-color: steelblue;
}
```

### 14. Test Different States

When using pseudo-classes, test the relevant states.

For interactive elements, check:

```text
Normal
  ↓
:hover
  ↓
:active
  ↓
:focus
  ↓
:focus-visible
```

For forms, check:

```text
Enabled
Disabled
Required
Optional
Valid
Invalid
Checked
```

### 15. Consider Different Input Methods

Interactive styles should work for:

- Mouse users
- Keyboard users
- Touch users
- Assistive technology users

Do not design an interaction that depends only on `:hover`.

### 16. Avoid Unnecessary Pseudo-Class Combinations

This selector may be valid:

```css
button:hover:focus:active {
    color: white;
}
```

but combining many states unnecessarily can make the stylesheet harder to understand.

Use only the conditions that are actually required.

### 17. Keep Related Styles Together

Group related pseudo-class styles when it improves readability.

```css
.button {
    background-color: gray;
}

.button:hover {
    background-color: steelblue;
}

.button:active {
    transform: scale(0.98);
}

.button:focus-visible {
    outline: 2px solid steelblue;
}
```

This makes the component's states easy to understand.

### 18. Remember Browser Behavior

Some pseudo-classes depend on browser interaction and form-validation behavior.

Test important interactive styles in the browsers that your project supports.

### Important Point

Good pseudo-class usage should aim for:

```text
Simple selectors
      +
Clear states
      +
Good accessibility
      +
Appropriate specificity
      +
Maintainable CSS
```

> 💡 **Tip:** Use pseudo-classes to describe states and conditions rather than creating unnecessary classes for every possible state.

> 💡 **Remember:** Good CSS is not only about making elements look different. Interactive and form-related states should remain clear, accessible, and easy to maintain.

---

## Common Mistakes

Avoiding common mistakes helps make CSS pseudo-class selectors more predictable, accessible, and maintainable.

### 1. Confusing `:first-child` with `:first-of-type`

These pseudo-classes do not work the same way.

```css
p:first-child {
    color: red;
}
```

checks whether the `<p>` is the first child overall.

```css
p:first-of-type {
    color: blue;
}
```

checks whether the `<p>` is the first `<p>` among its siblings.

Example:

```html
<div>
    <h2>Title</h2>
    <p>First paragraph</p>
</div>
```

Here:

```css
p:first-child
```

does not match, but:

```css
p:first-of-type
```

does match.

---

### 2. Confusing `:last-child` with `:last-of-type`

The same distinction applies to the last element.

```css
p:last-child {
    color: red;
}
```

requires the `<p>` to be the last child overall.

```css
p:last-of-type {
    color: blue;
}
```

selects the last `<p>` among its siblings.

---

### 3. Misunderstanding `:nth-child()`

`:nth-child()` counts all child elements.

Consider:

```html
<div>
    <h2>Title</h2>
    <p>First</p>
    <p>Second</p>
</div>
```

This:

```css
p:nth-child(2) {
    color: red;
}
```

selects the first `<p>` because it is the second child overall.

It does not mean "the second `<p>`".

For the second `<p>`, use:

```css
p:nth-of-type(2) {
    color: blue;
}
```

---

### 4. Forgetting That `:only-child` Counts All Children

`:only-child` means the element is the only child of its parent.

It does not mean the element is the only child of its own type.

```html
<div>
    <h2>Title</h2>
    <p>Paragraph</p>
</div>
```

This does not match:

```css
p:only-child {
    color: red;
}
```

because the `<p>` has an `<h2>` sibling.

---

### 5. Using `:not()` Incorrectly

`:not()` excludes elements matching the selector inside it.

```css
li:not(:first-child) {
    margin-top: 10px;
}
```

This selects every `<li>` except the first one.

A common mistake is expecting `:not()` to select only the element inside its parentheses. It does the opposite.

```text
:not(X)
    ↓
Select elements that do NOT match X
```

---

### 6. Removing Focus Indicators

A common accessibility mistake is:

```css
button:focus {
    outline: none;
}
```

without providing another visible focus indicator.

Keyboard users need to be able to identify the currently focused element.

If you remove the default indicator, provide a suitable replacement:

```css
button:focus-visible {
    outline: 3px solid steelblue;
    outline-offset: 2px;
}
```

---

### 7. Relying Only on `:hover`

Hover is primarily associated with pointer interaction.

Do not use `:hover` as the only way to communicate important information or interaction states.

For interactive controls, also consider keyboard focus:

```css
button:hover {
    background-color: steelblue;
}

button:focus-visible {
    outline: 3px solid steelblue;
}
```

---

### 8. Confusing `:focus` with `:focus-within`

`:focus` applies to the element that has focus.

```css
input:focus {
    border-color: steelblue;
}
```

`:focus-within` can apply to a parent when it or a descendant has focus.

```css
.form-group:focus-within {
    border-color: steelblue;
}
```

These pseudo-classes have different purposes.

---

### 9. Confusing `:required` with `:valid`

These represent different conditions.

```css
input:required {
    border-color: steelblue;
}
```

means the control has a required constraint.

```css
input:valid {
    border-color: green;
}
```

means its current state/value satisfies its applicable validation constraints.

A field can be:

```text
Required + Valid
Required + Invalid
Optional + Valid
Optional + Invalid
```

depending on its constraints and current value.

---

### 10. Styling `:invalid` Without Considering User Experience

This can immediately show an invalid style:

```css
input:invalid {
    border-color: red;
}
```

For forms, consider when and how validation feedback should appear so users are not presented with confusing error states before they meaningfully interact with the form.

---

### 11. Confusing `:disabled` with `:not(:disabled)`

These represent different states.

```css
button:disabled {
    opacity: 0.5;
}
```

selects disabled buttons.

```css
button:not(:disabled) {
    opacity: 1;
}
```

selects buttons that are not disabled.

Use the selector that clearly communicates the intended state.

---

### 12. Creating Overly Complex Selectors

This selector may be difficult to maintain:

```css
.container ul li:not(:first-child):not(:last-child):hover:focus {
    color: red;
}
```

Complex selectors can make styles harder to understand and debug.

Prefer simpler selectors when possible.

---

### 13. Using Too Many Pseudo-Classes

Combining pseudo-classes is useful, but unnecessary combinations can make CSS harder to maintain.

For example:

```css
button:hover:focus:active:enabled:not(:disabled) {
    color: white;
}
```

Some of these conditions may be redundant.

Use only the conditions that are actually needed.

---

### 14. Assuming `:nth-child()` Starts at Zero

CSS child positions start at `1`, not `0`.

```css
li:nth-child(1) {
    /* First child */
}
```

The sequence is:

```text
1 → First
2 → Second
3 → Third
4 → Fourth
```

There is no `0th` child.

---

### 15. Using the Wrong `:nth-child()` Formula

For example:

```css
li:nth-child(2n) {
    background-color: lightgray;
}
```

selects:

```text
2
4
6
8
...
```

while:

```css
li:nth-child(2n + 1) {
    background-color: lightblue;
}
```

selects:

```text
1
3
5
7
...
```

Understand the formula before using it.

---

### 16. Forgetting That `:checked` Represents State

`:checked` is a state-based pseudo-class.

```css
input:checked {
    accent-color: green;
}
```

It does not mean that the HTML originally contained:

```html
checked
```

as a permanent CSS class. The selector responds to the control's current checked state.

---

### 17. Relying Only on Color for Form States

Avoid communicating validation or status using color alone.

For example:

```css
input:invalid {
    border-color: red;
}
```

can provide useful visual feedback, but important error information should also be communicated through appropriate text or other accessible mechanisms.

---

### 18. Using Pseudo-Classes Instead of Semantic HTML

Pseudo-classes do not replace appropriate HTML elements.

Prefer:

```html
<button>Save</button>
```

for a button instead of using a generic element only because it can be styled with:

```css
.element:hover {
    /* styles */
}
```

Use semantic HTML first, then use pseudo-classes to style its states.

---

### 19. Ignoring Keyboard Navigation

Always consider how interactive elements behave when users navigate using the keyboard.

For example:

```css
a:focus-visible {
    outline: 2px solid steelblue;
}
```

This helps provide a visible focus indicator.

---

### 20. Not Testing Different States

A pseudo-class can represent a changing state, so test the relevant states.

For interactive elements:

```text
Normal
:hover
:active
:focus
:focus-visible
```

For form controls:

```text
:enabled
:disabled
:required
:optional
:valid
:invalid
:checked
```

Testing these states helps identify unexpected styling behavior.

### Important Point

Most pseudo-class mistakes come from misunderstanding what the pseudo-class actually represents.

```text
Structural
    ↓
:first-child
:last-child
:nth-child()
:nth-of-type()

Interaction
    ↓
:hover
:active
:focus
:focus-visible
:focus-within

Form state
    ↓
:checked
:enabled
:disabled
:required
:optional
:valid
:invalid

Conditional
    ↓
:not()
```

> 💡 **Tip:** Before using a pseudo-class, identify exactly what condition it represents. Then check whether that condition is based on position, element type, interaction, or form state.

> 💡 **Remember:** Understanding the difference between similar pseudo-classes—such as `:nth-child()` vs `:nth-of-type()` and `:focus` vs `:focus-within`—prevents many common CSS bugs.

---

## Interview Questions

The following questions cover the important concepts of CSS pseudo-classes, including interaction, structural selection, form states, validation, and accessibility.

### Basic Questions

#### 1. What is a CSS pseudo-class?

A CSS pseudo-class is a keyword added to a selector to style an element based on a particular state, condition, or position.

Example:

```css
button:hover {
    background-color: steelblue;
}
```

#### 2. What is the syntax of a pseudo-class?

Pseudo-classes use a single colon (`:`).

```css
selector:pseudo-class {
    property: value;
}
```

#### 3. What is the difference between a pseudo-class and a CSS class?

A CSS class is explicitly assigned in HTML:

```html
<p class="special">Text</p>
```

A pseudo-class represents a condition or state:

```css
p:hover {
    color: blue;
}
```

#### 4. What does `:hover` do?

`:hover` selects an element when the pointer is positioned over it.

```css
button:hover {
    background-color: steelblue;
}
```

#### 5. What does `:active` do?

`:active` selects an element while it is being activated.

```css
button:active {
    transform: scale(0.98);
}
```

#### 6. What does `:focus` do?

`:focus` selects an element that currently has focus.

```css
input:focus {
    border-color: steelblue;
}
```

---

### Structural Pseudo-Class Questions

#### 7. What does `:first-child` select?

It selects an element when it is the first child of its parent.

```css
li:first-child {
    font-weight: bold;
}
```

#### 8. What does `:last-child` select?

It selects an element when it is the last child of its parent.

```css
li:last-child {
    font-weight: bold;
}
```

#### 9. What is the difference between `:first-child` and `:first-of-type`?

`:first-child` checks the first child overall.

`:first-of-type` checks the first element of a particular type.

```html
<div>
    <h2>Title</h2>
    <p>Paragraph</p>
</div>
```

```css
p:first-child {
    color: red;
}
```

does not match the `<p>`.

```css
p:first-of-type {
    color: blue;
}
```

does match it.

#### 10. What is the difference between `:last-child` and `:last-of-type`?

`:last-child` selects the last child overall.

`:last-of-type` selects the last element of its type.

#### 11. What does `:nth-child()` do?

It selects elements based on their position among all children.

```css
li:nth-child(2) {
    color: red;
}
```

#### 12. What does `:nth-of-type()` do?

It selects an element based on its position among siblings of the same element type.

```css
p:nth-of-type(2) {
    color: blue;
}
```

#### 13. What is the main difference between `:nth-child()` and `:nth-of-type()`?

```text
:nth-child()
    ↓
Counts all child elements

:nth-of-type()
    ↓
Counts only elements of the same type
```

#### 14. What does `:only-child` select?

It selects an element when it is the only child of its parent.

```css
p:only-child {
    color: steelblue;
}
```

---

### Conditional Selection Questions

#### 15. What does `:not()` do?

`:not()` selects elements that do not match the selector inside its parentheses.

```css
li:not(:first-child) {
    margin-top: 10px;
}
```

#### 16. Can pseudo-classes be combined?

Yes.

```css
input:required:invalid {
    border-color: red;
}
```

The element must satisfy both conditions.

#### 17. Give an example of combining `:not()` with another pseudo-class.

```css
button:not(:disabled):hover {
    background-color: steelblue;
}
```

This targets buttons that are not disabled and are being hovered.

---

### Form-Related Questions

#### 18. What does `:checked` do?

`:checked` selects checked or selected form controls such as checkboxes and radio buttons.

```css
input:checked {
    accent-color: green;
}
```

#### 19. What is the difference between `:enabled` and `:disabled`?

```text
:enabled
    ↓
Control is enabled

:disabled
    ↓
Control is disabled
```

#### 20. What does `:required` do?

It selects form controls that have a required constraint.

```css
input:required {
    border-color: steelblue;
}
```

#### 21. What does `:optional` do?

It selects form controls that are not required.

```css
input:optional {
    border-color: gray;
}
```

#### 22. What does `:valid` do?

It selects form controls whose current value satisfies their applicable validation constraints.

```css
input:valid {
    border-color: green;
}
```

#### 23. What does `:invalid` do?

It selects form controls whose current value does not satisfy their applicable validation constraints.

```css
input:invalid {
    border-color: red;
}
```

#### 24. What is the difference between `:required` and `:valid`?

They describe different conditions.

```text
:required
    ↓
The control has a required constraint

:valid
    ↓
The current value satisfies applicable constraints
```

A control can be required and either valid or invalid depending on its current state.

---

### Focus and Accessibility Questions

#### 25. What is `:focus-visible`?

`:focus-visible` is used to provide a visible focus indicator when the browser determines that such an indicator should be shown.

```css
button:focus-visible {
    outline: 3px solid steelblue;
}
```

#### 26. What is `:focus-within`?

`:focus-within` selects an element when it or one of its descendants has focus.

```css
.form-group:focus-within {
    border-color: steelblue;
}
```

#### 27. What is the difference between `:focus` and `:focus-within`?

```text
:focus
    ↓
The element itself has focus

:focus-within
    ↓
The element or a descendant has focus
```

#### 28. Why are visible focus indicators important?

They help users, especially keyboard users, identify which interactive element currently has focus.

Example:

```css
button:focus-visible {
    outline: 3px solid steelblue;
    outline-offset: 2px;
}
```

---

### Practical Questions

#### 29. How would you style every list item except the last one?

```css
li:not(:last-child) {
    border-bottom: 1px solid gray;
}
```

#### 30. How would you style every even list item?

```css
li:nth-child(even) {
    background-color: lightgray;
}
```

#### 31. How would you style every odd list item?

```css
li:nth-child(odd) {
    background-color: lightblue;
}
```

#### 32. How would you style a required invalid input?

```css
input:required:invalid {
    border-color: red;
}
```

#### 33. How would you style a required valid input?

```css
input:required:valid {
    border-color: green;
}
```

#### 34. How would you style an enabled button when it is hovered?

```css
button:enabled:hover {
    background-color: steelblue;
}
```

#### 35. How would you style a parent when an input inside it receives focus?

```css
.form-group:focus-within {
    border-color: steelblue;
}
```

### Important Interview Points

Remember these common comparisons:

```text
:first-child
    vs
:first-of-type
```

```text
:last-child
    vs
:last-of-type
```

```text
:nth-child()
    vs
:nth-of-type()
```

```text
:focus
    vs
:focus-visible
    vs
:focus-within
```

```text
:required
    vs
:optional
```

```text
:valid
    vs
:invalid
```

```text
:enabled
    vs
:disabled
```

> 💡 **Interview Tip:** When explaining pseudo-classes, do not only give their definitions. Show a small HTML and CSS example and explain exactly which element matches the selector and why.