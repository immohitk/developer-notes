## Table of Contents

- [Introduction](#introduction)
- [Grid Container](#grid-container)
- [Grid Items](#grid-items)
- [Grid Columns](#grid-columns)
- [Grid Rows](#grid-rows)
- [Grid Tracks](#grid-tracks)
- [Grid Lines](#grid-lines)
- [Grid Cells](#grid-cells)
- [Grid Template Columns](#grid-template-columns)
- [Grid Template Rows](#grid-template-rows)
- [The `fr` Unit](#the-fr-unit)
- [`repeat()` Function](#repeat-function)
- [`minmax()` Function](#minmax-function)
- [`gap`](#gap)
- [Grid Column](#grid-column)
- [Grid Row](#grid-row)
- [Grid Areas](#grid-areas)
- [Grid Alignment](#grid-alignment)
- [Auto Placement](#auto-placement)
- [Explicit vs Implicit Grid](#explicit-vs-implicit-grid)
- [Responsive Grid](#responsive-grid)
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

CSS Grid is a **two-dimensional layout system** in CSS that allows elements to be arranged into rows and columns.

It is designed for layouts where you need control over both:

- Horizontal placement
- Vertical placement

### Basic Example

A Grid layout starts by making an element a grid container:

```css
.container {
    display: grid;
}
```

For example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
    <div>Item 4</div>
</div>
```

Once:

```css
.container {
    display: grid;
}
```

is applied, the `.container` becomes a **grid container** and its direct children become **grid items**.

### Two-Dimensional Layout

CSS Grid works with two dimensions:

```text
              Columns
        ↓        ↓        ↓
      ┌────────┬────────┐
Rows  │ Item 1 │ Item 2 │
  ↓   ├────────┼────────┤
      │ Item 3 │ Item 4 │
      └────────┴────────┘
```

The columns control the horizontal structure, while the rows control the vertical structure.

### Grid Compared With Flexbox

Flexbox is primarily a **one-dimensional** layout system.

It generally works along one main direction:

```text
Flexbox

Item 1 → Item 2 → Item 3 → Item 4
```

CSS Grid is designed for two-dimensional layouts:

```text
Grid

┌────────┬────────┐
│ Item 1 │ Item 2 │
├────────┼────────┤
│ Item 3 │ Item 4 │
└────────┴────────┘
```

This makes Grid particularly useful for layouts involving both rows and columns.

### Common Uses of CSS Grid

CSS Grid can be used for:

- Website page layouts
- Card layouts
- Image galleries
- Dashboard layouts
- Product grids
- Application interfaces
- Responsive layouts

For example, a simple card layout can be created with:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

This creates three columns of equal flexible width.

### Grid Terminology

CSS Grid introduces several important terms:

```text
Grid Container
      ↓
Grid Items
      ↓
Grid Lines
      ↓
Grid Tracks
      ↓
Grid Cells
      ↓
Grid Areas
```

These concepts describe different parts of a grid.

### Grid Container

The element with:

```css
display: grid;
```

is called the **grid container**.

Example:

```css
.container {
    display: grid;
}
```

### Grid Items

The direct children of a grid container are called **grid items**.

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
</div>
```

Here:

```text
.container
    ↓
Grid Container

<div>Item 1</div>
    ↓
Grid Item

<div>Item 2</div>
    ↓
Grid Item
```

### Defining Columns

A grid becomes more useful when columns are explicitly defined.

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
}
```

This creates two columns:

```text
┌────────────┬────────────┐
│            │            │
│  Column 1  │  Column 2  │
│            │            │
└────────────┴────────────┘
```

### Defining Rows

Rows can also be defined:

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
    grid-template-rows: 100px 100px;
}
```

This creates a two-column and two-row grid.

```text
┌────────────┬────────────┐
│            │            │  100px
├────────────┼────────────┤
│            │            │  100px
└────────────┴────────────┘
   200px        200px
```

### Why Grid Is Powerful

CSS Grid separates the layout structure from the individual content items.

Instead of manually positioning every element, you can define the grid structure:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
}
```

The browser then places the grid items according to the defined grid.

### Basic Mental Model

Think of CSS Grid as creating a framework:

```text
Define Grid
    ↓
Create Columns and Rows
    ↓
Place Grid Items
    ↓
Control Spacing
    ↓
Control Alignment
    ↓
Create Responsive Layout
```

> 💡 **Remember:** CSS Grid is a two-dimensional CSS layout system designed to control both rows and columns. It is especially useful for structured layouts where horizontal and vertical placement need to work together.

---

## Grid Container

A **grid container** is an element whose `display` property is set to `grid` or `inline-grid`.

Example:

```css
.container {
    display: grid;
}
```

The element with `display: grid` becomes the grid container, and its direct children become grid items.

### Basic Example

HTML:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

CSS:

```css
.container {
    display: grid;
}
```

The structure is:

```text
.container
     ↓
Grid Container
     │
     ├── Item 1 → Grid Item
     ├── Item 2 → Grid Item
     └── Item 3 → Grid Item
```

### `display: grid`

The most common way to create a grid container is:

```css
.container {
    display: grid;
}
```

This creates a block-level grid container.

For example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
</div>
```

```css
.container {
    display: grid;
}
```

The `.container` participates in normal block layout, while its direct children participate in grid layout.

### `display: inline-grid`

CSS also provides:

```css
.container {
    display: inline-grid;
}
```

`inline-grid` creates an inline-level grid container.

For example:

```css
.container {
    display: inline-grid;
}
```

The grid itself behaves like an inline-level element, while its direct children are still laid out using CSS Grid.

### Grid Container vs Grid Items

Consider:

```html
<div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
</div>
```

```css
.container {
    display: grid;
}
```

Here:

```text
.container
     ↓
Grid Container

.item
.item
     ↓
Grid Items
```

Only the **direct children** automatically become grid items.

### Defining Columns on the Container

The grid structure is normally defined on the grid container.

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
}
```

This creates two columns.

```text
┌────────────┬────────────┐
│   Item     │   Item     │
├────────────┼────────────┤
│   Item     │   Item     │
└────────────┴────────────┘
```

### Defining Rows on the Container

Rows can also be defined:

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
    grid-template-rows: 100px 100px;
}
```

The container now has two explicitly defined columns and two explicitly defined rows.

### Grid Container Controls the Layout

Many Grid properties are applied to the grid container.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
}
```

Here:

```text
display
    ↓
Creates the grid

grid-template-columns
    ↓
Defines the columns

gap
    ↓
Controls spacing between grid items
```

### Container With Four Items

HTML:

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
</div>
```

CSS:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The browser can place the items into the available columns:

```text
┌──────────┬──────────┐
│    1     │    2     │
├──────────┼──────────┤
│    3     │    4     │
└──────────┴──────────┘
```

### Grid Container With Three Columns

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

This creates three flexible columns:

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │ Item 5 │ Item 6 │
└────────┴────────┴────────┘
```

### Grid Container and Available Space

The grid container provides the available space in which the grid tracks are created.

For example:

```css
.container {
    width: 600px;
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The two `1fr` columns can divide the available grid space equally.

Conceptually:

```text
600px
  ↓
┌──────────────────────────────┐
│       300px      │   300px   │
└──────────────────────────────┘
```

### Grid Container Can Be Responsive

A grid container can use media queries:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

The same container can therefore use three columns on larger screens and one column on smaller screens.

### Important Point

The grid container is where the overall grid structure is established.

Common container properties include:

```css
.container {
    display: grid;
    grid-template-columns: ...;
    grid-template-rows: ...;
    gap: ...;
}
```

Later sections will cover these properties individually.

> 💡 **Remember:** A grid container is the element that establishes a CSS Grid formatting context. Its direct children become grid items and can then be arranged into rows and columns.