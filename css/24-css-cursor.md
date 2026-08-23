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

---

## Help Cursor

The `help` cursor value indicates that help or additional information is available for an element.

It is commonly used for help icons, information icons, tooltips, and elements that provide extra guidance.

### Syntax

```css
.element {
    cursor: help;
}
```

### Basic Example

```html
<span class="help-icon">
    ?
</span>
```

```css
.help-icon {
    cursor: help;
}
```

When the user moves the pointer over the element, the cursor indicates that additional information may be available.

### Help Cursor Meaning

The `help` cursor communicates:

```text
Help cursor
      ↓
Additional information is available
      ↓
User can learn more
```

### Common Use Cases

The `help` cursor can be used for:

- Help icons
- Information icons
- Tooltips
- Form field guidance
- Instructions
- Additional explanations

### Example: Help Icon

```html
<span class="help">
    ?
</span>
```

```css
.help {
    cursor: help;
}
```

The cursor provides visual feedback that the element may provide useful information.

### Example: Information Icon

```html
<span class="info">
    ℹ
</span>
```

```css
.info {
    cursor: help;
}
```

The icon can be used to indicate that additional information is available.

### Help Cursor Does Not Display Help Automatically

Using:

```css
.element {
    cursor: help;
}
```

does not automatically create:

- A tooltip
- A help message
- A popup
- Additional information

It only changes the appearance of the cursor.

```text
cursor: help
        ↓
Visual indication

Actual help content
        ↓
Requires HTML, CSS,
or JavaScript
```

### Example: Help With a Tooltip

```html
<span class="help" title="Enter your full name">
    ?
</span>
```

```css
.help {
    cursor: help;
}
```

The cursor indicates that help is available, while the `title` attribute provides additional information.

### Help Cursor vs Pointer Cursor

These cursor values communicate different purposes.

```text
cursor: pointer
→ Click or activate

cursor: help
→ Additional information or guidance
```

Use `help` when the main purpose of the element is to provide assistance or explanation.

### When to Use `help`

Use:

```css
cursor: help;
```

when an element provides additional guidance.

For example:

```text
Question mark icon
→ help

Information icon
→ help

Tooltip trigger
→ help

Clickable button
→ pointer
```

The cursor should match the actual behavior of the element.

### Important Points

```text
cursor: help
│
├── Indicates additional information
│
├── Useful for help and information elements
│
├── Provides visual feedback
│
├── Does not automatically display help
│
└── Should match the element's purpose
```

> 💡 **Remember:** `cursor: help` indicates that additional information or guidance is available. It changes only the cursor appearance; the actual help content must be provided separately.

---

## Not Allowed Cursor

The `not-allowed` cursor value indicates that an action is not permitted.

It is commonly used for disabled elements or actions that are currently unavailable.

### Syntax

```css
.element {
    cursor: not-allowed;
}
```

### Basic Example

```html
<button class="disabled-button" disabled>
    Submit
</button>
```

```css
.disabled-button {
    cursor: not-allowed;
}
```

When the user moves the pointer over the element, the cursor indicates that the action is unavailable.

### Not Allowed Cursor Meaning

The `not-allowed` cursor communicates:

```text
Not-allowed cursor
        ↓
Action is unavailable
        ↓
User should not perform the action
```

### Common Use Cases

The `not-allowed` cursor can be used for:

- Disabled buttons
- Unavailable actions
- Restricted features
- Invalid operations
- Elements that cannot currently be interacted with

### Example: Disabled Button

```html
<button class="button" disabled>
    Save
</button>
```

```css
.button:disabled {
    cursor: not-allowed;
}
```

This provides visual feedback that the button cannot currently be used.

### Not Allowed Cursor Does Not Disable an Element

Using:

```css
.element {
    cursor: not-allowed;
}
```

does not automatically disable the element.

It only changes the cursor appearance.

```text
cursor: not-allowed
        ↓
Visual feedback

Actual disabled behavior
        ↓
Requires HTML attributes,
CSS interaction control,
or JavaScript
```

For example:

```html
<button disabled>
    Submit
</button>
```

The `disabled` attribute provides the actual disabled behavior.

### Example: Unavailable Action

```html
<div class="restricted">
    Premium Feature
</div>
```

```css
.restricted {
    cursor: not-allowed;
}
```

The cursor communicates that the action is unavailable.

However, if the element should not respond to pointer interactions, additional behavior may be needed.

For example:

```css
.restricted {
    cursor: not-allowed;
    pointer-events: none;
}
```

### Not Allowed vs Pointer

These values communicate different meanings.

```text
cursor: pointer
→ Action is available

cursor: not-allowed
→ Action is unavailable
```

For example:

```css
.button {
    cursor: pointer;
}

.button:disabled {
    cursor: not-allowed;
}
```

This helps users understand the current state of the element.

### Disabled States

A common pattern is to combine the cursor with other visual changes.

```css
.button:disabled {
    cursor: not-allowed;
    opacity: 0.6;
}
```

The cursor indicates that the action is unavailable, while the reduced opacity provides an additional visual indication.

### When to Use `not-allowed`

Use:

```css
cursor: not-allowed;
```

when an action cannot currently be performed.

```text
Enabled action
→ pointer

Disabled action
→ not-allowed

Normal element
→ default or auto
```

The cursor should always match the actual state and behavior of the element.

### Important Points

```text
cursor: not-allowed
│
├── Indicates an unavailable action
│
├── Useful for disabled states
│
├── Provides visual feedback
│
├── Does not disable functionality by itself
│
└── Should match the actual element state
```

