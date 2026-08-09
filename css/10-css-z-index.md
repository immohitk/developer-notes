## Table of Contents

- [Introduction](#introduction)
- [What is CSS Z-Index?](#what-is-css-z-index)
- [Why is CSS Z-Index Important?](#why-is-css-z-index-important)
- [Z-Index Property](#z-index-property)
- [How Z-Index Works](#how-z-index-works)
- [Stacking Order](#stacking-order)
- [Positive Z-Index](#positive-z-index)
- [Negative Z-Index](#negative-z-index)
- [Z-Index with Positioned Elements](#z-index-with-positioned-elements)
- [Stacking Context](#stacking-context)
- [Creating a Stacking Context](#creating-a-stacking-context)
- [Z-Index and Flexbox](#z-index-and-flexbox)
- [Z-Index and Grid](#z-index-and-grid)
- [Common Use Cases](#common-use-cases)
- [Comparison and Examples](#comparison-and-examples)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


# Introduction

CSS `z-index` controls the **stacking order of overlapping elements**.

When multiple elements overlap, their stacking order determines which element appears in front and which element appears behind.

The `z-index` property is commonly used when working with:

- Overlapping elements
- Dropdown menus
- Modals
- Navigation bars
- Tooltips
- Notifications
- Image overlays
- Fixed and sticky elements

Understanding `z-index` is closely related to **CSS positioning**, **stacking order**, and **stacking contexts**.

> 💡 **Remember:** `z-index` controls the **stacking order of overlapping elements**.


---


## What is CSS Z-Index?

The CSS `z-index` property specifies the **stack order of an element**.

When elements overlap, the element with a higher stacking order is displayed in front of an element with a lower stacking order.

The `z-index` property accepts integer values, including:

- Positive values
- Zero
- Negative values

For example:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}
```

---


# Why is CSS Z-Index Important?

The `z-index` property is important when multiple elements **overlap** and their stacking order needs to be controlled.

Without controlling the stacking order, an element may appear behind another element even when it should visually appear in front.

`z-index` is commonly useful for:

- Navigation menus
- Dropdown menus
- Modal dialogs
- Tooltips
- Notifications
- Image overlays
- Badges
- Sticky elements
- Fixed elements
- Floating buttons

---

## Controlling Overlapping Elements

Consider two elements that overlap:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}
```

When they overlap within the same stacking context, `.box-two` appears above `.box-one`.

```text
Front
  │
  └── Box Two   z-index: 2
  │
  └── Box One   z-index: 1
  │
Back
```

This allows developers to control which element should be visible on top.

---

## Dropdown Menus

`z-index` is commonly used with dropdown menus.

```css
.navbar {
    position: relative;
    z-index: 10;
}

.dropdown {
    position: absolute;
    z-index: 20;
}
```

The dropdown can appear above surrounding page content.

```text
┌─────────────────────────────┐
│ Navigation                  │
│     ┌───────────────────┐   │
│     │ Dropdown          │   │
│     │ Item 1            │   │
│     │ Item 2            │   │
│     └───────────────────┘   │
│                             │
│       Page Content          │
└─────────────────────────────┘
```

---

## Modal Dialogs

Modal windows usually need to appear above the main page content.

```css
.modal {
    position: fixed;
    z-index: 1000;
}
```

A modal can therefore be placed above other interface elements when the relevant stacking contexts allow it.

```text
┌─────────────────────────────┐
│       Page Content          │
│                             │
│     ┌─────────────────┐     │
│     │      Modal      │     │
│     │                 │     │
│     │     Close       │     │
│     └─────────────────┘     │
│                             │
└─────────────────────────────┘
```

---

## Tooltips

Tooltips often overlap nearby content.

```css
.tooltip {
    position: absolute;
    z-index: 100;
}
```

This allows the tooltip to appear above surrounding elements.

---

## Notifications

Notification messages may need to remain visible above the rest of the page.

```css
.notification {
    position: fixed;
    top: 20px;
    right: 20px;
    z-index: 1000;
}
```

For example:

```text
┌──────────────────────────────┐
│                         ┌────┐│
│                         │ 🔔 ││
│                         │New ││
│                         └────┘│
│                              │
│        Page Content          │
│                              │
└──────────────────────────────┘
```

---

## Image Overlays

`z-index` can also be used when text, buttons, or other elements need to appear over an image.

```css
.image-container {
    position: relative;
}

.image {
    position: relative;
    z-index: 1;
}

.image-label {
    position: absolute;
    bottom: 10px;
    left: 10px;
    z-index: 2;
}
```

The label can appear above the image.

---

## Fixed and Sticky Elements

Fixed and sticky elements can overlap normal page content.

For example:

```css
.header {
    position: sticky;
    top: 0;
    z-index: 100;
}
```

The `z-index` helps keep the header visually above other content when the elements overlap.

---

## Why a High `z-index` Is Not Always Enough

A common mistake is assuming that a very large `z-index` value always places an element above everything else.

For example:

```css
.element {
    position: relative;
    z-index: 9999;
}
```

Even a value such as `9999` does not automatically place the element above elements that belong to a different stacking context.

The browser considers the **stacking context** before comparing stacking levels.

> 💡 **Pro Tip:** If a high `z-index` value does not seem to work, check the element's parent stacking context instead of continuously increasing the number.

---

## Real-World Layering

A web page can contain many different layers:

```text
Highest Layer
     │
     ├── Modal
     ├── Notification
     ├── Dropdown
     ├── Sticky Header
     ├── Page Content
     └── Background
     │
Lowest Layer
```

`z-index` helps developers organize these overlapping layers.

---

## Common Layering Example

A simple layering system might use:

```css
.background {
    z-index: 0;
}

.content {
    z-index: 1;
}

.dropdown {
    z-index: 10;
}

.header {
    z-index: 20;
}

.modal {
    z-index: 100;
}
```

The exact values are not important by themselves. What matters is the intended **stacking order**.

> ⚠️ **Important:** There is no special meaning to values such as `10`, `100`, or `1000`. They are simply numbers used to establish stacking levels within the relevant stacking context.

---

## Why Understanding Z-Index Matters

Understanding `z-index` helps prevent common UI problems such as:

- Dropdowns appearing behind content
- Modals appearing behind headers
- Tooltips being hidden
- Notifications appearing underneath other elements
- Buttons becoming inaccessible because another layer covers them
- Overlays appearing behind images or containers

A good understanding of `z-index` also makes it easier to debug complex layouts.

---

> 💡 **Remember:** `z-index` is important because it gives developers control over the **visual layering of overlapping elements**. However, the final result depends on the element's **stacking context** and stacking order.


---


# `z-index` Property

The CSS `z-index` property controls the **stacking order of overlapping elements**.

It determines which element appears in front of or behind another element when they overlap.

```css
.box {
    position: relative;
    z-index: 2;
}
```

The `z-index` property accepts:

- `auto`
- Positive integer values
- `0`
- Negative integer values

---

## Syntax

```css
selector {
    z-index: value;
}
```

Example:

```css
.box {
    position: relative;
    z-index: 10;
}
```

A higher `z-index` value generally places an element above an element with a lower `z-index` value when the elements belong to the same stacking context.

---

## `auto`

`auto` is the default value of the `z-index` property.

```css
.box {
    z-index: auto;
}
```

When `z-index` is `auto`, the element follows the default stacking order of its stacking context.

---

## Positive Values

Positive values can place an element higher in the stacking order.

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}
```

When the elements overlap within the same stacking context, `.box-two` appears above `.box-one`.

```text
Front
  │
  ├── Box Two   z-index: 2
  └── Box One   z-index: 1
  │
Back
```

---

## Zero

A `z-index` value of `0` places an element at the zero stacking level within its stacking context.

```css
.box {
    position: relative;
    z-index: 0;
}
```

It can be useful when explicitly defining the stacking level of an element without giving it a positive or negative priority.

---

## Negative Values

Negative values can place an element behind elements with higher stacking levels.

```css
.background {
    position: absolute;
    z-index: -1;
}
```

Negative values are commonly useful for decorative elements that need to appear behind other content.

However, the final result also depends on the element's stacking context.

---

## Comparing `z-index` Values

Consider:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 5;
}

.box-three {
    position: relative;
    z-index: 10;
}
```

The stacking order can be visualized as:

```text
Front
  │
  ├── Box Three   z-index: 10
  ├── Box Two     z-index: 5
  └── Box One     z-index: 1
  │
Back
```

A higher value places an element higher in the stacking order when the elements are being compared within the same stacking context.

---

## Common Values

| Value | Description |
|-------|-------------|
| `auto` | Default stacking behavior |
| `-1` | Lower stacking level |
| `0` | Zero stacking level |
| `1` | Higher stacking level |
| `10` | Higher stacking level |
| `9999` | Very high value, but still affected by stacking contexts |

---

## Large `z-index` Values

A common mistake is assuming that a very large `z-index` value will always place an element above everything else.

```css
.modal {
    position: fixed;
    z-index: 9999;
}
```

A large value does not automatically overcome a different stacking context.

The browser considers the relevant **stacking contexts** before comparing the stacking levels of elements.

> 💡 **Pro Tip:** If `z-index: 9999` does not work, do not keep increasing the number. Check the element's **stacking context** and its parent elements first.

---

## Important Point

The numerical value of `z-index` is only meaningful when the elements are being compared within the appropriate stacking context.

For example:

```css
.box-one {
    z-index: 10;
}

.box-two {
    z-index: 5;
}
```

This does not mean `.box-one` will always appear above every `.box-two` on the page.

Their parent stacking contexts can affect the final result.

> ⚠️ **Important:** A higher `z-index` does not automatically place an element above every element on the page. **Stacking contexts determine how different layers are compared.**

---

> 💡 **Remember:** `z-index` controls the **stacking order of overlapping elements**. A higher value generally appears in front of a lower value when the elements belong to the same stacking context.


---


# How Z-Index Works

The `z-index` property controls how overlapping elements are **stacked along the z-axis**.

While the `x-axis` controls horizontal position and the `y-axis` controls vertical position, the `z-axis` represents the depth or layering of elements.

```text
              Z-axis
                ↑
                │
        ┌─────────────┐
        │   Element   │  ← Front
        └─────────────┘
                │
        ┌─────────────┐
        │   Element   │
        └─────────────┘
                │
        ┌─────────────┐
        │   Element   │  ← Back
        └─────────────┘
```

When elements overlap, the browser uses their stacking order to determine which element should be displayed in front.

---

## Basic Example

Consider two overlapping elements:

```html
<div class="box box-one">Box One</div>
<div class="box box-two">Box Two</div>
```

```css
.box {
    position: absolute;
    width: 150px;
    height: 150px;
}

.box-one {
    z-index: 1;
}

.box-two {
    z-index: 2;
}
```

When the boxes overlap, `.box-two` appears above `.box-one` because it has the higher `z-index`.

```text
Front
  │
  └── Box Two   z-index: 2
       │
       └── Box One   z-index: 1
  │
Back
```

---

## Stacking Levels

Each element can participate in a stacking order.

For example:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 5;
}

.box-three {
    position: relative;
    z-index: 10;
}
```

The stacking order is:

```text
Highest
   │
   ├── Box Three   10
   ├── Box Two      5
   └── Box One      1
   │
Lowest
```

When these elements overlap within the same stacking context, the element with the higher stacking level appears in front.

---

## `z-index` Only Matters When Elements Overlap

If two elements do not overlap, their `z-index` values usually have no visible effect.

For example:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}
```

If the elements are placed far apart:

```text
┌───────────┐                 ┌───────────┐
│  Box One  │                 │  Box Two  │
└───────────┘                 └───────────┘
```

There is no visible layering because the elements do not overlap.

> 💡 **Remember:** `z-index` becomes visually important when elements **overlap**.

---

## Position and Stacking Are Different

`z-index` controls the **layering** of an element, not its physical position.

For example:

```css
.box {
    position: absolute;
    top: 50px;
    left: 100px;
    z-index: 5;
}
```

Here:

- `position` determines how the element is positioned.
- `top` determines its vertical offset.
- `left` determines its horizontal offset.
- `z-index` determines its stacking level.

```text
Position
   ↓
Where the element is located

z-index
   ↓
Which overlapping layer appears in front
```

---

## Higher `z-index` Does Not Always Win

A common misunderstanding is:

```text
Higher z-index = Always in front
```

This is not always true.

The elements may belong to different **stacking contexts**.

For example:

```css
.parent-one {
    position: relative;
    z-index: 1;
}

.child {
    position: relative;
    z-index: 9999;
}

.parent-two {
    position: relative;
    z-index: 2;
}
```

Even though `.child` has `z-index: 9999`, its stacking context is still controlled by its parent.

```text
Parent One
z-index: 1
    │
    └── Child
        z-index: 9999

Parent Two
z-index: 2
```

The child cannot simply escape its parent's stacking context because it has a larger number.

> 💡 **Pro Tip:** Think of `z-index` as a **layering system inside stacking contexts**, not as a global ranking system for the entire page.

---

## Stacking Context

A **stacking context** is a group of elements that are stacked together as a single unit within their parent stacking context.

This means that the `z-index` of a child is compared within its own stacking context before that entire context is compared with other stacking contexts.

```text
Root Stacking Context
│
├── Parent A
│   └── Child
│
└── Parent B
    └── Child
```

Understanding stacking contexts is essential when `z-index` does not produce the expected result.

---

## Negative and Positive Layers

`z-index` can create layers above and below other elements.

```css
.background {
    position: absolute;
    z-index: -1;
}

.content {
    position: relative;
    z-index: 1;
}

.modal {
    position: fixed;
    z-index: 100;
}
```

The intended order is:

```text
Front
  │
  ├── Modal       100
  ├── Content       1
  └── Background   -1
  │
Back
```

This makes `z-index` useful for creating layered user interfaces.

---

## Real-World Example

A typical interface might use different stacking levels:

```css
.page-content {
    z-index: 1;
}

.header {
    z-index: 10;
}

.dropdown {
    z-index: 20;
}

.notification {
    z-index: 30;
}

.modal {
    z-index: 100;
}
```

The intended visual hierarchy is:

```text
Highest
   │
   ├── Modal
   ├── Notification
   ├── Dropdown
   ├── Header
   └── Page Content
   │
Lowest
```

The actual result can still depend on stacking contexts.

---

## How the Browser Determines the Result

When elements overlap, the browser considers their **stacking contexts and stacking order** to determine which element is painted in front.

A simplified process is:

```text
Elements overlap
       ↓
Check stacking contexts
       ↓
Determine stacking order
       ↓
Compare stacking levels
       ↓
Paint elements in order
       ↓
Element on top becomes visible
```

This is why understanding only the numerical value of `z-index` is not always enough.

---

## Common Mistake

Consider:

```css
.modal {
    position: fixed;
    z-index: 9999;
}
```

Developers sometimes keep increasing the value when the modal still appears behind another element.

For example:

```css
z-index: 99999;
z-index: 999999;
z-index: 9999999;
```

This is usually not a good solution.

The problem may be caused by:

- A parent stacking context
- Another stacking context
- `transform`
- `opacity`
- `isolation`
- Other properties that create stacking contexts

> ⚠️ **Important:** When `z-index` appears not to work, inspect the **stacking context hierarchy** before increasing the value.

---

> 💡 **Remember:** `z-index` controls the stacking order of overlapping elements, but the final result is determined by the **stacking context and stacking order** in which those elements participate.


---


# Stacking Order

The **stacking order** determines how overlapping elements are layered along the z-axis.

When multiple elements overlap, the browser uses their stacking order to determine which element is painted in front of another.

```text
Front
  │
  ├── Element C
  ├── Element B
  └── Element A
  │
Back
```

An element that is higher in the stacking order appears visually in front of an element that is lower in the stacking order.

---

## Basic Example

Consider three overlapping elements:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}

.box-three {
    position: relative;
    z-index: 3;
}
```

Their stacking order is:

```text
Front
  │
  ├── Box Three   z-index: 3
  ├── Box Two     z-index: 2
  └── Box One     z-index: 1
  │
Back
```

If the elements overlap, `Box Three` appears above `Box Two`, and `Box Two` appears above `Box One`.

---

## Stacking Order Without `z-index`

Elements can still have a stacking order even when `z-index` is not explicitly specified.

For example:

```html
<div class="box box-one">Box One</div>
<div class="box box-two">Box Two</div>
```

```css
.box {
    position: absolute;
}

.box-one {
    background: lightblue;
}

.box-two {
    background: lightgray;
}
```

When positioned elements overlap, their stacking order can depend on the order in which they appear in the document and other stacking rules.

In simple cases, an element that appears later in the document can be painted above an earlier element when their other stacking properties are equivalent.

---

## Stacking Order with `z-index`

`z-index` allows the stacking order to be explicitly controlled.

```css
.box-one {
    position: relative;
    z-index: 5;
}

.box-two {
    position: relative;
    z-index: 10;
}
```

Here:

```text
Front
  │
  └── Box Two   z-index: 10
  │
  └── Box One   z-index: 5
  │
Back
```

`Box Two` appears above `Box One` when both are being compared within the same stacking context.

---

## Positive and Negative Stacking Levels

The stacking order can contain both positive and negative values.

```css
.background {
    position: relative;
    z-index: -1;
}

.content {
    position: relative;
    z-index: 0;
}

.overlay {
    position: relative;
    z-index: 1;
}
```

The intended order is:

```text
Front
  │
  ├── Overlay       1
  ├── Content       0
  └── Background   -1
  │
Back
```

This allows different elements to be placed at different visual layers.

---

## Stacking Contexts and Stacking Order

A stacking context creates a separate environment for stacking its child elements.

For example:

```css
.parent {
    position: relative;
    z-index: 2;
}

.child {
    position: relative;
    z-index: 9999;
}
```

The large `z-index` of `.child` does not make it globally higher than every element outside its parent's stacking context.

```text
Root Stacking Context
│
├── Parent A
│   z-index: 1
│   │
│   └── Child
│       z-index: 9999
│
└── Parent B
    z-index: 2
```

Here, the stacking level of the parent contexts is important when comparing the two groups.

> 💡 **Pro Tip:** Think of stacking contexts as **layers containing smaller layers**. A child can have a very high `z-index`, but it still participates within its parent's stacking context.

---

## Painting Order

The browser follows stacking rules to determine the order in which elements are painted.

A simplified model is:

```text
Background
    ↓
Lower stacking levels
    ↓
Normal content
    ↓
Higher stacking levels
    ↓
Foreground
```

The exact painting order is more detailed and depends on the element type, stacking context, and CSS properties involved.

---

## Example: Header and Modal

Consider a page with a header and modal:

```css
.header {
    position: sticky;
    top: 0;
    z-index: 10;
}

.modal {
    position: fixed;
    z-index: 100;
}
```

The intended stacking order is:

```text
Front
  │
  ├── Modal      100
  └── Header      10
  │
Back
```

The modal can therefore appear above the header when the relevant stacking contexts allow it.

---

## Example: Dropdown and Header

```css
.header {
    position: relative;
    z-index: 10;
}

.dropdown {
    position: absolute;
    z-index: 20;
}
```

The dropdown has a higher stacking level:

```text
Front
  │
  └── Dropdown   20
  │
  └── Header     10
  │
Back
```

This is a common pattern for navigation interfaces.

---

## Stacking Order Is Not the Same as DOM Order

The order of elements in the HTML document does not always determine which element appears in front.

For example:

```html
<div class="box box-one"></div>
<div class="box box-two"></div>
```

Even though `.box-one` appears first in the HTML, CSS can change the visual stacking order:

```css
.box-one {
    position: relative;
    z-index: 10;
}

.box-two {
    position: relative;
    z-index: 1;
}
```

Now `.box-one` can appear above `.box-two`.

> ⚠️ **Important:** DOM order is one part of the browser's stacking rules. `z-index`, positioning, stacking contexts, and other CSS properties can affect the final visual order.

---

## Practical Layering System

A project can use a consistent range of values to make its layering easier to understand.

For example:

```css
.page-content {
    z-index: 1;
}

.header {
    z-index: 10;
}

.dropdown {
    z-index: 20;
}

.notification {
    z-index: 30;
}

.modal {
    z-index: 100;
}
```

The intended hierarchy becomes:

```text
100 → Modal
 30 → Notification
 20 → Dropdown
 10 → Header
  1 → Page Content
```

The exact numbers are not important. The relationship between the layers is what matters.

---

> 💡 **Remember:** Stacking order determines **which overlapping element is painted in front**. `z-index` can influence that order, but the final result is also affected by **stacking contexts and other stacking rules**.


---


# Positive Z-Index

A **positive `z-index` value** places an element at a higher stacking level within its stacking context.

Positive values are commonly used when an element needs to appear **in front of other overlapping elements**.

```css
.box {
    position: relative;
    z-index: 10;
}
```

The larger the value, the higher the stacking level is when the elements are being compared within the same stacking context.

---

## Basic Example

Consider two overlapping elements:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}
```

The stacking order is:

```text
Front
  │
  └── Box Two   z-index: 2
  │
  └── Box One   z-index: 1
  │
Back
```

Therefore, `.box-two` appears above `.box-one` when they overlap within the same stacking context.

---

## Higher Positive Values

You can use different positive values to create multiple stacking levels.

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 5;
}

.box-three {
    position: relative;
    z-index: 10;
}
```

The resulting order is:

```text
Front
  │
  ├── Box Three   10
  ├── Box Two      5
  └── Box One      1
  │
Back
```

---

## Positive `z-index` Does Not Mean Pixel Distance

A `z-index` value is not a physical distance from the screen.

For example:

```css
.box-one {
    z-index: 1;
}

.box-two {
    z-index: 100;
}
```

This does not mean that `.box-two` is `99` pixels closer to the user.

The numbers simply represent **relative stacking levels**.

> 💡 **Remember:** `z-index: 100` does not mean `100px` above another element. It only represents a stacking level.

---

## Common Use Cases

Positive `z-index` values are commonly used for elements that should appear above normal page content.

### Dropdown Menu

```css
.dropdown {
    position: absolute;
    z-index: 20;
}
```

A dropdown can use a positive `z-index` to appear above surrounding content.

---

### Navigation Header

```css
.header {
    position: sticky;
    top: 0;
    z-index: 10;
}
```

This can help keep the header above content that scrolls underneath it.

---

### Notification

```css
.notification {
    position: fixed;
    top: 20px;
    right: 20px;
    z-index: 50;
}
```

The notification can be placed above normal page content.

---

### Modal

```css
.modal {
    position: fixed;
    inset: 0;
    z-index: 100;
}
```

A modal commonly needs a high stacking level so it can appear above other interface elements.

---

## Creating a Layer Hierarchy

Positive values can be used to establish a simple layering system.

```css
.content {
    position: relative;
    z-index: 1;
}

.header {
    position: relative;
    z-index: 10;
}

.dropdown {
    position: absolute;
    z-index: 20;
}

.notification {
    position: fixed;
    z-index: 30;
}

.modal {
    position: fixed;
    z-index: 100;
}
```

The intended hierarchy is:

```text
Front
  │
  ├── Modal          100
  ├── Notification    30
  ├── Dropdown        20
  ├── Header           10
  └── Content           1
  │
Back
```

This makes the layering relationship easy to understand.

---

## `z-index: 1` vs `z-index: 10`

Both values are positive.

```css
.box-one {
    z-index: 1;
}

.box-two {
    z-index: 10;
}
```

When compared within the same stacking context:

```text
z-index: 10
      ↓
Higher stacking level

z-index: 1
      ↓
Lower stacking level
```

Therefore, `.box-two` appears above `.box-one` when they overlap.

---

## `z-index` Values Do Not Need to Be Consecutive

You do not have to use:

```css
z-index: 1;
z-index: 2;
z-index: 3;
z-index: 4;
```

You can leave gaps:

```css
z-index: 10;
z-index: 20;
z-index: 50;
z-index: 100;
```

The actual numbers are less important than the relative ordering.

This can make it easier to introduce new layers later.

> 💡 **Pro Tip:** Using meaningful ranges such as `10`, `20`, `50`, and `100` can make a project's layering system easier to extend and maintain.

---

## Positive Z-Index and Stacking Contexts

A positive `z-index` value does not allow an element to escape its stacking context.

For example:

```css
.parent-one {
    position: relative;
    z-index: 1;
}

.child {
    position: relative;
    z-index: 9999;
}

.parent-two {
    position: relative;
    z-index: 2;
}
```

The child has a very large `z-index`, but it is still inside `.parent-one`'s stacking context.

```text
Parent One
z-index: 1
   │
   └── Child
       z-index: 9999

Parent Two
z-index: 2
```

The child's `9999` does not automatically make it appear above everything inside the page.

> ⚠️ **Important:** A positive `z-index` is only compared within the relevant stacking context. A very large value cannot automatically overcome a higher-level stacking context.

---

## Practical Example

```html
<div class="container">
    <div class="card card-one">Card One</div>
    <div class="card card-two">Card Two</div>
</div>
```

```css
.container {
    position: relative;
}

.card {
    position: absolute;
    width: 150px;
    height: 150px;
}

.card-one {
    top: 20px;
    left: 20px;
    z-index: 1;
}

.card-two {
    top: 60px;
    left: 60px;
    z-index: 2;
}
```

The cards overlap:

```text
┌───────────────────────┐
│                       │
│   ┌─────────────┐     │
│   │   Card One  │     │
│   │       ┌───────────┐
│   │       │ Card Two  │
│   └───────│           │
│           └───────────┘
│                       │
└───────────────────────┘
```

Because `.card-two` has a higher `z-index`, it appears above `.card-one` in the overlapping area.

---

## Important Difference

Positive `z-index` values do not change:

- The element's width
- The element's height
- Its `top` position
- Its `left` position
- The normal layout position of other elements

They control the **stacking order**.

```text
Positioning
    ↓
Controls where the element is placed

z-index
    ↓
Controls which overlapping layer appears in front
```

---

> 💡 **Remember:** Positive `z-index` values are useful when an element needs to appear **above other overlapping elements**. The value establishes a stacking level, but the final result still depends on the relevant stacking context.


---


# Negative Z-Index

A **negative `z-index` value** places an element at a lower stacking level within its stacking context.

Negative values are useful when an element needs to appear **behind other content** while still participating in the stacking order.

```css
.background {
    position: absolute;
    z-index: -1;
}
```

Common uses include:

- Decorative backgrounds
- Background shapes
- Visual effects
- Overlays placed behind content
- Layered design elements

---

## Basic Example

Consider two overlapping elements:

```css
.box-one {
    position: relative;
    z-index: 0;
}

.box-two {
    position: relative;
    z-index: -1;
}
```

The stacking order is:

```text
Front
  │
  └── Box One    z-index: 0
  │
  └── Box Two    z-index: -1
  │
Back
```

When the elements overlap within the appropriate stacking context, `.box-two` appears behind `.box-one`.

---

## Using `z-index: -1`

A common pattern is to place a decorative element behind the main content.

```html
<div class="card">
    <div class="decoration"></div>
    <h2>Card Title</h2>
    <p>Card content.</p>
</div>
```

```css
.card {
    position: relative;
}

.decoration {
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
}
```

The decoration can be positioned behind the card's content.

```text
┌─────────────────────────────┐
│  ┌───────────────────────┐  │
│  │    Decorative Shape   │  │
│  │                       │  │
│  │      Card Title       │  │
│  │      Card Content     │  │
│  └───────────────────────┘  │
└─────────────────────────────┘
```

---

## Negative Values Compared

Different negative values can create different stacking levels.

```css
.background {
    position: absolute;
    z-index: -10;
}

.decoration {
    position: absolute;
    z-index: -5;
}

.content {
    position: relative;
    z-index: 0;
}
```

The stacking order is:

```text
Front
  │
  ├── Content       0
  ├── Decoration   -5
  └── Background  -10
  │
Back
```

A value of `-5` is higher than `-10`.

Therefore:

```text
0 > -5 > -10
```

> 💡 **Remember:** With negative values, a value closer to zero has a **higher stacking level** than a more negative value.

---

## Negative Z-Index for Decorative Elements

Negative `z-index` values are often useful for decorative shapes.

```html
<section class="hero">
    <div class="circle"></div>

    <div class="content">
        <h1>Welcome</h1>
        <p>Learn CSS.</p>
    </div>
</section>
```

```css
.hero {
    position: relative;
}

.circle {
    position: absolute;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    z-index: -1;
}

.content {
    position: relative;
    z-index: 1;
}
```

The decorative circle can sit behind the content.

```text
┌─────────────────────────────┐
│       ◯                     │
│          Welcome            │
│          Learn CSS          │
│                             │
└─────────────────────────────┘
```

---

## Negative Z-Index and the Parent

A negative `z-index` does not automatically mean that an element will appear behind everything on the page.

The element still participates in its relevant **stacking context**.

For example:

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    z-index: -1;
}
```

The child is placed at a negative stacking level within the parent's stacking context.

```text
Parent Stacking Context
│
├── Content
│
└── Child
    z-index: -1
```

The final visual result depends on the parent's stacking context and other elements around it.

> ⚠️ **Important:** `z-index: -1` does not mean "put this behind the entire webpage." It places the element at a negative stacking level within the relevant stacking context.

---

## Negative Z-Index and Background Effects

Negative `z-index` can be useful for creating visual effects behind content.

```css
.card {
    position: relative;
}

.card::before {
    content: "";
    position: absolute;
    inset: 0;
    z-index: -1;
}
```

The pseudo-element can be used as a decorative layer behind the card's content.

This pattern is commonly used for:

- Background shapes
- Gradient layers
- Decorative borders
- Visual effects
- Highlight effects

---

## Negative vs Positive Z-Index

| Feature | Negative `z-index` | Positive `z-index` |
|---------|--------------------|--------------------|
| Stacking level | Lower | Higher |
| Common purpose | Background/decorative layers | Foreground/UI layers |
| Example | `z-index: -1` | `z-index: 10` |
| Can overlap content | ✅ | ✅ |
| Affected by stacking contexts | ✅ | ✅ |

---

## Example: Layered Card

```html
<div class="card">
    <div class="background-shape"></div>

    <div class="card-content">
        <h2>CSS</h2>
        <p>Learn positioning and layering.</p>
    </div>
</div>
```

```css
.card {
    position: relative;
}

.background-shape {
    position: absolute;
    inset: 0;
    z-index: -1;
}

.card-content {
    position: relative;
    z-index: 1;
}
```

The intended layering is:

```text
Front
  │
  └── Card Content      1
  │
  └── Background Shape -1
  │
Back
```

---

## Common Mistake

A common mistake is using:

```css
z-index: -9999;
```

simply because an element needs to appear behind another element.

A very large negative value is usually unnecessary.

If you only need a lower stacking level, a simple value such as:

```css
z-index: -1;
```

may be enough.

> 💡 **Pro Tip:** Prefer small, meaningful `z-index` values. Use the smallest value that clearly expresses the intended stacking relationship.

---

## Negative Z-Index and Visibility Problems

Negative `z-index` can sometimes cause an element to appear behind an ancestor's background or become difficult to see.

For example:

```css
.parent {
    background: white;
}

.child {
    position: absolute;
    z-index: -1;
}
```

The child may end up behind the parent's background depending on the stacking context.

This is one reason negative `z-index` should be used carefully.

> ⚠️ **Important:** If an element with `z-index: -1` unexpectedly disappears, inspect its **parent stacking context and background layers**.

---

## Practical Layering System

A page can use negative values for background layers and positive values for foreground elements.

```css
.background {
    position: absolute;
    z-index: -10;
}

.decoration {
    position: absolute;
    z-index: -5;
}

.content {
    position: relative;
    z-index: 1;
}

.modal {
    position: fixed;
    z-index: 100;
}
```

The intended hierarchy becomes:

```text
Front
  │
  ├── Modal          100
  ├── Content          1
  ├── Decoration      -5
  └── Background     -10
  │
Back
```

---

> 💡 **Remember:** Negative `z-index` values place elements at **lower stacking levels** and are especially useful for decorative or background layers. Always consider the element's **stacking context** before relying on a negative value.


---


# Z-Index with Positioned Elements

The `z-index` property is commonly used together with **positioned elements**.

Positioned elements include:

- `position: relative`
- `position: absolute`
- `position: fixed`
- `position: sticky`

A common pattern is:

```css
.box {
    position: relative;
    z-index: 10;
}
```

The `position` property controls how the element is positioned, while `z-index` controls its stacking level.

---

## `relative` with `z-index`

`position: relative` is commonly combined with `z-index`.

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}
```

When the elements overlap within the same stacking context, `.box-two` appears above `.box-one`.

```text
Front
  │
  └── Box Two   z-index: 2
  │
  └── Box One   z-index: 1
  │
Back
```

---

## `absolute` with `z-index`

Absolutely positioned elements are frequently used with `z-index` for overlays and layered components.

```css
.container {
    position: relative;
}

.overlay {
    position: absolute;
    z-index: 10;
}
```

For example:

```html
<div class="card">
    <img src="image.jpg" alt="Image">
    <span class="badge">New</span>
</div>
```

```css
.card {
    position: relative;
}

.badge {
    position: absolute;
    top: 10px;
    right: 10px;
    z-index: 2;
}
```

The badge can appear above the image.

```text
┌─────────────────────────────┐
│                      ┌────┐ │
│        IMAGE         │ New│ │
│                      └────┘ │
│                             │
└─────────────────────────────┘
```

---

## `fixed` with `z-index`

Fixed elements are often used for elements that need to remain visible above page content.

```css
.notification {
    position: fixed;
    top: 20px;
    right: 20px;
    z-index: 100;
}
```

The element remains fixed relative to the viewport while the `z-index` controls its stacking level.

Common examples include:

- Notifications
- Floating buttons
- Fixed navigation
- Cookie banners
- Modal overlays

---

## `sticky` with `z-index`

Sticky elements can also use `z-index`.

```css
.header {
    position: sticky;
    top: 0;
    z-index: 10;
}
```

This is useful when a sticky header needs to remain visually above content while scrolling.

```text
┌─────────────────────────────┐
│          Header             │ ← z-index: 10
├─────────────────────────────┤
│                             │
│       Page Content          │
│                             │
│       Page Content          │
│                             │
└─────────────────────────────┘
```

---

## Positioning and Z-Index Work Together

It is important to understand that `position` and `z-index` perform different jobs.

```css
.box {
    position: absolute;
    top: 20px;
    left: 30px;
    z-index: 5;
}
```

Here:

```text
position
   ↓
Determines how the element participates in positioning

top / left
   ↓
Determines where the element is placed

z-index
   ↓
Determines its stacking level
```

The properties work together to create layered layouts.

---

## Common Pattern: Relative Parent + Absolute Child

One of the most common CSS patterns is:

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    z-index: 2;
}
```

For example:

```html
<div class="card">
    <div class="badge">Sale</div>
    <h2>Product</h2>
</div>
```

```css
.card {
    position: relative;
}

.badge {
    position: absolute;
    top: 10px;
    right: 10px;
    z-index: 2;
}
```

The parent establishes the positioning context, while the child can be positioned and layered inside it.

```text
┌─────────────────────────────┐
│                     ┌─────┐ │
│                     │Sale │ │
│                     └─────┘ │
│                             │
│          Product            │
│                             │
└─────────────────────────────┘
```

---

## Multiple Positioned Elements

Multiple positioned elements can have different stacking levels.

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: absolute;
    z-index: 5;
}

.box-three {
    position: fixed;
    z-index: 10;
}
```

When they are being compared within the same stacking context:

```text
Front
  │
  ├── Box Three   10
  ├── Box Two      5
  └── Box One      1
  │
Back
```

The positioning method itself does not mean that one element is automatically above another. The stacking rules determine the final result.

> ⚠️ **Important:** `fixed` or `absolute` does not automatically mean "above everything." The final stacking order still depends on `z-index` and stacking contexts.

---

## `z-index` Without Positioning

Modern CSS also allows `z-index` to affect certain elements that are not traditionally positioned, including **flex items** and **grid items**.

For example:

```css
.container {
    display: flex;
}

.item {
    z-index: 2;
}
```

The item can participate in stacking even without explicitly setting:

```css
position: relative;
```

This is particularly important when working with Flexbox and Grid.

> 💡 **Pro Tip:** Do not assume that `position: relative` is always required for `z-index`. Flex items and grid items can use `z-index` without being positioned in the traditional sense.

---

## Comparison

| Position | Common Use | Can Use `z-index` |
|----------|-------------|-------------------|
| `relative` | Small offsets and positioning context | ✅ |
| `absolute` | Overlays and positioned children | ✅ |
| `fixed` | Viewport-level UI | ✅ |
| `sticky` | Sticky headers and sections | ✅ |
| `static` | Normal document flow | Usually not for traditional positioned stacking |

---

## Practical Example: Modal

A modal commonly combines `fixed` positioning with a high `z-index`.

```html
<div class="modal">
    <div class="modal-content">
        <h2>Modal</h2>
        <p>This is a modal window.</p>
    </div>
</div>
```

```css
.modal {
    position: fixed;
    inset: 0;
    z-index: 100;
}

.modal-content {
    position: relative;
    z-index: 101;
}
```

The modal is placed above normal page content, while the modal content can be given its own stacking level.

```text
Front
  │
  └── Modal Content   101
  │
  └── Modal           100
  │
  └── Page Content
  │
Back
```

---

## Important Difference

The following properties should not be confused:

```css
position: absolute;
```

controls **positioning**.

```css
z-index: 10;
```

controls **stacking level**.

For example:

```css
.badge {
    position: absolute;
    top: 10px;
    right: 10px;
    z-index: 5;
}
```

The element is positioned using `position`, while its visual layer is controlled using `z-index`.

> 💡 **Remember:** `position` determines **how and where an element is positioned**, while `z-index` determines **how overlapping elements are layered**. They are related, but they solve different problems.


---


# Stacking Context

A **stacking context** is a group of elements that are stacked together as a single unit within another stacking context.

Each stacking context creates its own independent environment for determining the stacking order of its child elements.

This means that a child element's `z-index` is generally compared **inside its own stacking context**, rather than directly against every element on the page.

---

## Basic Structure

A stacking context can be visualized as:

```text
Root Stacking Context
│
├── Element A
│
├── Stacking Context B
│   │
│   ├── Child B1
│   └── Child B2
│
└── Element C
```

The children inside Stacking Context B are first stacked relative to one another.

The entire stacking context is then positioned relative to the other elements in its parent stacking context.

---

## Why Stacking Contexts Matter

Consider:

```css
.parent-one {
    position: relative;
    z-index: 1;
}

.child {
    position: relative;
    z-index: 9999;
}

.parent-two {
    position: relative;
    z-index: 2;
}
```

The structure is:

```text
Parent One
z-index: 1
   │
   └── Child
       z-index: 9999

Parent Two
z-index: 2
```

It may seem that the child should always appear above `Parent Two` because it has `z-index: 9999`.

However, the child is part of `Parent One`'s stacking context.

The parent stacking contexts are compared at their own level:

```text
Parent Two   → 2
Parent One   → 1
```

The child cannot simply escape its parent's stacking context because it has a larger `z-index`.

> 💡 **Pro Tip:** Think of a stacking context as a **container of layers**. A child can move up and down inside that container, but it cannot use its `z-index` to escape the container's stacking order.

---

## Stacking Contexts Are Independent

Suppose a parent creates a stacking context:

```css
.parent {
    position: relative;
    z-index: 1;
}
```

Its children can have their own stacking levels:

```css
.child-one {
    position: relative;
    z-index: 1;
}

.child-two {
    position: relative;
    z-index: 10;
}
```

Inside the parent:

```text
Parent Stacking Context
│
├── Child Two   10
└── Child One    1
```

The browser compares the children according to their stacking order inside that context.

The entire parent stacking context is then compared with other stacking contexts at the parent level.

---

## Nested Stacking Contexts

Stacking contexts can be nested.

```text
Root Stacking Context
│
├── Parent A
│   │
│   └── Stacking Context B
│       │
│       ├── Child B1
│       └── Child B2
│
└── Parent C
```

Here:

- The root creates the outer stacking environment.
- Parent A can create another stacking context.
- Stacking Context B can create another nested stacking context.
- The children inside B are compared within B.

This hierarchy is important when debugging complex layering problems.

---

## Common Way to Create a Stacking Context

One common way to create a stacking context is to use a positioned element with a non-`auto` `z-index`.

For example:

```css
.parent {
    position: relative;
    z-index: 1;
}
```

The element can establish a stacking context.

Its children are then stacked within that context.

---

## `position` and `z-index`

A common pattern is:

```css
.parent {
    position: relative;
    z-index: 1;
}

.child {
    position: absolute;
    z-index: 10;
}
```

The parent establishes the positioning and stacking environment.

The child has its own stacking level inside that environment.

```text
Parent
z-index: 1
│
├── Child
│   z-index: 10
│
└── Other Child
    z-index: 5
```

The child with `z-index: 10` appears above the child with `z-index: 5` when they are compared within the same stacking context.

---

## Stacking Context vs Normal Element

A normal element can participate in a stacking order without necessarily creating a new stacking context.

A stacking context, however, creates an **independent stacking environment**.

```text
Normal Element
    ↓
Participates in its parent's stacking environment

Stacking Context
    ↓
Creates an independent stacking environment
    ↓
Contains its own stacking order
```

This distinction is one of the most important concepts when working with `z-index`.

---

## Stacking Context Hierarchy

Consider:

```css
.container {
    position: relative;
    z-index: 2;
}

.card {
    position: relative;
    z-index: 5;
}

.badge {
    position: absolute;
    z-index: 10;
}
```

The hierarchy can be represented as:

```text
Root
│
└── Container
    z-index: 2
    │
    └── Card
        z-index: 5
        │
        └── Badge
            z-index: 10
```

The badge's `z-index: 10` is not a global page-level value.

It is evaluated within the stacking context in which the badge participates.

> ⚠️ **Important:** `z-index` values from different stacking contexts should not be treated as if they were all part of one global number line.

---

## Why `z-index: 9999` Can Fail

Consider:

```css
.parent {
    position: relative;
    z-index: 1;
}

.child {
    position: relative;
    z-index: 9999;
}

.other {
    position: relative;
    z-index: 2;
}
```

You might expect:

```text
9999 > 2
```

and therefore expect `.child` to appear above `.other`.

But the child belongs to the stacking context created by `.parent`.

The browser first compares the relevant parent-level stacking contexts.

```text
Parent
z-index: 1
│
└── Child
    z-index: 9999

Other
z-index: 2
```

The entire `Parent` stacking context is still below `Other` at that level.

---

## Real-World Example

Consider a page with:

```css
.header {
    position: relative;
    z-index: 10;
}

.modal-container {
    position: relative;
    z-index: 20;
}

.modal {
    position: absolute;
    z-index: 1;
}
```

The modal has only `z-index: 1`, but it is inside a stacking context at `20`.

The simplified hierarchy is:

```text
Front
  │
  └── Modal Container   20
       │
       └── Modal         1
  │
  └── Header            10
  │
Back
```

The important comparison is between the parent stacking contexts.

---

## Properties That Can Create Stacking Contexts

Several CSS features can create stacking contexts.

Common examples include:

- A positioned element with a non-`auto` `z-index`
- `position: fixed`
- `position: sticky`
- `opacity` less than `1`
- `transform` other than `none`
- `filter` with a value other than `none`
- `isolation: isolate`
- Certain values of `mix-blend-mode`
- Certain containment properties

The exact list is broader and depends on the CSS specification.

> 💡 **Remember:** When debugging `z-index`, check whether a parent creates a stacking context through properties such as `z-index`, `transform`, `opacity`, or `isolation`.

---

## Creating an Explicit Stacking Context

The `isolation` property can be used when you intentionally want an element to establish a new stacking context.

```css
.container {
    isolation: isolate;
}
```

This can be useful when you want the layering of a component to remain isolated from surrounding content.

For example:

```css
.card {
    isolation: isolate;
}

.badge {
    position: absolute;
    z-index: 10;
}
```

The card can provide an isolated stacking environment for its contents.

---

## Stacking Context Visualization

A complex page can contain several stacking contexts:

```text
Root
│
├── Header
│   └── Navigation
│       └── Dropdown
│
├── Main Content
│   └── Card
│       └── Badge
│
└── Modal
    └── Modal Content
```

Each component can have its own stacking relationships.

This is why a large `z-index` value alone is not always enough to solve layering problems.

---

## Practical Debugging Approach

When `z-index` does not behave as expected, check the following:

```text
1. Are the elements overlapping?
          ↓
2. What are their z-index values?
          ↓
3. What stacking context does each element belong to?
          ↓
4. Does a parent create another stacking context?
          ↓
5. Are properties such as transform or opacity involved?
          ↓
6. Compare the parent stacking contexts
```

This approach is much more reliable than continuously increasing the `z-index` value.

> 💡 **Pro Tip:** Debug the **stacking context hierarchy from the outside inward**. Start with the parents, then inspect the child elements.

---

## Stacking Context vs `z-index`

| Concept | Purpose |
|---------|---------|
| `z-index` | Controls an element's stacking level |
| Stacking context | Creates an independent stacking environment |
| Parent stacking context | Determines the layer in which the child context participates |
| Child `z-index` | Controls stacking inside its relevant context |

---

> 💡 **Remember:** A stacking context is an **independent layering environment**. Elements inside it are stacked according to their own rules, while the entire stacking context is then positioned relative to other elements in its parent stacking context.


---


# Creating a Stacking Context

A **stacking context** can be created by several CSS properties and conditions.

Understanding how stacking contexts are created is important because they determine how `z-index` values are compared.

Once an element creates a stacking context, its descendants are stacked inside that context.

---

## Positioned Element with `z-index`

One common way to create a stacking context is using a positioned element with a non-`auto` `z-index`.

For example:

```css
.container {
    position: relative;
    z-index: 1;
}
```

The element can establish a new stacking context.

Its descendants are then stacked within that context.

```text
Root
│
├── Container
│   z-index: 1
│   │
│   ├── Child One
│   └── Child Two
│
└── Other Content
```

---

## `position: fixed`

An element with:

```css
position: fixed;
```

creates a stacking context.

For example:

```css
.modal {
    position: fixed;
    inset: 0;
    z-index: 100;
}
```

Fixed positioning is commonly used for:

- Modals
- Notifications
- Floating buttons
- Cookie banners
- Fixed navigation

Because these elements often need to appear above normal page content, `z-index` is frequently used with them.

---

## `position: sticky`

A sticky positioned element can also create a stacking context.

```css
.header {
    position: sticky;
    top: 0;
    z-index: 10;
}
```

This is commonly used for:

- Sticky headers
- Sticky navigation
- Persistent controls
- Table headers

The `z-index` controls how the sticky element layers with surrounding content.

---

## `opacity`

An element with an `opacity` value less than `1` creates a stacking context.

For example:

```css
.box {
    opacity: 0.8;
}
```

The value:

```css
opacity: 1;
```

does not create the same stacking context condition.

But:

```css
opacity: 0.9;
```

can create a stacking context.

This matters because adding opacity can unexpectedly change how descendant elements participate in stacking.

> ⚠️ **Important:** A seemingly simple visual property such as `opacity` can affect stacking behavior.

---

## `transform`

A transform other than:

```css
transform: none;
```

can create a stacking context.

For example:

```css
.card {
    transform: translateX(10px);
}
```

Even a small transform can therefore affect the stacking environment.

This is important when working with:

- Animations
- Transitions
- 3D effects
- Hover effects
- Component positioning

For example:

```css
.card:hover {
    transform: scale(1.05);
}
```

The transformed element participates in a stacking context.

---

## `filter`

A non-`none` `filter` can also create a stacking context.

Example:

```css
.image {
    filter: blur(2px);
}
```

Other filter effects include:

```css
filter: brightness(80%);
```

```css
filter: grayscale(100%);
```

```css
filter: contrast(120%);
```

Although `filter` is primarily used for visual effects, it can also affect stacking behavior.

---

## `isolation: isolate`

The `isolation` property can explicitly create a new stacking context.

```css
.container {
    isolation: isolate;
}
```

This is useful when you want a component's stacking behavior to remain isolated from surrounding elements.

For example:

```css
.card {
    isolation: isolate;
}

.badge {
    position: absolute;
    z-index: 10;
}
```

The card establishes an isolated stacking environment for its contents.

---

## Why `isolation` Is Useful

Consider a complex component:

```text
Page
│
├── Header
├── Main
│   │
│   └── Card
│       │
│       ├── Background
│       ├── Content
│       └── Badge
│
└── Footer
```

Adding:

```css
.card {
    isolation: isolate;
}
```

can help keep the card's stacking behavior isolated from surrounding content.

This is especially useful for reusable UI components.

> 💡 **Pro Tip:** `isolation: isolate` can be a clean way to establish a component-level stacking context without relying on a large `z-index` value.

---

## Other Ways to Create Stacking Contexts

Several other CSS features can also establish stacking contexts.

Common examples include:

- Positioned elements with a non-`auto` `z-index`
- `position: fixed`
- `position: sticky`
- `opacity` less than `1`
- `transform` other than `none`
- `filter` other than `none`
- `isolation: isolate`
- Certain `mix-blend-mode` values
- Certain containment properties

The exact conditions are defined by CSS specifications and can be more detailed than this list.

---

## Example of Multiple Stacking Contexts

Consider:

```css
.header {
    position: relative;
    z-index: 10;
}

.card {
    position: relative;
    z-index: 5;
}

.modal {
    position: fixed;
    z-index: 100;
}
```

The page can contain several stacking contexts:

```text
Root
│
├── Header
│   z-index: 10
│
├── Card
│   z-index: 5
│
└── Modal
    z-index: 100
```

The browser compares these stacking contexts according to their position in the stacking hierarchy.

---

## Accidental Stacking Contexts

A stacking context is not always created intentionally.

For example:

```css
.card {
    transform: translateY(0);
}
```

Even though the transform does not visually move the element, the presence of a transform can affect stacking behavior.

Similarly:

```css
.card {
    opacity: 0.99;
}
```

can create a stacking context.

This can sometimes explain why a previously working `z-index` stops behaving as expected after a CSS change.

> ⚠️ **Important:** When debugging a layering issue, check for CSS properties that may have unintentionally created a stacking context.

---

## Example: Unexpected `z-index` Behavior

Suppose:

```css
.parent {
    transform: translateZ(0);
}

.child {
    position: relative;
    z-index: 9999;
}
```

The transform on `.parent` can create a stacking context.

The child is therefore constrained by the parent's stacking environment.

```text
Root
│
└── Parent
    │
    └── Child
        z-index: 9999
```

The child's large value does not make it globally higher than elements outside the parent's stacking context.

---

## Stacking Context Checklist

When an element appears in an unexpected layer, check:

```text
Does the element have z-index?
        ↓
Does a parent have z-index?
        ↓
Is the parent positioned?
        ↓
Is there a transform?
        ↓
Is opacity less than 1?
        ↓
Is there a filter?
        ↓
Is isolation being used?
        ↓
Is the element fixed or sticky?
        ↓
Which stacking context contains the element?
```

This helps identify the actual source of the layering problem.

---

## Common Mistake

A common mistake is to keep increasing `z-index`:

```css
z-index: 100;
```

then:

```css
z-index: 1000;
```

then:

```css
z-index: 9999;
```

and finally:

```css
z-index: 999999;
```

If the element is trapped inside a lower stacking context, increasing the number will not solve the underlying problem.

The correct approach is to inspect the stacking context hierarchy.

---

## Practical Example

```html
<div class="page">
    <div class="card">
        <div class="badge">New</div>
        <h2>Product</h2>
    </div>
</div>
```

```css
.page {
    position: relative;
}

.card {
    isolation: isolate;
    position: relative;
}

.badge {
    position: absolute;
    top: 10px;
    right: 10px;
    z-index: 10;
}
```

The structure becomes:

```text
Page
│
└── Card
    │
    └── Badge
        z-index: 10
```

The card provides an isolated stacking context, while the badge is layered inside it.

---

## Common Stacking Context Triggers

| CSS Feature | Can Create Stacking Context |
|--------------|-----------------------------|
| Positioned + non-`auto` `z-index` | ✅ |
| `position: fixed` | ✅ |
| `position: sticky` | ✅ |
| `opacity < 1` | ✅ |
| `transform` other than `none` | ✅ |
| `filter` other than `none` | ✅ |
| `isolation: isolate` | ✅ |

---

> 💡 **Remember:** Stacking contexts can be created intentionally with properties such as `z-index` and `isolation`, but they can also be created indirectly by properties such as `opacity`, `transform`, and `filter`. When `z-index` behaves unexpectedly, always inspect the **stacking context hierarchy**.