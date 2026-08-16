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