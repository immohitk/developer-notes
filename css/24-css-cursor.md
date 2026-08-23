## Table of Contents

1. [Introduction](#introduction)
2. [What Is CSS Cursor?](#what-is-css-cursor)
3. [The `cursor` Property](#the-cursor-property)
4. [Cursor Syntax](#cursor-syntax)
5. [Default Cursor](#default-cursor)
6. [Pointer Cursor](#pointer-cursor)
7. [Text Cursor](#text-cursor)
8. [Move Cursor](#move-cursor)
9. [Wait Cursor](#wait-cursor)
10. [Help Cursor](#help-cursor)
11. [Not Allowed Cursor](#not-allowed-cursor)
12. [Crosshair Cursor](#crosshair-cursor)
13. [Grab and Grabbing Cursors](#grab-and-grabbing-cursors)
14. [Resize Cursors](#resize-cursors)
15. [Zoom Cursors](#zoom-cursors)
16. [Other Common Cursor Values](#other-common-cursor-values)
17. [Custom Cursor](#custom-cursor)
18. [Cursor With Images](#cursor-with-images)
19. [Cursor Fallback Values](#cursor-fallback-values)
20. [Practical Examples](#practical-examples)
21. [Key Takeaways](#key-takeaways)
22. [References](#references)
23. [Quick Revision](#quick-revision)
24. [Best Practices](#best-practices)
25. [Common Mistakes](#common-mistakes)
26. [Interview Questions](#interview-questions)
27. [Practice Exercises](#practice-exercises)
28. [Related Topics](#related-topics)

---

## Introduction

The CSS `cursor` property controls the appearance of the mouse cursor when it is positioned over an element.

For example, when you move the mouse over a button, link, text field, or draggable element, the cursor can change to indicate how the element can be interacted with.

```text
Mouse moves over an element
            ↓
CSS cursor property
            ↓
Cursor appearance changes
            ↓
User receives visual feedback
```

The `cursor` property helps users understand what actions are available.

For example:

```text
Pointer cursor
→ Element can be clicked

Text cursor
→ Text can be selected or edited

Move cursor
→ Element can be moved

Not-allowed cursor
→ Action is unavailable

Wait cursor
→ Browser or application is busy
```

### Basic Example

```css
button {
    cursor: pointer;
}
```

When the user moves the mouse over the button, the cursor changes to a pointer.

### Why Is the `cursor` Property Important?

The cursor provides visual feedback about an element's behavior.

For example:

```css
button {
    cursor: pointer;
}

input {
    cursor: text;
}

.disabled {
    cursor: not-allowed;
}
```

Each cursor communicates something different to the user.

### Common Use Cases

The `cursor` property is commonly used for:

- Buttons
- Links
- Text inputs
- Draggable elements
- Resizable elements
- Disabled elements
- Help icons
- Loading states
- Custom interfaces

### Visual Feedback

Consider a clickable element:

```html
<div class="button">
    Click Me
</div>
```

Without a cursor change, the user may not immediately know that the element is interactive.

You can provide visual feedback:

```css
.button {
    cursor: pointer;
}
```

Now the cursor helps communicate that the element can be clicked.

### Cursor Values

CSS provides many predefined cursor values.

Examples include:

```css
cursor: default;
cursor: pointer;
cursor: text;
cursor: move;
cursor: wait;
cursor: help;
cursor: not-allowed;
```

Different cursor values should be selected based on the purpose and behavior of the element.

### User Experience

The `cursor` property is a small but important part of user experience.

A correctly chosen cursor can make an interface feel more intuitive.

```text
Element behavior
        ↓
Appropriate cursor
        ↓
Visual feedback
        ↓
Better user experience
```

> 💡 **Remember:** The CSS `cursor` property controls the appearance of the mouse cursor and provides visual feedback about how an element can be interacted with.

---

## What Is CSS Cursor?

CSS cursor refers to the visual pointer displayed when a user moves a mouse or pointing device over an element.

The cursor can communicate how the user can interact with that element.

For example:

```text
Normal element
→ Default cursor

Clickable element
→ Pointer cursor

Text content
→ Text cursor

Draggable element
→ Move cursor

Unavailable action
→ Not-allowed cursor
```

CSS uses the `cursor` property to control this behavior.

### Basic Example

```css
.button {
    cursor: pointer;
}
```

When the user places the mouse over the element, the cursor changes to indicate that the element can be clicked.

### CSS Cursor Provides Visual Feedback

The cursor gives users information before they interact with an element.

For example:

```css
.editable-text {
    cursor: text;
}
```

The text cursor indicates that text can be selected or edited.

Another example:

```css
.disabled {
    cursor: not-allowed;
}
```

The `not-allowed` cursor indicates that an action is unavailable.

### Cursor and Element Interaction

Different elements can have different interaction purposes.

```text
Element
   ↓
Interaction purpose
   ↓
Appropriate cursor
   ↓
Visual feedback
```

For example:

```css
button {
    cursor: pointer;
}

input {
    cursor: text;
}

.draggable {
    cursor: move;
}
```

### Common Cursor Meanings

| Cursor | Meaning |
|---|---|
| `default` | Normal default cursor |
| `pointer` | Element can be clicked |
| `text` | Text can be selected or edited |
| `move` | Element can be moved |
| `wait` | Browser or application is busy |
| `help` | Help information is available |
| `not-allowed` | Action is unavailable |

### Cursor Does Not Add Functionality

An important point is that the `cursor` property only changes the appearance of the cursor.

For example:

```css
.box {
    cursor: pointer;
}
```

This does not automatically make the element clickable.

The element still needs appropriate functionality, such as:

```html
<button>Click Me</button>
```

or JavaScript for interactive behavior.

```text
cursor: pointer
        ↓
Visual indication only

Click behavior
        ↓
Requires HTML functionality
or JavaScript
```

### Why CSS Cursor Is Useful

CSS cursor values help make an interface easier to understand.

A properly selected cursor can communicate:

- Whether an element is clickable
- Whether text can be selected
- Whether an element can be moved
- Whether an element can be resized
- Whether an action is unavailable
- Whether the browser is busy

> 💡 **Remember:** CSS cursor controls the appearance of the pointer over an element. It provides visual feedback about possible interactions but does not add functionality by itself.

---

## The `cursor` Property

The CSS `cursor` property controls the type of cursor displayed when the user moves a pointing device over an element.

The cursor can provide visual feedback about how the element can be interacted with.

### Basic Syntax

```css
selector {
    cursor: value;
}
```

For example:

```css
button {
    cursor: pointer;
}
```

When the user moves the mouse over the button, the cursor changes to a pointer.

### Example With Different Elements

```css
button {
    cursor: pointer;
}

input {
    cursor: text;
}

.draggable {
    cursor: move;
}

.disabled {
    cursor: not-allowed;
}
```

Each value communicates a different possible interaction.

```text
pointer
→ Clickable

text
→ Text can be selected or edited

move
→ Element can be moved

not-allowed
→ Action is unavailable
```

### The Cursor Property Changes Appearance Only

The `cursor` property only controls the visual appearance of the cursor.

For example:

```css
.box {
    cursor: pointer;
}
```

This does not automatically make `.box` clickable.

The element still needs actual functionality.

```text
cursor property
        ↓
Changes cursor appearance

HTML or JavaScript
        ↓
Provides actual interaction
```

### Applying `cursor` to an Element

The property can be applied to many elements.

```css
.card {
    cursor: pointer;
}
```

```css
.text-area {
    cursor: text;
}
```

```css
.drag-item {
    cursor: move;
}
```

The appropriate value should match the expected behavior of the element.

### Inherited Behavior

The `cursor` property is inherited.

For example:

```css
.container {
    cursor: pointer;
}
```

Child elements can inherit the cursor behavior unless another cursor value is specified.

```css
.container {
    cursor: pointer;
}

.container .text {
    cursor: text;
}
```

In this example, `.text` uses the `text` cursor instead of inheriting `pointer`.

### Common Cursor Values

Some commonly used values are:

```css
cursor: auto;
cursor: default;
cursor: pointer;
cursor: text;
cursor: move;
cursor: wait;
cursor: help;
cursor: not-allowed;
```

CSS also provides many additional cursor values for resizing, grabbing, zooming, and custom cursor images.

### `auto` Value

```css
cursor: auto;
```

The browser automatically determines the cursor to display based on the current context.

This is the default behavior.

### Example

```html
<button class="button">
    Click Me
</button>
```

```css
.button {
    cursor: pointer;
}
```

The cursor provides visual feedback that the button is interactive.

### Important Points

```text
cursor property
│
├── Controls cursor appearance
│
├── Provides visual feedback
│
├── Does not add functionality
│
├── Can be inherited
│
└── Supports many cursor values
    ├── pointer
    ├── text
    ├── move
    ├── wait
    ├── help
    ├── not-allowed
    └── many others
```

> 💡 **Remember:** The `cursor` property changes the appearance of the cursor to communicate how an element can be interacted with. It provides visual feedback but does not create functionality.