## Table of Contents

1. [Introduction](#introduction)
2. [What Is Flexbox?](#what-is-flexbox)
3. [Why Is Flexbox Important?](#why-is-flexbox-important)
4. [Flex Container and Flex Items](#flex-container-and-flex-items)
5. [Creating a Flex Container](#creating-a-flex-container)
6. [Flex Direction](#flex-direction)
7. [Main Axis and Cross Axis](#main-axis-and-cross-axis)
8. [Flex Wrap](#flex-wrap)
9. [Flex Flow](#flex-flow)
10. [Justify Content](#justify-content)
11. [Align Items](#align-items)
12. [Align Content](#align-content)
13. [Gap](#gap)
14. [Row Gap and Column Gap](#row-gap-and-column-gap)
15. [Flex Item Properties](#flex-item-properties)
16. [Order](#order)
17. [Flex Grow](#flex-grow)
18. [Flex Shrink](#flex-shrink)
19. [Flex Basis](#flex-basis)
20. [Flex Shorthand](#flex-shorthand)
21. [Align Self](#align-self)
22. [Nested Flex Containers](#nested-flex-containers)
23. [Centering with Flexbox](#centering-with-flexbox)
24. [Common Flexbox Layouts](#common-flexbox-layouts)
25. [Flexbox vs Grid](#flexbox-vs-grid)
26. [Common Use Cases](#common-use-cases)
27. [Key Takeaways](#key-takeaways)
28. [References](#references)
29. [Quick Revision](#quick-revision)
30. [Best Practices](#best-practices)
31. [Common Mistakes](#common-mistakes)
32. [Interview Questions](#interview-questions)
33. [Practice Exercises](#practice-exercises)
34. [Related Topics](#related-topics)

---

# Introduction

**Flexbox**, short for **Flexible Box Layout**, is a CSS layout system designed to arrange elements efficiently within a container.

It provides a convenient way to control:

- The direction of elements
- Alignment
- Spacing
- Distribution of available space
- Sizing of elements
- Responsive layouts

A basic Flexbox container is created using:

```css
.container {
    display: flex;
}
```

When an element becomes a flex container, its **direct children** become flex items.

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

The structure becomes:

```text
Flex Container
      │
      ├── Flex Item
      ├── Flex Item
      └── Flex Item
```

---

## Why Was Flexbox Introduced?

Before Flexbox, developers commonly used techniques such as:

- Floats
- Inline-block
- Tables
- Positioning

These techniques could make common layout tasks unnecessarily complicated.

For example, vertically and horizontally centering an element often required additional CSS techniques.

Flexbox provides dedicated properties for these types of layout problems.

---

## One-Dimensional Layout

Flexbox is primarily a **one-dimensional layout system**.

This means it handles layout in one direction at a time:

```text
Horizontal
→ Row

Vertical
→ Column
```

For example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

arranges items horizontally.

While:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

arranges items vertically.

---

## Basic Visual Example

With:

```css
.container {
    display: flex;
}
```

the default layout is:

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│ Item 1  │  │ Item 2  │  │ Item 3  │
└─────────┘  └─────────┘  └─────────┘
```

With:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

the layout becomes:

```text
┌─────────┐
│ Item 1  │
└─────────┘
     ↓
┌─────────┐
│ Item 2  │
└─────────┘
     ↓
┌─────────┐
│ Item 3  │
└─────────┘
```

---

## Flexbox Is Controlled by the Parent

One important concept is that many Flexbox properties are applied to the **parent container**.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

These properties control how the child elements are positioned and aligned within the container.

Individual flex items also have their own properties, which will be covered later.

---

## Common Uses of Flexbox

Flexbox is commonly used for:

- Navigation bars
- Button groups
- Card layouts
- Toolbars
- Form layouts
- Headers
- Footers
- Centering content
- Aligning icons and text
- Responsive components

---

> 💡 **Pro Tip:** Don't try to memorize every Flexbox property at once. First understand the relationship between the **container and its items**, then learn how the main axis and cross axis control their layout.

---

> 💡 **Remember:** `display: flex` turns an element into a **flex container**, and its direct children become **flex items**. Flexbox is designed primarily for arranging items in a single direction at a time.

---

# What Is Flexbox?

**Flexbox** is a CSS layout model that provides a flexible way to arrange elements inside a container.

It is designed to make it easier to control the:

- Direction of elements
- Alignment of elements
- Distribution of available space
- Size of elements
- Spacing between elements

Flexbox is especially useful when elements need to adapt to the available space.

---

## Flex Container

The element on which Flexbox is enabled is called the **flex container**.

A flex container is created using:

```css
.container {
    display: flex;
}
```

Example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

Here:

```text
.container
    ↓
Flex Container
```

---

## Flex Items

The **direct children** of a flex container automatically become **flex items**.

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```text
Flex Container
      │
      ├── Item 1 → Flex Item
      ├── Item 2 → Flex Item
      └── Item 3 → Flex Item
```

You do not need to add a separate property to the children to make them flex items.

Simply using:

```css
display: flex;
```

on the parent is enough.

---

## Only Direct Children Become Flex Items

Consider:

```html
<div class="container">
    <div class="item">
        <span>Text</span>
    </div>
</div>
```

If:

```css
.container {
    display: flex;
}
```

then:

```text
.container
    ↓
Flex Container

.item
    ↓
Flex Item

span
    ↓
Not a flex item of .container
```

The `<span>` is a descendant of the flex container, but it is not its direct child.

This distinction is important when working with nested layouts.

---

## Flexbox Is One-Dimensional

Flexbox is primarily a **one-dimensional layout system**.

It works along one main direction at a time:

```text
Row
→ Horizontal layout

Column
→ Vertical layout
```

For example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

creates a horizontal layout.

While:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

creates a vertical layout.

---

## Default Flexbox Direction

When only:

```css
display: flex;
```

is specified, Flexbox uses:

```css
flex-direction: row;
```

Therefore:

```css
.container {
    display: flex;
}
```

is equivalent to:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

The items are placed along the horizontal main axis.

```text
Item 1 → Item 2 → Item 3
────────────────────────→
       Main Axis
```

---

## Flexbox Layout Model

A basic Flexbox layout can be visualized as:

```text
┌─────────────────────────────────────┐
│          Flex Container             │
│                                     │
│  ┌───────┐  ┌───────┐  ┌───────┐   │
│  │ Item 1│  │ Item 2│  │ Item 3│   │
│  └───────┘  └───────┘  └───────┘   │
│                                     │
└─────────────────────────────────────┘
```

The container controls how its flex items are laid out.

---

## Flex Container Properties

Many important Flexbox properties are applied to the container.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

These properties control the arrangement of the flex items.

Common container properties include:

```css
display
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
gap
```

---

## Flex Item Properties

Individual flex items can also have their own Flexbox properties.

For example:

```css
.item {
    flex-grow: 1;
}
```

Common item properties include:

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

This gives Flexbox two levels of control:

```text
Flex Container
      ↓
Controls overall layout

Flex Items
      ↓
Controls individual items
```

---

## Flexbox and Available Space

One of the main strengths of Flexbox is its ability to distribute available space.

For example:

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

The available space is distributed between the flex items.

```text
┌─────────────────────────────────────┐
│ Item 1          Item 2          Item 3│
└─────────────────────────────────────┘
```

This makes Flexbox useful for layouts where spacing needs to adapt to different container sizes.

---

## Flexbox Does Not Mean "Everything Is Automatically Responsive"

Flexbox provides flexible layout behavior, but a responsive design may still require:

- Flexible widths
- `flex-wrap`
- Media queries
- Relative units
- Minimum and maximum sizes

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

allows items to move onto additional lines when necessary.

---

> 💡 **Pro Tip:** Remember the basic relationship:

```text
display: flex
      ↓
Parent becomes Flex Container
      ↓
Direct children become Flex Items
      ↓
Flexbox controls their layout
```

Once this relationship is clear, the rest of Flexbox becomes much easier to understand.

---

> 💡 **Remember:** Flexbox is not a property applied to individual elements independently. It establishes a **layout context on a parent**, which controls the arrangement of its direct children.

---

# Why Is Flexbox Important?

Flexbox is important because it provides a dedicated system for creating **flexible, efficient, and responsive one-dimensional layouts**.

Instead of relying on older layout techniques or complicated positioning, Flexbox provides properties specifically designed for controlling the relationship between a container and its items.

---

## 1. Makes Alignment Easier

One of the biggest advantages of Flexbox is that it makes alignment much easier.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This can center an item horizontally and vertically within the flex container.

```text
┌──────────────────────────────┐
│                              │
│                              │
│          ┌────────┐          │
│          │  Item  │          │
│          └────────┘          │
│                              │
│                              │
└──────────────────────────────┘
```

Without Flexbox, achieving this kind of alignment often required more complicated CSS.

---

## 2. Controls Space Distribution

Flexbox provides properties for distributing available space between items.

For example:

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

The first item is placed at the beginning, the last item at the end, and the remaining space is distributed between them.

```text
┌──────────────────────────────────────┐
│ Item 1          Item 2          Item 3│
└──────────────────────────────────────┘
```

This is particularly useful for navigation bars and headers.

---

## 3. Supports Flexible Sizing

Flexbox allows items to grow or shrink based on the available space.

For example:

```css
.item {
    flex-grow: 1;
}
```

Items can use available space instead of requiring fixed dimensions.

This makes layouts more flexible when the container changes size.

---

## 4. Makes Responsive Layouts Easier

Flexbox can adapt to different container sizes.

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

When there is not enough horizontal space, items can move onto another line.

```text
Large screen:

┌────┐ ┌────┐ ┌────┐ ┌────┐
│ 1  │ │ 2  │ │ 3  │ │ 4  │
└────┘ └────┘ └────┘ └────┘


Smaller screen:

┌────┐ ┌────┐
│ 1  │ │ 2  │
└────┘ └────┘

┌────┐ ┌────┐
│ 3  │ │ 4  │
└────┘ └────┘
```

This behavior is useful for responsive components.

---

## 5. Reduces the Need for Positioning

Many layouts that might otherwise be created using:

```css
position
top
left
right
bottom
```

can be handled more naturally using Flexbox.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This is generally more appropriate for normal layout alignment than manually positioning elements.

---

## 6. Provides Clear Layout Control

Flexbox separates layout responsibilities into meaningful properties.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}
```

Each property has a specific purpose:

```text
flex-direction
→ Direction of the layout

justify-content
→ Distribution along the main axis

align-items
→ Alignment along the cross axis

gap
→ Space between items
```

This makes the layout easier to understand and maintain.

---

## 7. Useful for Common UI Components

Many everyday UI components can be built naturally with Flexbox.

### Navigation Bar

```css
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

### Button Group

```css
.buttons {
    display: flex;
    gap: 10px;
}
```

### Card Row

```css
.cards {
    display: flex;
    gap: 20px;
}
```

### Header

```css
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

---

## 8. Works Well with Different Content Sizes

Flexbox does not require every item to have exactly the same size.

For example:

```html
<div class="container">
    <div>Short</div>
    <div>This is a longer item</div>
    <div>Medium content</div>
</div>
```

Flexbox can arrange these items while taking their different sizes into account.

This is useful for real-world content where text and element sizes are not always predictable.

---

## 9. Makes Spacing More Consistent

The `gap` property provides a simple way to create consistent spacing between flex items.

```css
.container {
    display: flex;
    gap: 20px;
}
```

Instead of manually adding margins to individual children, the container can define the spacing.

```text
Item 1    20px    Item 2    20px    Item 3
```

---

## 10. Improves Maintainability

Flexbox layouts can often be expressed with a small number of clear properties.

For example:

```css
.container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}
```

The intent of the layout is easy to understand.

This can make CSS easier to read, modify, and maintain.

---

## Flexbox Compared with Older Layout Techniques

Before Flexbox, developers commonly used techniques such as:

```text
Floats
Inline-block
Tables
Absolute positioning
```

These approaches still have valid uses, but Flexbox provides a layout system specifically designed for flexible alignment and distribution.

A simplified comparison:

| Technique | Common Purpose |
|-----------|----------------|
| Float | Older page/content layouts |
| Inline-block | Inline element layouts |
| Positioning | Precise positioning |
| Flexbox | One-dimensional layouts |
| Grid | Two-dimensional layouts |

---

## Flexbox Is Not a Replacement for Everything

Flexbox is powerful, but it is not the best solution for every layout.

Use Flexbox when the layout is primarily:

```text
One direction
    ↓
Row or Column
```

For layouts requiring simultaneous control over:

```text
Rows
+
Columns
```

CSS Grid may be more appropriate.

---

> 💡 **Pro Tip:** Don't use Flexbox simply because it is available. First identify the layout problem. If you need to arrange and align items along one main direction, Flexbox is usually a strong choice.

---

> 💡 **Remember:** Flexbox is important because it turns common layout problems—**alignment, spacing, distribution, sizing, and responsive arrangement**—into problems that can be handled directly with dedicated CSS properties.

---

# Flex Container and Flex Items

Every Flexbox layout is based on two fundamental concepts:

```text
Flex Container
      │
      ├── Flex Item
      ├── Flex Item
      └── Flex Item
```

The **flex container** is the parent element on which Flexbox is enabled.

The **flex items** are its direct children.

---

## Flex Container

A **flex container** is an element whose `display` property is set to:

```css
display: flex;
```

Example:

```css
.container {
    display: flex;
}
```

The element now establishes a Flexbox formatting context for its direct children.

---

## Flex Items

The direct children of a flex container become **flex items** automatically.

Example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

The result is:

```text
.container
     ↓
Flex Container
     │
     ├── Item 1 → Flex Item
     ├── Item 2 → Flex Item
     └── Item 3 → Flex Item
```

No `display: flex` declaration is required on the children.

---

## Direct Children Only

An important rule is that **only direct children** become flex items.

Consider:

```html
<div class="container">
    <div class="item">
        <span>Text</span>
    </div>
</div>
```

```css
.container {
    display: flex;
}
```

Here:

```text
.container
    ↓
Flex Container

.item
    ↓
Flex Item

span
    ↓
Not a flex item of .container
```

The `<span>` can become a flex item if `.item` itself becomes a flex container:

```css
.item {
    display: flex;
}
```

Now there are two Flexbox contexts:

```text
.container
    ↓
Flex Container
    │
    └── .item
          ↓
       Flex Container
          │
          └── span
                ↓
             Flex Item
```

---

## A Flex Container Can Also Be a Flex Item

An element can be both:

- A flex item of its parent
- A flex container for its own children

Example:

```html
<div class="outer">
    <div class="inner">
        <span>Content</span>
    </div>
</div>
```

```css
.outer {
    display: flex;
}

.inner {
    display: flex;
}
```

The relationship is:

```text
.outer
  ↓
Flex Container
  │
  └── .inner
        ↓
     Flex Item
     +
     Flex Container
        │
        └── span
              ↓
           Flex Item
```

This is useful for creating **nested Flexbox layouts**.

---

## Default Arrangement

When a flex container is created:

```css
.container {
    display: flex;
}
```

its direct children are arranged in a row by default.

```text
┌─────────────────────────────────────┐
│                                     │
│  ┌─────┐  ┌─────┐  ┌─────┐          │
│  │  1  │  │  2  │  │  3  │          │
│  └─────┘  └─────┘  └─────┘          │
│                                     │
└─────────────────────────────────────┘
```

This happens because the default value of:

```css
flex-direction
```

is:

```css
row
```

---

## Container Controls the Layout

Many Flexbox properties are applied to the container.

Example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

These properties control how the flex items are arranged.

The items themselves can also have Flexbox-specific properties.

For example:

```css
.item {
    flex-grow: 1;
}
```

This gives Flexbox two levels of control:

```text
Container
   ↓
Controls overall arrangement

Items
   ↓
Controls individual behavior
```

---

## Normal CSS Properties Still Work

Flex items are still normal CSS elements.

You can apply properties such as:

```css
.item {
    width: 100px;
    padding: 20px;
    margin: 10px;
    background-color: lightblue;
}
```

Flexbox adds additional layout behavior on top of normal CSS.

---

## Flex Container vs Flex Item

| Concept | Flex Container | Flex Item |
|---------|----------------|------------|
| Created by | `display: flex` | Automatically |
| Usually represents | Parent | Direct child |
| Controls children | Yes | No, not its siblings |
| Can use container properties | Yes | No |
| Can use item properties | It can also be an item if nested | Yes |
| Main purpose | Controls layout | Participates in layout |

---

## Example

```html
<div class="container">
    <div class="item">One</div>
    <div class="item">Two</div>
    <div class="item">Three</div>
</div>
```

```css
.container {
    display: flex;
}

.item {
    padding: 20px;
}
```

The parent creates the Flexbox layout:

```text
┌─────────────────────────────────────┐
│ Container                           │
│                                     │
│  ┌───────┐  ┌───────┐  ┌───────┐   │
│  │ One   │  │ Two   │  │ Three │   │
│  └───────┘  └───────┘  └───────┘   │
│                                     │
└─────────────────────────────────────┘
```

---

> 💡 **Pro Tip:** When debugging a Flexbox layout, first identify **which element is the flex container**. Then identify its **direct children**. Most Flexbox properties make sense once you know exactly which container they belong to.

---

> 💡 **Remember:** `display: flex` creates the **flex container**, while its **direct children automatically become flex items**. A flex container can also be a flex item if it is itself a child of another flex container.

---

# Creating a Flex Container

To use Flexbox, an element must first be turned into a **flex container**.

This is done using:

```css
display: flex;
```

---

## Basic Syntax

```css
.container {
    display: flex;
}
```

Once `display: flex` is applied, the element becomes a flex container.

Its direct children automatically become flex items.

```text
.container
     ↓
Flex Container
     │
     ├── Item 1 → Flex Item
     ├── Item 2 → Flex Item
     └── Item 3 → Flex Item
```

---

## Basic Example

```html
<div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

By default, the items are arranged in a row:

```text
┌─────────────────────────────────────┐
│                                     │
│  ┌───────┐  ┌───────┐  ┌───────┐   │
│  │ Item 1│  │ Item 2│  │ Item 3│   │
│  └───────┘  └───────┘  └───────┘   │
│                                     │
└─────────────────────────────────────┘
```

---

## What Changes When `display: flex` Is Applied?

Before Flexbox, block-level elements normally stack vertically.

```text
┌─────────┐
│ Item 1  │
└─────────┘

┌─────────┐
│ Item 2  │
└─────────┘

┌─────────┐
│ Item 3  │
└─────────┘
```

After:

```css
.container {
    display: flex;
}
```

the direct children are laid out according to Flexbox.

By default:

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│ Item 1  │  │ Item 2  │  │ Item 3  │
└─────────┘  └─────────┘  └─────────┘
```

This happens because the default `flex-direction` is:

```css
row
```

---

## `display: flex` vs `display: block`

Consider:

```html
<div class="container">
    <div>One</div>
    <div>Two</div>
    <div>Three</div>
</div>
```

Without Flexbox:

```css
.container {
    display: block;
}
```

The children follow the normal block layout.

With:

```css
.container {
    display: flex;
}
```

the children become flex items and participate in the Flexbox layout.

```text
display: block
→ Normal block layout

display: flex
→ Flexbox layout
```

---

## Flex Container Is Still a Normal Element

Making an element a flex container does not remove its normal CSS properties.

You can still use:

```css
.container {
    width: 500px;
    height: 300px;
    padding: 20px;
    border: 1px solid black;
    background-color: lightgray;
    display: flex;
}
```

Flexbox controls how the children are laid out inside the container.

---

## Adding a Gap

A common pattern is to combine Flexbox with `gap`.

```css
.container {
    display: flex;
    gap: 20px;
}
```

This creates space between the flex items.

```text
Item 1
   ↓
  20px
   ↓
Item 2
   ↓
  20px
   ↓
Item 3
```

The `gap` property will be covered in more detail later.

---

## Creating a Column Layout

Although the default direction is a row, the container can be changed to a column.

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Result:

```text
┌─────────┐
│ Item 1  │
└─────────┘
     ↓
┌─────────┐
│ Item 2  │
└─────────┘
     ↓
┌─────────┐
│ Item 3  │
└─────────┘
```

The `flex-direction` property will be covered separately.

---

## Flex Container Establishes a Flex Formatting Context

When:

```css
display: flex;
```

is applied, the element establishes a **flex formatting context** for its contents.

Its direct children are laid out as flex items instead of following the normal layout behavior of the parent.

This is what enables Flexbox properties such as:

```css
justify-content
align-items
flex-wrap
gap
```

to control the layout.

---

## Inline Flex Container

CSS also provides:

```css
display: inline-flex;
```

This creates an **inline-level flex container**.

Example:

```css
.container {
    display: inline-flex;
}
```

The element itself participates in the surrounding inline layout, while its children are still laid out using Flexbox.

Compare:

```text
display: flex
→ Block-level flex container

display: inline-flex
→ Inline-level flex container
```

Both create Flexbox layouts for their children.

---

## `flex` vs `inline-flex`

Example:

```css
.block-container {
    display: flex;
}
```

and:

```css
.inline-container {
    display: inline-flex;
}
```

The main difference is how the **container itself participates in the surrounding layout**.

The children of both containers are still flex items.

---

## Example with `inline-flex`

```html
<div class="container">
    <span>One</span>
    <span>Two</span>
</div>

<div class="container">
    <span>Three</span>
    <span>Four</span>
</div>
```

```css
.container {
    display: inline-flex;
}
```

The containers can participate alongside other inline-level content.

---

## Common Pattern

A very common Flexbox setup is:

```css
.container {
    display: flex;
    gap: 20px;
    align-items: center;
}
```

This means:

```text
display: flex
→ Enable Flexbox

gap
→ Add space between items

align-items
→ Control cross-axis alignment
```

Additional properties can then be added depending on the layout requirements.

---

> 💡 **Pro Tip:** When starting a Flexbox layout, begin with the smallest useful declaration:

```css
.container {
    display: flex;
}
```

Then add properties such as `flex-direction`, `justify-content`, `align-items`, and `gap` only when the layout actually requires them. This keeps the CSS easier to understand and debug.

---

> 💡 **Remember:** `display: flex` is the declaration that creates a **flex container**. Its direct children become **flex items**, and the container can then control their direction, alignment, spacing, and distribution.

---

# Flex Direction

The `flex-direction` property controls the **direction in which flex items are placed** inside a flex container.

```css
.container {
    display: flex;
    flex-direction: row;
}
```

The default value is:

```css
row
```

---

## Syntax

```css
.container {
    display: flex;
    flex-direction: value;
}
```

The `flex-direction` property accepts four values:

```text
row
row-reverse
column
column-reverse
```

---

## `row`

The default value is:

```css
flex-direction: row;
```

Items are arranged from left to right in a left-to-right writing mode.

```text
┌────────┐  ┌────────┐  ┌────────┐
│ Item 1 │  │ Item 2 │  │ Item 3 │
└────────┘  └────────┘  └────────┘
      ────────────────────────→
            Main Axis
```

Example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

This is the same as:

```css
.container {
    display: flex;
}
```

because `row` is the default value.

---

## `row-reverse`

The `row-reverse` value reverses the direction of the row.

```css
.container {
    display: flex;
    flex-direction: row-reverse;
}
```

The items are placed in the opposite direction of `row`.

```text
┌────────┐  ┌────────┐  ┌────────┐
│ Item 3 │  │ Item 2 │  │ Item 1 │
└────────┘  └────────┘  └────────┘
←────────────────────────
        Main Axis
```

The visual order is reversed.

---

## `column`

The `column` value arranges items vertically.

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Result:

```text
┌────────┐
│ Item 1 │
└────────┘
     ↓
┌────────┐
│ Item 2 │
└────────┘
     ↓
┌────────┐
│ Item 3 │
└────────┘
```

The main axis is now vertical.

```text
Main Axis
    ↓
    ↓
    ↓
```

---

## `column-reverse`

The `column-reverse` value reverses the vertical direction.

```css
.container {
    display: flex;
    flex-direction: column-reverse;
}
```

Result:

```text
┌────────┐
│ Item 3 │
└────────┘
     ↑
┌────────┐
│ Item 2 │
└────────┘
     ↑
┌────────┐
│ Item 1 │
└────────┘
```

The items are arranged in the reverse direction of `column`.

---

## Comparing the Four Values

| Value | Direction | Main Axis |
|-------|-----------|-----------|
| `row` | Horizontal | Left → Right |
| `row-reverse` | Horizontal reversed | Right → Left |
| `column` | Vertical | Top → Bottom |
| `column-reverse` | Vertical reversed | Bottom → Top |

The exact visual direction can also be affected by the document's writing mode and direction.

---

## `row` Example

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>
```

```css
.container {
    display: flex;
    flex-direction: row;
}
```

Result:

```text
1 → 2 → 3
```

---

## `row-reverse` Example

```css
.container {
    display: flex;
    flex-direction: row-reverse;
}
```

Result:

```text
3 → 2 → 1
```

The items are visually arranged in the reverse direction.

---

## `column` Example

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Result:

```text
1
↓
2
↓
3
```

---

## `column-reverse` Example

```css
.container {
    display: flex;
    flex-direction: column-reverse;
}
```

Result:

```text
3
↑
2
↑
1
```

---

## Flex Direction Changes the Main Axis

The `flex-direction` property is important because it determines the **main axis**.

With:

```css
flex-direction: row;
```

the main axis is horizontal.

```text
────────────────────→
     Main Axis
```

With:

```css
flex-direction: column;
```

the main axis is vertical.

```text
     Main Axis
          ↓
          ↓
          ↓
```

This is important when using properties such as:

```css
justify-content
align-items
```

because their behavior is based on the flex container's axes.

---

## `flex-direction` and `justify-content`

`justify-content` operates along the **main axis**.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
}
```

The items are centered horizontally.

```text
┌──────────────────────────────┐
│       1   2   3              │
└──────────────────────────────┘
```

If the direction changes:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```

the same `justify-content: center` centers the items along the vertical main axis.

```text
┌──────────────────────────────┐
│                              │
│          1                   │
│          2                   │
│          3                   │
│                              │
└──────────────────────────────┘
```

This is why understanding the main axis is essential when working with Flexbox.

---

## `flex-direction` and `align-items`

`align-items` operates along the **cross axis**.

For:

```css
flex-direction: row;
```

the cross axis is vertical.

For:

```css
flex-direction: column;
```

the cross axis is horizontal.

Therefore, changing `flex-direction` changes how these alignment properties behave.

---

## Reversing Direction vs Changing HTML Order

Consider:

```html
<div>1</div>
<div>2</div>
<div>3</div>
```

Using:

```css
flex-direction: row-reverse;
```

changes the visual direction without changing the HTML source order.

```text
HTML order:

1 → 2 → 3

Visual arrangement:

3 → 2 → 1
```

This distinction can be important for accessibility and logical document structure.

For many layouts, it is preferable to keep meaningful content in a logical HTML order and use CSS for presentation.

---

## Common Use Cases

### Horizontal Navigation

```css
.nav {
    display: flex;
    flex-direction: row;
}
```

### Vertical Menu

```css
.menu {
    display: flex;
    flex-direction: column;
}
```

### Reversing a Layout

```css
.container {
    display: flex;
    flex-direction: row-reverse;
}
```

### Reversing a Vertical Layout

```css
.container {
    display: flex;
    flex-direction: column-reverse;
}
```

---

## Important Difference

`flex-direction` does **not** determine whether an element is a flex container.

This:

```css
.container {
    display: flex;
}
```

creates the Flexbox layout.

This:

```css
.container {
    flex-direction: column;
}
```

controls the direction of that layout.

Therefore, a common combination is:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

---

> 💡 **Pro Tip:** When a Flexbox alignment property seems to behave unexpectedly, check `flex-direction` first. The main axis and cross axis depend on the direction of the flex container.

---

> 💡 **Remember:** `flex-direction` controls the direction of the flex items and determines the **main axis**. Its four values are `row`, `row-reverse`, `column`, and `column-reverse`.

---

# Main Axis and Cross Axis

Flexbox layouts are based on two axes:

```text
Main Axis
Cross Axis
```

Understanding these axes is essential because Flexbox alignment properties work relative to them.

The direction of these axes depends on the value of:

```css
flex-direction
```

---

## Main Axis

The **main axis** is the primary direction in which flex items are laid out.

For example, with:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

the main axis is horizontal.

```text
Item 1 → Item 2 → Item 3
────────────────────────→
        Main Axis
```

With:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

the main axis becomes vertical.

```text
        Main Axis
             ↓
             ↓
             ↓
```

---

## Cross Axis

The **cross axis** is perpendicular to the main axis.

When:

```css
flex-direction: row;
```

the main axis is horizontal and the cross axis is vertical.

```text
             Cross Axis
                  ↓
                  ↓
                  ↓

Item 1    Item 2    Item 3
────────────────────────────→
          Main Axis
```

When:

```css
flex-direction: column;
```

the main axis is vertical and the cross axis is horizontal.

```text
        Cross Axis
    ←────────────────→

         Item 1
            ↓
         Item 2
            ↓
         Item 3

        Main Axis
```

---

## Axes Depend on `flex-direction`

The relationship between the axes changes depending on the flex direction.

### `row`

```css
flex-direction: row;
```

```text
Main Axis   → Horizontal
Cross Axis  ↓ Vertical
```

### `row-reverse`

```css
flex-direction: row-reverse;
```

```text
Main Axis   ← Horizontal
Cross Axis  ↓ Vertical
```

### `column`

```css
flex-direction: column;
```

```text
Main Axis   ↓ Vertical
Cross Axis  → Horizontal
```

### `column-reverse`

```css
flex-direction: column-reverse;
```

```text
Main Axis   ↑ Vertical
Cross Axis  → Horizontal
```

---

## Visual Comparison

```text
flex-direction: row

Cross Axis
    ↓
    ↓
    ↓
┌──────────────────────────────┐
│  1    2    3                 │
└──────────────────────────────┘
──────────────────────────────→
          Main Axis
```

```text
flex-direction: column

       Cross Axis
←────────────────────→

┌─────────┐
│    1    │
└─────────┘
     ↓
┌─────────┐
│    2    │
└─────────┘
     ↓
┌─────────┐
│    3    │
└─────────┘

     Main Axis
```

---

## Why Are the Axes Important?

Flexbox properties such as:

```css
justify-content
align-items
align-content
```

use the flex container's axes to determine how items are positioned.

For example:

```css
.container {
    display: flex;
    justify-content: center;
}
```

`justify-content` aligns items along the **main axis**.

Therefore, changing:

```css
flex-direction: row;
```

to:

```css
flex-direction: column;
```

changes the direction in which `justify-content` operates.

---

## `justify-content` and the Main Axis

With:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
}
```

the items are centered horizontally.

```text
┌──────────────────────────────┐
│                              │
│        1   2   3             │
│                              │
└──────────────────────────────┘
```

The main axis is horizontal, so `justify-content` works horizontally.

Now change the direction:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```

The main axis becomes vertical.

Therefore, `justify-content` now centers the items vertically.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

---

## `align-items` and the Cross Axis

`align-items` operates along the **cross axis**.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    align-items: center;
}
```

Since the cross axis is vertical, the items are centered vertically.

```text
┌──────────────────────────────┐
│                              │
│      1    2    3             │
│                              │
└──────────────────────────────┘
```

If the direction changes:

```css
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

the cross axis becomes horizontal.

The items are therefore centered horizontally.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

---

## The Most Important Rule

A useful way to remember Flexbox axes is:

```text
justify-content
        ↓
Main Axis

align-items
        ↓
Cross Axis
```

And:

```text
flex-direction
        ↓
Determines the Main Axis
        ↓
Cross Axis is perpendicular to it
```

---

## Complete Example

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
```

Here:

```text
display: flex
    ↓
Creates Flexbox

flex-direction: row
    ↓
Main Axis = Horizontal
Cross Axis = Vertical

justify-content: center
    ↓
Centers items on Main Axis

align-items: center
    ↓
Centers items on Cross Axis
```

Result:

```text
┌──────────────────────────────┐
│                              │
│          1   2   3           │
│                              │
└──────────────────────────────┘
```

---

## Common Mistake

A common mistake is memorizing:

```text
justify-content = horizontal
align-items = vertical
```

This is **not always true**.

These properties are based on the **main and cross axes**, not permanently on horizontal and vertical directions.

For example:

```css
flex-direction: column;
```

changes the main axis to vertical.

Therefore:

```css
justify-content
```

also operates vertically.

---

## Quick Reference

| `flex-direction` | Main Axis | Cross Axis |
|-------------------|-----------|------------|
| `row` | Horizontal | Vertical |
| `row-reverse` | Horizontal | Vertical |
| `column` | Vertical | Horizontal |
| `column-reverse` | Vertical | Horizontal |

---

> 💡 **Pro Tip:** Never memorize `justify-content` as "horizontal" and `align-items` as "vertical." Instead, remember **`justify-content` follows the main axis** and **`align-items` follows the cross axis**.

---

> 💡 **Remember:** `flex-direction` determines the **main axis**, while the **cross axis** is perpendicular to it. Flexbox alignment properties work according to these axes.

---

# Flex Wrap

By default, Flexbox tries to place all flex items on a **single line**.

The `flex-wrap` property controls whether flex items are allowed to move onto multiple lines when there is not enough available space.

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

---

## Default Behavior

The default value of `flex-wrap` is:

```css
nowrap
```

This means flex items remain on a single line.

```css
.container {
    display: flex;
    flex-wrap: nowrap;
}
```

Result:

```text
┌──────────────────────────────────────────┐
│  1    2    3    4    5    6    7       │
└──────────────────────────────────────────┘
```

If the container becomes too small, the items can become compressed or overflow depending on their sizing and the available space.

---

## `nowrap`

```css
flex-wrap: nowrap;
```

This is the default value.

All flex items remain on one flex line.

```text
Container

┌───────────────────────────────┐
│  1   2   3   4   5   6        │
└───────────────────────────────┘
```

The items do not automatically move onto another line.

---

## `wrap`

The `wrap` value allows flex items to move onto additional lines when necessary.

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

Example:

```text
┌───────────────────────────────┐
│  1    2    3                  │
│                               │
│  4    5    6                  │
└───────────────────────────────┘
```

The items remain flex items, but they can now form multiple flex lines.

---

## Basic Example

```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
</div>
```

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}

.item {
    width: 100px;
    padding: 20px;
}
```

If the container is not wide enough to hold all the items on one line, the items can wrap:

```text
┌──────────────────────────────────┐
│  ┌─────┐  ┌─────┐  ┌─────┐      │
│  │  1  │  │  2  │  │  3  │      │
│  └─────┘  └─────┘  └─────┘      │
│                                  │
│  ┌─────┐  ┌─────┐  ┌─────┐      │
│  │  4  │  │  5  │  │  6  │      │
│  └─────┘  └─────┘  └─────┘      │
└──────────────────────────────────┘
```

---

## `wrap-reverse`

The third value is:

```css
flex-wrap: wrap-reverse;
```

This also allows multiple flex lines, but the cross-axis direction of the lines is reversed.

```css
.container {
    display: flex;
    flex-wrap: wrap-reverse;
}
```

Conceptually:

```text
Normal wrap:

Line 1
Line 2
Line 3
   ↓


Wrap reverse:

Line 3
Line 2
Line 1
```

The exact visual direction depends on the flex direction and writing mode.

---

## Comparing the Values

| Value | Behavior |
|-------|----------|
| `nowrap` | Keeps items on one line |
| `wrap` | Allows items to move onto multiple lines |
| `wrap-reverse` | Allows multiple lines and reverses their cross-axis direction |

---

## `flex-wrap` and Container Size

Wrapping becomes useful when the container has limited available space.

For example:

```css
.container {
    width: 400px;
    display: flex;
    flex-wrap: wrap;
}
```

If the items cannot all fit on one line, additional items can move to another line.

```text
┌──────────────────────────────┐
│  1     2     3               │
│                              │
│  4     5     6               │
└──────────────────────────────┘
```

Without wrapping:

```css
.container {
    width: 400px;
    display: flex;
    flex-wrap: nowrap;
}
```

the items are kept on one line.

---

## Wrapping Is Based on Available Space

Flexbox does not wrap simply because a certain number of items exists.

Wrapping depends on whether the items can fit within the available space.

For example:

```text
Wide container:

┌─────────────────────────────────────┐
│  1   2   3   4   5   6             │
└─────────────────────────────────────┘
```

The same items in a smaller container:

```text
┌──────────────────────┐
│  1   2   3           │
│                      │
│  4   5   6           │
└──────────────────────┘
```

This makes `flex-wrap` particularly useful for responsive layouts.

---

## `flex-wrap` With `flex-direction`

`flex-wrap` works together with `flex-direction`.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
```

The items are laid out in rows and can create additional rows.

```text
1   2   3
4   5   6
```

With:

```css
.container {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}
```

the main direction is vertical, so additional flex lines can form horizontally.

```text
1   4
2   5
3   6
```

The exact result depends on the available container dimensions.

---

## `flex-wrap` With `gap`

`flex-wrap` is commonly used together with `gap`.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

This provides consistent spacing between items and between flex lines.

```text
┌───────────────────────────────┐
│  1     2     3                │
│                               │
│  4     5     6                │
└───────────────────────────────┘
```

---

## Common Use Cases

`flex-wrap` is commonly useful for:

- Card layouts
- Product lists
- Button groups
- Tags
- Navigation elements
- Image galleries
- Responsive components

### Card Example

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

Cards can move to additional lines when the available width becomes smaller.

---

## Responsive Layout Example

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 250px;
}
```

This allows the cards to grow and shrink while also wrapping when necessary.

The `flex` property will be covered later in this chapter.

---

## `flex-wrap` Does Not Change Item Order

When normal wrapping occurs:

```css
flex-wrap: wrap;
```

items continue following their normal order.

For example:

```text
1   2   3
4   5   6
```

The order remains:

```text
1 → 2 → 3 → 4 → 5 → 6
```

Wrapping changes the layout into multiple lines; it does not by itself reorder the items.

---

## Single Line vs Multiple Lines

A useful way to think about `flex-wrap` is:

```text
nowrap
   ↓
One flex line

wrap
   ↓
Multiple flex lines allowed

wrap-reverse
   ↓
Multiple flex lines allowed
+
Cross-axis direction reversed
```

---

> 💡 **Pro Tip:** For responsive card or button layouts, `flex-wrap: wrap` is often a good starting point. Combine it with flexible item sizing and `gap` to create layouts that adapt naturally to available space.

---

> 💡 **Remember:** `flex-wrap` controls whether flex items stay on one line or are allowed to form multiple flex lines. Its three values are `nowrap`, `wrap`, and `wrap-reverse`.

---

# Flex Flow

The `flex-flow` property is a **shorthand property** that combines:

```css
flex-direction
flex-wrap
```

Instead of writing both properties separately:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
```

you can write:

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

Both produce the same Flexbox configuration.

---

## Syntax

```css
.container {
    display: flex;
    flex-flow: <flex-direction> <flex-wrap>;
}
```

The two values are:

```text
flex-direction
+
flex-wrap
```

For example:

```css
flex-flow: row wrap;
```

means:

```css
flex-direction: row;
flex-wrap: wrap;
```

---

## Basic Example

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

This means:

```text
Direction → row
Wrapping  → wrap
```

The items are arranged horizontally and can move onto additional lines when necessary.

```text
┌───────────────────────────────┐
│  1     2     3                │
│                               │
│  4     5     6                │
└───────────────────────────────┘
```

---

## `flex-flow: row nowrap`

```css
.container {
    display: flex;
    flex-flow: row nowrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
}
```

Items are arranged in a row and remain on one flex line.

---

## `flex-flow: row wrap`

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
```

Items are arranged in a row and can wrap onto additional lines.

---

## `flex-flow: row-reverse wrap`

```css
.container {
    display: flex;
    flex-flow: row-reverse wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: row-reverse;
    flex-wrap: wrap;
}
```

The items are arranged in the reverse row direction and can wrap.

---

## `flex-flow: column wrap`

```css
.container {
    display: flex;
    flex-flow: column wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}
```

The main direction is vertical, and items can form additional flex lines.

```text
1    4
2    5
3    6
```

---

## `flex-flow: column-reverse wrap`

```css
.container {
    display: flex;
    flex-flow: column-reverse wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: column-reverse;
    flex-wrap: wrap;
}
```

The items use a reversed column direction and are allowed to wrap.

---

## Order of Values

The values are normally written as:

```css
flex-flow: flex-direction flex-wrap;
```

For example:

```css
flex-flow: row wrap;
```

However, the two values can be provided in either order because the values have different allowed keywords.

For clarity and readability, the conventional order is:

```css
flex-flow: row wrap;
```

---

## Default Value

The initial value of `flex-flow` is equivalent to:

```css
flex-flow: row nowrap;
```

This means:

```css
flex-direction: row;
flex-wrap: nowrap;
```

Therefore:

```css
.container {
    display: flex;
}
```

uses the default Flexbox flow of:

```text
row
+
nowrap
```

---

## Common Combinations

### Row Without Wrapping

```css
flex-flow: row nowrap;
```

### Row With Wrapping

```css
flex-flow: row wrap;
```

### Reversed Row With Wrapping

```css
flex-flow: row-reverse wrap;
```

### Column Without Wrapping

```css
flex-flow: column nowrap;
```

### Column With Wrapping

```css
flex-flow: column wrap;
```

### Reversed Column With Wrapping

```css
flex-flow: column-reverse wrap;
```

---

## `flex-flow` vs Individual Properties

Using separate properties:

```css
.container {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}
```

Using the shorthand:

```css
.container {
    display: flex;
    flex-flow: column wrap;
}
```

The result is equivalent.

The shorthand simply provides a more compact way to specify both properties.

---

## When to Use `flex-flow`

`flex-flow` can be useful when:

- You need both `flex-direction` and `flex-wrap`.
- You want to keep related Flexbox settings together.
- You prefer concise CSS.
- The direction and wrapping behavior are clear from one declaration.

For example:

```css
.cards {
    display: flex;
    flex-flow: row wrap;
    gap: 20px;
}
```

This clearly communicates that the cards should flow horizontally and wrap when necessary.

---

## Important Difference

`flex-flow` does not replace:

```css
display: flex;
```

You still need to create the flex container.

For example:

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

Here:

```text
display: flex
    ↓
Creates the Flexbox container

flex-flow
    ↓
Controls direction + wrapping
```

---

> 💡 **Pro Tip:** Use `flex-flow` when you want to configure direction and wrapping together. If you are learning or debugging Flexbox, writing `flex-direction` and `flex-wrap` separately can sometimes make the CSS easier to understand.

---

> 💡 **Remember:** `flex-flow` is shorthand for **`flex-direction` + `flex-wrap`**.

```css
flex-flow: row wrap;
```

is equivalent to:

```css
flex-direction: row;
flex-wrap: wrap;
```

---

# Justify Content

The `justify-content` property controls how flex items are **aligned and distributed along the main axis** of a flex container.

```css
.container {
    display: flex;
    justify-content: center;
}
```

The effect of `justify-content` depends on the value of:

```css
flex-direction
```

because `flex-direction` determines the main axis.

---

## Syntax

```css
.container {
    display: flex;
    justify-content: value;
}
```

Common values include:

```text
flex-start
flex-end
center
space-between
space-around
space-evenly
```

---

## `flex-start`

The default value is:

```css
justify-content: flex-start;
```

Items are placed at the beginning of the main axis.

For a normal left-to-right `row`:

```text
┌──────────────────────────────────────┐
│  1    2    3                         │
└──────────────────────────────────────┘
→ Main Axis
```

Example:

```css
.container {
    display: flex;
    justify-content: flex-start;
}
```

---

## `flex-end`

The `flex-end` value places the items at the end of the main axis.

```css
.container {
    display: flex;
    justify-content: flex-end;
}
```

Result for a normal `row`:

```text
┌──────────────────────────────────────┐
│                         1    2    3  │
└──────────────────────────────────────┘
```

---

## `center`

The `center` value places the items together in the center of the main axis.

```css
.container {
    display: flex;
    justify-content: center;
}
```

Result:

```text
┌──────────────────────────────────────┐
│             1    2    3              │
└──────────────────────────────────────┘
```

This is one of the most commonly used values.

---

## `space-between`

The `space-between` value distributes the available space **between the items**.

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

Result:

```text
┌──────────────────────────────────────┐
│  1             2              3      │
└──────────────────────────────────────┘
```

The first item is placed at the beginning and the last item at the end.

There is no extra distributed space before the first item or after the last item.

---

## `space-around`

The `space-around` value distributes space around each item.

```css
.container {
    display: flex;
    justify-content: space-around;
}
```

Conceptually:

```text
┌──────────────────────────────────────┐
│    1        2        3               │
└──────────────────────────────────────┘
```

Each item receives space around it.

The space between two neighboring items is effectively twice the space at either outer edge.

---

## `space-evenly`

The `space-evenly` value distributes the available space so that the spaces between items and the container edges are equal.

```css
.container {
    display: flex;
    justify-content: space-evenly;
}
```

Result:

```text
┌──────────────────────────────────────┐
│     1        2        3              │
└──────────────────────────────────────┘
```

The spacing is equal:

```text
Edge
 ↓
[space] 1 [space] 2 [space] 3 [space]
                                             ↑
                                            Edge
```

---

## Comparing the Values

Consider three items:

```text
1   2   3
```

### `flex-start`

```text
1   2   3
```

Items start at the beginning.

### `flex-end`

```text
                    1   2   3
```

Items move to the end.

### `center`

```text
            1   2   3
```

Items are grouped in the center.

### `space-between`

```text
1              2              3
```

Space is placed between the items.

### `space-around`

```text
   1        2        3
```

Space is distributed around each item.

### `space-evenly`

```text
    1       2       3
```

All available spaces are equal.

---

## `justify-content` Uses the Main Axis

A very important concept is:

```text
justify-content
        ↓
Main Axis
```

For:

```css
flex-direction: row;
```

the main axis is horizontal.

Therefore:

```css
justify-content: center;
```

centers the items horizontally.

```text
┌──────────────────────────────┐
│        1   2   3             │
└──────────────────────────────┘
```

---

## With `flex-direction: column`

Now consider:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```

The main axis is now vertical.

Therefore, `justify-content` centers the items vertically.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

This is why `justify-content` should not simply be remembered as "horizontal alignment."

It always works along the **main axis**.

---

## `justify-content` With `row`

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}
```

Result:

```text
┌──────────────────────────────────────┐
│  1              2              3     │
└──────────────────────────────────────┘
```

The main axis is horizontal.

---

## `justify-content` With `column`

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
```

Result:

```text
┌──────────────────────┐
│ 1                    │
│                      │
│ 2                    │
│                      │
│ 3                    │
└──────────────────────┘
```

The main axis is vertical, so the available space is distributed vertically.

---

## Free Space

`justify-content` becomes especially useful when there is **extra free space** along the main axis.

For example:

```css
.container {
    width: 600px;
    display: flex;
    justify-content: center;
}
```

If the items occupy less space than the container, the remaining space can be distributed according to the chosen `justify-content` value.

```text
Container width
────────────────────────────────────────

Items width
──────────────

Remaining space
────────────────────
```

`justify-content` determines how that remaining space is handled.

---

## Common Navigation Example

A navigation bar can use:

```css
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

This can position one group at the beginning and another at the end.

```text
┌──────────────────────────────────────┐
│ Logo                 Home About Login│
└──────────────────────────────────────┘
```

---

## Common Centering Example

To center items along the main axis:

```css
.container {
    display: flex;
    justify-content: center;
}
```

For complete horizontal and vertical centering in a row-based container, it is common to combine:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Here:

```text
justify-content
→ Main axis

align-items
→ Cross axis
```

---

## Important Difference

Do not confuse:

```css
justify-content
```

with:

```css
align-items
```

`justify-content` controls distribution along the **main axis**.

`align-items` controls alignment along the **cross axis**.

```text
Main Axis
    ↓
justify-content

Cross Axis
    ↓
align-items
```

---

## Quick Reference

| Value | Behavior |
|-------|----------|
| `flex-start` | Items at the start |
| `flex-end` | Items at the end |
| `center` | Items centered |
| `space-between` | Equal space between items |
| `space-around` | Space around each item |
| `space-evenly` | Equal space everywhere |

---

> 💡 **Pro Tip:** If `justify-content` appears to do nothing, check whether there is any free space along the main axis. If the flex items already consume all available space, there may be no extra space for the property to distribute.

---

> 💡 **Remember:** `justify-content` controls how flex items are positioned and distributed along the **main axis**. The main axis is determined by `flex-direction`.

---

# Align Items

The `align-items` property controls how flex items are **aligned along the cross axis** of a flex container.

```css
.container {
    display: flex;
    align-items: center;
}
```

The cross axis depends on the value of:

```css
flex-direction
```

---

## Syntax

```css
.container {
    display: flex;
    align-items: value;
}
```

Common values include:

```text
stretch
flex-start
flex-end
center
baseline
```

---

## `stretch`

The default value is:

```css
align-items: stretch;
```

Flex items stretch along the cross axis when their cross-axis size is `auto`.

Example:

```css
.container {
    display: flex;
    align-items: stretch;
}
```

For a row-based container:

```text
┌──────────────────────────────────────┐
│  ┌────┐  ┌────┐  ┌────┐              │
│  │    │  │    │  │    │              │
│  │  1 │  │  2 │  │  3 │              │
│  │    │  │    │  │    │              │
│  └────┘  └────┘  └────┘              │
└──────────────────────────────────────┘
```

The items can stretch to fill the available cross-axis space.

---

## `flex-start`

The `flex-start` value places items at the beginning of the cross axis.

```css
.container {
    display: flex;
    align-items: flex-start;
}
```

For a normal row:

```text
┌──────────────────────────────────────┐
│  1      2      3                     │
│                                      │
│                                      │
│                                      │
└──────────────────────────────────────┘
```

The items are aligned toward the start of the cross axis.

---

## `flex-end`

The `flex-end` value places items at the end of the cross axis.

```css
.container {
    display: flex;
    align-items: flex-end;
}
```

For a normal row:

```text
┌──────────────────────────────────────┐
│                                      │
│                                      │
│                                      │
│  1      2      3                     │
└──────────────────────────────────────┘
```

---

## `center`

The `center` value centers the flex items along the cross axis.

```css
.container {
    display: flex;
    align-items: center;
}
```

For a row-based container:

```text
┌──────────────────────────────────────┐
│                                      │
│       1      2      3                │
│                                      │
└──────────────────────────────────────┘
```

This is one of the most commonly used values.

---

## `baseline`

The `baseline` value aligns flex items according to their text baselines.

```css
.container {
    display: flex;
    align-items: baseline;
}
```

This is particularly useful when items contain text with different font sizes.

Example:

```text
┌──────────────────────────────────────┐
│  Small     LARGE     Medium          │
│     ────────────────                 │
│          Common Baseline             │
└──────────────────────────────────────┘
```

The text baselines are aligned rather than simply aligning the top or bottom edges of the items.

---

## Comparing the Values

For a row-based container:

### `flex-start`

```text
1   2   3
```

Items align at the top.

### `flex-end`

```text
        1   2   3
```

Items align at the bottom.

### `center`

```text
    1   2   3
```

Items align in the center.

### `stretch`

```text
┌───┐ ┌───┐ ┌───┐
│ 1 │ │ 2 │ │ 3 │
│   │ │   │ │   │
│   │ │   │ │   │
└───┘ └───┘ └───┘
```

Items stretch across the available cross-axis space when applicable.

### `baseline`

```text
1       LARGE       3
───────────────
   Common Baseline
```

Text baselines are aligned.

---

## `align-items` Uses the Cross Axis

The most important rule is:

```text
align-items
     ↓
Cross Axis
```

For:

```css
flex-direction: row;
```

the cross axis is vertical.

Therefore:

```css
align-items: center;
```

centers items vertically.

```text
┌──────────────────────────────┐
│                              │
│       1   2   3              │
│                              │
└──────────────────────────────┘
```

---

## With `flex-direction: column`

Consider:

```css
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

Now the main axis is vertical and the cross axis is horizontal.

Therefore, `align-items: center` centers the items horizontally.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

This is why `align-items` should not simply be remembered as "vertical alignment."

It always operates along the **cross axis**.

---

## `justify-content` vs `align-items`

These two properties are often used together.

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Their responsibilities are:

```text
justify-content
      ↓
Main Axis

align-items
      ↓
Cross Axis
```

For a normal row:

```text
Main Axis
────────────────────────→

Cross Axis
      ↓
      ↓
      ↓
```

Therefore:

```css
justify-content: center;
```

centers items along the horizontal main axis.

And:

```css
align-items: center;
```

centers them along the vertical cross axis.

Together, they can center items in both directions.

---

## Complete Centering Example

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 300px;
}
```

Result:

```text
┌──────────────────────────────┐
│                              │
│                              │
│          1   2   3           │
│                              │
│                              │
└──────────────────────────────┘
```

Here:

```text
justify-content
→ Centers on the main axis

align-items
→ Centers on the cross axis
```

---

## `align-items` and Item Height

The effect of `align-items` is easiest to see when the flex container has extra space along its cross axis.

For example:

```css
.container {
    height: 300px;
    display: flex;
    align-items: center;
}
```

The items can then be positioned within the available vertical space.

Without enough cross-axis space, there may be little or no visible difference between some alignment values.

---

## `align-items` With Different Item Sizes

Flex items do not have to be the same size.

Example:

```html
<div class="container">
    <div class="item small">Small</div>
    <div class="item large">Large</div>
    <div class="item medium">Medium</div>
</div>
```

```css
.container {
    display: flex;
    align-items: center;
}
```

The different-sized items are aligned according to the selected cross-axis alignment.

```text
┌──────────────────────────────────────┐
│                                      │
│   Small     Large     Medium         │
│                                      │
└──────────────────────────────────────┘
```

---

## Common Use Cases

### Vertically Centering a Row

```css
.container {
    display: flex;
    align-items: center;
}
```

### Centering Items in a Column

```css
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

### Aligning Header Content

```css
.header {
    display: flex;
    align-items: center;
}
```

This is commonly used to vertically align a logo, navigation, and buttons.

### Aligning Different Text Sizes

```css
.container {
    display: flex;
    align-items: baseline;
}
```

This can keep text baselines visually aligned.

---

## Important Difference From `align-content`

Do not confuse:

```css
align-items
```

with:

```css
align-content
```

`align-items` controls the alignment of **items within a flex line**.

`align-content` controls the distribution of **multiple flex lines** when wrapping creates extra cross-axis space.

```text
align-items
     ↓
Items

align-content
     ↓
Flex Lines
```

`align-content` becomes relevant when there are multiple flex lines, such as when:

```css
flex-wrap: wrap;
```

is being used.

---

## Quick Reference

| Value | Behavior |
|-------|----------|
| `stretch` | Stretches items along the cross axis when applicable |
| `flex-start` | Aligns items at the start of the cross axis |
| `flex-end` | Aligns items at the end of the cross axis |
| `center` | Centers items along the cross axis |
| `baseline` | Aligns items according to their baselines |

---

> 💡 **Pro Tip:** If you want to understand what `align-items` is doing, first identify the cross axis. Ask: **"Which direction is perpendicular to my `flex-direction`?"** That is the direction in which `align-items` works.

---

> 💡 **Remember:** `align-items` controls the alignment of flex items along the **cross axis**. It is commonly used with `justify-content` to control alignment in both axes.