> 💡 **Remember:** `cursor: not-allowed` communicates that an action is unavailable. It provides visual feedback only and does not automatically disable the element.

---

## Crosshair Cursor

The `crosshair` cursor value displays a crosshair-style cursor.

It is commonly used when the user needs to select a precise location or position.

### Syntax

```css
.element {
    cursor: crosshair;
}
```

### Basic Example

```html
<div class="drawing-area">
    Select a position
</div>
```

```css
.drawing-area {
    cursor: crosshair;
}
```

When the user moves the pointer over the element, the cursor changes to a crosshair.

### Crosshair Cursor Meaning

The crosshair cursor communicates:

```text
Crosshair cursor
        ↓
Precise positioning
        ↓
User can select a location
```

### Common Use Cases

The `crosshair` cursor can be useful for:

- Drawing applications
- Image editors
- Design tools
- Canvas applications
- Selection tools
- Precise positioning
- Interactive maps
- Games

### Example: Drawing Area

```html
<div class="canvas">
    Draw Here
</div>
```

```css
.canvas {
    cursor: crosshair;
}
```

The cursor provides visual feedback that the user can interact with a specific location.

### Example: Image Selection

```css
.image-selector {
    cursor: crosshair;
}
```

This can indicate that the user can select a specific point or area on an image.

### Crosshair Cursor Does Not Add Selection Functionality

Using:

```css
.element {
    cursor: crosshair;
}
```

only changes the appearance of the cursor.

It does not automatically provide:

- Drawing functionality
- Position selection
- Image editing
- Area selection

```text
cursor: crosshair
        ↓
Visual indication

Actual functionality
        ↓
Requires HTML, Canvas,
or JavaScript
```

### Crosshair vs Pointer

These cursor values communicate different interactions.

```text
cursor: pointer
→ Click or activate

cursor: crosshair
→ Select a precise location
```

Use `crosshair` when precision or location selection is the main interaction.

### Example: Interactive Area

```html
<div class="interactive-area">
    Click a point
</div>
```

```css
.interactive-area {
    cursor: crosshair;
}
```

The crosshair suggests that the user is selecting a specific position.

### When to Use `crosshair`

Use:

```css
cursor: crosshair;
```

when the user needs to interact with a precise location.

```text
Button
→ pointer

Text
→ text

Draggable element
→ move or grab

Precise location
→ crosshair
```

### Important Points

```text
cursor: crosshair
│
├── Indicates precise positioning
│
├── Useful for drawing and editing tools
│
├── Useful for selecting locations
│
├── Provides visual feedback
│
└── Does not create functionality by itself
```

> 💡 **Remember:** `cursor: crosshair` is useful when an interface requires precise position selection, such as drawing tools, image editors, or interactive areas.

---

## Grab and Grabbing Cursors

The `grab` and `grabbing` cursor values are commonly used for drag-and-drop interactions.

They provide visual feedback about whether an element can be grabbed or is currently being dragged.

### `grab` Cursor

The `grab` cursor indicates that an element can be grabbed and moved.

### Syntax

```css
.element {
    cursor: grab;
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
    cursor: grab;
}
```

The cursor indicates that the element is available to be grabbed.

### `grab` Cursor Meaning

```text
grab
  ↓
Element can be grabbed
  ↓
User can begin dragging
```

### `grabbing` Cursor

The `grabbing` cursor indicates that the user is currently grabbing or dragging an element.

### Syntax

```css
.element {
    cursor: grabbing;
}
```

### Basic Example

```css
.draggable:active {
    cursor: grabbing;
}
```

This can provide feedback while the user is pressing and dragging the element.

### `grab` and `grabbing` Together

A common pattern is:

```css
.draggable {
    cursor: grab;
}

.draggable:active {
    cursor: grabbing;
}
```

The cursor changes based on the interaction state.

```text
Before interaction
        ↓
cursor: grab

User starts dragging
        ↓
cursor: grabbing
```

### Example

```html
<div class="card">
    Drag Me
</div>
```

```css
.card {
    cursor: grab;
}

.card:active {
    cursor: grabbing;
}
```

This creates visual feedback during the interaction.

### Common Use Cases

The `grab` and `grabbing` cursors can be used for:

- Drag-and-drop interfaces
- Image galleries
- Interactive maps
- Sliders
- Kanban boards
- Layout builders
- Design tools
- Scrollable interfaces

### Example: Draggable Item

```css
.draggable-item {
    cursor: grab;
}

.draggable-item:active {
    cursor: grabbing;
}
```

This indicates:

```text
Normal state
→ Element can be grabbed

Active state
→ Element is being grabbed
```

### `grab` vs `move`

These cursor values communicate slightly different interactions.

```text
grab
→ Element can be picked up or grabbed

grabbing
→ Element is currently being grabbed

move
→ Element can be moved or repositioned
```

The `grab` and `grabbing` values are often more intuitive for direct drag interactions.

### `grab` and `grabbing` Do Not Add Drag Functionality

Using:

```css
.draggable {
    cursor: grab;
}
```

does not automatically make the element draggable.

Similarly:

```css
.draggable:active {
    cursor: grabbing;
}
```

does not implement drag behavior.

```text
Cursor property
        ↓
Visual feedback

Actual dragging
        ↓
Requires HTML drag behavior
or JavaScript
```

### Example With HTML Dragging

An element can use the `draggable` attribute:

```html
<div draggable="true" class="item">
    Drag Me
</div>
```

