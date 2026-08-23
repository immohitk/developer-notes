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

---

## Cursor Syntax

The CSS `cursor` property is used by assigning a cursor value to an element.

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

The general syntax is:

```css
cursor: <cursor-value>;
```

### Using a Keyword Value

Most commonly, `cursor` uses a predefined keyword.

```css
.element {
    cursor: pointer;
}
```

Other examples include:

```css
.element {
    cursor: default;
}
```

```css
.element {
    cursor: text;
}
```

```css
.element {
    cursor: move;
}
```

### Common Syntax Pattern

```text
Selector
    ↓
cursor
    ↓
Cursor value
```

For example:

```css
.button {
    cursor: pointer;
}
```

```text
.button
    ↓
Selected element

cursor
    ↓
CSS property

pointer
    ↓
Cursor value
```

### Using Multiple Cursor Values

The `cursor` property can include multiple values when using a custom cursor image with fallback options.

For example:

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

Here:

```text
Custom cursor image
        ↓
If supported and available
        ↓
Use cursor.png

Otherwise
        ↓
Use pointer
```

The fallback cursor value is important because a custom cursor image may not always be available or supported.

### Custom Cursor With Coordinates

A custom cursor can also specify hotspot coordinates.

```css
.element {
    cursor: url("cursor.png") 10 10, pointer;
}
```

The coordinates define the active point of the cursor image.

```text
cursor image
      ↓
10 10
      ↓
Hotspot position
```

The first value represents the horizontal coordinate.

The second value represents the vertical coordinate.

### Syntax With a Fallback

A recommended pattern for custom cursors is:

```css
.element {
    cursor: url("custom-cursor.png"), auto;
}
```

If the custom cursor cannot be used, the browser uses:

```css
auto
```

### Multiple Custom Cursor Images

More than one custom cursor image can be provided.

```css
.element {
    cursor:
        url("cursor.svg"),
        url("cursor.png"),
        pointer;
}
```

The browser attempts to use the cursor images in order.

```text
cursor.svg
    ↓
If unavailable

cursor.png
    ↓
If unavailable

pointer
```

### Global Values

Like other CSS properties, `cursor` can also use global values.

```css
cursor: inherit;
cursor: initial;
cursor: revert;
cursor: revert-layer;
cursor: unset;
```

### Example With `inherit`

```css
.child {
    cursor: inherit;
}
```

The element uses the cursor value inherited from its parent.

### Important Syntax Rules

```text
cursor
│
├── Can use predefined keyword values
│
├── Can use custom cursor images
│
├── Can include hotspot coordinates
│
├── Can include multiple cursor images
│
└── Should include a fallback cursor keyword
```

### Simple Examples

```css
button {
    cursor: pointer;
}
```

```css
input {
    cursor: text;
}
```

```css
.drag-item {
    cursor: move;
}
```

```css
.disabled {
    cursor: not-allowed;
}
```

> 💡 **Remember:** The simplest `cursor` syntax uses a predefined keyword such as `pointer`, `text`, or `move`. Custom cursor images can also be used, but they should include a fallback cursor value.

---

## Default Cursor

The `default` cursor value displays the default cursor determined by the browser or operating system.

### Syntax

```css
.element {
    cursor: default;
}
```

The exact appearance of the default cursor can vary depending on the operating system and browser.

### Example

```html
<div class="box">
    Hover over me
</div>
```

```css
.box {
    cursor: default;
}
```

When the user moves the pointer over the element, the default cursor is displayed.

### `default` Cursor Meaning

The `default` cursor generally represents a normal element with no special interaction indicated.

```text
Normal element
      ↓
cursor: default
      ↓
Default system cursor
```

### Example With Different Elements

```css
.normal {
    cursor: default;
}

.clickable {
    cursor: pointer;
}

.text-content {
    cursor: text;
}
```

Each element can display a cursor that better represents its intended interaction.

### `default` vs `auto`

The `default` and `auto` values are different.

```css
cursor: default;
```

The browser displays the default cursor.

```css
cursor: auto;
```

The browser automatically determines the cursor based on the context.

For example:

```text
default
→ Use the normal default cursor

auto
→ Browser decides the appropriate cursor
```

### Example

```html
<a href="#">Link</a>
```

With:

```css
a {
    cursor: auto;
}
```

the browser can choose an appropriate cursor based on the element.

With:

```css
a {
    cursor: default;
}
```

the element displays the default cursor instead of using the browser's automatic behavior.

### When to Use `default`

Use:

```css
cursor: default;
```

when you want to explicitly show the normal default cursor.

For example:

```css
.static-element {
    cursor: default;
}
```

However, it is usually unnecessary to set `default` unless you need to override another cursor value.

### Example: Overriding an Inherited Cursor

Because the `cursor` property can be inherited, a parent may set a cursor value:

```css
.container {
    cursor: pointer;
}
```

You can reset a child element to the default cursor:

```css
.container .static-content {
    cursor: default;
}
```

### Important Points

```text
cursor: default
│
├── Displays the default system cursor
│
├── Indicates no special interaction
│
├── Can override an inherited cursor
│
└── May look different across operating systems
```

> 💡 **Remember:** `cursor: default` explicitly displays the normal default cursor, while `cursor: auto` allows the browser to automatically choose the appropriate cursor based on the context.

---

## Pointer Cursor

The `pointer` cursor value displays a pointer cursor when the user moves over an element.

It is commonly used to indicate that an element can be clicked or interacted with.

### Syntax

```css
.element {
    cursor: pointer;
}
```

### Basic Example

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

When the user moves the mouse over the button, the cursor changes to a pointer.

### Pointer Cursor Meaning

The pointer cursor communicates:

```text
Pointer cursor
      ↓
Element is interactive
      ↓
User can click or activate it
```

### Common Use Cases

The `pointer` cursor is commonly used for:

- Buttons
- Links
- Clickable cards
- Clickable icons
- Custom controls
- Interactive elements

### Example: Clickable Card

```html
<div class="card">
    Clickable Card
</div>
```

```css
.card {
    cursor: pointer;
}
```

The cursor provides visual feedback that the card can be interacted with.

### Example: Clickable Icon

```css
.icon {
    cursor: pointer;
}
```

This is useful when an icon performs an action.

For example:

```text
Delete icon
→ pointer

Edit icon
→ pointer

Menu icon
→ pointer
```

### Pointer Cursor Does Not Add Functionality

Using:

```css
.element {
    cursor: pointer;
}
```

does not automatically make the element clickable.

The property only changes the cursor appearance.

```text
cursor: pointer
        ↓
Visual feedback

Actual click behavior
        ↓
HTML functionality
or JavaScript
```

For example:

```html
<div class="card" onclick="openCard()">
    Clickable Card
</div>
```

```css
.card {
    cursor: pointer;
}
```

The JavaScript provides the functionality, while the cursor provides visual feedback.

### Pointer Cursor and Links

Links usually display an appropriate cursor automatically.

For example:

```html
<a href="https://example.com">
    Visit Website
</a>
```

In many cases, you do not need to manually add:

```css
cursor: pointer;
```

because the browser already provides visual feedback for links.

### Pointer Cursor and Buttons

Native buttons are also interactive elements.

```html
<button>Submit</button>
```

Depending on browser and operating system behavior, the cursor appearance may already provide interaction feedback.

You can explicitly set:

```css
button {
    cursor: pointer;
}
```

when you want consistent cursor behavior.

### Use Pointer Only for Interactive Elements

Avoid using:

```css
cursor: pointer;
```

for elements that do not perform an action.

For example:

```css
.static-text {
    cursor: pointer;
}
```

This can confuse users because the cursor suggests that the element is clickable.

A better approach is to match the cursor with the actual behavior of the element.

```text
Clickable element
→ pointer

Text selection
→ text

Draggable element
→ move or grab

Normal element
→ default or auto
```

### Important Points

```text
cursor: pointer
│
├── Indicates interaction
│
├── Commonly used for clickable elements
│
├── Provides visual feedback
│
├── Does not add click functionality
│
└── Should match actual element behavior
```

