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