```css
.item {
    cursor: grab;
}

.item:active {
    cursor: grabbing;
}
```

The HTML attribute provides draggable behavior, while the cursor provides visual feedback.

### When to Use `grab`

Use:

```css
cursor: grab;
```

when the user can begin a drag interaction.

### When to Use `grabbing`

Use:

```css
cursor: grabbing;
```

when the user is actively dragging or holding an element.

### Important Points

```text
grab and grabbing
│
├── grab
│   → Element can be grabbed
│
├── grabbing
│   → Element is currently being grabbed
│
├── Useful for drag interactions
│
├── Provide visual feedback
│
└── Do not create drag functionality
```

> 💡 **Remember:** Use `grab` to indicate that an element can be picked up and `grabbing` to indicate that the user is actively dragging it.

---

## Resize Cursors

CSS provides several cursor values that indicate an element can be resized.

These cursors are commonly used for resizable panels, windows, columns, images, and other interface elements.

### Basic Syntax

```css
.element {
    cursor: resize-value;
}
```

For example:

```css
.resizable {
    cursor: ew-resize;
}
```

This indicates that the element can be resized horizontally.

## Common Resize Cursor Values

CSS provides directional resize cursors.

| Cursor Value | Direction |
|---|---|
| `col-resize` | Column can be resized |
| `row-resize` | Row can be resized |
| `n-resize` | Resize upward |
| `s-resize` | Resize downward |
| `e-resize` | Resize right |
| `w-resize` | Resize left |
| `ne-resize` | Resize toward north-east |
| `nw-resize` | Resize toward north-west |
| `se-resize` | Resize toward south-east |
| `sw-resize` | Resize toward south-west |
| `ew-resize` | Horizontal resize |
| `ns-resize` | Vertical resize |
| `nesw-resize` | Diagonal resize |
| `nwse-resize` | Diagonal resize |

### Horizontal Resize

The `ew-resize` value indicates horizontal resizing.

```css
.horizontal-resize {
    cursor: ew-resize;
}
```

```text
← → 
Horizontal resizing
```

### Vertical Resize

The `ns-resize` value indicates vertical resizing.

```css
.vertical-resize {
    cursor: ns-resize;
}
```

```text
↕
Vertical resizing
```

### Diagonal Resize

The `nwse-resize` value indicates diagonal resizing.

```css
.corner {
    cursor: nwse-resize;
}
```

This is commonly used for resize handles positioned on corners.

Another example:

```css
.corner {
    cursor: nesw-resize;
}
```

The direction should match the intended resize behavior.

### Directional Resize Cursors

Individual directions can also be specified.

```css
.top {
    cursor: n-resize;
}

.bottom {
    cursor: s-resize;
}

.left {
    cursor: w-resize;
}

.right {
    cursor: e-resize;
}
```

Diagonal directions can also be used.

```css
.top-right {
    cursor: ne-resize;
}

.top-left {
    cursor: nw-resize;
}

.bottom-right {
    cursor: se-resize;
}

.bottom-left {
    cursor: sw-resize;
}
```

### Column Resize

The `col-resize` cursor is commonly used for resizable columns.

```css
.column-handle {
    cursor: col-resize;
}
```

Common use cases include:

- Tables
- Data grids
- Resizable sidebars
- Column layouts

### Row Resize

The `row-resize` cursor is commonly used for resizable rows.

```css
.row-handle {
    cursor: row-resize;
}
```

Common use cases include:

- Tables
- Layout editors
- Resizable sections

### Example: Resize Handle

```html
<div class="resize-handle"></div>
```

```css
.resize-handle {
    cursor: ew-resize;
}
```

The cursor provides visual feedback that the handle can be used for horizontal resizing.

### Resize Cursors Do Not Add Resize Functionality

Using:

```css
.resize-handle {
    cursor: ew-resize;
}
```

does not automatically make an element resizable.

```text
Resize cursor
        ↓
Visual feedback

Actual resizing
        ↓
Requires CSS resize property
or JavaScript functionality
```

For example, CSS provides the `resize` property:

```css
textarea {
    resize: both;
}
```

JavaScript can also be used to create custom resizing behavior.

### Example: Custom Resize Interface

```css
.left-handle {
    cursor: ew-resize;
}

.top-handle {
    cursor: ns-resize;
}

.corner-handle {
    cursor: nwse-resize;
}
```

Each cursor helps communicate the direction in which the element can be resized.

### Important Points

```text
Resize cursors
│
├── Horizontal
│   → ew-resize
│
├── Vertical
│   → ns-resize
│
├── Diagonal
│   → nwse-resize
│   → nesw-resize
│
├── Column
│   → col-resize
│
└── Row
    → row-resize
```

> 💡 **Remember:** Resize cursors provide visual feedback about the direction in which an element can be resized. They change only the cursor appearance and do not create resize functionality by themselves.

---

## Zoom Cursors

CSS provides cursor values that indicate zooming actions.

The two main zoom cursor values are:

- `zoom-in`
- `zoom-out`

These cursors are commonly used in image viewers, maps, galleries, and other interfaces where users can change the zoom level.

### `zoom-in` Cursor

The `zoom-in` cursor indicates that the user can increase the zoom level.

### Syntax

```css
.element {
    cursor: zoom-in;
}
```

### Basic Example

```html
<img class="image" src="image.jpg" alt="Example image">
```

```css
.image {
    cursor: zoom-in;
}
```

The cursor indicates that clicking or interacting with the image may increase its zoom level.

