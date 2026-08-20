## Table of Contents

- [Introduction](#introduction)
- [What Is Overflow?](#what-is-overflow)
- [`overflow`](#overflow)
- [`overflow-x`](#overflow-x)
- [`overflow-y`](#overflow-y)
- [`overflow: visible`](#overflow-visible)
- [`overflow: hidden`](#overflow-hidden)
- [`overflow: scroll`](#overflow-scroll)
- [`overflow: auto`](#overflow-auto)
- [`overflow: clip`](#overflow-clip)
- [Two-Value Overflow](#two-value-overflow)
- [`text-overflow`](#text-overflow)
- [Overflow With Text](#overflow-with-text)
- [Overflow With Images](#overflow-with-images)
- [Overflow With Border Radius](#overflow-with-border-radius)
- [Overflow With Positioning](#overflow-with-positioning)
- [Overflow in CSS Grid](#overflow-in-css-grid)
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

CSS Overflow controls what happens when the content of an element is **larger than the space available inside its box**.

Normally, content fits inside an element:

```text
┌──────────────────────┐
│      Content         │
│      Content         │
└──────────────────────┘
```

When the content becomes larger than the available space, it can overflow:

```text
┌──────────────────────┐
│      Content         │
│      Content         │
└──────────────────────┘
      Content continues
      outside the box
```

CSS provides overflow properties that allow you to control this behavior.

### Why Overflow Matters

Overflow commonly occurs when:

- An element has a fixed width or height.
- Text is too long to fit.
- An image is larger than its container.
- A child element extends beyond its parent.
- Content does not wrap as expected.
- A layout needs a scrollable region.

For example:

```css
.box {
    width: 200px;
    height: 100px;
}
```

If the content requires more than the available:

```text
Width  → 200px
Height → 100px
```

the extra content needs to be handled somehow.

### Controlling Overflow

The main property is:

```css
overflow
```

Example:

```css
.box {
    overflow: hidden;
}
```

Other related properties include:

```css
overflow-x
overflow-y
```

These allow horizontal and vertical overflow to be controlled independently.

### Common Overflow Values

The most commonly used values are:

```css
visible
hidden
scroll
auto
clip
```

They provide different behaviors when content exceeds the available space.

### Simple Example

HTML:

```html
<div class="box">
    This is some content that is larger than the available space.
</div>
```

CSS:

```css
.box {
    width: 200px;
    height: 100px;
    overflow: auto;
}
```

If the content fits, no scrolling is needed.

If the content does not fit, the browser can provide scrolling.

### Overflow and the Box

It is useful to think of an element as having a visible area:

```text
┌──────────────────────────┐
│      Visible Area        │
│                          │
│      Content             │
│                          │
└──────────────────────────┘
            ↓
      Overflow handling
```

CSS determines what happens to content outside that available area.

### Horizontal and Vertical Overflow

Overflow can occur in two directions:

```text
Horizontal
←────────────────────────→

Vertical
        ↓
        ↓
        ↓
```

You can control them separately:

```css
.box {
    overflow-x: auto;
    overflow-y: hidden;
}
```

Here:

```text
Horizontal → scrolling when necessary
Vertical   → clipped
```

### Overflow Is Not Always a Problem

Overflow is not necessarily an error.

Sometimes overflow is intentional.

For example, a code editor, table, or horizontally scrollable container may intentionally allow content to extend beyond its visible area.

```css
.code {
    overflow-x: auto;
}
```

The important point is to choose the behavior that matches the design.

> 💡 **Remember:** CSS Overflow controls what happens when content is larger than the available space inside an element. The main properties are `overflow`, `overflow-x`, and `overflow-y`, while values such as `visible`, `hidden`, `scroll`, `auto`, and `clip` determine how that overflow is handled.

---

## What Is Overflow?

**Overflow** occurs when the content inside an element is larger than the space available within that element's box.

For example:

```css
.box {
    width: 200px;
    height: 100px;
}
```

If the content requires more than `200px` of width or `100px` of height, the content can extend beyond the element's available area.

### Simple Example

HTML:

```html
<div class="box">
    This is a very long piece of content that may not fit inside the box.
</div>
```

CSS:

```css
.box {
    width: 200px;
    height: 100px;
}
```

Conceptually:

```text
┌──────────────────────┐
│ Content that fits    │
│ inside the box       │
└──────────────────────┘
        ↓
   Extra content
   may overflow
```

### Why Does Overflow Happen?

Overflow commonly happens when:

- Content is too wide.
- Content is too tall.
- An element has fixed dimensions.
- An image is larger than its container.
- Text does not wrap.
- A child element extends outside its parent.
- A layout contains content that cannot shrink enough.

### Horizontal Overflow

Horizontal overflow occurs when content is wider than the available width.

```text
Available width:

┌──────────────────────┐
│ Content               │
└──────────────────────┘
              ────────────────→
              Extra width
```

For example:

```css
.box {
    width: 200px;
}
```

If the content needs `400px`, it can overflow horizontally.

### Vertical Overflow

Vertical overflow occurs when content is taller than the available height.

```text
┌──────────────────────┐
│ Content              │
│ Content              │
│ Content              │
└──────────────────────┘
          ↓
          ↓
     Extra content
```

For example:

```css
.box {
    height: 100px;
}
```

If the content requires `300px` of height, it can overflow vertically.

### Overflow Is Related to Available Space

Think of an element as having a limited visible area:

```text
Element
┌─────────────────────────┐
│                         │
│    Available Space      │
│                         │
└─────────────────────────┘
            ↓
      Content exceeds
      available space
            ↓
         Overflow
```

The browser then applies the overflow behavior specified by CSS.

### Controlling Overflow

The main property used to control overflow is:

```css
overflow
```

For example:

```css
.box {
    width: 200px;
    height: 100px;
    overflow: hidden;
}
```

Here, content that extends outside the box is clipped.

Other related properties are:

```css
overflow-x
overflow-y
```

These control horizontal and vertical overflow separately.

### Overflow Is Not Necessarily an Error

Overflow can be intentional.

For example, a horizontally scrollable code block can use:

```css
.code {
    overflow-x: auto;
}
```

A large table can also require horizontal scrolling on smaller screens.

```text
Small screen

┌──────────────────────┐
│ Table                │
│ ────────────────────→│
└──────────────────────┘
       scroll
```

In these situations, overflow is part of the intended design.

### Overflow vs Normal Content Flow

Normally, browsers try to lay out content inside the available space.

When content cannot fit, the browser must determine what happens to the extra content.

CSS gives you control over this behavior through:

```css
overflow
overflow-x
overflow-y
```

The specific value determines whether the content remains visible, is clipped, or becomes scrollable.

### Important Points

```text
Overflow
│
├── Content is larger than available space
│
├── Horizontal overflow
│   └── Content is too wide
│
├── Vertical overflow
│   └── Content is too tall
│
└── Controlled using
    ├── overflow
    ├── overflow-x
    └── overflow-y
```

> 💡 **Remember:** Overflow simply means that content does not fit within the available space of its element. It can happen horizontally, vertically, or in both directions, and CSS provides properties to control what happens to that extra content.

---

## `overflow`

The `overflow` property controls how content that extends beyond an element's box is handled.

### Syntax

```css
overflow: value;
```

Example:

```css
.box {
    width: 200px;
    height: 100px;
    overflow: hidden;
}
```

The main values are:

```css
visible
hidden
scroll
auto
clip
```

### `overflow` Controls Both Axes

The `overflow` property controls overflow in both the horizontal and vertical directions.

```css
.box {
    overflow: auto;
}
```

Conceptually:

```text
          Horizontal
       ←──────────────→

      ┌────────────────┐
      │                │
      │    Content     │
      │                │
      └────────────────┘
             │
             │
          Vertical
```

If the content becomes too wide or too tall, the selected overflow behavior is applied.

### Default Value

The default value is:

```css
overflow: visible;
```

This means overflowing content remains visible outside the element's box.

### `overflow` vs `overflow-x` / `overflow-y`

Use:

```css
overflow
```

when both axes should use the same overflow behavior.

Example:

```css
.box {
    overflow: hidden;
}
```

Use:

```css
overflow-x
overflow-y
```

when the horizontal and vertical axes need different behavior.

Example:

```css
.box {
    overflow-x: auto;
    overflow-y: hidden;
}
```

### One-Value Syntax

A single value applies to both axes:

```css
.box {
    overflow: hidden;
}
```

Equivalent conceptually to:

```css
.box {
    overflow-x: hidden;
    overflow-y: hidden;
}
```

### Two-Value Syntax

The property can also accept two values:

```css
.box {
    overflow: hidden auto;
}
```

The values correspond to:

```text
First value  → overflow-x
Second value → overflow-y
```

So:

```css
overflow: hidden auto;
```

means:

```text
Horizontal → hidden
Vertical   → auto
```

Another example:

```css
overflow: auto hidden;
```

means:

```text
Horizontal → auto
Vertical   → hidden
```

### Common Examples

Hide overflowing content:

```css
.box {
    overflow: hidden;
}
```

Allow scrolling when necessary:

```css
.box {
    overflow: auto;
}
```

Always provide scrolling:

```css
.box {
    overflow: scroll;
}
```

Keep overflow visible:

```css
.box {
    overflow: visible;
}
```

Clip overflow without a scrolling mechanism:

```css
.box {
    overflow: clip;
}
```

### When to Use `overflow`

Use `overflow` when you need to control content that exceeds an element's available space.

Common situations include:

```text
Fixed-height containers
Scrollable panels
Code blocks
Large tables
Images inside containers
Cards with clipped content
Grid and flex layouts
```

### Important Points

```text
overflow
│
├── Controls overflow on both axes
│
├── One value
│   └── Applies to both axes
│
├── Two values
│   ├── First → horizontal
│   └── Second → vertical
│
└── Common values
    ├── visible
    ├── hidden
    ├── scroll
    ├── auto
    └── clip
```

> 💡 **Remember:** `overflow` controls what happens when content exceeds an element's available space. With one value, the same behavior applies to both axes; with two values, the first controls horizontal overflow and the second controls vertical overflow.

---

## `overflow-x`

The `overflow-x` property controls what happens when content overflows an element in the **horizontal direction**.

It is useful when content becomes wider than the available width of its container.

### Syntax

```css
overflow-x: value;
```

Common values are:

```css
visible
hidden
scroll
auto
clip
```

### Basic Example

```css
.box {
    width: 200px;
    overflow-x: auto;
}
```

If the content becomes wider than `200px`, horizontal scrolling can be used.

```text
┌──────────────────────┐
│ Wide content         │
└──────────────────────┘
←──── horizontal ─────→
       scrolling
```

### `overflow-x: visible`

```css
.box {
    overflow-x: visible;
}
```

Horizontal overflow remains visible outside the element's box.

```text
┌──────────────────┐
│ Content          │
└──────────────────┘──────────────
                  Extra content
```

This is the default behavior associated with visible overflow.

### `overflow-x: hidden`

```css
.box {
    overflow-x: hidden;
}
```

Horizontal overflow is clipped.

```text
┌──────────────────────┐
│ Content that fits    │
└──────────────────────┘
```

Any content extending beyond the horizontal boundary is not visible.

### `overflow-x: scroll`

```css
.box {
    overflow-x: scroll;
}
```

A horizontal scrolling mechanism is provided for overflowing content.

```text
┌──────────────────────────┐
│ Wide content             │
├──────────────────────────┤
│◄───────────────►         │
└──────────────────────────┘
```

Depending on the browser and platform, a scrollbar may be shown even when horizontal overflow is not currently present.

### `overflow-x: auto`

```css
.box {
    overflow-x: auto;
}
```

The browser provides horizontal scrolling when it is needed.

This is commonly useful for:

- Wide tables
- Code blocks
- Long unbroken content
- Large horizontal layouts
- Responsive containers

### `overflow-x: clip`

```css
.box {
    overflow-x: clip;
}
```

Horizontal overflow is clipped without providing a scrolling mechanism.

It is useful when content should simply be prevented from extending beyond the horizontal clipping area.

### Horizontal Overflow With Long Text

Long text can cause horizontal overflow when wrapping is disabled.

```css
.text {
    white-space: nowrap;
    overflow-x: auto;
}
```

If the text is wider than the container, the user can scroll horizontally.

```text
┌────────────────────────────┐
│ This is a very long text → │
└────────────────────────────┘
```

### Horizontal Overflow With Code

Code is often wider than a small screen.

```css
.code {
    overflow-x: auto;
}
```

Example:

```html
<pre class="code">
const result = someVeryLongFunctionName();
</pre>
```

Instead of forcing the code to wrap, the container can allow horizontal scrolling.

### Horizontal Overflow With Tables

Wide tables can overflow on small screens.

A common pattern is:

```css
.table-container {
    overflow-x: auto;
}
```

HTML:

```html
<div class="table-container">
    <table>
        <!-- table content -->
    </table>
</div>
```

Conceptually:

```text
Small screen

┌──────────────────────┐
│ Column 1 | Column 2  │
│ Column 3 | Column 4  │
│ Column 5 | Column 6 →│
└──────────────────────┘
             scroll →
```

The table can remain wide while its surrounding container provides horizontal scrolling.

### `overflow-x` and `overflow-y`

These properties can be controlled independently.

```css
.box {
    overflow-x: auto;
    overflow-y: hidden;
}
```

This means:

```text
Horizontal → scroll when necessary
Vertical   → clipped
```

Another example:

```css
.box {
    overflow-x: hidden;
    overflow-y: auto;
}
```

This means:

```text
Horizontal → clipped
Vertical   → scroll when necessary
```

### Difference Between `overflow` and `overflow-x`

```css
overflow: auto;
```

controls both horizontal and vertical overflow.

While:

```css
overflow-x: auto;
```

controls only the horizontal overflow behavior.

For example:

```css
.box {
    overflow: auto;
}
```

versus:

```css
.box {
    overflow-x: auto;
    overflow-y: hidden;
}
```

The second example explicitly gives different behavior to the two axes.

### Practical Example

HTML:

```html
<div class="container">
    <div class="content">
        This content is intentionally wider than the container.
    </div>
</div>
```

CSS:

```css
.container {
    width: 300px;
    overflow-x: auto;
}

.content {
    width: 600px;
}
```

The container remains `300px` wide while the content is `600px` wide.

The user can scroll horizontally to access the remaining content.

### Important Points

```text
overflow-x
│
├── Controls horizontal overflow
│
├── visible → overflow remains visible
├── hidden  → overflow is clipped
├── scroll  → scrolling mechanism is provided
├── auto    → scrolling when necessary
└── clip    → clips without scrolling
```

> 💡 **Remember:** Use `overflow-x` when content can become wider than its container and you need to control horizontal overflow independently from vertical overflow. `auto` is particularly useful for responsive tables, code blocks, and other wide content.

---

## `overflow-y`

The `overflow-y` property controls what happens when content overflows an element in the **vertical direction**.

It is useful when content becomes taller than the available height of its container.

### Syntax

```css
overflow-y: value;
```

Common values are:

```css
visible
hidden
scroll
auto
clip
```

### Basic Example

```css
.box {
    height: 150px;
    overflow-y: auto;
}
```

If the content becomes taller than `150px`, vertical scrolling can be used.

```text
┌──────────────────────┐
│ Content              │
│ Content              │
│ Content              │
│              █       │
│              █       │
└──────────────────────┘
        ↑
     Vertical
     scrolling
```

### `overflow-y: visible`

```css
.box {
    overflow-y: visible;
}
```

Vertical overflow remains visible outside the element's box.

```text
┌──────────────────────┐
│ Content              │
│ Content              │
└──────────────────────┘
│ More content         │
│ More content         │
```

### `overflow-y: hidden`

```css
.box {
    overflow-y: hidden;
}
```

Vertical overflow is clipped.

```text
┌──────────────────────┐
│ Content              │
│ Content              │
│ Content              │
└──────────────────────┘
```

Content extending beyond the vertical boundary is not visible.

### `overflow-y: scroll`

```css
.box {
    overflow-y: scroll;
}
```

A vertical scrolling mechanism is provided for the element.

```text
┌──────────────────────┐
│ Content              │
│ Content              │
│ Content              │
│ Content              │
│                   █  │
│                   █  │
└──────────────────────┘
```

Depending on the browser and platform, a scrollbar may be shown even when the content does not currently overflow.

### `overflow-y: auto`

```css
.box {
    overflow-y: auto;
}
```

The browser provides vertical scrolling when it is needed.

This is commonly useful for:

- Long lists
- Chat panels
- Sidebars
- Modal content
- Fixed-height containers
- Scrollable sections

### `overflow-y: clip`

```css
.box {
    overflow-y: clip;
}
```

Vertical overflow is clipped without providing a scrolling mechanism.

This is useful when content should simply be prevented from extending beyond the vertical clipping area.

### Vertical Overflow With Text

A fixed-height text container can become vertically scrollable:

```css
.text {
    height: 200px;
    overflow-y: auto;
}
```

If the text becomes longer than the available height, the user can scroll vertically.

```text
┌────────────────────────┐
│ Line 1                 │
│ Line 2                 │
│ Line 3                 │
│ Line 4                 │
│ Line 5             █   │
│ Line 6             █   │
└────────────────────────┘
```

### Vertical Overflow With Lists

A long list can be placed inside a fixed-height container:

```css
.list {
    height: 250px;
    overflow-y: auto;
}
```

HTML:

```html
<div class="list">
    <p>Item 1</p>
    <p>Item 2</p>
    <p>Item 3</p>
    <p>Item 4</p>
    <p>Item 5</p>
    <p>Item 6</p>
</div>
```

The container remains `250px` high while the list can continue beyond the visible area.

### Vertical Overflow With a Sidebar

A sidebar can use vertical scrolling when its content becomes too tall:

```css
.sidebar {
    height: 100vh;
    overflow-y: auto;
}
```

This can be useful for navigation menus with many items.

### Vertical Overflow With a Modal

A modal may have a maximum height:

```css
.modal {
    max-height: 80vh;
    overflow-y: auto;
}
```

If the content is short, the modal remains within the available height.

If the content becomes longer, the modal can scroll vertically.

### `overflow-y` and `overflow-x`

The two axes can be controlled independently.

```css
.box {
    overflow-x: hidden;
    overflow-y: auto;
}
```

This means:

```text
Horizontal → clipped
Vertical   → scroll when necessary
```

Another example:

```css
.box {
    overflow-x: auto;
    overflow-y: hidden;
}
```

This means:

```text
Horizontal → scroll when necessary
Vertical   → clipped
```

### Difference Between `overflow` and `overflow-y`

```css
overflow: auto;
```

controls both horizontal and vertical overflow.

While:

```css
overflow-y: auto;
```

controls only the vertical overflow behavior.

For example:

```css
.box {
    overflow-y: auto;
}
```

allows you to leave horizontal overflow behavior controlled separately.

### Practical Example

HTML:

```html
<div class="content">
    <p>Content 1</p>
    <p>Content 2</p>
    <p>Content 3</p>
    <p>Content 4</p>
    <p>Content 5</p>
    <p>Content 6</p>
</div>
```

CSS:

```css
.content {
    height: 200px;
    overflow-y: auto;
}
```

The container has a fixed height:

```text
200px
```

When the content exceeds that height, vertical scrolling becomes available.

### Important Points

```text
overflow-y
│
├── Controls vertical overflow
│
├── visible → overflow remains visible
├── hidden  → overflow is clipped
├── scroll  → scrolling mechanism is provided
├── auto    → scrolling when necessary
└── clip    → clips without scrolling
```

> 💡 **Remember:** Use `overflow-y` when you need to control content that becomes taller than its container. `auto` is particularly useful for scrollable lists, sidebars, modals, and fixed-height content areas.

---

## `overflow: visible`

`overflow: visible` is the default overflow behavior.

It allows content that extends beyond an element's box to remain visible.

### Syntax

```css
.box {
    overflow: visible;
}
```

Because `visible` is the default value, the following is generally equivalent when no other overflow behavior has been set:

```css
.box {
    overflow: visible;
}
```

### Basic Example

HTML:

```html
<div class="box">
    This content is larger than the available space.
</div>
```

CSS:

```css
.box {
    width: 200px;
    height: 100px;
    overflow: visible;
}
```

If the content does not fit inside the box, it can extend outside the element.

```text
┌──────────────────────┐
│ Content that fits    │
│ inside the box       │
└──────────────────────┘
        │
        │ Extra content
        │ remains visible
        ↓
        ───────────────────
```

### What `visible` Does

With:

```css
overflow: visible;
```

the browser does not clip overflowing content.

Conceptually:

```text
Content fits
    ↓
┌────────────────────┐
│      Content       │
└────────────────────┘

Content overflows
    ↓
┌────────────────────┐
│      Content       │
└────────────────────┘──────────────
             Extra content
             remains visible
```

### Horizontal Overflow

If content becomes wider than the element:

```css
.box {
    width: 200px;
    overflow-x: visible;
}
```

the extra horizontal content can remain visible outside the box.

```text
┌────────────────────┐
│ Content             │
└────────────────────┘───────────────
                  Extra content
```

### Vertical Overflow

If content becomes taller than the element:

```css
.box {
    height: 100px;
    overflow-y: visible;
}
```

the extra vertical content can remain visible outside the box.

```text
┌────────────────────┐
│ Content            │
│ Content            │
└────────────────────┘
│ More content       │
│ More content       │
```

### `visible` Does Not Create Scrolling

Unlike:

```css
overflow: auto;
```

or:

```css
overflow: scroll;
```

`visible` does not provide a scrolling mechanism for the overflowing content.

The content simply remains visible outside the element's box.

### `visible` vs `hidden`

Compare:

```css
overflow: visible;
```

with:

```css
overflow: hidden;
```

`visible`:

```text
┌──────────────┐
│ Content      │
└──────────────┘──────────
       Overflow remains visible
```

`hidden`:

```text
┌──────────────┐
│ Content      │
└──────────────┘
       Overflow is clipped
```

### `visible` vs `auto`

With:

```css
overflow: visible;
```

overflow remains visible.

With:

```css
overflow: auto;
```

the browser can provide scrolling when necessary.

```text
visible
→ Content remains visible outside the box

auto
→ Content can be scrolled when it overflows
```

### Overflowing Child Element

`visible` is useful when a child element intentionally extends outside its parent.

HTML:

```html
<div class="parent">
    <div class="child">
        Child
    </div>
</div>
```

CSS:

```css
.parent {
    width: 200px;
    height: 100px;
    overflow: visible;
}

.child {
    width: 300px;
}
```

The child can extend beyond the parent's width.

```text
Parent
┌────────────────────┐
│ Child              │
└────────────────────┘────────────
                 Child continues
                 outside parent
```

### Common Uses

`overflow: visible` can be appropriate when:

- Content should remain visible outside its container.
- A decorative element extends beyond its parent.
- A dropdown or popup needs to extend beyond a container.
- Clipping is not desired.
- Overflow is intentionally part of the design.

However, whether a dropdown or popup can escape an ancestor also depends on other layout and rendering conditions.

### Important Consideration

`visible` does not mean the content is removed from the layout.

The overflowing content still exists; it is simply allowed to be displayed outside the element's box.

### Important Points

```text
overflow: visible
│
├── Default overflow value
├── Overflow remains visible
├── Content can extend outside the box
├── Does not create scrolling
└── Does not clip overflowing content
```

> 💡 **Remember:** `overflow: visible` allows overflowing content to remain visible outside the element's box. It is the default overflow behavior and does not create a scrolling mechanism.

---

## `overflow: hidden`

`overflow: hidden` clips content that extends beyond an element's box.

The overflowing content is not visible outside the element's boundaries.

### Syntax

```css
.box {
    overflow: hidden;
}
```

### Basic Example

```css
.box {
    width: 200px;
    height: 100px;
    overflow: hidden;
}
```

If the content is larger than the available space, the extra content is clipped.

```text
┌──────────────────────┐
│ Content that fits    │
│ inside the box       │
│                      │
└──────────────────────┘
      Extra content
        is hidden
```

### How It Works

Consider a box with limited dimensions:

```css
.box {
    width: 200px;
    height: 100px;
}
```

If its content requires more space:

```text
Required space
┌───────────────────────────────┐
│                               │
│          Content              │
│                               │
│                               │
│                               │
└───────────────────────────────┘
```

but the container only provides:

```text
┌──────────────────────┐
│ Available area       │
│                      │
│                      │
└──────────────────────┘
```

then:

```css
overflow: hidden;
```

clips the portion outside the available area.

### Horizontal Overflow

You can control horizontal clipping specifically:

```css
.box {
    overflow-x: hidden;
}
```

Content extending beyond the left or right boundary is clipped.

```text
┌──────────────────────┐
│ Visible content      │
└──────────────────────┘
        ↑
   Extra horizontal
   content clipped
```

### Vertical Overflow

You can control vertical clipping specifically:

```css
.box {
    overflow-y: hidden;
}
```

Content extending beyond the top or bottom boundary is clipped.

```text
┌──────────────────────┐
│ Visible content      │
│ Visible content      │
└──────────────────────┘
       ↓
   Extra content
     clipped
```

### `hidden` Does Not Mean `display: none`

This is an important distinction.

```css
overflow: hidden;
```

does **not** remove the content from the document.

The content still exists, but the overflowing portion is clipped.

Compare:

```css
display: none;
```

with:

```css
overflow: hidden;
```

```text
display: none
→ Element/content is not displayed

overflow: hidden
→ Element remains
→ Overflowing portion is clipped
```

### `hidden` Does Not Create Normal Scrolling

Unlike:

```css
overflow: auto;
```

`hidden` does not provide a normal scrolling mechanism for the clipped overflow.

```text
hidden
→ Clip overflow

auto
→ Allow scrolling when needed
```

### Clipping an Image

A common use is clipping a large image inside a fixed-size container.

HTML:

```html
<div class="image-box">
    <img src="image.jpg" alt="Example image">
</div>
```

CSS:

```css
.image-box {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-box img {
    width: 500px;
}
```

The image can extend beyond the container, but the container clips the excess.

```text
┌──────────────────────────────┐
│                              │
│       Visible image          │
│                              │
└──────────────────────────────┘
        Extra image clipped
```

### Clipping With `border-radius`

A very common UI pattern is:

```css
.card {
    border-radius: 16px;
    overflow: hidden;
}
```

This can prevent child content such as an image from visually extending outside the rounded corners.

```text
     ╭────────────────────╮
     │      Image         │
     │                    │
     │      Content       │
     ╰────────────────────╯
```

### Preventing Positioned Content From Escaping

`overflow: hidden` is often used with positioned or transformed children.

```css
.container {
    position: relative;
    overflow: hidden;
}

.child {
    position: absolute;
    right: -50px;
}
```

The portion of the child extending outside the container can be clipped.

### Clipping Transformed Elements

For example:

```css
.container {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.element {
    transform: scale(1.5);
}
```

The transformed element may become larger than the container, but the overflowing portion is clipped.

This is commonly useful for image zoom effects.

### Image Hover Effect

HTML:

```html
<div class="image-box">
    <img src="image.jpg" alt="Example">
</div>
```

CSS:

```css
.image-box {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-box img {
    width: 100%;
    transition: transform 0.3s;
}

.image-box:hover img {
    transform: scale(1.1);
}
```

The image grows when hovered, but `overflow: hidden` keeps it visually inside the container.

### Text Clipping

`overflow: hidden` can clip text that exceeds a fixed area.

```css
.text {
    width: 200px;
    height: 50px;
    overflow: hidden;
}
```

However, if the goal is to display an ellipsis for a single line of text, a typical pattern also uses:

```css
white-space: nowrap;
text-overflow: ellipsis;
```

### `overflow: hidden` vs `overflow: clip`

Both can clip overflowing content, but they are not identical.

```css
overflow: hidden;
```

provides clipping and can establish a scroll container in ways that `clip` does not.

```css
overflow: clip;
```

is specifically intended for clipping without providing scrolling.

Use `clip` when you specifically want clipping without scrolling behavior.

### `overflow: hidden` vs `overflow: auto`

```text
hidden
→ Overflow is clipped

auto
→ Overflow can be scrolled when necessary
```

Example:

```css
.hidden {
    overflow: hidden;
}

.scrollable {
    overflow: auto;
}
```

### Common Uses

`overflow: hidden` is commonly used for:

```text
Image containers
Rounded cards
Hover effects
Zoom effects
Clipping decorative elements
Preventing visual overflow
Fixed-size components
```

### Important Points

```text
overflow: hidden
│
├── Clips overflowing content
├── Content outside the box is not visible
├── Does not remove the element
├── Does not behave like display: none
├── Useful for image and hover effects
├── Common with border-radius
└── Can be applied independently with
    ├── overflow-x: hidden
    └── overflow-y: hidden
```

> 💡 **Remember:** `overflow: hidden` keeps the element in the layout but clips content that extends beyond its box. It is especially useful for image containers, rounded cards, transforms, and visual effects where overflow should not be visible.

---

## `overflow: scroll`

The `overflow: scroll` value provides a scrolling mechanism for content that overflows an element's box.

Unlike `auto`, which provides scrolling when necessary, `scroll` explicitly requests scrolling mechanisms for the element.

### Syntax

```css
.box {
    overflow: scroll;
}
```

### Basic Example

```css
.box {
    width: 200px;
    height: 100px;
    overflow: scroll;
}
```

If the content is larger than the available space, the user can scroll through the overflowing content.

```text
┌──────────────────────┐
│ Content              │
│ Content              │
│ Content              │
│                  █   │
├──────────────────────┤
│◄──────────────────►  │
└──────────────────────┘
```

The exact appearance of scrollbars depends on the browser and operating system.

### Horizontal and Vertical Scrolling

Because:

```css
overflow: scroll;
```

controls both axes, the element can provide scrolling in both directions when required.

```text
Horizontal
←────────────────────→

Vertical
      ↓
      ↓
      ↓
```

For example:

```css
.box {
    width: 300px;
    height: 150px;
    overflow: scroll;
}
```

### `overflow-x: scroll`

You can request horizontal scrolling specifically:

```css
.box {
    overflow-x: scroll;
}
```

This is useful for content that may be wider than its container.

Example:

```css
.table-container {
    overflow-x: scroll;
}
```

### `overflow-y: scroll`

You can request vertical scrolling specifically:

```css
.box {
    overflow-y: scroll;
}
```

This is useful for fixed-height containers containing potentially long content.

Example:

```css
.list {
    height: 300px;
    overflow-y: scroll;
}
```

### `scroll` vs `auto`

The important difference is:

```text
scroll
→ Provides scrolling mechanisms regardless of whether
  content currently overflows

auto
→ Provides scrolling mechanisms when the browser
  determines they are needed
```

Example:

```css
.box {
    overflow: scroll;
}
```

versus:

```css
.box {
    overflow: auto;
}
```

With `auto`, a small amount of content may require no scrolling mechanism.

With `scroll`, the browser is instructed to provide a scrolling mechanism.

The exact visual presence of scrollbars can still depend on browser and operating-system scrollbar behavior.

### `scroll` vs `hidden`

Compare:

```css
overflow: scroll;
```

with:

```css
overflow: hidden;
```

```text
scroll
→ Overflow can be accessed by scrolling

hidden
→ Overflow is clipped
```

For example:

```css
.scrollable {
    overflow: scroll;
}

.clipped {
    overflow: hidden;
}
```

### `scroll` vs `visible`

```css
overflow: visible;
```

allows overflow to remain visible outside the box.

```css
overflow: scroll;
```

provides scrolling for the overflow.

```text
visible
┌──────────────┐
│ Content      │
└──────────────┘──────────
     overflow visible

scroll
┌──────────────┐
│ Content      │
│ Content      │
└──────────────┘
     scrollable
```

### Scrollable Code Block

A code block may be wider than the available container.

```css
.code {
    overflow-x: scroll;
}
```

Example:

```html
<pre class="code">
const veryLongVariableName = someVeryLongFunctionName();
</pre>
```

The code remains on one line while the user can scroll horizontally.

### Scrollable List

A fixed-height list can use vertical scrolling:

```css
.list {
    height: 250px;
    overflow-y: scroll;
}
```

HTML:

```html
<div class="list">
    <p>Item 1</p>
    <p>Item 2</p>
    <p>Item 3</p>
    <p>Item 4</p>
    <p>Item 5</p>
    <p>Item 6</p>
</div>
```

The list remains within its defined height while additional content can be accessed through scrolling.

### Scrollable Table

A table can be placed inside a horizontally scrollable container:

```css
.table-container {
    overflow-x: scroll;
}
```

This can be useful when a table has many columns.

```text
┌──────────────────────────┐
│ Column 1 | Column 2 | ...│
├──────────────────────────┤
│ Data     | Data     | ...│
└──────────────────────────┘
       ←──── scroll ────→
```

### When to Use `scroll`

Use `scroll` when you explicitly want a scrolling mechanism for a container.

Common situations include:

```text
Scrollable code blocks
Wide tables
Fixed-size panels
Long lists
Scrollable data areas
```

However, if scrolling should only appear when content actually overflows, `auto` is often more appropriate.

### Important Points

```text
overflow: scroll
│
├── Provides a scrolling mechanism
├── Controls horizontal and vertical overflow
├── overflow-x: scroll → horizontal scrolling
├── overflow-y: scroll → vertical scrolling
├── Unlike hidden → overflow can be accessed
└── Unlike auto → scrolling is explicitly requested
```

> 💡 **Remember:** `overflow: scroll` provides a scrolling mechanism for an element's overflow. Use `auto` when you want scrolling only when necessary, and use `scroll` when you explicitly want a scrolling mechanism.

---

## `overflow: auto`

The `overflow: auto` value allows the browser to provide scrolling when the content overflows an element's available space.

It is one of the most commonly used overflow values because it avoids unnecessary scrolling when the content already fits.

### Syntax

```css
.box {
    overflow: auto;
}
```

### Basic Example

```css
.box {
    width: 200px;
    height: 100px;
    overflow: auto;
}
```

If the content fits:

```text
┌──────────────────────┐
│ Content fits here    │
│ No scrolling needed  │
└──────────────────────┘
```

If the content is larger:

```text
┌──────────────────────┐
│ Content              │
│ Content              │
│ Content           █  │
│ Content           █  │
└──────────────────────┘
        scrolling
```

The browser can provide the appropriate scrolling mechanism when needed.

### `auto` With Horizontal Overflow

Use:

```css
overflow-x: auto;
```

when content may become wider than the container.

```css
.table-container {
    overflow-x: auto;
}
```

This is commonly used for wide tables.

```text
┌──────────────────────────┐
│ Column 1 | Column 2 |... │
└──────────────────────────┘
       ←── scroll ──→
```

### `auto` With Vertical Overflow

Use:

```css
overflow-y: auto;
```

when content may become taller than the container.

```css
.list {
    height: 300px;
    overflow-y: auto;
}
```

This is useful for:

- Lists
- Sidebars
- Chat panels
- Modal content
- Fixed-height sections

### `auto` vs `scroll`

The main difference is:

```text
auto
→ Scrolling is provided when necessary

scroll
→ A scrolling mechanism is explicitly requested
```

Example:

```css
.auto {
    overflow: auto;
}

.scroll {
    overflow: scroll;
}
```

With `auto`, a container whose content fits does not need scrolling.

With `scroll`, scrolling mechanisms are explicitly requested, although the exact visual appearance of scrollbars depends on the browser and operating system.

### `auto` vs `hidden`

Compare:

```css
overflow: auto;
```

with:

```css
overflow: hidden;
```

```text
auto
→ Overflow can be accessed through scrolling

hidden
→ Overflow is clipped
```

Use `auto` when users should be able to access content that does not fit.

Use `hidden` when the overflowing content should simply not be visible.

### `auto` vs `visible`

```css
overflow: visible;
```

allows overflowing content to remain visible outside the element.

```css
overflow: auto;
```

keeps the content within a scrollable area when scrolling is needed.

```text
visible
┌──────────────┐
│ Content      │
└──────────────┘────────────
       overflow visible

auto
┌──────────────┐
│ Content      │
│ Content   █  │
└──────────────┘
       scroll when needed
```

### Scrollable Table

A common real-world use is a responsive table.

HTML:

```html
<div class="table-container">
    <table>
        <tr>
            <th>Name</th>
            <th>Email</th>
            <th>Department</th>
            <th>Location</th>
        </tr>
        <tr>
            <td>Mohit</td>
            <td>example@email.com</td>
            <td>Computer Science</td>
            <td>Delhi</td>
        </tr>
    </table>
</div>
```

CSS:

```css
.table-container {
    overflow-x: auto;
}
```

If the table becomes wider than the container, the user can scroll horizontally.

### Scrollable Code Block

Code often contains long lines that should not wrap.

```css
.code {
    overflow-x: auto;
}
```

HTML:

```html
<pre class="code">
const result = someVeryLongFunctionName(firstArgument, secondArgument);
</pre>
```

The container can remain within the available width while allowing horizontal scrolling.

### Scrollable List

```css
.list {
    height: 250px;
    overflow-y: auto;
}
```

If the list becomes longer than `250px`, the user can scroll through the additional items.

### Scrollable Modal Content

```css
.modal {
    max-height: 80vh;
    overflow-y: auto;
}
```

This allows a modal to remain within the viewport while still allowing long content to be accessed.

### Combining Horizontal and Vertical Behavior

You can control the two axes independently:

```css
.box {
    overflow-x: auto;
    overflow-y: auto;
}
```

Both directions can become scrollable when necessary.

You can also mix behaviors:

```css
.box {
    overflow-x: auto;
    overflow-y: hidden;
}
```

Here:

```text
Horizontal → scroll when necessary
Vertical   → clipped
```

### `auto` With Fixed Dimensions

`auto` is especially useful when the content size is unpredictable.

```css
.panel {
    width: 300px;
    height: 200px;
    overflow: auto;
}
```

The panel remains within its specified dimensions while overflow can be accessed through scrolling.

### `auto` in CSS Grid

A Grid layout may contain content that needs its own scrolling area.

For example:

```css
.layout {
    display: grid;
    grid-template-columns:
        240px minmax(0, 1fr);
}

.main {
    overflow: auto;
}
```

The main content area can then become scrollable when its content exceeds the available space.

### Common Uses

```text
overflow: auto
│
├── Responsive tables
├── Code blocks
├── Long lists
├── Sidebars
├── Chat panels
├── Modal content
├── Fixed-height containers
└── Scrollable Grid sections
```

### Important Points

```text
overflow: auto
│
├── Allows scrolling when necessary
├── Avoids unnecessary scrolling when content fits
├── overflow-x: auto → horizontal scrolling
├── overflow-y: auto → vertical scrolling
└── Useful for unpredictable content sizes
```

> 💡 **Remember:** `overflow: auto` is useful when you want content to remain accessible without forcing a scrollbar when it is not needed. It is especially common for responsive tables, long lists, code blocks, modals, and scrollable content areas.

---

## `overflow: clip`

`overflow: clip` clips content that extends beyond an element's overflow clip edge.

Unlike `overflow: hidden`, `clip` does not provide a scrolling mechanism for the clipped content.

### Syntax

```css
.box {
    overflow: clip;
}
```

### Basic Example

```css
.box {
    width: 200px;
    height: 100px;
    overflow: clip;
}
```

If the content is larger than the available space, the overflowing portion is clipped.

```text
┌──────────────────────┐
│ Content that fits    │
│ inside the box       │
│                      │
└──────────────────────┘
      Extra content
         clipped
```

### `clip` vs `hidden`

Both can prevent overflowing content from being visible:

```css
overflow: hidden;
```

and:

```css
overflow: clip;
```

However, they are not identical.

```text
hidden
→ Clips overflow
→ Can establish a scroll container

clip
→ Clips overflow
→ Does not provide scrolling
```

When you specifically want clipping without scrolling behavior, `clip` expresses that intention clearly.

### `overflow-x: clip`

You can clip horizontal overflow:

```css
.box {
    overflow-x: clip;
}
```

Content extending beyond the horizontal boundaries is clipped.

### `overflow-y: clip`

You can clip vertical overflow:

```css
.box {
    overflow-y: clip;
}
```

Content extending beyond the vertical boundaries is clipped.

### `clip` Does Not Create Scrolling

For example:

```css
.box {
    overflow: clip;
}
```

does not provide a normal scrolling mechanism for accessing the clipped content.

Compare:

```css
.clip {
    overflow: clip;
}

.scroll {
    overflow: auto;
}
```

```text
clip
→ Content outside the clipping area is inaccessible through scrolling

auto
→ Content can be accessed by scrolling when necessary
```

### Clipping an Image

A common use is preventing a large image from extending outside its container.

```css
.image-box {
    width: 300px;
    height: 200px;
    overflow: clip;
}

.image-box img {
    width: 500px;
}
```

The image can be larger than the container, but the excess is clipped.

```text
┌────────────────────────────┐
│                            │
│       Visible image        │
│                            │
└────────────────────────────┘
       Extra image
          clipped
```

### Clipping a Transformed Element

```css
.container {
    width: 300px;
    height: 200px;
    overflow: clip;
}

.image {
    transform: scale(1.2);
}
```

The transformed element can extend beyond the container, but the overflowing portion is clipped.

### `clip` and `border-radius`

A component can combine clipping with rounded corners:

```css
.card {
    border-radius: 16px;
    overflow: clip;
}
```

This can keep child content visually contained within the card's clipping boundary.

### `clip` vs `visible`

Compare:

```css
overflow: visible;
```

with:

```css
overflow: clip;
```

```text
visible
→ Overflow remains visible

clip
→ Overflow is clipped
```

### `clip` vs `scroll`

Compare:

```css
overflow: clip;
```

with:

```css
overflow: scroll;
```

```text
clip
→ Overflow is clipped

scroll
→ Overflow can be accessed through scrolling
```

### When to Use `clip`

Use `overflow: clip` when:

- Overflow should not be visible.
- The content should not be scrollable.
- You specifically want clipping behavior.
- A container needs to clip visual effects.
- A child element should remain visually contained.

### When to Use `hidden` Instead

Use:

```css
overflow: hidden;
```

when you need clipping but may also need the element's scroll-container behavior.

Use:

```css
overflow: clip;
```

when you explicitly want clipping without scrolling.

### Important Points

```text
overflow: clip
│
├── Clips overflowing content
├── Does not provide scrolling
├── Can be applied to both axes
├── overflow-x: clip → horizontal clipping
├── overflow-y: clip → vertical clipping
└── Useful for intentional clipping
```

> 💡 **Remember:** `overflow: clip` is specifically for clipping overflow without providing scrolling. It is similar to `hidden` visually, but its behavior and scrolling implications are different.

---

## Two-Value Overflow

The `overflow` shorthand can accept **one or two values**.

Using two values allows you to control horizontal and vertical overflow independently.

### Syntax

```css
overflow: horizontal vertical;
```

The values correspond to:

```text
First value
    ↓
Horizontal overflow
(overflow-x)

Second value
    ↓
Vertical overflow
(overflow-y)
```

### Basic Example

```css
.box {
    overflow: hidden auto;
}
```

This means:

```text
Horizontal → hidden
Vertical   → auto
```

Conceptually:

```text
Horizontal
→ clipped

Vertical
→ scroll when necessary
```

### One Value vs Two Values

With one value:

```css
overflow: hidden;
```

the same behavior is applied to both axes.

Conceptually:

```css
overflow-x: hidden;
overflow-y: hidden;
```

With two values:

```css
overflow: hidden auto;
```

different behavior can be specified for each axis.

Conceptually:

```css
overflow-x: hidden;
overflow-y: auto;
```

### Example: Horizontal Hidden, Vertical Scroll

```css
.box {
    width: 300px;
    height: 200px;
    overflow: hidden auto;
}
```

This means:

```text
Horizontal → hidden
Vertical   → auto
```

If content becomes too wide:

```text
Horizontal overflow
→ clipped
```

If content becomes too tall:

```text
Vertical overflow
→ scrolling when necessary
```

### Example: Horizontal Scroll, Vertical Hidden

```css
.box {
    overflow: auto hidden;
}
```

This means:

```text
Horizontal → auto
Vertical   → hidden
```

Useful for content that should scroll horizontally but should not extend vertically.

### Example: Both Axes Hidden

```css
.box {
    overflow: hidden hidden;
}
```

This explicitly sets:

```css
overflow-x: hidden;
overflow-y: hidden;
```

Usually, however, the shorter form is preferred:

```css
overflow: hidden;
```

### Example: Both Axes Auto

```css
.box {
    overflow: auto auto;
}
```

This explicitly sets:

```css
overflow-x: auto;
overflow-y: auto;
```

The simpler form is usually:

```css
overflow: auto;
```

### Example: Horizontal Scroll, Vertical Auto

```css
.box {
    overflow: scroll auto;
}
```

This means:

```text
Horizontal → scroll
Vertical   → auto
```

### Example: Horizontal Auto, Vertical Scroll

```css
.box {
    overflow: auto scroll;
}
```

This means:

```text
Horizontal → auto
Vertical   → scroll
```

### Two-Value Syntax Reference

```text
overflow: A B;

A → overflow-x
B → overflow-y
```

Examples:

```css
overflow: hidden auto;
```

means:

```text
x → hidden
y → auto
```

```css
overflow: auto hidden;
```

means:

```text
x → auto
y → hidden
```

```css
overflow: scroll auto;
```

means:

```text
x → scroll
y → auto
```

```css
overflow: auto scroll;
```

means:

```text
x → auto
y → scroll
```

### Two-Value Overflow With a Table

A responsive table commonly needs horizontal scrolling but does not need a special vertical scrolling area.

```css
.table-container {
    overflow: auto hidden;
}
```

Here:

```text
Horizontal → auto
Vertical   → hidden
```

For a table specifically, a more common choice is simply:

```css
.table-container {
    overflow-x: auto;
}
```

because it leaves the vertical behavior independent.

### Two-Value Overflow With a Panel

Suppose a panel should:

```text
Clip horizontal overflow
Allow vertical scrolling
```

Use:

```css
.panel {
    width: 300px;
    height: 400px;
    overflow: hidden auto;
}
```

This is equivalent in intent to:

```css
.panel {
    overflow-x: hidden;
    overflow-y: auto;
}
```

### Two-Value Overflow With a Code Area

Suppose a code area should allow horizontal scrolling while vertical overflow is clipped:

```css
.code {
    overflow: auto hidden;
}
```

This means:

```text
Horizontal → auto
Vertical   → hidden
```

For a normal code block, however, the more explicit approach is often:

```css
.code {
    overflow-x: auto;
}
```

### Important Rule

Remember the order:

```css
overflow: X Y;
```

where:

```text
X → horizontal
Y → vertical
```

Do not confuse the order.

For example:

```css
overflow: hidden auto;
```

does **not** mean:

```text
Vertical → hidden
Horizontal → auto
```

It means:

```text
Horizontal → hidden
Vertical   → auto
```

### `overflow` and Its Longhand Properties

The shorthand:

```css
overflow: hidden auto;
```

corresponds to:

```css
overflow-x: hidden;
overflow-y: auto;
```

This makes it easier to understand what the shorthand is doing.

### Important Points

```text
Two-value overflow
│
├── Syntax
│   └── overflow: X Y;
│
├── X → overflow-x
│   └── Horizontal
│
└── Y → overflow-y
    └── Vertical
```

> 💡 **Remember:** With two `overflow` values, the **first controls horizontal overflow** and the **second controls vertical overflow**. For example, `overflow: hidden auto` means horizontal overflow is hidden while vertical overflow can scroll when necessary.

---

## `text-overflow`

The `text-overflow` property controls how text that overflows its containing element is represented.

It is commonly used to show an ellipsis (`...`) when text is clipped because it does not fit within the available space.

### Syntax

```css
.text {
    text-overflow: value;
}
```

Common values are:

```css
clip
ellipsis
```

### `text-overflow: clip`

`clip` is the default behavior.

```css
.text {
    text-overflow: clip;
}
```

The overflowing text is simply clipped at the content area.

```text
This is a very long tex
```

The remaining text is not represented by an ellipsis.

### `text-overflow: ellipsis`

```css
.text {
    text-overflow: ellipsis;
}
```

When the text is clipped, the browser can represent the hidden portion with an ellipsis.

```text
This is a very long...
```

### Important: `text-overflow` Alone Is Usually Not Enough

A common mistake is to write:

```css
.text {
    text-overflow: ellipsis;
}
```

and expect the text to automatically display an ellipsis.

Typically, the element also needs:

```css
overflow: hidden;
white-space: nowrap;
```

A common single-line pattern is:

```css
.text {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### How the Ellipsis Pattern Works

The three properties have different responsibilities:

```text
white-space: nowrap
        ↓
Keeps the text on one line

overflow: hidden
        ↓
Clips content that does not fit

text-overflow: ellipsis
        ↓
Represents clipped text with "..."
```

### Complete Example

HTML:

```html
<p class="title">
    This is a very long title that does not fit in the container.
</p>
```

CSS:

```css
.title {
    width: 250px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

Result:

```text
This is a very long title tha...
```

### Why `white-space: nowrap` Is Used

Without:

```css
white-space: nowrap;
```

the text may wrap onto multiple lines instead of overflowing horizontally.

```text
Without nowrap:

This is a very long
title that wraps
to another line.
```

With:

```css
white-space: nowrap;
```

the text stays on one line:

```text
This is a very long title that...
```

### Why `overflow: hidden` Is Used

The overflow needs to be clipped for the ellipsis behavior to become visible.

```css
overflow: hidden;
```

prevents the extra text from simply extending outside the element.

### Fixed or Constrained Width

The text needs a constrained available width for this common pattern to have an overflow to handle.

For example:

```css
.title {
    width: 250px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

A responsive element can also use a maximum or otherwise constrained width depending on the layout:

```css
.title {
    max-width: 250px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### `text-overflow` With a Long Title

This pattern is common for:

```text
Card titles
Navigation items
Product names
File names
User names
Table cells
```

Example:

```css
.card-title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### `text-overflow` in a Table

A table cell may contain more text than the available column width.

Example:

```css
td {
    max-width: 200px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

The visible text can then be shortened with an ellipsis when it overflows.

### `text-overflow` and `overflow: auto`

Be careful when combining the two.

```css
.text {
    overflow: auto;
    text-overflow: ellipsis;
}
```

This does not represent the standard single-line ellipsis pattern.

For a typical single-line ellipsis effect, use:

```css
.text {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### `clip` vs `ellipsis`

```css
text-overflow: clip;
```

means:

```text
Overflowing text
        ↓
Simply clipped
```

While:

```css
text-overflow: ellipsis;
```

means:

```text
Overflowing text
        ↓
Represented with an ellipsis
```

Conceptually:

```text
clip:
This is a very long tex

ellipsis:
This is a very long...
```

### Important Points

```text
text-overflow
│
├── Controls the representation of overflowing text
│
├── clip
│   └── Clips the text
│
└── ellipsis
    └── Represents clipped text with "..."
```

Common single-line pattern:

```css
.text {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

> 💡 **Remember:** `text-overflow` controls how overflowing text is represented. For the common single-line ellipsis effect, combine `text-overflow: ellipsis` with `overflow: hidden` and `white-space: nowrap`.

---

## Overflow With Text

Text can overflow when it is larger than the available space of its container.

This commonly happens with:

- Long sentences
- Long words
- URLs
- File names
- Code
- Non-wrapping text
- Fixed-width containers

### Basic Example

```css
.text {
    width: 200px;
}
```

If the text is longer than the available width, it may extend beyond the container.

```text
┌────────────────────┐
│ This is some long  │
│ text that may      │
└────────────────────┘
       ↓
   Extra text
   may overflow
```

### Controlling Text Overflow

The `overflow` property can control what happens to overflowing text.

```css
.text {
    width: 200px;
    overflow: hidden;
}
```

The overflowing portion is clipped.

```text
┌────────────────────┐
│ This is some long  │
│ text that may      │
└────────────────────┘
```

### Horizontal Scrolling Text

If the text should remain accessible, use horizontal scrolling:

```css
.text {
    width: 200px;
    white-space: nowrap;
    overflow-x: auto;
}
```

The text remains on one line and can be scrolled horizontally when it is wider than the container.

```text
┌────────────────────┐
│ This is some long →│
└────────────────────┘
       scroll →
```

### Preventing Text From Wrapping

The `white-space` property controls how whitespace and line wrapping are handled.

For example:

```css
.text {
    white-space: nowrap;
}
```

This keeps the text on a single line.

Without `nowrap`, normal text can wrap:

```text
This is some long
text that wraps
onto another line.
```

With `nowrap`:

```text
This is some long text that stays on one line...
```

### Single-Line Ellipsis

A common UI pattern is to replace clipped text with an ellipsis.

```css
.text {
    width: 200px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

Result:

```text
This is some very...
```

The three properties work together:

```text
white-space: nowrap
        ↓
Keep text on one line

overflow: hidden
        ↓
Clip overflowing text

text-overflow: ellipsis
        ↓
Show "..."
```

### Long Words

A single extremely long word can overflow even when normal text wrapping is enabled.

For example:

```text
ThisIsAnExtremelyLongWordThatMayNotFit
```

Depending on the available width and CSS settings, such content may extend beyond its container.

When necessary, consider text wrapping and breaking properties such as:

```css
overflow-wrap
word-break
```

For example:

```css
.text {
    overflow-wrap: break-word;
}
```

This can allow an otherwise unbreakable string to wrap when needed.

### `overflow-wrap`

`overflow-wrap` controls whether the browser should break an otherwise unbreakable string when it would overflow its container.

Example:

```css
.text {
    overflow-wrap: break-word;
}
```

This can be useful for:

```text
Long URLs
Long identifiers
Long file names
Other unbroken strings
```

### `word-break`

`word-break` controls how words should break when text reaches the edge of its container.

Example:

```css
.text {
    word-break: break-all;
}
```

This can allow breaks between individual characters.

Use this carefully because it can make normal text harder to read.

### `overflow-wrap` vs `word-break`

A useful distinction is:

```text
overflow-wrap
→ Helps prevent long unbreakable strings
  from overflowing

word-break
→ Controls where words can break
```

For normal text, prefer natural wrapping where possible.

### Long URLs

URLs can be difficult to wrap because they may contain long sequences without spaces.

Example:

```text
https://example.com/a/very/long/path/without/breaks
```

A container can use:

```css
.url {
    overflow-wrap: break-word;
}
```

to help prevent the URL from creating unwanted horizontal overflow.

### Code and Text Overflow

Code often contains long lines.

For a horizontally scrollable code block:

```css
.code {
    overflow-x: auto;
    white-space: pre;
}
```

This keeps the formatting of the code while allowing horizontal scrolling.

Example:

```text
┌──────────────────────────────┐
│ const veryLongFunctionName( →│
└──────────────────────────────┘
             scroll →
```

### Multi-Line Text

`text-overflow: ellipsis` is commonly associated with single-line text.

For multiple lines, truncation requires additional techniques and should not be confused with the simple single-line pattern.

The standard basic pattern remains:

```css
.text {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### Text Inside Grid or Flex Layouts

Text can also overflow when it is inside Grid or Flex layouts.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px minmax(0, 1fr);
}
```

Using:

```css
minmax(0, 1fr)
```

for the flexible Grid track can help the track shrink appropriately.

For a Flexbox item, a common technique is:

```css
.item {
    min-width: 0;
}
```

The exact solution depends on the layout and the type of content causing the overflow.

### Practical Example

HTML:

```html
<div class="card">
    <h2 class="title">
        This is a very long title that needs to fit inside the card.
    </h2>
</div>
```

CSS:

```css
.card {
    width: 250px;
}

.title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

Result:

```text
┌──────────────────────────┐
│ This is a very long...   │
└──────────────────────────┘
```

### Important Points

```text
Text Overflow
│
├── overflow
│   ├── visible
│   ├── hidden
│   ├── auto
│   ├── scroll
│   └── clip
│
├── white-space
│   └── Controls wrapping
│
├── text-overflow
│   ├── clip
│   └── ellipsis
│
├── overflow-wrap
│   └── Helps break long strings
│
└── word-break
    └── Controls word-breaking behavior
```

> 💡 **Remember:** Text overflow can be handled by allowing text to wrap, clipping it, scrolling it, or displaying an ellipsis. For the common single-line ellipsis pattern, use `white-space: nowrap`, `overflow: hidden`, and `text-overflow: ellipsis` together.

---

## Overflow With Images

Images can cause overflow when their dimensions are larger than the available space of their container.

This commonly happens when:

- An image has a fixed width larger than its parent.
- An image has a fixed height larger than its parent.
- An image is transformed using `scale()`.
- An image is positioned outside its container.
- The image does not adapt to the container size.

### Basic Example

HTML:

```html
<div class="image-box">
    <img src="image.jpg" alt="Example image">
</div>
```

CSS:

```css
.image-box {
    width: 300px;
}

.image-box img {
    width: 500px;
}
```

The image is wider than the container:

```text
Container
┌──────────────────────────────┐
│                              │
│        Image                 │
│                              │
└──────────────────────────────┘
────────────────────────────────────
       Image extends outside
       the container
```

This creates horizontal overflow.

### Using `overflow: hidden`

If the image should remain visually inside the container:

```css
.image-box {
    width: 300px;
    height: 200px;
    overflow: hidden;
}
```

The part of the image outside the container is clipped.

```text
┌──────────────────────────────┐
│                              │
│       Visible image          │
│                              │
└──────────────────────────────┘
        Extra image
           clipped
```

### Responsive Images

A common way to prevent an image from overflowing its container is:

```css
img {
    max-width: 100%;
    height: auto;
}
```

This allows the image to shrink when the container becomes narrower.

```text
Large screen

┌───────────────────────────────┐
│           Image               │
└───────────────────────────────┘

Small screen

┌───────────────────┐
│      Image        │
└───────────────────┘
```

### Why `max-width: 100%` Helps

Consider:

```css
img {
    max-width: 100%;
}
```

The image cannot become wider than its containing block's available width under normal sizing conditions.

This helps prevent unwanted horizontal overflow.

### `width: 100%` vs `max-width: 100%`

These declarations have different intentions.

```css
img {
    width: 100%;
}
```

makes the image's width equal to the available width.

While:

```css
img {
    max-width: 100%;
}
```

prevents the image from becoming wider than the available width while allowing a smaller intrinsic image to remain smaller.

A common responsive image pattern is:

```css
img {
    max-width: 100%;
    height: auto;
}
```

### Image With `overflow: auto`

An image can also intentionally be placed inside a scrollable container.

```css
.image-container {
    width: 300px;
    overflow-x: auto;
}

.image-container img {
    width: 600px;
}
```

The container remains `300px` wide while the larger image can be accessed through horizontal scrolling.

```text
┌──────────────────────┐
│      Large image →   │
└──────────────────────┘
       scroll →
```

This can be useful for diagrams, maps, screenshots, or other images that need to remain at a larger size.

### Image With `object-fit`

When an image must fit inside a fixed-size box, `object-fit` can often be more appropriate than simply allowing it to overflow.

Example:

```css
.image-box {
    width: 300px;
    height: 200px;
}

.image-box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

The image fills the container while maintaining its aspect ratio, with some portions potentially cropped.

### Image Zoom Effect

`overflow: hidden` is commonly used with transformed images.

HTML:

```html
<div class="image-box">
    <img src="image.jpg" alt="Example image">
</div>
```

CSS:

```css
.image-box {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-box img {
    width: 100%;
    transition: transform 0.3s;
}

.image-box:hover img {
    transform: scale(1.1);
}
```

When the image is scaled:

```text
Normal

┌──────────────────────────┐
│        Image             │
└──────────────────────────┘

Scaled

┌──────────────────────────┐
│      Enlarged image      │
│      cropped at edges    │
└──────────────────────────┘
```

The container clips the enlarged image.

### Image With `overflow: clip`

The same visual clipping idea can use:

```css
.image-box {
    overflow: clip;
}
```

This clips the image without providing scrolling.

### Image Positioned Outside the Container

A positioned image can also extend outside its parent.

```css
.image-box {
    position: relative;
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image {
    position: absolute;
    right: -50px;
}
```

The portion outside the container is clipped.

### Image Overflow and Border Radius

A common card pattern is:

```css
.card {
    border-radius: 16px;
    overflow: hidden;
}
```

For example:

```html
<div class="card">
    <img src="image.jpg" alt="Example">
</div>
```

The image is clipped to the card's visible shape.

```text
      ╭────────────────────╮
      │                    │
      │       Image        │
      │                    │
      ╰────────────────────╯
```

### Image Overflow in Responsive Layouts

Images should generally adapt to their available space.

A useful baseline is:

```css
img {
    max-width: 100%;
    height: auto;
}
```

For a fixed display area, you can use:

```css
.image-box {
    overflow: hidden;
}

.image-box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

The correct approach depends on whether the image should:

```text
Shrink
Crop
Scroll
Clip
```

### Choosing the Right Approach

```text
Image should shrink
        ↓
max-width: 100%

Image should fill a fixed box
        ↓
object-fit

Image should be cropped
        ↓
overflow: hidden / clip
+
appropriate image sizing

Image should remain large
        ↓
overflow-x: auto

Image should extend outside intentionally
        ↓
overflow: visible
```

### Important Points

```text
Image Overflow
│
├── max-width: 100%
│   └── Helps prevent unwanted horizontal overflow
│
├── overflow: hidden
│   └── Clips overflowing images
│
├── overflow: clip
│   └── Clips without scrolling
│
├── overflow-x: auto
│   └── Allows horizontal scrolling
│
└── object-fit
    └── Controls how an image fits its box
```

> 💡 **Remember:** Image overflow can be handled by making images responsive, clipping them, allowing scrolling, or controlling how they fit inside a container. Use `max-width: 100%` for responsive images and `overflow: hidden` or `clip` when intentional visual clipping is required.

---

## Overflow With Border Radius

`overflow` and `border-radius` are commonly used together when content, especially images, should remain inside a rounded container.

### Basic Example

```css
.card {
    width: 300px;
    border-radius: 16px;
    overflow: hidden;
}
```

The rounded corners define the shape of the container, while `overflow: hidden` clips overflowing child content.

```text
      ╭────────────────────╮
      │                    │
      │      Content       │
      │                    │
      ╰────────────────────╯
```

### Why Use `overflow: hidden` With `border-radius`?

Consider a card containing an image:

```html
<div class="card">
    <img src="image.jpg" alt="Example image">
</div>
```

CSS:

```css
.card {
    border-radius: 16px;
}

.card img {
    width: 100%;
}
```

Depending on the layout and child content, the child can visually extend beyond the rounded shape.

Adding:

```css
overflow: hidden;
```

clips the child content to the container's overflow area.

```css
.card {
    border-radius: 16px;
    overflow: hidden;
}
```

### Image Card Example

HTML:

```html
<div class="card">
    <img src="image.jpg" alt="Mountain landscape">

    <div class="content">
        <h2>Mountain</h2>
        <p>A simple card example.</p>
    </div>
</div>
```

CSS:

```css
.card {
    width: 300px;
    border-radius: 16px;
    overflow: hidden;
}

.card img {
    width: 100%;
    display: block;
}
```

The image stays visually contained within the rounded card.

### Rounded Image Container

You can also use the technique for a dedicated image container:

```css
.image-box {
    width: 300px;
    height: 200px;
    border-radius: 12px;
    overflow: hidden;
}

.image-box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

This is a common pattern for thumbnails and image cards.

```text
      ╭────────────────────────╮
      │                        │
      │        Image           │
      │                        │
      ╰────────────────────────╯
```

### Border Radius With Image Zoom

This pattern is particularly useful for hover effects.

```css
.image-box {
    width: 300px;
    height: 200px;
    border-radius: 16px;
    overflow: hidden;
}

.image-box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s;
}

.image-box:hover img {
    transform: scale(1.1);
}
```

The image becomes larger during the transform, but the container clips the transformed image.

```text
Normal:

╭────────────────────────╮
│        Image           │
╰────────────────────────╯

Hover:

╭────────────────────────╮
│    Enlarged image      │
│      cropped           │
╰────────────────────────╯
```

### `overflow: hidden` vs `overflow: clip`

Both can be used to clip overflowing content:

```css
.card {
    border-radius: 16px;
    overflow: hidden;
}
```

or:

```css
.card {
    border-radius: 16px;
    overflow: clip;
}
```

The important distinction is that `clip` is specifically intended to clip overflow without providing a scrolling mechanism.

```text
hidden
→ Clips overflow
→ Has scroll-container behavior

clip
→ Clips overflow
→ Does not provide scrolling
```

### Border Radius Does Not Replace Overflow Control

A common misconception is:

```css
.card {
    border-radius: 16px;
}
```

automatically handling every type of child overflow.

`border-radius` controls the rounded corners of the element itself. Overflow behavior is controlled separately.

When child content needs to be clipped to the rounded container, use an appropriate overflow value.

For example:

```css
.card {
    border-radius: 16px;
    overflow: hidden;
}
```

### Common Uses

This combination is commonly used for:

```text
Image cards
Profile pictures
Thumbnails
Hero images
Gallery items
Product cards
Video previews
Image hover effects
```

### Practical Example

```css
.product-card {
    width: 280px;
    border-radius: 12px;
    overflow: hidden;
}

.product-card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    display: block;
}

.product-card .content {
    padding: 16px;
}
```

The card has:

```text
Rounded container
        +
Clipped child content
        +
Responsive image
```

### Important Points

```text
border-radius
    ↓
Creates rounded corners

overflow: hidden / clip
    ↓
Controls child content extending
outside the container

Together
    ↓
Create clean rounded components
with contained child content
```

> 💡 **Remember:** `border-radius` controls the rounded shape, while `overflow` controls content that extends beyond the element. Combining `border-radius` with `overflow: hidden` or `overflow: clip` is a common way to keep images and other child content visually inside rounded containers.

---

## Overflow With Positioning

Positioned elements can extend outside the boundaries of their parent element.

CSS Overflow can be used to control whether that extra content remains visible, is clipped, or can be accessed through scrolling.

### Basic Example

HTML:

```html
<div class="container">
    <div class="child">Child</div>
</div>
```

CSS:

```css
.container {
    position: relative;
    width: 300px;
    height: 200px;
}

.child {
    position: absolute;
    right: -50px;
}
```

The child is positioned `50px` outside the right side of the container.

```text
Container
┌──────────────────────────────┐
│                              │
│                         Child│────────
│                              │
└──────────────────────────────┘
                           ↑
                     Outside parent
```

### Using `overflow: hidden`

If the positioned child should not be visible outside the parent:

```css
.container {
    position: relative;
    width: 300px;
    height: 200px;
    overflow: hidden;
}
```

The overflowing portion of the child is clipped.

```text
┌──────────────────────────────┐
│                              │
│                         Chil │
│                              │
└──────────────────────────────┘
```

### Why `position: relative` Is Commonly Used

A common pattern is:

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
}
```

The positioned parent establishes the containing block used by the absolutely positioned child.

For example:

```css
.card {
    position: relative;
    overflow: hidden;
}

.badge {
    position: absolute;
    top: 0;
    right: 0;
}
```

This is frequently used for cards, image containers, badges, overlays, and decorative elements.

### Positioned Element Extending Outside a Card

HTML:

```html
<div class="card">
    <div class="badge">NEW</div>
    <h2>Product</h2>
</div>
```

CSS:

```css
.card {
    position: relative;
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.badge {
    position: absolute;
    top: 10px;
    right: -20px;
}
```

The badge extends beyond the right edge, but `overflow: hidden` clips the part outside the card.

### Negative Positioning Values

Negative values can intentionally move an element outside its parent.

```css
.child {
    position: absolute;
    top: -20px;
    left: -20px;
}
```

The child extends beyond the top and left edges.

With:

```css
.parent {
    overflow: hidden;
}
```

the overflowing portion is clipped.

### Positioned Decorative Elements

Overflow control is often useful for decorative elements.

```css
.card {
    position: relative;
    overflow: hidden;
}

.card::before {
    content: "";
    position: absolute;
    width: 150px;
    height: 150px;
    border-radius: 50%;
    top: -70px;
    right: -70px;
}
```

The pseudo-element extends beyond the card, but the card can clip it.

```text
      Decorative circle
           ╭───────╮
        ╭──╯       │
┌───────┼──────────┤
│       │  Card    │
│       │          │
└───────┴──────────┘
```

### Positioned Image

An image can also be positioned outside its container.

```css
.image-box {
    position: relative;
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image {
    position: absolute;
    width: 350px;
    left: -25px;
}
```

The image extends beyond the container, but the overflow is clipped.

### `overflow: visible`

If the parent uses:

```css
.parent {
    overflow: visible;
}
```

the positioned child can remain visible outside the parent's box.

```text
┌──────────────────────┐
│ Parent               │
└──────────────────────┘──────────
                         Child
```

This can be useful when the child intentionally needs to appear outside the parent.

### `overflow: hidden`

With:

```css
.parent {
    overflow: hidden;
}
```

the overflowing portion is clipped.

```text
┌──────────────────────┐
│ Parent               │
│ Child                │
└──────────────────────┘
        ↑
   Outside portion
      clipped
```

### `overflow: auto`

With:

```css
.parent {
    overflow: auto;
}
```

overflow can become scrollable when necessary.

This is useful when the positioned content should remain accessible rather than being permanently clipped.

### `overflow: clip`

With:

```css
.parent {
    overflow: clip;
}
```

overflow is clipped without providing a scrolling mechanism.

This can be useful when positioned elements are purely decorative.

### Positioning and Transforms

Transforms can also cause an element to extend beyond its container.

```css
.container {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.child {
    transform: scale(1.2);
}
```

The transformed child becomes visually larger and may extend outside the container.

The container clips the overflowing portion.

### Hover Effects

This technique is common for image and card hover effects.

```css
.card {
    position: relative;
    overflow: hidden;
}

.card img {
    transition: transform 0.3s;
}

.card:hover img {
    transform: scale(1.1);
}
```

The image grows beyond its original dimensions, but the card clips the excess.

### Important Consideration

`overflow` controls the visibility and scrolling behavior of content extending outside an element's overflow area.

It does not change the positioning values themselves.

For example:

```css
.child {
    right: -50px;
}
```

still positions the child outside the parent.

Adding:

```css
.parent {
    overflow: hidden;
}
```

only changes how the overflow is displayed.

### Common Uses

Overflow with positioning is commonly used for:

```text
Card badges
Image overlays
Decorative shapes
Image zoom effects
Hover animations
Badges and labels
Clipped illustrations
Positioned backgrounds
```

### Important Points

```text
Positioned element
        ↓
Can extend outside parent
        ↓
Parent overflow controls visibility
        │
        ├── visible → remains visible
        ├── hidden  → clipped
        ├── auto    → scroll when necessary
        └── clip    → clipped without scrolling
```

> 💡 **Remember:** Positioning can intentionally move elements outside their parent. Use the parent's `overflow` property to decide whether that outside portion should remain visible, be clipped, or be accessible through scrolling.

---

## Overflow in CSS Grid

CSS Grid can experience overflow when the content of a grid item is larger than the space available in its grid track.

This is especially important when using flexible tracks such as:

```css
1fr
```

### Basic Example

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
}
```

The second column is flexible, but its contents can still affect its minimum size.

For example:

```text
┌───────────┬──────────────────────┐
│ Sidebar   │ Main content         │
│           │ Very long content... │
└───────────┴──────────────────────┘
```

If the main content contains a very long unbreakable string, the grid can become wider than expected.

### Long Unbreakable Content

Consider:

```html
<div class="layout">
    <aside>Sidebar</aside>

    <main>
        AReallyLongUnbreakableStringThatMayCauseOverflow
    </main>
</div>
```

CSS:

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
}
```

The long string may contribute a large minimum size to the flexible track.

This can cause horizontal overflow.

### Using `minmax(0, 1fr)`

A common solution is:

```css
.layout {
    display: grid;
    grid-template-columns: 200px minmax(0, 1fr);
}
```

Here:

```text
200px
  ↓
Fixed sidebar

minmax(0, 1fr)
  ↓
Flexible main content
```

The `0` minimum allows the flexible track to shrink instead of being forced wider by its content's minimum contribution.

### Why `minmax(0, 1fr)` Helps

Compare:

```css
grid-template-columns: 200px 1fr;
```

with:

```css
grid-template-columns: 200px minmax(0, 1fr);
```

The second version explicitly allows the flexible track to have a minimum size of `0`.

This is useful when content needs to be constrained within the available grid area.

### Adding Overflow to the Grid Item

Sometimes the content itself should become scrollable.

```css
.layout {
    display: grid;
    grid-template-columns: 200px minmax(0, 1fr);
}

.main {
    overflow: auto;
}
```

Now the main area can handle content that exceeds its available space.

### Horizontal Scrolling

For content that should remain wide, use:

```css
.main {
    overflow-x: auto;
}
```

For example, a wide table inside a Grid item can remain wide while the item provides horizontal scrolling.

```text
┌──────────────────────────────┐
│ Wide content                →│
└──────────────────────────────┘
             scroll →
```

### Preventing Long Text From Breaking the Layout

For normal text, allow it to wrap naturally.

For long unbroken strings, consider:

```css
.main {
    overflow-wrap: break-word;
}
```

This can help prevent long strings from creating unwanted horizontal overflow.

Depending on the content, other text-breaking properties may also be appropriate.

### Grid Item `min-width`

Another useful technique is setting:

```css
.main {
    min-width: 0;
}
```

This can allow a Grid item to shrink within its grid area when its content would otherwise impose a larger minimum size.

A common pattern is:

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
}

.main {
    min-width: 0;
}
```

Alternatively, the track itself can use:

```css
grid-template-columns: 200px minmax(0, 1fr);
```

### Which Approach Should You Use?

Use `minmax(0, 1fr)` when you want the grid track itself to be allowed to shrink.

```css
grid-template-columns:
    200px minmax(0, 1fr);
```

Use:

```css
min-width: 0;
```

when you need to control the minimum size of a particular Grid item.

Use:

```css
overflow-x: auto;
```

when the content should remain wider and be accessed through horizontal scrolling.

Use:

```css
overflow-wrap: break-word;
```

when long text or strings should be allowed to wrap.

### Grid With a Scrollable Main Area

A practical layout might be:

```css
.layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
    gap: 20px;
}

.main {
    overflow-x: auto;
}
```

This creates:

```text
┌────────────┬────────────────────────┐
│            │                        │
│  Sidebar   │       Main             │
│            │       Content          │
│            │                        │
└────────────┴────────────────────────┘
```

The main area can remain flexible while wide content can scroll horizontally.

### Grid With Long Code

A code block inside a Grid item can also cause overflow.

```css
.layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
}

.code-container {
    overflow-x: auto;
}
```

This keeps the Grid layout from being forced wider by long code lines.

### Grid and Images

Images can also contribute to overflow.

A responsive image can use:

```css
img {
    max-width: 100%;
    height: auto;
}
```

If the image is intentionally larger and should be scrollable:

```css
.image-container {
    overflow-x: auto;
}
```

### Grid Overflow vs Grid Item Overflow

It is useful to distinguish between:

```text
Grid overflow
    ↓
The overall grid becomes larger than its container

Grid item overflow
    ↓
Content inside an item extends beyond
the item's available area
```

The solution depends on which type of overflow is occurring.

### Debugging Grid Overflow

When a Grid layout unexpectedly becomes wider than the viewport, check:

```text
1. Very long unbroken text
2. Large images
3. Fixed-width children
4. 1fr tracks with large minimum content
5. Grid items with non-zero minimum sizes
6. Positioned elements
7. Transformed elements
```

Then inspect whether:

```css
minmax(0, 1fr)
```

or:

```css
min-width: 0;
```

or an appropriate overflow rule is needed.

### Practical Example

```html
<div class="layout">
    <aside class="sidebar">
        Navigation
    </aside>

    <main class="main">
        <pre class="code">
const veryLongFunctionName = someVeryLongFunctionName(firstArgument, secondArgument);
        </pre>
    </main>
</div>
```

CSS:

```css
.layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
    gap: 20px;
}

.main {
    min-width: 0;
}

.code {
    overflow-x: auto;
}
```

The result is:

```text
┌────────────┬──────────────────────────┐
│            │ Code                     │
│  Sidebar   │ const veryLong...      → │
│            │                          │
└────────────┴──────────────────────────┘
                    scroll →
```

### Important Points

```text
CSS Grid Overflow
│
├── Long content can affect track sizing
│
├── minmax(0, 1fr)
│   └── Allows flexible track to shrink
│
├── min-width: 0
│   └── Allows Grid item to shrink
│
├── overflow-x: auto
│   └── Allows wide content to scroll
│
├── overflow-wrap
│   └── Helps break long strings
│
└── max-width: 100%
    └── Helps keep images within their container
```

> 💡 **Remember:** Grid overflow often comes from content imposing a large minimum size on a flexible track. `minmax(0, 1fr)`, `min-width: 0`, appropriate text wrapping, and controlled overflow can help keep Grid layouts within their available space.

---

## Practical Examples

The `overflow` property is useful in many real-world layouts. The following examples combine the overflow properties covered in this topic.

### Example 1: Scrollable Card

```html
<div class="card">
    <p>
        This card contains more content than can fit inside
        its available height.
    </p>
    <p>
        Additional content can be accessed by scrolling.
    </p>
</div>
```

```css
.card {
    width: 300px;
    height: 150px;
    overflow-y: auto;
}
```

The card remains `150px` tall while additional content can be accessed vertically.

### Example 2: Single-Line Text With Ellipsis

```html
<h2 class="title">
    This is a very long title that does not fit inside the card.
</h2>
```

```css
.title {
    max-width: 250px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

Result:

```text
This is a very long title...
```

### Example 3: Responsive Image

```html
<img src="image.jpg" alt="Example image">
```

```css
img {
    max-width: 100%;
    height: auto;
}
```

The image can shrink to fit its available container width.

### Example 4: Image Cropping

```html
<div class="image-box">
    <img src="image.jpg" alt="Example image">
</div>
```

```css
.image-box {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

The image fills the container while portions outside the visible area are cropped.

### Example 5: Rounded Image Card

```html
<div class="card">
    <img src="image.jpg" alt="Example image">
</div>
```

```css
.card {
    width: 300px;
    border-radius: 16px;
    overflow: hidden;
}

.card img {
    width: 100%;
    display: block;
}
```

The image remains visually contained within the rounded card.

### Example 6: Image Zoom Effect

```html
<div class="image-box">
    <img src="image.jpg" alt="Example image">
</div>
```

```css
.image-box {
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.image-box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s;
}

.image-box:hover img {
    transform: scale(1.1);
}
```

The image grows on hover while the container clips the overflowing portion.

### Example 7: Horizontally Scrollable Table

```html
<div class="table-container">
    <table>
        <tr>
            <th>Name</th>
            <th>Email</th>
            <th>Department</th>
            <th>Location</th>
            <th>Phone</th>
        </tr>
        <tr>
            <td>Mohit</td>
            <td>example@email.com</td>
            <td>Computer Science</td>
            <td>Delhi</td>
            <td>1234567890</td>
        </tr>
    </table>
</div>
```

```css
.table-container {
    overflow-x: auto;
}

table {
    min-width: 700px;
}
```

On a narrow screen, the table can be accessed through horizontal scrolling.

### Example 8: Scrollable Code Block

```html
<pre class="code">
const result = someVeryLongFunctionName(firstArgument, secondArgument);
</pre>
```

```css
.code {
    overflow-x: auto;
    white-space: pre;
}
```

Long code lines remain intact while the user can scroll horizontally.

### Example 9: Preventing Long URLs From Overflowing

```html
<p class="url">
    https://example.com/a/very/long/path/that/may/not/fit
</p>
```

```css
.url {
    overflow-wrap: break-word;
}
```

This allows long unbroken strings to wrap when necessary.

### Example 10: Grid Layout With Scrollable Content

```html
<div class="layout">
    <aside class="sidebar">
        Sidebar
    </aside>

    <main class="main">
        <pre class="code">
const veryLongFunctionName = someVeryLongFunctionName(firstArgument, secondArgument);
        </pre>
    </main>
</div>
```

```css
.layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
    gap: 20px;
}

.main {
    min-width: 0;
}

.code {
    overflow-x: auto;
}
```

The flexible Grid area can shrink while the wide code remains horizontally scrollable.

### Example 11: Positioned Element Clipped by Its Parent

```html
<div class="container">
    <div class="child"></div>
</div>
```

```css
.container {
    position: relative;
    width: 300px;
    height: 200px;
    overflow: hidden;
}

.child {
    position: absolute;
    width: 150px;
    height: 150px;
    right: -50px;
}
```

The portion of the positioned child outside the container is clipped.

### Example 12: Horizontal and Vertical Overflow Separately

```css
.panel {
    width: 300px;
    height: 200px;
    overflow-x: auto;
    overflow-y: hidden;
}
```

This creates:

```text
Horizontal → scroll when necessary
Vertical   → clipped
```

### Example 13: Two-Value Overflow

The same behavior can be written using the shorthand:

```css
.panel {
    overflow: auto hidden;
}
```

The order is:

```text
First value  → horizontal
Second value → vertical
```

Therefore:

```css
overflow: auto hidden;
```

means:

```text
overflow-x → auto
overflow-y → hidden
```

### Example 14: Clipping Without Scrolling

```css
.container {
    width: 300px;
    height: 200px;
    overflow: clip;
}
```

This clips overflowing content without providing a scrolling mechanism.

### Example 15: Complete Card Component

HTML:

```html
<article class="card">
    <div class="image-box">
        <img src="image.jpg" alt="Example image">
    </div>

    <div class="card-content">
        <h2 class="card-title">
            A very long card title that may not fit
        </h2>

        <p>
            This is some additional content inside the card.
        </p>
    </div>
</article>
```

CSS:

```css
.card {
    width: 300px;
    border-radius: 16px;
    overflow: hidden;
}

.image-box {
    height: 180px;
    overflow: hidden;
}

.image-box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card-title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

.card-content {
    padding: 16px;
}
```

This example combines:

```text
border-radius
      +
overflow: hidden
      +
object-fit
      +
text-overflow
      +
white-space
```

to create a controlled card layout.

### Example 16: Choosing the Appropriate Overflow

Use:

```css
overflow: visible;
```

when overflow should remain visible.

Use:

```css
overflow: hidden;
```

when overflow should be clipped.

Use:

```css
overflow: scroll;
```

when a scrolling mechanism should be explicitly provided.

Use:

```css
overflow: auto;
```

when scrolling should be available when necessary.

Use:

```css
overflow: clip;
```

when overflow should be clipped without scrolling.

Use:

```css
overflow-x: auto;
```

when wide content should scroll horizontally.

Use:

```css
overflow-y: auto;
```

when tall content should scroll vertically.

### Quick Decision Guide

```text
Should overflow remain visible?
        ↓
overflow: visible

Should overflow be clipped?
        ↓
overflow: hidden

Should overflow be scrollable?
        ↓
overflow: auto

Should a scrolling mechanism be explicitly requested?
        ↓
overflow: scroll

Should overflow be clipped without scrolling?
        ↓
overflow: clip

Only horizontal overflow needs scrolling?
        ↓
overflow-x: auto

Only vertical overflow needs scrolling?
        ↓
overflow-y: auto
```

> 💡 **Remember:** Choose the overflow behavior based on what should happen to content that does not fit: remain visible, be clipped, or remain accessible through scrolling.

---

## Key Takeaways

- **Overflow** occurs when content is larger than the available space inside an element.

- The `overflow` property controls overflow in both horizontal and vertical directions.

- The main `overflow` values are:
  - `visible`
  - `hidden`
  - `scroll`
  - `auto`
  - `clip`

- `overflow-x` controls **horizontal overflow**.

- `overflow-y` controls **vertical overflow**.

- `overflow: visible` allows overflowing content to remain visible outside the element.

- `overflow: hidden` clips overflowing content.

- `overflow: scroll` provides a scrolling mechanism for overflowing content.

- `overflow: auto` allows scrolling when the content requires it.

- `overflow: clip` clips overflow without providing a scrolling mechanism.

- The two-value syntax follows this order:

```css
overflow: horizontal vertical;
```

- `text-overflow` controls how overflowing text is represented.

- A common single-line ellipsis pattern is:

```css
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;
```

- Images can cause overflow when they are larger than their containers.

- A common responsive image pattern is:

```css
img {
    max-width: 100%;
    height: auto;
}
```

- `overflow: hidden` or `overflow: clip` can be used to contain visual effects such as image zooming.

- `border-radius` and overflow control are commonly combined to keep child content inside rounded containers.

- Positioned elements can extend outside their parents, and the parent's overflow behavior determines how that overflow is handled.

- CSS Grid layouts can experience overflow when content imposes a large minimum size on a grid track.

- `minmax(0, 1fr)` can allow a flexible Grid track to shrink:

```css
grid-template-columns: 200px minmax(0, 1fr);
```

- `min-width: 0` can allow a Grid item to shrink within its available track.

- `overflow-x: auto` is useful for wide content such as tables and code blocks.

- `overflow-y: auto` is useful for tall content such as lists, sidebars, and modal content.

### Quick Summary

```text
CSS Overflow
│
├── overflow
│   ├── visible
│   ├── hidden
│   ├── scroll
│   ├── auto
│   └── clip
│
├── overflow-x
│   └── Horizontal overflow
│
├── overflow-y
│   └── Vertical overflow
│
├── text-overflow
│   ├── clip
│   └── ellipsis
│
└── Common applications
    ├── Text
    ├── Images
    ├── Cards
    ├── Positioning
    ├── Grid
    ├── Tables
    └── Scrollable containers
```

> 💡 **Remember:** Overflow is about deciding what should happen when content does not fit. Choose between keeping it visible, clipping it, or making it accessible through scrolling.

---

## References

- [MDN Web Docs — CSS Overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
- [MDN Web Docs — overflow-x](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x)
- [MDN Web Docs — overflow-y](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y)
- [MDN Web Docs — text-overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow)
- [MDN Web Docs — overflow-wrap](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)
- [MDN Web Docs — CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout)
- [MDN Web Docs — object-fit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
- [MDN Web Docs — border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)
- [MDN Web Docs — position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)

---

## Quick Revision

### What Is Overflow?

Overflow occurs when an element's content is larger than the available space inside its box.

```css
.box {
    width: 200px;
    height: 100px;
}
```

### Main Overflow Property

```css
overflow: value;
```

Common values:

```text
visible
hidden
scroll
auto
clip
```

### Overflow Values

| Value | Behavior |
|---|---|
| `visible` | Overflow remains visible |
| `hidden` | Overflow is clipped |
| `scroll` | Provides scrolling mechanism |
| `auto` | Provides scrolling when necessary |
| `clip` | Clips overflow without scrolling |

### Axis-Specific Overflow

Horizontal:

```css
overflow-x: auto;
```

Vertical:

```css
overflow-y: auto;
```

### Two-Value Syntax

```css
overflow: X Y;
```

```text
X → Horizontal / overflow-x
Y → Vertical / overflow-y
```

Example:

```css
overflow: hidden auto;
```

means:

```text
Horizontal → hidden
Vertical   → auto
```

### Text Overflow

Common single-line ellipsis pattern:

```css
.text {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### Responsive Images

```css
img {
    max-width: 100%;
    height: auto;
}
```

### Clipping Images

```css
.image-box {
    overflow: hidden;
}
```

Often combined with:

```css
border-radius: 16px;
```

### Scrollable Content

Horizontal:

```css
.container {
    overflow-x: auto;
}
```

Vertical:

```css
.container {
    overflow-y: auto;
}
```

Both directions:

```css
.container {
    overflow: auto;
}
```

### Grid Overflow

A flexible Grid track can be allowed to shrink with:

```css
grid-template-columns: 200px minmax(0, 1fr);
```

A Grid item may also need:

```css
min-width: 0;
```

### Quick Decision Guide

```text
Keep overflow visible
→ overflow: visible

Clip overflow
→ overflow: hidden

Scroll explicitly
→ overflow: scroll

Scroll when necessary
→ overflow: auto

Clip without scrolling
→ overflow: clip

Horizontal scrolling
→ overflow-x: auto

Vertical scrolling
→ overflow-y: auto
```

### Important Reminders

```text
overflow
    ↓
Controls overflowing content

overflow-x
    ↓
Horizontal overflow

overflow-y
    ↓
Vertical overflow

text-overflow
    ↓
Controls representation of overflowing text

white-space: nowrap
    ↓
Keeps text on one line

minmax(0, 1fr)
    ↓
Helps flexible Grid tracks shrink
```

> 💡 **Remember:** When content does not fit, decide whether it should remain visible, be clipped, or be made accessible through scrolling. Choose the overflow property that matches that requirement.

---

## Best Practices

Use CSS overflow intentionally. Avoid hiding or scrolling content without considering how users will access the overflowing information.

### 1. Prefer `auto` When Scrolling Is Optional

When content may or may not overflow, prefer:

```css
.container {
    overflow: auto;
}
```

This allows scrolling when necessary instead of always requesting a scrolling mechanism.

For axis-specific control:

```css
.container {
    overflow-x: auto;
}
```

or:

```css
.container {
    overflow-y: auto;
}
```

### 2. Use `hidden` for Intentional Visual Clipping

Use:

```css
overflow: hidden;
```

when content is intentionally meant to be clipped.

Common examples include:

```text
Image zoom effects
Rounded cards
Clipped decorative elements
Image containers
```

Example:

```css
.image-box {
    overflow: hidden;
}
```

### 3. Use `clip` When You Specifically Want Clipping

When the requirement is specifically to clip overflow without providing scrolling behavior, use:

```css
overflow: clip;
```

This communicates the intended behavior more explicitly than using a scrolling value.

### 4. Use `overflow-x: auto` for Wide Content

For content that can become wider than its container, use horizontal scrolling when appropriate:

```css
.table-container {
    overflow-x: auto;
}
```

This is particularly useful for:

```text
Wide tables
Code blocks
Large diagrams
Other horizontally wide content
```

### 5. Make Images Responsive

A common responsive image pattern is:

```css
img {
    max-width: 100%;
    height: auto;
}
```

This helps prevent images from becoming wider than their available container.

### 6. Use Ellipsis Carefully

For single-line text that should be shortened visually, use:

```css
.title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

Do not rely on:

```css
text-overflow: ellipsis;
```

alone.

The overflow and whitespace behavior must also support the intended truncation.

### 7. Do Not Hide Important Content Accidentally

Avoid using:

```css
overflow: hidden;
```

simply to make a layout look correct if the clipped content contains information the user needs.

For example:

```text
Important information
        ↓
overflow: hidden
        ↓
Information becomes inaccessible
```

Instead, consider:

```css
overflow: auto;
```

or redesign the layout so the content fits naturally.

### 8. Avoid Unnecessary Fixed Heights

Fixed heights can create overflow unexpectedly.

Instead of:

```css
.card {
    height: 100px;
}
```

consider allowing the content to determine the height when appropriate.

If a fixed height is required, provide an appropriate overflow strategy:

```css
.card {
    height: 100px;
    overflow-y: auto;
}
```

### 9. Handle Long Unbroken Content

Long URLs, identifiers, and other unbroken strings can cause horizontal overflow.

Consider:

```css
.content {
    overflow-wrap: break-word;
}
```

This can help prevent long strings from extending beyond their container.

### 10. Be Careful With `white-space: nowrap`

`white-space: nowrap` is useful when text must remain on one line:

```css
.title {
    white-space: nowrap;
}
```

However, it can create horizontal overflow when the text is too long.

When using it, combine it with an intentional overflow strategy:

```css
.title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### 11. Use `min-width: 0` in Flexible Layouts When Needed

Grid and Flex layouts can sometimes prevent items from shrinking because of their minimum content size.

For a Grid or Flex item, this can help:

```css
.item {
    min-width: 0;
}
```

This is especially useful when the item contains long text or other wide content.

### 12. Use `minmax(0, 1fr)` in Grid When Appropriate

For a Grid layout:

```css
.layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
}
```

This allows the flexible track to shrink down to `0` rather than being forced wider by its minimum content contribution.

### 13. Keep Overflow Rules Close to the Problem

Apply overflow to the element that actually needs to control the overflowing content.

For example:

```css
.code-container {
    overflow-x: auto;
}
```

is often clearer than applying broad overflow rules to a distant ancestor.

### 14. Use Axis-Specific Properties When Only One Axis Needs Control

Instead of:

```css
overflow: auto;
```

when only horizontal overflow needs handling, prefer:

```css
overflow-x: auto;
```

This makes the intended behavior clearer.

### 15. Test Overflow at Different Screen Sizes

A layout that works on a large screen may overflow on a smaller screen.

Test:

```text
Large desktop
Tablet
Mobile
Very narrow viewport
```

Pay particular attention to:

```text
Long text
Images
Tables
Code
Grid layouts
Flex layouts
Fixed-width elements
```

### 16. Check for Accidental Horizontal Page Overflow

Unexpected horizontal scrolling on the entire page is often a sign that some element is wider than the viewport.

Common causes include:

```text
Large fixed-width elements
Large images
Long unbroken text
Grid tracks
Flex items
Positioned elements
Transforms
```

Identify the element causing the overflow rather than hiding the problem globally.

### 17. Prefer Layout Solutions Over Overflow Hacks

Do not use overflow simply to hide a layout problem.

For example:

```css
body {
    overflow-x: hidden;
}
```

may hide unwanted horizontal scrolling, but it does not necessarily fix the element that is causing the overflow.

First identify why the element is wider than expected.

### 18. Choose Overflow Based on User Intent

A useful decision process is:

```text
Should the content remain visible?
        ↓
visible

Should the extra content be intentionally clipped?
        ↓
hidden / clip

Should the user access extra content?
        ↓
auto / scroll

Is only horizontal content too wide?
        ↓
overflow-x

Is only vertical content too tall?
        ↓
overflow-y
```

### Best-Practice Pattern

A common responsive content container might use:

```css
.container {
    max-width: 100%;
    overflow-x: auto;
}
```

For a responsive image:

```css
img {
    max-width: 100%;
    height: auto;
}
```

For a single-line title:

```css
.title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

For a flexible Grid layout:

```css
.layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
}

.main {
    min-width: 0;
}
```

### Best-Practice Checklist

```text
□ Use overflow intentionally
□ Prefer auto when scrolling is conditional
□ Use hidden/clip for intentional clipping
□ Make images responsive
□ Handle long strings
□ Use ellipsis intentionally
□ Avoid unnecessary fixed heights
□ Check Grid and Flex minimum sizes
□ Use min-width: 0 when appropriate
□ Use minmax(0, 1fr) when appropriate
□ Avoid hiding important content
□ Test at different viewport sizes
□ Fix the source of unexpected overflow
□ Use axis-specific properties when appropriate
```

> 💡 **Remember:** Good overflow management should solve the actual layout requirement rather than simply hide problems. Make important content accessible, make images and layouts responsive, and choose `visible`, `hidden`, `clip`, `auto`, or `scroll` intentionally.

---

## Common Mistakes

### 1. Using `overflow: hidden` Without Understanding the Consequences

A common mistake is using:

```css
.container {
    overflow: hidden;
}
```

just to remove unwanted scrolling.

This may hide content that users need to see.

Instead, find the element causing the overflow and determine whether the content should be:

```text
Visible
Clipped
Scrollable
Wrapped
```

### 2. Using `overflow-x: hidden` to Hide a Layout Problem

This is often used:

```css
body {
    overflow-x: hidden;
}
```

Although it can hide horizontal scrolling, it may only conceal the actual cause.

Common causes include:

- Oversized images
- Fixed-width elements
- Long unbroken text
- Grid tracks
- Flex items
- Positioned elements
- Transformed elements

Fix the source of the overflow when possible.

### 3. Using `text-overflow: ellipsis` Alone

This usually does not create the expected single-line ellipsis:

```css
.title {
    text-overflow: ellipsis;
}
```

A common pattern is:

```css
.title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

Each property has a different role.

### 4. Forgetting `white-space: nowrap`

For the common single-line ellipsis pattern, forgetting:

```css
white-space: nowrap;
```

can cause the text to wrap instead of overflowing horizontally.

Use:

```css
.title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

when the design requires a single line.

### 5. Confusing `hidden` With `clip`

These values are related but not identical:

```css
overflow: hidden;
```

and:

```css
overflow: clip;
```

Both can clip overflow, but `clip` is specifically intended for clipping without providing scrolling behavior.

Choose the value based on the required behavior.

### 6. Using `scroll` When `auto` Is More Appropriate

Using:

```css
overflow: scroll;
```

when scrolling is only occasionally necessary can request scrolling mechanisms even when content fits.

Often:

```css
overflow: auto;
```

is more appropriate when scrolling should be available only when needed.

### 7. Forgetting Which Axis Comes First

With two overflow values:

```css
overflow: hidden auto;
```

the first value controls horizontal overflow and the second controls vertical overflow.

```text
First  → overflow-x
Second → overflow-y
```

Do not reverse the order.

### 8. Forgetting That `overflow` Controls Both Axes

This:

```css
overflow: auto;
```

controls both horizontal and vertical overflow.

If only horizontal overflow needs special handling, use:

```css
overflow-x: auto;
```

instead.

### 9. Making Images Larger Than Their Containers

This can create unwanted horizontal overflow:

```css
img {
    width: 800px;
}
```

inside a smaller container.

For responsive images, a common pattern is:

```css
img {
    max-width: 100%;
    height: auto;
}
```

### 10. Using Fixed Heights Without Handling Extra Content

This can create unexpected overflow:

```css
.card {
    height: 100px;
}
```

If the content becomes taller, consider whether the element should grow naturally or provide scrolling:

```css
.card {
    max-height: 100px;
    overflow-y: auto;
}
```

### 11. Forgetting About Long Unbroken Strings

Long URLs, identifiers, and other strings without normal breaking opportunities can cause horizontal overflow.

For example:

```text
ThisIsAnExtremelyLongUnbrokenStringThatMayNotFit
```

Consider:

```css
.content {
    overflow-wrap: break-word;
}
```

when appropriate.

### 12. Ignoring Grid Minimum Sizes

A Grid layout such as:

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
}
```

can encounter overflow when the content of the flexible track has a large minimum size.

A common solution is:

```css
.layout {
    grid-template-columns: 200px minmax(0, 1fr);
}
```

### 13. Forgetting `min-width: 0`

A Grid or Flex item may need:

```css
.item {
    min-width: 0;
}
```

to allow it to shrink within the available space.

This is especially important when the item contains wide content.

### 14. Using Overflow to Hide Important Information

Avoid:

```css
overflow: hidden;
```

when the clipped content contains information the user needs.

For example:

```text
Important text
        ↓
overflow: hidden
        ↓
Text becomes inaccessible
```

Consider wrapping, resizing, scrolling, or another layout solution.

### 15. Assuming `border-radius` Controls Child Overflow

This:

```css
.card {
    border-radius: 16px;
}
```

does not by itself replace overflow control.

When child content needs to be clipped to the rounded container, use an appropriate overflow value:

```css
.card {
    border-radius: 16px;
    overflow: hidden;
}
```

### 16. Forgetting That Transforms Can Cause Overflow

A transformed element can become larger than its original box:

```css
.image {
    transform: scale(1.2);
}
```

If it should remain visually inside its container:

```css
.container {
    overflow: hidden;
}
```

### 17. Applying Overflow to the Wrong Element

Make sure the element receiving the overflow rule is actually the element whose content needs to be controlled.

For example:

```css
.code-container {
    overflow-x: auto;
}
```

is often more appropriate than applying a broad rule to an unrelated ancestor.

### 18. Ignoring Mobile Layouts

A layout may look correct on a desktop screen but overflow on mobile.

Always test:

```text
Desktop
Tablet
Mobile
Very narrow screens
```

Pay particular attention to:

- Tables
- Images
- Long text
- Code
- Grid layouts
- Fixed-width components

### 19. Hiding Overflow Instead of Fixing the Layout

Avoid treating:

```css
overflow: hidden;
```

as a universal solution.

If an element is unexpectedly too wide, first determine why.

For example:

```text
Unexpected page overflow
        ↓
Find the oversized element
        ↓
Fix its width / sizing / wrapping
        ↓
Use overflow only if appropriate
```

### 20. Forgetting Accessibility and Usability

Scrollable content should remain understandable and usable.

Do not hide essential information simply because it does not fit.

When using scrolling:

```css
overflow: auto;
```

make sure users can reasonably discover and interact with the scrollable content.

### Common Mistakes Checklist

```text
□ Using overflow: hidden to hide layout problems
□ Hiding page overflow without finding the cause
□ Using text-overflow: ellipsis alone
□ Forgetting white-space: nowrap for single-line ellipsis
□ Confusing hidden and clip
□ Using scroll when auto is more appropriate
□ Reversing two-value overflow order
□ Forgetting that overflow controls both axes
□ Using oversized fixed-width images
□ Using fixed heights without overflow planning
□ Ignoring long unbroken strings
□ Ignoring Grid minimum sizes
□ Forgetting min-width: 0
□ Hiding important content
□ Assuming border-radius controls child overflow
□ Forgetting transformed elements can overflow
□ Applying overflow to the wrong element
□ Failing to test responsive layouts
```

> 💡 **Remember:** `overflow` should be used to intentionally control content that does not fit, not simply to hide layout problems. Always determine why overflow occurs before deciding how to handle it.