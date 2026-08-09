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