### `zoom-in` Cursor Meaning

```text
zoom-in
   ↓
Increase zoom level
   ↓
View content more closely
```

### `zoom-out` Cursor

The `zoom-out` cursor indicates that the user can decrease the zoom level.

### Syntax

```css
.element {
    cursor: zoom-out;
}
```

### Basic Example

```css
.zoomed-image {
    cursor: zoom-out;
}
```

This indicates that the user may be able to return to a smaller zoom level.

### `zoom-out` Cursor Meaning

```text
zoom-out
    ↓
Decrease zoom level
    ↓
View more content
```

### Using Zoom Cursors Together

A common pattern is to change the cursor depending on the zoom state.

```css
.image {
    cursor: zoom-in;
}

.image.zoomed {
    cursor: zoom-out;
}
```

The cursor changes depending on the current state.

```text
Normal image
     ↓
zoom-in

Zoomed image
     ↓
zoom-out
```

### Common Use Cases

Zoom cursors can be used for:

- Image galleries
- Image viewers
- Maps
- Product images
- Photo editors
- Document viewers
- Interactive diagrams

### Example: Clickable Image

```html
<img class="photo" src="photo.jpg" alt="Example photo">
```

```css
.photo {
    cursor: zoom-in;
}
```

The cursor provides visual feedback that the image can be enlarged.

### Example: Zoom State

```css
.photo {
    cursor: zoom-in;
}

.photo.zoomed {
    cursor: zoom-out;
}
```

The `.zoomed` class can be added when the image is enlarged.

### Zoom Cursors Do Not Add Zoom Functionality

Using:

```css
.element {
    cursor: zoom-in;
}
```

does not automatically zoom an element.

Similarly:

```css
.element {
    cursor: zoom-out;
}
```

does not automatically reduce the zoom level.

```text
Zoom cursor
       ↓
Visual feedback

Actual zooming
       ↓
Requires CSS transforms,
browser functionality,
or JavaScript
```

### Example With CSS

A zoom effect can be created using `transform`.

```css
.image {
    cursor: zoom-in;
}

.image.zoomed {
    transform: scale(1.5);
    cursor: zoom-out;
}
```

The cursor communicates the possible interaction, while the `transform` property creates the visual zoom effect.

### `zoom-in` vs `zoom-out`

```text
zoom-in
→ Increase magnification

zoom-out
→ Decrease magnification
```

The cursor should match the action that will occur when the user interacts with the element.

### Important Points

```text
Zoom cursors
│
├── zoom-in
│   → Increase zoom level
│
├── zoom-out
│   → Decrease zoom level
│
├── Useful for zoomable interfaces
│
├── Provide visual feedback
│
└── Do not create zoom functionality
```

> 💡 **Remember:** Use `zoom-in` to indicate that an element can be enlarged and `zoom-out` to indicate that the zoom level can be reduced. These cursor values provide visual feedback but do not create zoom functionality by themselves.

---

## Other Common Cursor Values

CSS provides several additional cursor values for specific interactions and interface states.

These values can help provide clearer visual feedback to users.

### `auto`

The `auto` value allows the browser to automatically determine the appropriate cursor.

```css
.element {
    cursor: auto;
}
```

This is the default behavior.

```text
cursor: auto
      ↓
Browser determines
the appropriate cursor
```

### `none`

The `none` value hides the cursor when it is over an element.

```css
.element {
    cursor: none;
}
```

This can be useful for:

- Games
- Custom cursor interfaces
- Full-screen applications
- Drawing applications

Example:

```css
.game-area {
    cursor: none;
}
```

Use `none` carefully because hiding the cursor can make an interface difficult to use.

### `context-menu`

The `context-menu` value indicates that a context menu is available.

```css
.element {
    cursor: context-menu;
}
```

This may be useful for elements that provide additional options.

```text
context-menu
      ↓
Additional options
may be available
```

### `progress`

The `progress` cursor indicates that an operation is currently in progress.

```css
.element {
    cursor: progress;
}
```

Unlike `wait`, the `progress` cursor can indicate that processing is happening while the user may still be able to interact with the interface.

```text
wait
→ User may need to wait

progress
→ Processing is happening,
  but interaction may still be possible
```

### `cell`

The `cell` cursor is commonly used for interfaces that work with cells or tables.

```css
.cell {
    cursor: cell;
}
```

Possible use cases include:

- Spreadsheet applications
- Data tables
- Grid interfaces
- Cell selection tools

### `copy`

The `copy` cursor indicates that an item may be copied.

```css
.item {
    cursor: copy;
}
```

This can be useful during drag-and-drop interactions.

```text
copy
  ↓
Element or content
may be copied
```

### `alias`

The `alias` cursor indicates that an alias, shortcut, or linked reference may be created.

```css
.item {
    cursor: alias;
}
```

This value is less commonly used but can be useful in specialized interfaces.

### `vertical-text`

The `vertical-text` cursor indicates that vertical text interaction is possible.

```css
.vertical-text {
    cursor: vertical-text;
}
```

It may be useful for vertical writing or specialized text interfaces.

### Common Cursor Values Summary

| Cursor Value | Purpose |
|---|---|
| `auto` | Browser automatically selects the cursor |
| `none` | Hides the cursor |
| `context-menu` | Indicates a context menu |
| `progress` | Indicates processing is in progress |
| `cell` | Indicates cell selection |
| `copy` | Indicates content can be copied |
| `alias` | Indicates an alias or shortcut |
| `vertical-text` | Indicates vertical text interaction |