> 💡 **Remember:** Use `cursor: pointer` when an element is genuinely interactive. The pointer cursor communicates that the user can click or activate the element.

---

## Text Cursor

The `text` cursor value displays a cursor that indicates text can be selected or edited.

It is commonly shown when the user moves the pointer over selectable text or a text input area.

### Syntax

```css
.element {
    cursor: text;
}
```

### Basic Example

```html
<p class="text-content">
    Select this text.
</p>
```

```css
.text-content {
    cursor: text;
}
```

When the user moves the pointer over the text, the cursor changes to indicate that text can be selected.

### Text Cursor Meaning

The text cursor communicates:

```text
Text cursor
      ↓
Text interaction is possible
      ↓
User can select or edit text
```

### Common Use Cases

The `text` cursor is commonly associated with:

- Text content
- Text inputs
- Textareas
- Editable content
- Selectable text

### Example: Text Input

```html
<input type="text" placeholder="Enter your name">
```

Text input elements normally display an appropriate text cursor automatically.

You can also explicitly define it:

```css
input {
    cursor: text;
}
```

### Example: Textarea

```html
<textarea placeholder="Write something"></textarea>
```

```css
textarea {
    cursor: text;
}
```

This provides visual feedback that the user can enter or edit text.

### Example: Editable Content

```html
<div class="editable" contenteditable="true">
    Edit this text.
</div>
```

```css
.editable {
    cursor: text;
}
```

The cursor indicates that the content can be edited.

### `text` Cursor vs `pointer`

These cursor values communicate different interactions.

```text
cursor: text
→ Select or edit text

cursor: pointer
→ Click or activate an element
```

For example:

```css
.article {
    cursor: text;
}

.button {
    cursor: pointer;
}
```

The cursor should match the expected behavior of the element.

### `text` Cursor Does Not Make Text Editable

Using:

```css
.element {
    cursor: text;
}
```

does not automatically make the content editable.

It only changes the cursor appearance.

For example:

```html
<p class="example">
    This is normal text.
</p>
```

```css
.example {
    cursor: text;
}
```

The text may still not be editable.

To make content editable, appropriate HTML or JavaScript functionality is required.

For example:

```html
<div contenteditable="true">
    Edit this content.
</div>
```

### When to Use `text`

Use:

```css
cursor: text;
```

when the user should understand that text can be selected or edited.

Avoid using it for elements that perform actions unrelated to text interaction.

```text
Selectable text
→ text

Editable content
→ text

Text input
→ text

Clickable button
→ pointer
```

### Important Points

```text
cursor: text
│
├── Indicates text interaction
│
├── Commonly used for selectable text
│
├── Commonly used for editable content
│
├── Provides visual feedback
│
└── Does not make content editable
```

> 💡 **Remember:** `cursor: text` indicates that the user can interact with text, such as selecting or editing it. It only changes the cursor appearance and does not add editing functionality by itself.

---

## Move Cursor

The `move` cursor value indicates that an element can be moved.

It is commonly used for draggable elements and interfaces where users can reposition content.

### Syntax

```css
.element {
    cursor: move;
}
```

### Basic Example

```html
<div class="draggable">
    Drag Me
</div>
```

```css
.draggable {
    cursor: move;
}
```

When the user moves the pointer over the element, the cursor indicates that the element can be moved.

### Move Cursor Meaning

The `move` cursor communicates:

```text
Move cursor
      ↓
Element may be repositioned
      ↓
User can drag or move it
```

### Common Use Cases

The `move` cursor can be used for:

- Draggable elements
- Movable panels
- Drag-and-drop interfaces
- Interactive editors
- Layout builders
- Canvas elements

### Example: Draggable Box

```html
<div class="box">
    Move Me
</div>
```

```css
.box {
    cursor: move;
}
```

The cursor provides visual feedback that the element is intended to be moved.

### `cursor: move` Does Not Add Drag Functionality

An important point is that:

```css
.element {
    cursor: move;
}
```

only changes the appearance of the cursor.

It does not automatically make the element draggable.

