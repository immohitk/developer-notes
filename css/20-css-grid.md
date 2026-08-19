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

---

## Grid Items

A **grid item** is an element that is a direct child of a grid container.

A grid item participates in the CSS Grid layout created by its parent.

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

### Direct Children Become Grid Items

Only the **direct children** of a grid container automatically become grid items.

For example:

```html
<div class="container">
    <div class="item">
        <span>Text</span>
    </div>
</div>
```

Here:

```text
.container
    ↓
Grid Container
    ↓
.item
    ↓
Grid Item
    ↓
<span>
    ↓
Not a grid item
```

The `<span>` is a descendant of the grid container, but it is not a direct child.

### Basic Grid Items

Consider:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

HTML:

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
</div>
```

The four direct children become grid items:

```text
┌──────────┬──────────┐
│    1     │    2     │
├──────────┼──────────┤
│    3     │    4     │
└──────────┴──────────┘
```

### Grid Items Can Contain Other Elements

A grid item can contain its own content.

```html
<div class="container">
    <article class="card">
        <h2>Title</h2>
        <p>Description</p>
    </article>
</div>
```

Here:

```text
.container
    ↓
Grid Container

.card
    ↓
Grid Item

<h2>
<p>
    ↓
Content inside the grid item
```

The internal elements do not automatically become items of the outer grid.

### Grid Item Placement

By default, Grid automatically places items into available grid cells.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

With four items:

```text
Item 1 → Cell 1
Item 2 → Cell 2
Item 3 → Cell 3
Item 4 → Cell 4
```

Result:

```text
┌──────────┬──────────┐
│ Item 1   │ Item 2   │
├──────────┼──────────┤
│ Item 3   │ Item 4   │
└──────────┴──────────┘
```

This automatic behavior is called **auto-placement** and will be covered later.

### Styling Individual Grid Items

Grid items can have their own styles.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}

.item {
    padding: 20px;
    background-color: lightblue;
}
```

The container controls the grid layout, while the item can control its own appearance.

### Placing an Item Across Columns

A grid item can span multiple columns.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.item:first-child {
    grid-column: span 2;
}
```

The first item occupies two columns:

```text
┌──────────────────────┬──────────┐
│       Item 1         │  Item 2  │
│      2 columns       │          │
├──────────┬───────────┴──────────┤
│ Item 3   │ Item 4                │
└──────────┴───────────────────────┘
```

The `grid-column` property will be covered in detail later.

### Placing an Item Across Rows

Grid items can also span multiple rows.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}

.item:first-child {
    grid-row: span 2;
}
```

The first item occupies two rows.

```text
┌──────────┬──────────┐
│          │  Item 2  │
│  Item 1  ├──────────┤
│          │  Item 3  │
└──────────┴──────────┘
```

### Grid Items Can Be Repositioned

Grid items can be explicitly positioned using properties such as:

```css
grid-column
grid-row
```

For example:

```css
.item {
    grid-column: 1 / 3;
}
```

This tells the item to occupy the space between grid column lines 1 and 3.

### Grid Items and Alignment

Grid items can also be aligned within their grid areas.

For example:

```css
.item {
    justify-self: center;
    align-self: center;
}
```

These properties control the individual item's position within its grid area.

### Grid Item Size

A grid item's size is influenced by the grid tracks it occupies.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 300px;
}
```

The first column is:

```text
200px
```

and the second is:

```text
300px
```

An item placed in the first column is therefore positioned within that 200px track.

### Grid Items and `gap`

The spacing between grid items is controlled by the grid container.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

The grid items are separated by the specified gap.

```text
┌──────────┐ 20px ┌──────────┐
│  Item 1  │      │  Item 2  │
└──────────┘      └──────────┘
```

### Important Point

A grid item is specifically a **direct child** of a grid container.

```text
Grid Container
      │
      ├── Direct Child → Grid Item
      ├── Direct Child → Grid Item
      └── Direct Child → Grid Item
```

A nested descendant does not automatically become an item of the outer grid.

> 💡 **Remember:** A grid item is a direct child of a grid container. The grid container establishes the layout, while individual grid items can be styled, positioned, aligned, or made to span multiple rows and columns.

---

## Grid Columns

Grid columns are the **vertical tracks** of a CSS Grid.

They divide the grid container from left to right and determine how much horizontal space is available for grid items.

### Basic Example

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

Each column has a width of:

```text
200px
```

### Creating Multiple Columns

You can define several columns in `grid-template-columns`.

```css
.container {
    display: grid;
    grid-template-columns: 100px 200px 300px;
}
```

This creates:

```text
┌───────┬──────────────┬────────────────────┐
│ 100px │    200px     │       300px        │
└───────┴──────────────┴────────────────────┘
```

Each value represents one column.

### Equal-Width Columns

The `fr` unit can be used to create flexible columns.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The available space is divided equally:

```text
┌────────────────┬────────────────┐
│    Column 1     │    Column 2    │
│      1fr        │      1fr       │
└────────────────┴────────────────┘
```

### Three Equal Columns

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Result:

```text
┌──────────┬──────────┬──────────┐
│    1fr   │    1fr   │    1fr   │
└──────────┴──────────┴──────────┘
```

Each column receives an equal share of the available space.

### Unequal Flexible Columns

Different `fr` values create different proportions.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
}
```