### Choosing the Correct Cursor

The cursor should match the expected interaction.

```text
Normal interaction
→ auto

No cursor required
→ none

Processing
→ progress

Copy operation
→ copy

Cell interaction
→ cell

Additional options
→ context-menu
```

Using the correct cursor helps users understand what actions may be available.

### Important Points

```text
Other cursor values
│
├── auto
│   → Browser chooses cursor
│
├── none
│   → Hides cursor
│
├── progress
│   → Operation in progress
│
├── copy
│   → Copy operation
│
├── cell
│   → Cell interaction
│
└── context-menu
    → Additional options
```

> 💡 **Remember:** CSS provides many cursor values beyond common options such as `pointer`, `text`, and `move`. Choose a cursor value that accurately represents the interaction available to the user.

---

## Custom Cursor

CSS allows you to use a custom image as the cursor.

This can be useful when building games, creative interfaces, drawing tools, or branded user interfaces.

Custom cursors are created using the `url()` function with the `cursor` property.

### Basic Syntax

```css
.element {
    cursor: url("cursor.png"), auto;
}
```

The browser attempts to use the custom cursor image.

If the image cannot be used, the fallback cursor is displayed.

```text
Custom cursor image
        ↓
If supported
        ↓
Use custom image

Otherwise
        ↓
Use fallback cursor
```

### Basic Example

```html
<div class="custom-area">
    Hover over me
</div>
```

```css
.custom-area {
    cursor: url("cursor.png"), pointer;
}
```

The custom image is used as the cursor when the user moves over the element.

If the image cannot be loaded or supported, the browser uses `pointer`.

### Why Use a Fallback?

A fallback cursor should always be included.

For example:

```css
.element {
    cursor: url("custom-cursor.png"), pointer;
}
```

The fallback is important because:

- The image may fail to load
- The image format may not be supported
- The browser may reject the cursor image
- The image may be unavailable

A predefined cursor value provides a reliable alternative.

### Example With `auto`

```css
.element {
    cursor: url("cursor.png"), auto;
}
```

If the custom image cannot be used, the browser automatically determines the appropriate cursor.

### Custom Cursor Formats

Cursor images can use supported image formats.

For example:

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

Another example:

```css
.element {
    cursor: url("cursor.svg"), pointer;
}
```

Browser support and behavior can vary depending on the image format and browser.

### Multiple Custom Cursor Images

More than one cursor image can be provided.

```css
.element {
    cursor:
        url("cursor.svg"),
        url("cursor.png"),
        pointer;
}
```

The browser attempts to use the images in order.

```text
cursor.svg
     ↓
If unavailable

cursor.png
     ↓
If unavailable

pointer
```

### Custom Cursor With a Hotspot

A custom cursor can specify hotspot coordinates.

```css
.element {
    cursor: url("cursor.png") 10 10, pointer;
}
```

The hotspot defines the active point of the cursor.

```text
Cursor image
     ↓
Hotspot coordinates
     ↓
Active click position
```

The first value represents the horizontal position.

The second value represents the vertical position.

### Example

```css
.element {
    cursor: url("cursor.png") 5 5, auto;
}
```

The browser uses the specified point in the image as the active position.

### Custom Cursor Does Not Add Functionality

A custom cursor only changes the appearance of the pointer.

For example:

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

This does not automatically make the element:

- Clickable
- Draggable
- Interactive

```text
Custom cursor
        ↓
Visual appearance

Actual interaction
        ↓
Requires HTML,
CSS behavior,
or JavaScript
```

### When to Use Custom Cursors

Custom cursors can be useful for:

- Games
- Drawing applications
- Creative websites
- Interactive tools
- Custom interfaces
- Specialized user experiences

They should be used carefully because unusual cursor designs can confuse users.

### Important Points

```text
Custom cursor
│
├── Uses url()
│
├── Can use an image
│
├── Should include a fallback
│
├── Can specify hotspot coordinates
│
├── Can provide multiple image options
│
└── Changes appearance only
```

> 💡 **Remember:** A custom CSS cursor uses an image with `url()`. Always provide a fallback cursor value so the interface remains usable if the custom image cannot be displayed.

---

## Cursor With Images

CSS allows images to be used as custom cursors with the `url()` function.

This allows you to replace a standard browser cursor with an image.

### Basic Syntax

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

The browser attempts to use the image as the cursor.

If the image cannot be used, the fallback cursor is displayed.

```text
Cursor image
     ↓
Browser attempts to load image
     ↓
Custom cursor displayed

If unsuccessful
     ↓
Fallback cursor displayed
```

### Basic Example

```html
<div class="image-area">
    Hover over me
</div>
```

```css
.image-area {
    cursor: url("cursor.png"), pointer;
}
```

When the user moves the pointer over the element, the custom image is used as the cursor.

### Image Path

The image path can be relative to the CSS file.

```css
.element {
    cursor: url("images/cursor.png"), auto;
}
```

An absolute path can also be used.

```css
.element {
    cursor: url("/images/cursor.png"), auto;
}
```

The correct path must be provided so the browser can locate the image.

### Using Different Image Formats

Custom cursor images can use supported image formats.

For example:

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

Another example:

```css
.element {
    cursor: url("cursor.svg"), pointer;
}
```

Support and behavior can vary depending on the browser and image format.

### Cursor Image With Hotspot Coordinates

By default, the active point is determined by the cursor image.

You can specify a hotspot using coordinates.