```text
cursor: move
        ↓
Visual indication only

Actual dragging
        ↓
Requires HTML functionality
or JavaScript
```

For example, JavaScript may be required to implement actual dragging behavior.

### Move Cursor vs Pointer Cursor

These values communicate different interactions.

```text
cursor: pointer
→ Click or activate

cursor: move
→ Move or reposition
```

Use the cursor that best represents the actual interaction.

### Example

```css
.button {
    cursor: pointer;
}

.draggable-item {
    cursor: move;
}
```

The button indicates clicking, while the draggable item indicates movement.

### Move Cursor vs Grab Cursor

The `move` cursor generally indicates that an element can be moved.

The `grab` and `grabbing` cursors are often used for drag interactions.

```text
move
→ Indicates movement or repositioning

grab
→ Element can be grabbed

grabbing
→ Element is currently being dragged
```

For example:

```css
.item {
    cursor: grab;
}

.item:active {
    cursor: grabbing;
}
```

The choice depends on the type of interaction and visual feedback required.

### Example: Movable Interface Element

```css
.panel {
    cursor: move;
}
```

This can indicate that the panel can be repositioned.

However, the actual movement functionality must be implemented separately.

### Important Points

```text
cursor: move
│
├── Indicates that an element can be moved
│
├── Useful for draggable interfaces
│
├── Provides visual feedback
│
├── Does not create drag functionality
│
└── Should match the actual behavior
```

> 💡 **Remember:** `cursor: move` visually indicates that an element can be moved or repositioned. It provides feedback only; actual dragging or movement requires additional functionality.

---

## Wait Cursor

The `wait` cursor value indicates that the browser, application, or system is busy and the user may need to wait.

It is commonly used when an operation is in progress.

### Syntax

```css
.element {
    cursor: wait;
}
```

### Basic Example

```html
<div class="loading">
    Loading...
</div>
```

```css
.loading {
    cursor: wait;
}
```

When the user moves the pointer over the element, the cursor indicates that the system is busy.

### Wait Cursor Meaning

The `wait` cursor communicates:

```text
Wait cursor
      ↓
Operation in progress
      ↓
System is busy
      ↓
User may need to wait
```

### Common Use Cases

The `wait` cursor can be useful during:

- Data loading
- File processing
- Page updates
- Background operations
- Long-running tasks
- Application processing

### Example: Loading State

```html
<div class="content loading">
    Loading data...
</div>
```

```css
.loading {
    cursor: wait;
}
```

The cursor provides visual feedback that the operation is still in progress.

### Wait Cursor Does Not Block Interaction

Using:

```css
.element {
    cursor: wait;
}
```

only changes the cursor appearance.

It does not automatically:

- Disable buttons
- Prevent clicks
- Stop keyboard input
- Block interaction

For example:

```css
.loading {
    cursor: wait;
}
```

The element may still be interactive unless additional functionality is implemented.

### Wait Cursor and Disabled Elements

If an element should not be used while loading, additional styling or functionality may be required.

For example:

```css
.loading {
    cursor: wait;
    pointer-events: none;
}
```

In this example:

```text
cursor: wait
→ Shows that processing is happening

pointer-events: none
→ Prevents pointer interaction
```

### Wait Cursor vs Progress Cursor

CSS provides both:

```css
cursor: wait;
```

and:

```css
cursor: progress;
```

They communicate slightly different states.

```text
wait
→ System is busy
→ User may need to wait

progress
→ An operation is in progress
→ The user may still be able to interact
```

The exact appearance can vary depending on the browser and operating system.

### Example: Application Processing

```css
.processing {
    cursor: wait;
}
```

This can be applied while an application performs an operation.

Once the operation is complete, the cursor can return to normal:

```css
.processing {
    cursor: auto;
}
```

### Important Points

```text
cursor: wait
│
├── Indicates that processing is happening
│
├── Suggests that the user should wait
│
├── Provides visual feedback
│
├── Does not automatically disable interaction
│
└── Can be used with loading states
```

> 💡 **Remember:** `cursor: wait` indicates that the system is busy or processing something. It provides visual feedback but does not automatically prevent the user from interacting with the element.