The available space is divided into three fractional parts:

```text
┌──────────┬─────────────────────┐
│   1fr    │        2fr          │
└──────────┴─────────────────────┘
```

The second column is twice the flexible size of the first.

### Fixed and Flexible Columns

You can combine fixed lengths with flexible columns.

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr;
}
```

This is useful for layouts such as a sidebar and main content:

```text
┌──────────────┬──────────────────────────┐
│   Sidebar    │       Main Content       │
│    200px     │           1fr            │
└──────────────┴──────────────────────────┘
```

### Three Columns With Different Sizes

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 300px;
}
```

The layout contains:

```text
200px       flexible        300px
   ↓            ↓              ↓
┌───────┬────────────────┬─────────┐
│ Left  │     Center     │  Right  │
└───────┴────────────────┴─────────┘
```

### Using Percentages

Columns can also be defined using percentages.

```css
.container {
    grid-template-columns: 50% 50%;
}
```

This creates two columns, each taking 50% of the grid container's relevant size.

However, when using percentages together with gaps, the total layout can require additional consideration.

### Using `auto`

The `auto` keyword can also be used.

```css
.container {
    grid-template-columns: auto 1fr;
}
```

The first column can size itself based on its contents and available space, while the second column uses the remaining flexible space.

### Combining Different Units

Grid columns can use different CSS units together.

```css
.container {
    grid-template-columns: 150px 20% 1fr;
}
```

You can combine:

```text
px
%
fr
auto
```

and other appropriate CSS length values.

### Using `repeat()`

When several columns follow the same pattern, `repeat()` makes the declaration shorter.

Instead of:

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

you can write:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

Both create three equal flexible columns.

### Four Equal Columns

```css
.container {
    grid-template-columns: repeat(4, 1fr);
}
```

Result:

```text
┌──────┬──────┬──────┬──────┐
│ 1fr  │ 1fr  │ 1fr  │ 1fr  │
└──────┴──────┴──────┴──────┘
```

The `repeat()` function will be covered in more detail later.

### Columns With a Gap

The `gap` property can add space between columns.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
}
```

The result is conceptually:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│ Column 1 │      │ Column 2 │      │ Column 3 │
└──────────┘      └──────────┘      └──────────┘
```

The gap is separate from the column track sizes.

### Responsive Columns

Grid columns can be changed using media queries.

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

Large screens:

```text
┌────────┬────────┬────────┐
│        │        │        │
└────────┴────────┴────────┘
```

Small screens:

```text
┌──────────────────────────┐
│                          │
├──────────────────────────┤
│                          │
├──────────────────────────┤
│                          │
└──────────────────────────┘
```

### Practical Card Grid

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

HTML:

```html
<div class="cards">
    <article>Card 1</article>
    <article>Card 2</article>
    <article>Card 3</article>
    <article>Card 4</article>
    <article>Card 5</article>
    <article>Card 6</article>
</div>
```

The cards are automatically arranged into three columns:

```text
┌────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │
├────────┼────────┼────────┤
│ Card 4 │ Card 5 │ Card 6 │
└────────┴────────┴────────┘
```

### Important Property

The main property for defining grid columns is:

```css
grid-template-columns
```

Its value defines the size of the column tracks.

Examples:

```css
grid-template-columns: 200px 300px;
```

```css
grid-template-columns: 1fr 1fr;
```

```css
grid-template-columns: repeat(3, 1fr);
```

```css
grid-template-columns: 200px 1fr;
```

> 💡 **Remember:** `grid-template-columns` defines the columns of a grid. Each value represents a column track, and you can combine fixed sizes, flexible `fr` units, percentages, `auto`, and other supported sizing values.

---

## Grid Rows

Grid rows are the **horizontal tracks** of a CSS Grid.

They determine how the grid is divided vertically and control the available space for grid items from top to bottom.