```css
.element {
    cursor: url("cursor.png") 10 10, pointer;
}
```

The syntax is:

```css
cursor: url("image-path") x y, fallback;
```

Where:

```text
x
→ Horizontal hotspot position

y
→ Vertical hotspot position
```

The hotspot represents the active point used for interactions.

### Example

```css
.drawing-tool {
    cursor: url("brush.png") 5 20, crosshair;
}
```

The custom image is used when available.

If it cannot be used, the `crosshair` cursor is displayed.

### Multiple Cursor Images

More than one cursor image can be provided.

```css
.element {
    cursor:
        url("cursor.svg"),
        url("cursor.png"),
        pointer;
}
```

The browser attempts to use each image in order.

```text
cursor.svg
     ↓
If unavailable

cursor.png
     ↓
If unavailable

pointer
```

### Using Images for Different Interactions

Different cursor images can represent different actions.

```css
.select-tool {
    cursor: url("select.png"), default;
}

.brush-tool {
    cursor: url("brush.png"), crosshair;
}

.move-tool {
    cursor: url("move.png"), move;
}
```

This can be useful in drawing applications and specialized interfaces.

### Example: Custom Tool Interface

```html
<div class="canvas brush-tool">
    Draw here
</div>
```

```css
.brush-tool {
    cursor: url("brush.png") 5 20, crosshair;
}
```

The custom cursor image provides visual feedback about the active tool.

### Cursor Images and Functionality

Using an image as a cursor only changes the appearance of the pointer.

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

It does not automatically add:

- Click functionality
- Drag functionality
- Drawing functionality
- Custom interaction behavior

```text
Cursor image
      ↓
Visual feedback only

Actual interaction
      ↓
Requires additional functionality
```

### Important Points

```text
Cursor images
│
├── Use url()
│
├── Can use image files
│
├── Can specify hotspot coordinates
│
├── Can provide multiple images
│
├── Should include a fallback
│
└── Change appearance only
```

> 💡 **Remember:** Images can be used as CSS cursors with `url()`. Always include an appropriate fallback cursor so the interface remains usable if the image cannot be loaded or used.

---

## Cursor Fallback Values

When using custom cursor images, it is important to provide a fallback cursor value.

A fallback is used when the browser cannot load or use the custom cursor image.

### Basic Syntax

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

In this example:

```text
Custom cursor image
        ↓
If available and supported
        ↓
Use cursor.png

Otherwise
        ↓
Use pointer
```

The fallback value ensures that the user still receives appropriate visual feedback.

### Why Fallback Values Are Important

A custom cursor image may not be used for several reasons.

For example:

- The image file cannot be found
- The image fails to load
- The image format is unsupported
- The browser rejects the image
- The cursor image is too large
- The browser has limitations for custom cursors

A fallback helps keep the interface usable.

### Example With `pointer`

```css
.button {
    cursor: url("custom-pointer.png"), pointer;
}
```

If the custom image cannot be displayed, the user sees the standard pointer cursor.

### Example With `text`

```css
.editable {
    cursor: url("text-cursor.png"), text;
}
```

If the custom cursor image is unavailable, the `text` cursor is used.

### Example With `move`

```css
.draggable {
    cursor: url("move-cursor.png"), move;
}
```

The fallback cursor still communicates that the element can be moved.

### Example With `crosshair`

```css
.drawing-area {
    cursor: url("brush.png"), crosshair;
}
```

If the brush image cannot be used, the crosshair provides a suitable alternative.

### Choosing the Correct Fallback

The fallback should match the intended interaction.

```text
Clickable element
→ pointer

Text interaction
→ text

Draggable element
→ move or grab

Drawing area
→ crosshair

Normal element
→ default or auto
```

For example:

```css
.button {
    cursor: url("custom-button.png"), pointer;
}
```

Using:

```css
.button {
    cursor: url("custom-button.png"), text;
}
```

would provide incorrect visual feedback because `text` does not represent a clickable button.

### Multiple Cursor Images With a Fallback

You can provide multiple custom cursor images before the fallback.

```css
.element {
    cursor:
        url("cursor.svg"),
        url("cursor.png"),
        pointer;
}
```

The browser attempts to use the values from left to right.

```text
cursor.svg
     ↓
If unavailable

cursor.png
     ↓
If unavailable

pointer
```

The final keyword acts as the fallback.

### Fallback With `auto`

You can also use `auto` as a fallback.

```css
.element {
    cursor: url("cursor.png"), auto;
}
```

If the custom cursor cannot be used, the browser automatically selects an appropriate cursor.

### Fallback With `default`

```css
.element {
    cursor: url("cursor.png"), default;
}
```

If the image cannot be used, the default system cursor is displayed.

### Cursor Fallback Rules

A reliable pattern is:

```css
cursor: url("custom-cursor.png"), fallback-value;
```

For example:

```css
cursor: url("custom-cursor.png"), pointer;
```

The final keyword should always communicate the correct interaction.

### Important Points

```text
Cursor fallback values
│
├── Used when a custom cursor fails
│
├── Improve reliability
│
├── Should match the interaction
│
├── Can follow multiple cursor images
│
└── Provide a usable alternative
```

> 💡 **Remember:** When using a custom cursor image, always provide a fallback cursor keyword. The fallback should accurately represent the interaction so the interface remains usable even if the custom cursor cannot be displayed.

---

## Practical Examples

The following examples demonstrate common ways to use the CSS `cursor` property in real interfaces.

### Example 1: Clickable Button

Use `pointer` for an element that can be clicked.

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

