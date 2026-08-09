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