### Basic Example

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px;
}
```

This creates two rows:

```text
┌────────────────────────────┐
│          Row 1             │ 100px
├────────────────────────────┤
│          Row 2             │ 100px
└────────────────────────────┘
```

Each value in `grid-template-rows` defines one row track.

### Creating Multiple Rows

You can define several rows:

```css
.container {
    display: grid;
    grid-template-rows: 100px 150px 200px;
}
```

This creates three rows:

```text
┌────────────────────────────┐
│          Row 1             │
├────────────────────────────┤
│          Row 2             │
├────────────────────────────┤
│          Row 3             │
└────────────────────────────┘
```

The rows have heights of:

```text
100px
150px
200px
```

### Equal-Height Rows

The `fr` unit can be used to divide available space between rows.

```css
.container {
    display: grid;
    grid-template-rows: 1fr 1fr;
}
```

The available grid height is divided equally:

```text
┌────────────────────────────┐
│           1fr              │
├────────────────────────────┤
│           1fr              │
└────────────────────────────┘
```

### Three Equal Rows

```css
.container {
    display: grid;
    grid-template-rows: repeat(3, 1fr);
}
```

This creates three equal flexible rows.

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

### Fixed and Flexible Rows

You can combine fixed and flexible values.

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr;
}
```

This is useful for layouts such as a header and main content area.

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│        Main Content        │ 1fr
│                            │
└────────────────────────────┘
```

### Header, Main, and Footer

A common page layout can use:

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr 60px;
}
```

Conceptually:

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│           Main             │ 1fr
│                            │
├────────────────────────────┤
│           Footer           │ 60px
└────────────────────────────┘
```

### Using `auto`

Rows can also use `auto`.

```css
.container {
    display: grid;
    grid-template-rows: auto 1fr;
}
```

The first row can size itself based on its content and available space, while the second row uses flexible space.

### Combining Different Units

Grid rows can use different sizing values.

```css
.container {
    grid-template-rows: 80px 30% 1fr;
}
```

You can combine values such as:

```text
px
%
fr
auto
```

and other supported CSS sizing values.

### Rows and Columns Together

Rows are usually defined together with columns.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 200px;
}
```

This creates:

```text
             Column 1       Column 2
          ┌──────────────┬──────────────┐
Row 1     │              │              │ 100px
          ├──────────────┼──────────────┤
Row 2     │              │              │ 200px
          └──────────────┴──────────────┘
```

### Rows With Gaps

The `gap` property can add spacing between rows.

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px 100px;
    gap: 20px;
}
```

The rows are separated by `20px`.

```text
┌────────────────────────────┐
│           Row 1            │
└────────────────────────────┘
             20px
┌────────────────────────────┐
│           Row 2            │
└────────────────────────────┘
             20px
┌────────────────────────────┐
│           Row 3            │
└────────────────────────────┘
```

### Responsive Rows

Rows can be changed using media queries.

```css
.container {
    display: grid;
    grid-template-rows: 100px 1fr;
}

@media (max-width: 600px) {
    .container {
        grid-template-rows: 60px 1fr;
    }
}
```

The header row becomes smaller on narrow screens.

### `grid-template-rows`

The main property for explicitly defining rows is:

```css
grid-template-rows
```

For example:

```css
grid-template-rows: 100px 200px;
```

creates two row tracks.

Another example:

```css
grid-template-rows: repeat(3, 1fr);
```

creates three equal flexible row tracks.

### Important Point

Columns describe the horizontal structure:

```css
grid-template-columns
```

Rows describe the vertical structure:

```css
grid-template-rows
```

Together they define the main grid structure:

```text
        Columns →
     ┌──────┬──────┬──────┐
Rows │      │      │      │
  ↓  ├──────┼──────┼──────┤
     │      │      │      │
     ├──────┼──────┼──────┤
     │      │      │      │
     └──────┴──────┴──────┘
```

> 💡 **Remember:** `grid-template-rows` defines the size of grid row tracks. It can be combined with `grid-template-columns` to create a complete two-dimensional grid structure.

---

## Grid Tracks

A **grid track** is the space between two adjacent grid lines.

A grid track can be either:

- A **column track**
- A **row track**

In simple terms:

```text
Grid
│
├── Column tracks → vertical
└── Row tracks    → horizontal
```

### Column Tracks

When you define columns:

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 2fr;
}
```

you create three column tracks:

```text
┌──────────┬──────────┬────────────────┐
│ Track 1  │ Track 2  │    Track 3     │
│  200px   │   1fr    │      2fr       │
└──────────┴──────────┴────────────────┘
```

Each value in `grid-template-columns` defines the size of a column track.

### Row Tracks

Similarly, when you define rows:

```css
.container {
    display: grid;
    grid-template-rows: 100px 1fr 200px;
}
```

you create three row tracks:

```text
┌──────────────────────────────┐
│          Track 1             │ 100px
├──────────────────────────────┤
│          Track 2             │ 1fr
├──────────────────────────────┤
│          Track 3             │ 200px
└──────────────────────────────┘
```

Each value in `grid-template-rows` defines the size of a row track.

### Grid Lines Define Tracks

Grid lines surround grid tracks.

For example, two columns have three vertical grid lines:

```text
Line 1       Line 2       Line 3
   ↓            ↓            ↓
   │            │            │
   ├────────────┼────────────┤
   │  Column 1  │  Column 2  │
   ├────────────┼────────────┤
   │            │            │
```

The space between:

```text
Line 1 → Line 2
```

is the first column track.

The space between:

```text
Line 2 → Line 3
```

is the second column track.

### Tracks and Grid Cells

A **grid cell** is created where a row track and a column track intersect.

For example:

```text
             Column Tracks
          ┌────────┬────────┐
Row       │        │        │
Track 1   │ Cell 1 │ Cell 2 │
          ├────────┼────────┤
Row       │        │        │
Track 2   │ Cell 3 │ Cell 4 │
          └────────┴────────┘
```

So:

```text
Column Track + Row Track
          ↓
      Grid Cell
```

### Fixed-Size Tracks

A track can have a fixed size.

```css
.container {
    grid-template-columns: 200px 300px;
}
```

This creates:

```text
Track 1 → 200px
Track 2 → 300px
```

### Flexible Tracks

Tracks can use the `fr` unit.

```css
.container {
    grid-template-columns: 1fr 2fr;
}
```

The available flexible space is divided into three parts:

```text
┌──────────┬─────────────────────┐
│   1fr    │        2fr          │
└──────────┴─────────────────────┘
```

The second track receives twice the flexible share of the first.

The `fr` unit will be covered in detail later.

### `auto` Tracks

Tracks can also use `auto`.

```css
.container {
    grid-template-columns: auto 1fr;
}
```

An `auto` track can size itself based on its contents and available space.

### Track Sizing With `minmax()`

Grid tracks can use `minmax()` to specify a minimum and maximum size.

```css
.container {
    grid-template-columns: minmax(200px, 1fr) 1fr;
}
```

The first track can grow flexibly while respecting the specified minimum.

The `minmax()` function will be covered in detail later.

### Repeating Tracks

The `repeat()` function can create multiple tracks with the same pattern.

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

This creates:

```text
1fr | 1fr | 1fr
```

or three equal column tracks.

### Explicit Tracks

Tracks directly defined using:

```css
grid-template-columns
grid-template-rows
```

are called **explicit grid tracks**.

Example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}
```

This explicitly defines:

```text
2 column tracks
2 row tracks
```

### Implicit Tracks

Grid can also create additional tracks automatically when there are more items than the explicitly defined grid can accommodate.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

If there are five items:

```text
┌────────┬────────┐
│ Item 1 │ Item 2 │
├────────┼────────┤
│ Item 3 │ Item 4 │
├────────┼────────┤
│ Item 5 │        │
└────────┴────────┘
```

The additional row is created automatically.

These automatically generated tracks are called **implicit tracks**.

### Track Size vs Item Size

A grid track is part of the grid structure.

A grid item is placed inside one or more tracks.

For example:

```text
Grid Track
┌─────────────────────┐
│                     │
│      Grid Item      │
│                     │
└─────────────────────┘
```

The track determines the available grid space, while the item's own size and alignment determine how its content occupies that space.

### Grid Tracks and `gap`

A gap creates space between tracks.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

Conceptually:

```text
┌────────────┐  20px  ┌────────────┐
│ Track 1    │        │ Track 2    │
│            │        │            │
└────────────┘        └────────────┘
```

The gap is not itself a grid track.

### Important Grid Track Properties

Grid tracks are commonly created and sized using:

```css
grid-template-columns
grid-template-rows
```

and can use sizing techniques such as:

```css
fr
repeat()
minmax()
auto
px
%
```

### Track Mental Model

```text
Grid Lines
    ↓
┌────────┬────────┐
│ Track  │ Track  │
│   1    │   2    │
├────────┼────────┤
│ Track  │ Track  │
│   3    │   4    │
└────────┴────────┘
    ↑
Grid Cells
```

A more accurate conceptual model is:

```text
Grid Line
    ↓
┌──────────────┐
│ Grid Track   │
└──────────────┘
    ↑
Grid Line
```

> 💡 **Remember:** A grid track is a row or column of the grid. `grid-template-columns` creates column tracks, while `grid-template-rows` creates row tracks. Grid lines define the boundaries of those tracks.