### Example 2: Text Input

Use `text` when the user can enter or edit text.

```html
<input
    type="text"
    class="name-input"
    placeholder="Enter your name"
>
```

```css
.name-input {
    cursor: text;
}
```

The cursor indicates that text interaction is possible.

### Example 3: Draggable Element

Use `grab` and `grabbing` for drag interactions.

```html
<div class="draggable">
    Drag Me
</div>
```

```css
.draggable {
    cursor: grab;
}

.draggable:active {
    cursor: grabbing;
}
```

The cursor changes during interaction.

```text
Normal state
    ↓
grab

Active state
    ↓
grabbing
```

### Example 4: Disabled Button

Use `not-allowed` to indicate that an action is unavailable.

```html
<button class="button" disabled>
    Submit
</button>
```

```css
.button:disabled {
    cursor: not-allowed;
    opacity: 0.6;
}
```

The cursor and reduced opacity provide visual feedback about the disabled state.

### Example 5: Loading State

Use `wait` while an operation is being processed.

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

The cursor indicates that processing is happening.

### Example 6: Drawing Area

Use `crosshair` when the user needs to select a precise position.

```html
<div class="drawing-area">
    Draw Here
</div>
```

```css
.drawing-area {
    width: 300px;
    height: 200px;
    border: 1px solid black;
    cursor: crosshair;
}
```

The crosshair provides visual feedback for precise interaction.

### Example 7: Resizable Column

Use `col-resize` for a horizontal column resize handle.

```html
<div class="column-resize"></div>
```

```css
.column-resize {
    cursor: col-resize;
}
```

This indicates that a column can be resized.

### Example 8: Horizontal Resize

Use `ew-resize` for left and right resizing.

```css
.resize-handle {
    cursor: ew-resize;
}
```

The cursor communicates horizontal resizing.

### Example 9: Vertical Resize

Use `ns-resize` for upward and downward resizing.

```css
.resize-handle {
    cursor: ns-resize;
}
```

The cursor communicates vertical resizing.

### Example 10: Zoomable Image

Use `zoom-in` for an image that can be enlarged.

```html
<img
    class="image"
    src="photo.jpg"
    alt="Example photo"
>
```

```css
.image {
    cursor: zoom-in;
}
```

When the image is zoomed, the cursor can change.

```css
.image.zoomed {
    cursor: zoom-out;
}
```

```text
Normal image
    ↓
zoom-in

Zoomed image
    ↓
zoom-out
```

### Example 11: Custom Cursor

Use an image as a custom cursor.

```css
.custom-area {
    cursor: url("cursor.png"), pointer;
}
```

The browser uses the custom image when possible.

If the image cannot be used, `pointer` is displayed.

### Example 12: Custom Cursor With Hotspot

You can specify the active point of the cursor.

```css
.drawing-tool {
    cursor: url("brush.png") 5 20, crosshair;
}
```

The coordinates define the hotspot position.

```text
5
→ Horizontal position

20
→ Vertical position
```

### Example 13: Multiple Cursor Images

Provide multiple image options with a fallback.

```css
.custom-element {
    cursor:
        url("cursor.svg"),
        url("cursor.png"),
        pointer;
}
```

The browser attempts to use each option.

```text
cursor.svg
    ↓
If unavailable

cursor.png
    ↓
If unavailable

pointer
```

### Example 14: Context Menu

Use `context-menu` when an element provides additional options.

```css
.menu-area {
    cursor: context-menu;
}
```

This indicates that additional actions or options may be available.

### Example 15: Copy Interaction

Use `copy` when an item may be copied.

```css
.copy-item {
    cursor: copy;
}
```

This can be useful in drag-and-drop interfaces.

### Example 16: Spreadsheet Cell

Use `cell` for spreadsheet-like interfaces.

```css
.spreadsheet-cell {
    cursor: cell;
}
```

This provides visual feedback for cell-based interaction.

### Example 17: Complete Example

```html
<div class="demo">
    <button class="click-button">
        Click Me
    </button>

    <input
        class="text-input"
        type="text"
        placeholder="Enter text"
    >

    <div class="drag-item">
        Drag Me
    </div>

    <div class="drawing-area">
        Draw Here
    </div>

    <button class="disabled-button" disabled>
        Disabled
    </button>
</div>
```

```css
.click-button {
    cursor: pointer;
}

.text-input {
    cursor: text;
}

.drag-item {
    cursor: grab;
}

.drag-item:active {
    cursor: grabbing;
}

.drawing-area {
    width: 300px;
    height: 150px;
    border: 1px solid black;
    cursor: crosshair;
}

.disabled-button:disabled {
    cursor: not-allowed;
    opacity: 0.6;
}
```

This example demonstrates how different cursor values can communicate different interactions.

```text
Clickable button
→ pointer

Text input
→ text

Draggable item
→ grab / grabbing

Drawing area
→ crosshair

Disabled button
→ not-allowed
```

### Important Points

```text
Practical cursor usage
│
├── Clickable element
│   → pointer
│
├── Text interaction
│   → text
│
├── Drag interaction
│   → grab / grabbing
│
├── Precise selection
│   → crosshair
│
├── Resizing
│   → resize cursors
│
├── Zooming
│   → zoom-in / zoom-out
│
└── Unavailable action
    → not-allowed
```

> 💡 **Remember:** The best cursor value is the one that clearly matches the actual interaction available to the user. Cursors should provide helpful visual feedback without misleading users.

---

## Key Takeaways

The CSS `cursor` property controls the appearance of the mouse pointer when it is placed over an element.

It helps provide visual feedback about the type of interaction available.

### Main Purpose

```text
CSS cursor
    ↓
Changes pointer appearance
    ↓
Provides visual feedback
    ↓
Helps users understand interactions
```

### Basic Syntax

```css
.element {
    cursor: value;
}
```

Example:

```css
.button {
    cursor: pointer;
}
```

### Common Cursor Values

Some commonly used cursor values are:

```text
default
→ Default cursor

pointer
→ Clickable element

text
→ Text interaction

move
→ Movable element

wait
→ System is busy

help
→ Additional information

not-allowed
→ Action unavailable

crosshair
→ Precise selection
```

### Drag Cursors

The `grab` and `grabbing` values are useful for drag interactions.

```css
.item {
    cursor: grab;
}

.item:active {
    cursor: grabbing;
}
```

```text
grab
→ Element can be grabbed

grabbing
→ Element is currently being dragged
```

### Resize Cursors

CSS provides several cursors for resize interactions.

```text
ew-resize
→ Horizontal resizing

ns-resize
→ Vertical resizing

nwse-resize
→ Diagonal resizing

nesw-resize
→ Diagonal resizing

col-resize
→ Column resizing

row-resize
→ Row resizing
```

These cursors provide visual feedback about the direction of resizing.

### Zoom Cursors

CSS provides:

```text
zoom-in
→ Increase zoom level

zoom-out
→ Decrease zoom level
```

These values are commonly used for images, maps, and zoomable content.

### Custom Cursors

Custom images can be used as cursors.

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

A fallback cursor should always be included.

```text
Custom cursor
      ↓
If available
      ↓
Display custom image

Otherwise
      ↓
Display fallback cursor
```

### Hotspot Coordinates

Custom cursors can specify an active point.

```css
.element {
    cursor: url("cursor.png") 10 10, pointer;
}
```

The coordinates define the hotspot position within the cursor image.

### Cursor Images

Multiple cursor images can be provided.

```css
.element {
    cursor:
        url("cursor.svg"),
        url("cursor.png"),
        pointer;
}
```

The browser attempts to use the cursor values in order.

### Important Principle

The cursor should match the actual interaction.

```text
Clickable element
→ pointer

Text input
→ text

Draggable element
→ grab or move

Drawing area
→ crosshair

Disabled action
→ not-allowed

Resize handle
→ Appropriate resize cursor
```

### Cursors Provide Visual Feedback Only

The `cursor` property changes only the appearance of the pointer.

It does not automatically create functionality.

```text
cursor property
      ↓
Visual feedback only

Actual interaction
      ↓
Requires HTML,
CSS functionality,
or JavaScript
```

For example:

```css
.draggable {
    cursor: grab;
}
```

does not automatically make an element draggable.

### Best Usage

Use cursor values carefully and consistently.

```text
Correct cursor
      ↓
Clear user expectation
      ↓
Better user experience
```

An incorrect cursor can confuse users by suggesting an interaction that is not actually available.

### Summary

```text
CSS Cursor
│
├── Controls pointer appearance
│
├── Provides visual feedback
│
├── Helps communicate interactions
│
├── Supports predefined cursor values
│
├── Supports custom cursor images
│
├── Supports fallback values
│
└── Does not create functionality by itself
```

> 💡 **Remember:** The CSS `cursor` property should accurately represent the interaction available to the user. It improves usability by providing clear visual feedback, but it only changes the cursor appearance and does not create functionality.

---

## References

The following resources can be used to learn more about the CSS `cursor` property and available cursor values.

### MDN Web Docs

MDN Web Docs provides detailed documentation about the CSS `cursor` property.

Topics include:

- Cursor syntax
- Predefined cursor values
- Custom cursor images
- Hotspot coordinates
- Fallback values
- Browser behavior

### CSS Specifications

The CSS specifications define how the `cursor` property and its values should behave.

They provide technical details about:

- Property syntax
- Cursor keywords
- Image cursors
- Hotspot coordinates
- Fallback behavior

### Browser Developer Tools

Browser developer tools can be used to experiment with cursor values.

For example:

```css
.element {
    cursor: pointer;
}
```

You can change the value and immediately observe the cursor behavior.

### Useful Practice

Create a small HTML page and experiment with different cursor values.

```html
<div class="pointer">Pointer</div>
<div class="text">Text</div>
<div class="move">Move</div>
<div class="help">Help</div>
<div class="disabled">Disabled</div>
```

```css
.pointer {
    cursor: pointer;
}

.text {
    cursor: text;
}

.move {
    cursor: move;
}

.help {
    cursor: help;
}

.disabled {
    cursor: not-allowed;
}
```

This is a simple way to understand how each cursor communicates a different type of interaction.

### Recommended Topics for Further Learning

After understanding CSS cursors, you can explore:

- CSS pseudo-classes
- CSS pseudo-elements
- CSS transitions
- CSS animations
- CSS transforms
- CSS user interface properties
- CSS accessibility
- Interactive web design

### Reference Summary

```text
Useful resources
│
├── MDN Web Docs
│   → CSS documentation
│
├── CSS Specifications
│   → Official standards
│
├── Browser Developer Tools
│   → Test and experiment
│
└── Practice Projects
    → Apply cursor values
```

> 💡 **Remember:** References are useful for checking syntax, supported cursor values, browser behavior, and advanced CSS features. Regular experimentation is one of the best ways to understand how cursor values behave in real interfaces.