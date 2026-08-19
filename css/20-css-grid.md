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

---

## Grid Lines

**Grid lines** are the horizontal and vertical dividing lines that form the structure of a CSS Grid.

They define the boundaries of grid tracks and are used to position grid items.

### Basic Grid

Consider a grid with two columns and two rows:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}
```

Conceptually:

```text
        Column Line
        1       2       3
        ↓       ↓       ↓
        │       │       │
     ┌──┼───────┼───────┐
  1  │  │       │       │
     ├──┼───────┼───────┤
  2  │  │       │       │
     └──┼───────┼───────┘
        ↑       ↑       ↑
        1       2       3
```

There are:

- **3 vertical grid lines** for 2 columns
- **3 horizontal grid lines** for 2 rows

### Grid Lines and Columns

If a grid has:

```css
grid-template-columns: 1fr 1fr;
```

there are two column tracks.

Two tracks require three vertical grid lines:

```text
Line 1       Line 2       Line 3
   │            │            │
   │  Track 1   │  Track 2   │
   │            │            │
```

The first column is between:

```text
Grid Line 1 → Grid Line 2
```

The second column is between:

```text
Grid Line 2 → Grid Line 3
```

### Grid Lines and Rows

If a grid has:

```css
grid-template-rows: 100px 100px;
```

there are two row tracks.

Two row tracks require three horizontal grid lines:

```text
Grid Line 1
───────────────

    Row Track 1

Grid Line 2
───────────────

    Row Track 2

Grid Line 3
───────────────
```

### Grid Line Numbering

Grid lines are automatically numbered.

For a grid with three columns:

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

there are four vertical grid lines:

```text
Line 1     Line 2     Line 3     Line 4
   │          │          │          │
   │  1fr     │  1fr     │  1fr     │
   │          │          │          │
```

The columns are therefore:

```text
Column 1 → Line 1 to Line 2
Column 2 → Line 2 to Line 3
Column 3 → Line 3 to Line 4
```

### Grid Lines Are Used to Position Items

Grid items can be positioned using grid line numbers.

For example:

```css
.item {
    grid-column: 1 / 3;
}
```

This means the item starts at column line `1` and ends at column line `3`.

```text
Line 1       Line 2       Line 3
   ↓            ↓            ↓
   │            │            │
   ├────────────┼────────────┤
   │                         │
   │         Item            │
   │                         │
   └─────────────────────────┘
```

The item therefore spans two column tracks.

### Grid Row Lines

Rows can also be referenced by their line numbers.

```css
.item {
    grid-row: 1 / 3;
}
```

This starts the item at row line `1` and ends it at row line `3`.

```text
Row Line 1
───────────────
       │
       │ Item
       │
Row Line 2
───────────────
       │
       │ Item
       │
Row Line 3
───────────────
```

The item spans two row tracks.

### Grid Line Names

Grid lines can also have custom names.

For example:

```css
.container {
    display: grid;
    grid-template-columns:
        [sidebar-start] 200px
        [sidebar-end content-start] 1fr
        [content-end] 200px;
}
```

The lines now have names such as:

```text
sidebar-start
sidebar-end
content-start
content-end
```

These names can be used when positioning items.

For example:

```css
.sidebar {
    grid-column: sidebar-start / sidebar-end;
}
```

Named lines can make complex layouts easier to understand.

### Negative Grid Line Numbers

Grid lines can also be referenced using negative numbers.

The last grid line is:

```text
-1
```

For example, in a four-column grid:

```text
Line:    1    2    3    4    5
         │    │    │    │    │
         │    │    │    │    │
Negative -5   -4   -3   -2   -1
```

This can be useful when you want to reference the end of the grid without knowing its exact positive line number.

Example:

```css
.item {
    grid-column: 1 / -1;
}
```

This makes the item span from the first grid line to the last grid line.

Conceptually:

```text
┌────────────────────────────────┐
│             Item               │
└────────────────────────────────┘
```

### Grid Lines vs Grid Tracks

These terms are related but different.

**Grid line:**

```text
Boundary
```

**Grid track:**

```text
Space between two adjacent grid lines
```

For example:

```text
Line 1        Line 2        Line 3
  │             │             │
  │   Track 1   │   Track 2   │
  │             │             │
```

So:

```text
Grid Lines
    ↓
Define boundaries
    ↓
Grid Tracks
    ↓
Contain grid cells
```

### Grid Lines vs Grid Cells

A grid cell is the space created by the intersection of one row track and one column track.

```text
          Column Lines
       1       2       3
       ↓       ↓       ↓
       │       │       │
  1 ───┼───────┼───────┤
       │ Cell  │ Cell  │
  2 ───┼───────┼───────┤
       │ Cell  │ Cell  │
  3 ───┴───────┴───────┘
```

The lines create the boundaries, while the cells occupy the spaces between those boundaries.

### Important Rule

If a grid contains:

```text
N columns
```

it normally has:

```text
N + 1 vertical grid lines
```

Similarly, if it contains:

```text
N rows
```

it normally has:

```text
N + 1 horizontal grid lines
```

For example:

```text
2 columns → 3 column lines
3 columns → 4 column lines
4 columns → 5 column lines
```

And:

```text
2 rows → 3 row lines
3 rows → 4 row lines
4 rows → 5 row lines
```

### Basic Mental Model

```text
Grid Lines
    ↓
┌───────┬───────┐
│       │       │
│ Cell  │ Cell  │
│       │       │
├───────┼───────┤
│       │       │
│ Cell  │ Cell  │
│       │       │
└───────┴───────┘
    ↑
Grid Lines
```

> 💡 **Remember:** Grid lines are the boundaries of a CSS Grid. They are automatically numbered, can optionally be named, and are commonly used with `grid-column` and `grid-row` to precisely position and span grid items.

---

## Grid Cells

A **grid cell** is the smallest unit of space in a CSS Grid.

A grid cell is created where **one row track and one column track intersect**.

### Basic Example

Consider a grid with two columns and two rows:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}
```

This creates four grid cells:

```text
┌────────────┬────────────┐
│   Cell 1   │   Cell 2   │
├────────────┼────────────┤
│   Cell 3   │   Cell 4   │
└────────────┴────────────┘
```

Each cell is the intersection of:

```text
One column track
       +
One row track
       ↓
Grid Cell
```

### Grid Cell vs Grid Track

A **grid track** is an entire row or column.

A **grid cell** is one individual area inside the grid.

For example:

```text
Column Track 1     Column Track 2
      ↓                  ↓
┌───────────────┬───────────────┐
│    Cell 1     │    Cell 2     │ ← Row Track 1
├───────────────┼───────────────┤
│    Cell 3     │    Cell 4     │ ← Row Track 2
└───────────────┴───────────────┘
```

Here:

```text
Column Track 1 → Cells 1 and 3
Column Track 2 → Cells 2 and 4

Row Track 1 → Cells 1 and 2
Row Track 2 → Cells 3 and 4
```

### Grid Cell vs Grid Item

A grid cell is a **location in the grid**.

A grid item is an **element placed into that location**.

For example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
</div>
```

With:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The browser can place the items into cells:

```text
┌────────────┬────────────┐
│   Item 1   │   Item 2   │
│   Cell 1   │   Cell 2   │
└────────────┴────────────┘
```

So:

```text
Grid Cell
   ↓
Available location

Grid Item
   ↓
Element placed in that location
```

### Number of Grid Cells

If a grid has:

```text
3 columns
2 rows
```

the grid contains:

```text
3 × 2 = 6 cells
```

Example:

```text
┌────────┬────────┬────────┐
│ Cell 1 │ Cell 2 │ Cell 3 │
├────────┼────────┼────────┤
│ Cell 4 │ Cell 5 │ Cell 6 │
└────────┴────────┴────────┘
```

Similarly:

```text
4 columns × 3 rows = 12 cells
```

### Grid Cells and Grid Lines

Grid lines form the boundaries of grid cells.

For a two-column, two-row grid:

```text
        Line 1     Line 2     Line 3
           ↓          ↓          ↓
           │          │          │
Line 1 ────┼──────────┼──────────┤
           │  Cell 1  │  Cell 2  │
Line 2 ────┼──────────┼──────────┤
           │  Cell 3  │  Cell 4  │
Line 3 ────┴──────────┴──────────┘
```

Each cell is bounded by:

- Two vertical grid lines
- Two horizontal grid lines

### Positioning Items Using Cells

Grid items are normally placed into cells automatically.

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

With three items:

```text
┌──────────┬──────────┬──────────┐
│  Item 1  │  Item 2  │  Item 3  │
│  Cell 1  │  Cell 2  │  Cell 3  │
└──────────┴──────────┴──────────┘
```

The first item occupies the first available cell, the second item occupies the next available cell, and so on.

This automatic behavior is called **auto-placement**.

### An Item Can Span Multiple Cells

A grid item does not have to remain inside a single cell.

It can span multiple columns or rows.

For example:

```css
.item {
    grid-column: span 2;
}
```

An item can occupy two adjacent column tracks:

```text
┌────────────────────────────┬──────────┐
│          Item 1            │  Item 2  │
│        spans 2 cells       │          │
└────────────────────────────┴──────────┘
```

The item covers the space that would otherwise contain two cells.

### Spanning Rows

An item can also span multiple rows:

```css
.item {
    grid-row: span 2;
}
```

Example:

```text
┌────────────┬────────────┐
│            │   Item 2   │
│   Item 1   ├────────────┤
│            │   Item 3   │
└────────────┴────────────┘
```

Here, `Item 1` spans two row tracks.

### Grid Area

When an item spans multiple cells, the combined space occupied by that item can be considered its **grid area**.

For example:

```css
.item {
    grid-column: span 2;
    grid-row: span 2;
}
```

Conceptually:

```text
┌───────────────────────┬──────────┐
│                       │          │
│        Item 1         │  Item 2  │
│                       ├──────────┤
│                       │  Item 3  │
└───────────────────────┴──────────┘
```

The item's grid area covers multiple cells.

### Empty Grid Cells

A grid can contain cells that do not currently contain a grid item.

For example:

```text
┌──────────┬──────────┐
│  Item 1  │          │
├──────────┼──────────┤
│  Item 2  │  Item 3  │
└──────────┴──────────┘
```

The top-right cell is still part of the grid even though no item occupies it.

### Grid Cells and `gap`

When `gap` is used:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

the cells remain part of the grid, while the gap creates space between the tracks.

Conceptually:

```text
┌────────────┐      ┌────────────┐
│   Cell 1   │ 20px │   Cell 2   │
└────────────┘      └────────────┘
```

The gap itself is not a grid cell or grid track.

### Grid Cell Mental Model

```text
Grid
 │
 ├── Grid Lines
 │      ↓
 │   Boundaries
 │
 ├── Grid Tracks
 │      ↓
 │   Rows / Columns
 │
 └── Grid Cells
        ↓
     Individual
     grid spaces
```

A useful way to remember the relationship is:

```text
Grid Lines
    ↓
define
    ↓
Grid Tracks
    ↓
intersect
    ↓
Grid Cells
    ↓
contain
    ↓
Grid Items
```

> 💡 **Remember:** A grid cell is the smallest individual space in a CSS Grid, created by the intersection of one row track and one column track. Grid items are placed into these cells and can span multiple cells.

---

## Grid Template Columns

The `grid-template-columns` property defines the **number and size of column tracks** in a CSS Grid.

It is one of the main properties used to create the column structure of a grid.

### Basic Syntax

```css
.container {
    display: grid;
    grid-template-columns: value;
}
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 300px;
}
```

This creates two columns:

```text
┌────────────┬────────────────┐
│   200px    │     300px      │
└────────────┴────────────────┘
```

### Multiple Column Values

Each value represents a column track.

```css
.container {
    grid-template-columns: 100px 200px 300px;
}
```

This creates three columns:

```text
┌───────┬──────────────┬────────────────────┐
│ 100px │    200px     │       300px        │
└───────┴──────────────┴────────────────────┘
```

So:

```text
1st value → Column 1
2nd value → Column 2
3rd value → Column 3
```

### Equal Columns

You can create equal-width columns using the `fr` unit:

```css
.container {
    grid-template-columns: 1fr 1fr;
}
```

The available space is divided equally:

```text
┌────────────────┬────────────────┐
│      1fr       │      1fr       │
└────────────────┴────────────────┘
```

Three equal columns:

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

Or:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

### Fixed-Width Columns

You can use fixed lengths:

```css
.container {
    grid-template-columns: 200px 300px;
}
```

The first column is `200px` and the second is `300px`.

This is useful when a specific column width is required.

### Fixed and Flexible Columns

Fixed and flexible tracks can be combined:

```css
.container {
    grid-template-columns: 200px 1fr;
}
```

Conceptually:

```text
┌──────────────┬──────────────────────────┐
│   Sidebar    │       Main Content       │
│    200px     │           1fr            │
└──────────────┴──────────────────────────┘
```

The `200px` column keeps its defined size, while `1fr` uses the remaining flexible space.

### Different Flexible Sizes

Different `fr` values create proportional columns:

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

The second column receives twice the flexible share of the first.

### Three Different Flexible Columns

```css
.container {
    grid-template-columns: 1fr 2fr 1fr;
}
```

The ratio is:

```text
1 : 2 : 1
```

Conceptually:

```text
┌──────────┬─────────────────────┬──────────┐
│   1fr    │        2fr          │   1fr    │
└──────────┴─────────────────────┴──────────┘
```

### Using `auto`

The `auto` keyword can be used as a track size:

```css
.container {
    grid-template-columns: auto 1fr;
}
```

The `auto` track can size itself based on its content and available space.

This can be useful for layouts where one column should adapt to its contents.

### Using Percentages

Percentages can also define columns:

```css
.container {
    grid-template-columns: 50% 50%;
}
```

This creates two columns based on the grid container's relevant size.

When using percentages together with gaps, remember that the percentage track sizes and the gaps both contribute to the overall layout.

### Combining Different Units

Different sizing values can be combined:

```css
.container {
    grid-template-columns: 150px 20% 1fr;
}
```

A grid can therefore contain:

```text
Fixed column
      +
Percentage column
      +
Flexible column
```

### Using `repeat()`

The `repeat()` function is useful when multiple columns use the same pattern.

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

Both create three equal columns.

Another example:

```css
.container {
    grid-template-columns: repeat(4, 200px);
}
```

This creates four `200px` columns.

### Repeating Mixed Patterns

`repeat()` can also repeat a more complex pattern.

```css
.container {
    grid-template-columns: repeat(2, 100px 1fr);
}
```

This repeats:

```text
100px 1fr
```

twice.

Conceptually:

```text
100px | 1fr | 100px | 1fr
```

### Using `minmax()`

`minmax()` can define a minimum and maximum size for a column.

```css
.container {
    grid-template-columns: minmax(200px, 1fr) 1fr;
}
```

The first column can grow as flexible space becomes available while respecting the specified minimum.

`minmax()` is especially useful for responsive layouts.

### Responsive Column Pattern

A common responsive pattern is:

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

### Grid Columns With `gap`

The `gap` property adds space between the columns:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Conceptually:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│ Column 1 │      │ Column 2 │      │ Column 3 │
└──────────┘      └──────────┘      └──────────┘
```

The `gap` is separate from the column track sizes.

### Common Examples

Two equal columns:

```css
grid-template-columns: 1fr 1fr;
```

Three equal columns:

```css
grid-template-columns: repeat(3, 1fr);
```

Sidebar and content:

```css
grid-template-columns: 250px 1fr;
```

Three-column layout:

```css
grid-template-columns: 1fr 2fr 1fr;
```

Four fixed columns:

```css
grid-template-columns: repeat(4, 200px);
```

Responsive minimum-width columns:

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

### Important Point

`grid-template-columns` controls the **explicit column tracks** of the grid.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 2fr;
}
```

This explicitly defines three column tracks.

```text
200px | 1fr | 2fr
```

> 💡 **Remember:** `grid-template-columns` defines the column structure of a grid. Each value represents a column track, and values such as `px`, `%`, `auto`, `fr`, `repeat()`, and `minmax()` can be used to create flexible and responsive layouts.

---

## Grid Template Rows

The `grid-template-rows` property defines the **number and size of row tracks** in a CSS Grid.

It is the row equivalent of `grid-template-columns`.

### Basic Syntax

```css
.container {
    display: grid;
    grid-template-rows: value;
}
```

For example:

```css
.container {
    display: grid;
    grid-template-rows: 100px 200px;
}
```

This creates two rows:

```text
┌────────────────────────────┐
│          Row 1             │ 100px
├────────────────────────────┤
│          Row 2             │ 200px
└────────────────────────────┘
```

### Multiple Row Values

Each value represents one row track.

```css
.container {
    grid-template-rows: 100px 150px 200px;
}
```

This creates three rows:

```text
┌────────────────────────────┐
│          Row 1             │ 100px
├────────────────────────────┤
│          Row 2             │ 150px
├────────────────────────────┤
│          Row 3             │ 200px
└────────────────────────────┘
```

### Equal-Height Rows

The `fr` unit can be used to divide available space equally.

```css
.container {
    grid-template-rows: 1fr 1fr;
}
```

The available flexible space is divided equally:

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

Three equal rows:

```css
.container {
    grid-template-rows: repeat(3, 1fr);
}
```

### Fixed and Flexible Rows

You can combine fixed and flexible row sizes.

```css
.container {
    grid-template-rows: 80px 1fr;
}
```

This is useful for layouts such as a header and main content:

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

A common page structure can be created with:

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr 60px;
}
```

Result:

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

### Different Flexible Sizes

Different `fr` values can create proportional row sizes.

```css
.container {
    grid-template-rows: 1fr 2fr;
}
```

The available flexible space is divided into three parts:

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│                            │
│            2fr             │
│                            │
└────────────────────────────┘
```

The second row receives twice the flexible share of the first.

### Using `auto`

Rows can use the `auto` keyword:

```css
.container {
    grid-template-rows: auto 1fr;
}
```

The `auto` track can size itself based on its contents and available space.

This can be useful for content-dependent rows.

### Using Percentages

Percentage values can also define row tracks.

```css
.container {
    grid-template-rows: 30% 70%;
}
```

The row sizes are calculated relative to the relevant size of the grid container.

When percentages are combined with gaps, the total layout should be considered carefully.

### Combining Different Units

Different sizing values can be combined:

```css
.container {
    grid-template-rows: 80px 30% 1fr;
}
```

For example:

```text
80px
  +
30%
  +
1fr
```

This allows different rows to use different sizing strategies.

### Using `repeat()`

The `repeat()` function can create multiple rows with the same size.

Instead of:

```css
.container {
    grid-template-rows: 100px 100px 100px;
}
```

you can write:

```css
.container {
    grid-template-rows: repeat(3, 100px);
}
```

Both create three `100px` rows.

### Repeating Flexible Rows

```css
.container {
    grid-template-rows: repeat(3, 1fr);
}
```

This creates three equal flexible row tracks.

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

### Using `minmax()`

`minmax()` can define a minimum and maximum row size.

```css
.container {
    grid-template-rows: minmax(100px, 1fr) 1fr;
}
```

The first row can grow flexibly while respecting its minimum size.

This is useful when row content needs a minimum amount of space.

### Rows With `gap`

The `gap` property creates space between rows.

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px 100px;
    gap: 20px;
}
```

Conceptually:

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

The gap is space between the tracks, not another row.

### Rows and Columns Together

`grid-template-rows` is commonly used together with `grid-template-columns`.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 200px;
}
```

This creates:

```text
              Columns
          1fr          1fr
       ┌────────────┬────────────┐
100px  │            │            │
       ├────────────┼────────────┤
200px  │            │            │
       └────────────┴────────────┘
          ↑
         Rows
```

### Practical Page Layout

A complete page structure can use:

```css
.page {
    display: grid;
    grid-template-rows: 70px 1fr 50px;
}
```

HTML:

```html
<div class="page">
    <header>Header</header>
    <main>Main Content</main>
    <footer>Footer</footer>
</div>
```

The layout becomes:

```text
┌────────────────────────────┐
│           Header           │
├────────────────────────────┤
│                            │
│        Main Content        │
│                            │
├────────────────────────────┤
│           Footer           │
└────────────────────────────┘
```

### Important Property

The main property for defining explicit row tracks is:

```css
grid-template-rows
```

Examples:

```css
grid-template-rows: 100px 200px;
```

```css
grid-template-rows: 1fr 1fr;
```

```css
grid-template-rows: repeat(3, 1fr);
```

```css
grid-template-rows: 80px 1fr 60px;
```

### Columns vs Rows

```text
grid-template-columns
        ↓
Defines column tracks
        ↓
Horizontal structure

grid-template-rows
        ↓
Defines row tracks
        ↓
Vertical structure
```

Together:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: 100px 1fr;
}
```

create the two-dimensional grid structure.

> 💡 **Remember:** `grid-template-rows` defines the size of explicit row tracks. It can use fixed values, flexible `fr` units, `auto`, percentages, `repeat()`, `minmax()`, and other supported sizing values.

---

## The `fr` Unit

The `fr` unit stands for **fraction**.

It represents a **fraction of the available space** in a CSS Grid container.

The `fr` unit is one of the most useful sizing units in CSS Grid because it allows grid tracks to share available space proportionally.

### Basic Syntax

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

This creates two columns that share the available flexible space equally.

```text
┌────────────────┬────────────────┐
│      1fr       │      1fr       │
└────────────────┴────────────────┘
```

Each column receives one fraction of the available space.

### Two Equal Fractions

```css
grid-template-columns: 1fr 1fr;
```

The available space is divided into:

```text
1 + 1 = 2 fractions
```

Each column receives:

```text
1 / 2
```

of the available flexible space.

### Three Equal Fractions

```css
grid-template-columns: 1fr 1fr 1fr;
```

The available flexible space is divided into:

```text
1 + 1 + 1 = 3 fractions
```

Result:

```text
┌──────────┬──────────┬──────────┐
│   1fr    │   1fr    │   1fr    │
└──────────┴──────────┴──────────┘
```

Each column receives an equal share.

### Unequal Fractions

Different `fr` values create proportional tracks.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
}
```

The total number of fractions is:

```text
1 + 2 = 3
```

Therefore:

```text
First column  → 1/3
Second column → 2/3
```

Conceptually:

```text
┌──────────┬─────────────────────┐
│   1fr    │        2fr          │
└──────────┴─────────────────────┘
```

The second column receives twice the flexible share of the first.

### Three Different Fractions

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr 3fr;
}
```

The total is:

```text
1 + 2 + 3 = 6
```

Therefore:

```text
Column 1 → 1/6
Column 2 → 2/6
Column 3 → 3/6
```

Conceptually:

```text
┌─────┬──────────┬───────────────┐
│ 1fr │   2fr    │      3fr      │
└─────┴──────────┴───────────────┘
```

### `fr` With Fixed Columns

The `fr` unit is especially useful when combined with fixed sizes.

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr;
}
```

The `200px` track gets its defined size first.

The `1fr` track uses the remaining available space.

```text
┌──────────────┬──────────────────────────┐
│   200px      │           1fr            │
│              │                          │
└──────────────┴──────────────────────────┘
```

This pattern is commonly used for sidebars.

### Multiple Flexible Tracks With a Fixed Track

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 2fr;
}
```

Conceptually:

```text
┌──────────────┬──────────┬────────────────┐
│    200px     │   1fr    │      2fr       │
└──────────────┴──────────┴────────────────┘
```

The fixed track is allocated separately, and the remaining flexible space is distributed according to the `fr` values.

### `fr` and `gap`

Consider:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

The gap occupies space between the tracks.

Conceptually:

```text
┌──────────────┐ 20px ┌──────────────┐
│     1fr      │      │     1fr      │
└──────────────┘      └──────────────┘
```

The `fr` tracks share the space available after accounting for the gap.

### `fr` Can Be Used for Rows

The `fr` unit is not limited to columns.

It can also be used with rows:

```css
.container {
    display: grid;
    grid-template-rows: 1fr 1fr;
}
```

This divides the available grid height into two flexible portions.

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

### Header and Main Content

A common layout is:

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr;
}
```

The first row is fixed:

```text
80px
```

The second row takes the remaining flexible space:

```text
1fr
```

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│        Main Content        │ 1fr
│                            │
└────────────────────────────┘
```

### `fr` Is Different From `%`

These two approaches are not always equivalent.

For example:

```css
grid-template-columns: 50% 50%;
```

uses percentages based on the grid container's relevant size.

While:

```css
grid-template-columns: 1fr 1fr;
```

divides the available flexible space between the tracks.

This distinction becomes especially important when gaps or other fixed-sized tracks are present.

### `fr` With `auto`

You can combine `fr` with `auto`:

```css
.container {
    display: grid;
    grid-template-columns: auto 1fr;
}
```

The first column can size itself based on its content, while the second flexible column receives the remaining available space.

### `fr` and Content

The exact final size of an `fr` track can also depend on the grid's sizing rules and the minimum size requirements of its contents.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

does not simply mean that every possible piece of space is always split blindly in half.

Grid's track-sizing algorithm also considers factors such as:

- Available space
- Track sizing functions
- Minimum contributions from grid items
- Gaps
- Other fixed or intrinsic sizes

For straightforward layouts, however, `1fr 1fr` can be understood as two equal flexible portions.

### Common `fr` Patterns

Two equal columns:

```css
grid-template-columns: 1fr 1fr;
```

Three equal columns:

```css
grid-template-columns: repeat(3, 1fr);
```

Sidebar and content:

```css
grid-template-columns: 250px 1fr;
```

Main content with a larger secondary area:

```css
grid-template-columns: 1fr 2fr;
```

Header and flexible content:

```css
grid-template-rows: 70px 1fr;
```

### Practical Example

HTML:

```html
<div class="layout">
    <aside>Sidebar</aside>
    <main>Main Content</main>
</div>
```

CSS:

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
    gap: 20px;
}
```

Result:

```text
┌──────────────┐ 20px ┌──────────────────────────┐
│   Sidebar    │      │       Main Content       │
│    200px     │      │           1fr            │
└──────────────┘      └──────────────────────────┘
```

The sidebar keeps its fixed width while the main content expands into the remaining space.

### Important Points

```text
fr
│
├── Means fraction
├── Represents flexible space
├── Can be used for columns
├── Can be used for rows
├── Multiple fr values create proportions
├── Works with fixed-size tracks
├── Works with gaps
└── Is useful for responsive layouts
```

> 💡 **Remember:** The `fr` unit represents a flexible fraction of the available grid space. Values such as `1fr 2fr` distribute flexible space proportionally, while fixed tracks such as `200px` can be combined with `fr` tracks to create practical layouts.

---

## `repeat()` Function

The `repeat()` function is a CSS Grid function used to **repeat a pattern of grid tracks**.

It is commonly used with `grid-template-columns` and `grid-template-rows` to avoid writing the same track size multiple times.

### Basic Syntax

```css
repeat(count, track-size)
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

This is equivalent to:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Both create three equal columns.

### Repeating Equal Columns

```css
.container {
    grid-template-columns: repeat(4, 1fr);
}
```

Result:

```text
┌────────┬────────┬────────┬────────┐
│  1fr   │  1fr   │  1fr   │  1fr   │
└────────┴────────┴────────┴────────┘
```

The first argument specifies how many times the track should be repeated.

The second argument specifies the track size.

```text
repeat(4, 1fr)
       │   │
       │   └── Track size
       └────── Number of repetitions
```

### Repeating Fixed-Size Columns

`repeat()` is not limited to `fr`.

```css
.container {
    grid-template-columns: repeat(3, 200px);
}
```

This creates:

```text
200px | 200px | 200px
```

Equivalent to:

```css
grid-template-columns: 200px 200px 200px;
```

### Repeating Rows

`repeat()` can also be used with rows.

```css
.container {
    grid-template-rows: repeat(3, 100px);
}
```

This creates three `100px` rows:

```text
┌──────────────────────┐
│       100px           │
├──────────────────────┤
│       100px           │
├──────────────────────┤
│       100px           │
└──────────────────────┘
```

### Repeating Different Flexible Sizes

You can repeat a pattern containing different track sizes.

```css
.container {
    grid-template-columns: repeat(2, 1fr 2fr);
}
```

This produces:

```text
1fr | 2fr | 1fr | 2fr
```

Equivalent to:

```css
grid-template-columns: 1fr 2fr 1fr 2fr;
```

### Repeating Multiple Values

The second argument can contain multiple track sizes.

```css
.container {
    grid-template-columns: repeat(3, 100px 1fr);
}
```

This produces:

```text
100px | 1fr | 100px | 1fr | 100px | 1fr
```

The pattern:

```text
100px 1fr
```

is repeated three times.

### Combining `repeat()` With Other Tracks

You can combine `repeat()` with tracks outside the function.

```css
.container {
    grid-template-columns: 200px repeat(3, 1fr) 150px;
}
```

This creates:

```text
200px | 1fr | 1fr | 1fr | 150px
```

This is useful when the beginning and end of a layout have fixed columns while the middle contains repeated flexible columns.

### `repeat()` With `minmax()`

`repeat()` can be combined with `minmax()`.

```css
.container {
    grid-template-columns: repeat(3, minmax(200px, 1fr));
}
```

This creates three columns where each track has:

```text
Minimum → 200px
Maximum → 1fr
```

This is particularly useful for responsive card layouts.

### Responsive Card Layout

A common Grid pattern is:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, minmax(200px, 1fr));
    gap: 20px;
}
```

This creates three columns while giving each column a minimum size.

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│  Card 1  │  Card 2  │  Card 3  │
└──────────┴──────────┴──────────┘
```

If the available space becomes insufficient for the minimum track sizes, the layout may need another responsive strategy, such as media queries or the auto-repeat forms discussed later.

### `repeat()` With `auto-fit`

`repeat()` can use the `auto-fit` keyword:

```css
.container {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(200px, 1fr)
    );
}
```

The browser determines how many tracks can fit based on the available space and the minimum track size.

This can create responsive grids without specifying a fixed number of columns.

### `repeat()` With `auto-fill`

Similarly:

```css
.container {
    display: grid;
    grid-template-columns: repeat(
        auto-fill,
        minmax(200px, 1fr)
    );
}
```

`auto-fill` and `auto-fit` are useful for responsive Grid layouts.

Their behavior differs when there is extra space and when empty tracks can be created, so they should not be treated as identical.

### `repeat()` With Rows and Columns

You can use `repeat()` independently for both dimensions.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 100px);
}
```

This creates:

```text
Columns → 3 equal tracks
Rows    → 2 tracks of 100px
```

Result:

```text
┌────────┬────────┬────────┐
│        │        │        │ 100px
├────────┼────────┼────────┤
│        │        │        │ 100px
└────────┴────────┴────────┘
```

### `repeat()` vs Writing Values Manually

Without `repeat()`:

```css
grid-template-columns:
    1fr 1fr 1fr 1fr 1fr;
```

With `repeat()`:

```css
grid-template-columns: repeat(5, 1fr);
```

The second version is shorter and makes the repetition pattern more obvious.

### Common Examples

Three equal columns:

```css
grid-template-columns: repeat(3, 1fr);
```

Four fixed columns:

```css
grid-template-columns: repeat(4, 200px);
```

Three equal rows:

```css
grid-template-rows: repeat(3, 1fr);
```

Repeated mixed pattern:

```css
grid-template-columns: repeat(2, 1fr 2fr);
```

Responsive columns:

```css
grid-template-columns: repeat(
    auto-fit,
    minmax(200px, 1fr)
);
```

### Important Points

```text
repeat()
│
├── Repeats grid tracks
├── Used with columns and rows
├── First argument → repetition count
├── Second argument → track pattern
├── Can repeat one track size
├── Can repeat multiple track sizes
├── Can be combined with minmax()
├── Can be combined with auto-fit
└── Can be combined with auto-fill
```

> 💡 **Remember:** `repeat()` makes Grid declarations shorter by repeating a track size or pattern. For example, `repeat(3, 1fr)` creates three equal flexible tracks.

---

## `minmax()` Function

The `minmax()` function is a CSS Grid function used to define a **minimum and maximum size for a grid track**.

It is useful when you want a grid track to be flexible while preventing it from becoming too small or too large.

### Basic Syntax

```css
minmax(minimum, maximum)
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: minmax(200px, 1fr);
}
```

This means:

```text
Minimum size → 200px
Maximum size → 1fr
```

The track can grow as needed, but it should not become smaller than its minimum size.

### Basic Example

```css
.container {
    display: grid;
    grid-template-columns: minmax(200px, 400px);
}
```

The column can have a size between:

```text
200px → 400px
```

Conceptually:

```text
Minimum                 Maximum
  200px                    400px
    │                        │
    ├────────────────────────┤
             Track
```

### `minmax()` With `fr`

A common pattern is:

```css
.container {
    display: grid;
    grid-template-columns: minmax(200px, 1fr);
}
```

Here:

```text
Minimum → 200px
Maximum → 1fr
```

The column can grow to use available flexible space while maintaining a minimum size.

### Multiple Columns

You can use `minmax()` with multiple columns:

```css
.container {
    display: grid;
    grid-template-columns:
        minmax(200px, 1fr)
        minmax(200px, 1fr);
}
```

This creates two flexible columns, each with a minimum size of `200px`.

```text
┌────────────────┬────────────────┐
│     1fr        │      1fr       │
│ min 200px      │  min 200px     │
└────────────────┴────────────────┘
```

### `minmax()` With `repeat()`

`minmax()` becomes especially useful when combined with `repeat()`.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, minmax(200px, 1fr));
}
```

This creates three columns.

Each column has:

```text
Minimum → 200px
Maximum → 1fr
```

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│  Column  │  Column  │  Column  │
│ min 200  │ min 200  │ min 200  │
└──────────┴──────────┴──────────┘
```

### Responsive Card Layout

A common use of `minmax()` is a card grid:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(3, minmax(200px, 1fr));
    gap: 20px;
}
```

The columns can grow when more space is available while maintaining their minimum size.

### `auto-fit` With `minmax()`

For responsive layouts, `auto-fit` can be combined with `minmax()`:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
}
```

This allows the browser to determine how many columns can fit while using:

```text
Minimum column size → 200px
Maximum column size → 1fr
```

For example, a wide screen might produce:

```text
┌────────┬────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │ Card 4 │
└────────┴────────┴────────┴────────┘
```

A narrower screen might produce:

```text
┌────────┬────────┐
│ Card 1 │ Card 2 │
├────────┼────────┤
│ Card 3 │ Card 4 │
└────────┴────────┘
```

### `auto-fill` With `minmax()`

Another common pattern is:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fill, minmax(200px, 1fr));
}
```

`auto-fill` allows the grid to create as many tracks as can fit according to the minimum track size.

### `auto-fit` vs `auto-fill`

Both are commonly used with:

```css
repeat()
```

and:

```css
minmax()
```

For example:

```css
repeat(auto-fit, minmax(200px, 1fr))
```

and:

```css
repeat(auto-fill, minmax(200px, 1fr))
```

They are similar when the grid is filled with enough items, but they can behave differently when there is extra space and fewer items than available tracks.

A useful simplified distinction is:

```text
auto-fill
    ↓
Keeps fitting tracks into the available space

auto-fit
    ↓
Fits tracks and can collapse empty tracks
    allowing existing items to expand
```

### `minmax()` With Fixed Maximum

You can use fixed values for both arguments:

```css
grid-template-columns: minmax(200px, 400px);
```

The track is constrained between:

```text
200px minimum
400px maximum
```

### `minmax()` With `auto`

`auto` can also be used in supported track-sizing combinations.

For example:

```css
grid-template-columns: minmax(200px, auto);
```

This allows the track to have a minimum of `200px` while its maximum sizing behavior is based on `auto`.

### `minmax()` With Rows

`minmax()` is not limited to columns.

It can also be used for rows:

```css
.container {
    display: grid;
    grid-template-rows: minmax(100px, 1fr);
}
```

The row has:

```text
Minimum → 100px
Maximum → 1fr
```

### Preventing Very Small Columns

Consider a responsive card layout:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

Depending on the available space, the columns can become too narrow for the intended design.

Using:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(3, minmax(200px, 1fr));
}
```

provides a minimum track size.

### `minmax()` and `gap`

`minmax()` can be combined with `gap`:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

The grid must account for both:

```text
Minimum track sizes
        +
Gaps
        +
Available container space
```

This makes the pattern useful for responsive card layouts.

### Common Examples

Minimum `200px`, flexible maximum:

```css
grid-template-columns: minmax(200px, 1fr);
```

Three flexible columns:

```css
grid-template-columns:
    repeat(3, minmax(200px, 1fr));
```

Responsive columns:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
```

Fixed range:

```css
grid-template-columns:
    minmax(200px, 400px);
```

Flexible rows:

```css
grid-template-rows:
    minmax(100px, 1fr);
```

### Important Points

```text
minmax()
│
├── Defines a minimum size
├── Defines a maximum size
├── Used for grid tracks
├── Works with columns
├── Works with rows
├── Commonly used with fr
├── Commonly used with repeat()
├── Useful for responsive layouts
├── Works with auto-fit
└── Works with auto-fill
```

> 💡 **Remember:** `minmax(minimum, maximum)` gives a grid track a size range. It is especially useful for responsive layouts where a track should remain usable at smaller sizes but still expand when more space is available.

---

## `gap`

The `gap` property controls the **space between rows and columns** in a CSS Grid.

It is useful for creating consistent spacing between grid tracks without adding margins to individual grid items.

### Basic Syntax

```css
.container {
    display: grid;
    gap: 20px;
}
```

This creates a `20px` gap between both rows and columns.

### Basic Example

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

The result is conceptually:

```text
┌────────────┐  20px  ┌────────────┐
│   Item 1   │        │   Item 2   │
└────────────┘        └────────────┘

             20px

┌────────────┐  20px  ┌────────────┐
│   Item 3   │        │   Item 4   │
└────────────┘        └────────────┘
```

The `20px` spacing is applied between the grid tracks.

### `gap` Between Columns and Rows

When a single value is used:

```css
gap: 20px;
```

the same gap is applied to:

```text
Rows    → 20px
Columns → 20px
```

### Different Row and Column Gaps

You can specify separate values:

```css
.container {
    gap: 10px 20px;
}
```

The order is:

```text
gap: row-gap column-gap;
```

Therefore:

```text
Row gap    → 10px
Column gap → 20px
```

Conceptually:

```text
┌────────────┐ 20px ┌────────────┐
│            │      │            │
└────────────┘      └────────────┘
       ↑
      10px
       ↓
┌────────────┐ 20px ┌────────────┐
│            │      │            │
└────────────┘      └────────────┘
```

### `row-gap`

The `row-gap` property controls the spacing **between rows**.

```css
.container {
    row-gap: 30px;
}
```

Only the vertical spacing between row tracks is affected.

Example:

```text
┌────────────┐
│    Row 1   │
└────────────┘
      ↑
    30px
      ↓
┌────────────┐
│    Row 2   │
└────────────┘
```

### `column-gap`

The `column-gap` property controls the spacing **between columns**.

```css
.container {
    column-gap: 20px;
}
```

Only the horizontal spacing between column tracks is affected.

Example:

```text
┌──────────┐ 20px ┌──────────┐
│ Column 1 │      │ Column 2 │
└──────────┘      └──────────┘
```

### `gap` vs `row-gap` and `column-gap`

These are related properties:

```css
gap: 20px;
```

sets both row and column gaps.

```css
row-gap: 20px;
column-gap: 30px;
```

sets them independently.

The shorthand:

```css
gap: 20px 30px;
```

is equivalent to:

```css
row-gap: 20px;
column-gap: 30px;
```

### `gap` With Multiple Columns

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Result:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│  Item 1  │      │  Item 2  │      │  Item 3  │
└──────────┘      └──────────┘      └──────────┘
```

The same `20px` spacing is used between the columns.

### `gap` With Rows

```css
.container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    row-gap: 30px;
}
```

This creates `30px` of vertical spacing between the rows.

```text
┌──────────┬──────────┐
│  Item 1  │  Item 2  │
└──────────┴──────────┘

          30px

┌──────────┬──────────┐
│  Item 3  │  Item 4  │
└──────────┴──────────┘
```

### `gap` With `fr`

The `gap` is separate from flexible `fr` tracks.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

Conceptually:

```text
┌──────────────┐ 20px ┌──────────────┐
│     1fr      │      │     1fr      │
└──────────────┘      └──────────────┘
```

The available space is distributed to the flexible tracks after the fixed gap is accounted for.

### `gap` With `minmax()`

`gap` is commonly combined with responsive `minmax()` layouts.

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

This creates:

```text
Responsive columns
        +
Consistent spacing
```

For example:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│  Card 1  │      │  Card 2  │      │  Card 3  │
└──────────┘      └──────────┘      └──────────┘
```

### `gap` vs Margins

Without `gap`, you might add margins to individual items:

```css
.item {
    margin: 10px;
}
```

With Grid, you can instead use:

```css
.container {
    gap: 20px;
}
```

This allows the container to control the spacing between grid tracks.

### Why `gap` Is Useful

Using `gap` provides several advantages:

- Consistent spacing
- Simpler CSS
- No need to add margins to every grid item
- Works for both rows and columns
- Easy to change responsively
- Useful for reusable components

### Responsive Gap

The gap can be changed using a media query.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
        gap: 12px;
    }
}
```

Large screens:

```text
Gap → 24px
```

Small screens:

```text
Gap → 12px
```

### Practical Card Layout

HTML:

```html
<div class="cards">
    <article>Card 1</article>
    <article>Card 2</article>
    <article>Card 3</article>
    <article>Card 4</article>
</div>
```

CSS:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
}
```

Result:

```text
┌────────────┐ 20px ┌────────────┐
│   Card 1   │      │   Card 2   │
└────────────┘      └────────────┘

             20px

┌────────────┐ 20px ┌────────────┐
│   Card 3   │      │   Card 4   │
└────────────┘      └────────────┘
```

### Important Points

```text
gap
│
├── Controls spacing between grid tracks
├── Can control rows and columns
├── One value → same row and column gap
├── Two values → row gap and column gap
├── row-gap → spacing between rows
├── column-gap → spacing between columns
└── Does not create an additional grid track
```

### Common Examples

Same gap everywhere:

```css
gap: 20px;
```

Different row and column gaps:

```css
gap: 10px 20px;
```

Only row spacing:

```css
row-gap: 20px;
```

Only column spacing:

```css
column-gap: 30px;
```

Responsive card grid:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));

gap: 20px;
```

> 💡 **Remember:** `gap` controls the space between grid rows and columns. It is the preferred way to create consistent spacing between Grid tracks instead of adding margins to individual grid items.

---

## Grid Column

The `grid-column` property controls **where a grid item starts and ends across the column grid lines**.

It can be used to position an item in specific columns or make it span multiple columns.

### Basic Syntax

```css
.item {
    grid-column: start / end;
}
```

For example:

```css
.item {
    grid-column: 1 / 3;
}
```

This means:

```text
Start at column line 1
End at column line 3
```

Since the space between line 1 and line 3 contains two column tracks, the item spans two columns.

### Grid Column Lines

Consider a three-column grid:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

There are four column lines:

```text
Line 1      Line 2      Line 3      Line 4
   │           │           │           │
   │    1fr    │    1fr    │    1fr    │
   │           │           │           │
```

The columns are:

```text
Column 1 → Line 1 to Line 2
Column 2 → Line 2 to Line 3
Column 3 → Line 3 to Line 4
```

### Positioning an Item

To place an item in the first column:

```css
.item {
    grid-column: 1 / 2;
}
```

Conceptually:

```text
Line 1       Line 2       Line 3       Line 4
   ↓            ↓            ↓            ↓
   ├────────────┼────────────┼────────────┤
   │   Item     │            │            │
   └────────────┴────────────┴────────────┘
```

The item occupies the first column track.

### Spanning Two Columns

```css
.item {
    grid-column: 1 / 3;
}
```

The item spans:

```text
Line 1 → Line 3
```

Therefore it occupies two column tracks.

```text
┌──────────────────────┬──────────┐
│       Item 1         │  Item 2  │
│     2 columns        │          │
└──────────────────────┴──────────┘
```

### Spanning Three Columns

For a three-column grid:

```css
.item {
    grid-column: 1 / 4;
}
```

The item starts at line `1` and ends at line `4`.

```text
┌─────────────────────────────────┐
│             Item                │
│          3 columns              │
└─────────────────────────────────┘
```

### Using `span`

Instead of specifying the ending line, you can use `span`.

```css
.item {
    grid-column: span 2;
}
```

This tells the item to span two column tracks.

For example:

```text
┌──────────────────────┬──────────┐
│        Item 1        │  Item 2  │
│       span 2         │          │
└──────────────────────┴──────────┘
```

### Starting at a Specific Line and Spanning

You can combine a starting line with `span`.

```css
.item {
    grid-column: 2 / span 2;
}
```

This means:

```text
Start at line 2
    ↓
Span 2 columns
```

Conceptually:

```text
Line 1      Line 2      Line 3      Line 4
   │           │           │           │
   │           ├───────────────────────┤
   │           │        Item           │
   │           └───────────────────────┘
```

### Using `grid-column-start`

The `grid-column` property is a shorthand.

You can specify the starting line separately:

```css
.item {
    grid-column-start: 2;
}
```

This tells the item to start at column line `2`.

### Using `grid-column-end`

You can also specify the ending line:

```css
.item {
    grid-column-end: 4;
}
```

This tells the item to end at column line `4`.

Together:

```css
.item {
    grid-column-start: 2;
    grid-column-end: 4;
}
```

is equivalent to:

```css
.item {
    grid-column: 2 / 4;
}
```

### `grid-column` Shorthand

The general form is:

```css
grid-column: start / end;
```

For example:

```css
grid-column: 1 / 3;
```

The two values represent:

```text
Start line
    /
End line
```

### Negative Line Numbers

Grid column lines can also be referenced using negative numbers.

The last column line is:

```text
-1
```

For example:

```css
.item {
    grid-column: 1 / -1;
}
```

This makes the item span from the first column line to the last column line.

For a three-column grid:

```text
Line 1      Line 2      Line 3      Line 4
   │           │           │           │
   │                                   │
   ├───────────────────────────────────┤
   │               Item                │
   └───────────────────────────────────┘
                                       ↑
                                      -1
```

### Full-Width Element

A very common pattern is:

```css
.full-width {
    grid-column: 1 / -1;
}
```

This makes an item span across the entire explicit grid width.

Example:

```text
┌──────────────────────────────────────┐
│              Header                  │
├──────────────┬──────────────┬────────┤
│   Item 1     │   Item 2     │ Item 3 │
└──────────────┴──────────────┴────────┘
```

### Practical Example

HTML:

```html
<div class="layout">
    <header>Header</header>
    <main>Main Content</main>
    <aside>Sidebar</aside>
    <footer>Footer</footer>
</div>
```

CSS:

```css
.layout {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 20px;
}

header {
    grid-column: 1 / -1;
}

footer {
    grid-column: 1 / -1;
}
```

The layout can be structured as:

```text
┌───────────────────────────────┐
│            Header             │
├────────────────────┬──────────┤
│                    │          │
│     Main Content   │ Sidebar  │
│                    │          │
├────────────────────┴──────────┤
│            Footer             │
└───────────────────────────────┘
```

### `grid-column` With `repeat()`

Consider:

```css
.container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}
```

You can make an item span two columns:

```css
.item {
    grid-column: span 2;
}
```

Result:

```text
┌──────────────────────┬──────────┬──────────┐
│        Item 1        │  Item 2  │  Item 3  │
│       span 2         │          │          │
└──────────────────────┴──────────┴──────────┘
```

### `grid-column` Does Not Change the Grid Definition

This is an important distinction.

The grid structure is defined by:

```css
grid-template-columns
```

For example:

```css
.container {
    grid-template-columns: repeat(4, 1fr);
}
```

The position or span of an individual item is controlled by:

```css
grid-column
```

So:

```text
grid-template-columns
        ↓
Defines the grid

grid-column
        ↓
Positions an individual item
```

### Important Points

```text
grid-column
│
├── Positions a grid item horizontally
├── Uses column grid lines
├── Can define start and end lines
├── Can use span
├── Can use negative line numbers
├── grid-column-start → starting line
├── grid-column-end → ending line
└── Commonly used to make items span columns
```

Common examples:

```css
grid-column: 1 / 3;
```

```css
grid-column: span 2;
```

```css
grid-column: 2 / span 2;
```

```css
grid-column: 1 / -1;
```

> 💡 **Remember:** `grid-column` controls an individual grid item's horizontal placement by specifying the column grid lines where the item starts and ends.

---

## Grid Row

The `grid-row` property controls **where a grid item starts and ends across the row grid lines**.

It is used to position an item vertically or make it span multiple rows.

### Basic Syntax

```css
.item {
    grid-row: start / end;
}
```

For example:

```css
.item {
    grid-row: 1 / 3;
}
```

This means:

```text
Start at row line 1
End at row line 3
```

The item therefore spans two row tracks.

### Row Grid Lines

Consider a grid with three rows:

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px 100px;
}
```

There are four horizontal grid lines:

```text
Line 1
───────────────
    Row 1
───────────────
Line 2
    Row 2
───────────────
Line 3
    Row 3
───────────────
Line 4
```

The rows are:

```text
Row 1 → Line 1 to Line 2
Row 2 → Line 2 to Line 3
Row 3 → Line 3 to Line 4
```

### Positioning an Item

To place an item in the first row:

```css
.item {
    grid-row: 1 / 2;
}
```

The item starts at row line `1` and ends at row line `2`.

```text
┌────────────────────────────┐
│           Item             │
├────────────────────────────┤
│                            │
├────────────────────────────┤
│                            │
└────────────────────────────┘
```

### Spanning Two Rows

An item can span multiple rows:

```css
.item {
    grid-row: 1 / 3;
}
```

This makes the item span:

```text
Row 1
Row 2
```

Conceptually:

```text
┌────────────────┬───────────┐
│                │   Item 2  │
│    Item 1      ├───────────┤
│                │   Item 3  │
└────────────────┴───────────┘
```

### Using `span`

Instead of specifying the ending line, you can use `span`.

```css
.item {
    grid-row: span 2;
}
```

This tells the grid item to occupy two row tracks.

```text
┌────────────┬────────────┐
│            │   Item 2   │
│   Item 1   ├────────────┤
│  span 2    │   Item 3   │
└────────────┴────────────┘
```

### Starting at a Specific Line and Spanning

You can combine a starting line with `span`.

```css
.item {
    grid-row: 2 / span 2;
}
```

This means:

```text
Start at row line 2
        ↓
Span 2 rows
```

### `grid-row-start`

The `grid-row` property is a shorthand.

You can specify the starting line separately:

```css
.item {
    grid-row-start: 2;
}
```

This places the item's starting position at row line `2`.

### `grid-row-end`

You can specify the ending line separately:

```css
.item {
    grid-row-end: 4;
}
```

This tells the item to end at row line `4`.

Together:

```css
.item {
    grid-row-start: 2;
    grid-row-end: 4;
}
```

is equivalent to:

```css
.item {
    grid-row: 2 / 4;
}
```

### `grid-row` Shorthand

The general form is:

```css
grid-row: start / end;
```

For example:

```css
grid-row: 1 / 3;
```

means:

```text
Start → Row Line 1
End   → Row Line 3
```

Therefore, the item spans two row tracks.

### Negative Row Line Numbers

Grid row lines can also be referenced using negative numbers.

The last row line is:

```text
-1
```

For example:

```css
.item {
    grid-row: 1 / -1;
}
```

This makes the item span from the first row line to the last row line.

For a three-row grid:

```text
Line 1
───────────────
    Row 1
───────────────
    Row 2
───────────────
    Row 3
───────────────
Line 4 = -1
```

The item can therefore occupy the complete height of the grid.

### Full-Height Element

A common pattern is:

```css
.sidebar {
    grid-row: 1 / -1;
}
```

This makes the sidebar span from the first row line to the last row line.

Example:

```text
┌────────────┬─────────────────────┐
│            │       Header        │
│            ├─────────────────────┤
│  Sidebar   │                     │
│            │    Main Content     │
│            ├─────────────────────┤
│            │       Footer        │
└────────────┴─────────────────────┘
```

### Practical Example

HTML:

```html
<div class="layout">
    <header>Header</header>
    <aside>Sidebar</aside>
    <main>Main Content</main>
    <footer>Footer</footer>
</div>
```

CSS:

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
    grid-template-rows: 80px 1fr 60px;
    gap: 20px;
}

header {
    grid-column: 1 / -1;
}

aside {
    grid-row: 2 / 3;
}

main {
    grid-row: 2 / 3;
}

footer {
    grid-column: 1 / -1;
}
```

The structure is:

```text
┌───────────────────────────────┐
│            Header             │
├──────────────┬────────────────┤
│   Sidebar    │  Main Content  │
├──────────────┴────────────────┤
│            Footer             │
└───────────────────────────────┘
```

### `grid-row` Does Not Define the Grid

It is important to distinguish:

```css
grid-template-rows
```

from:

```css
grid-row
```

`grid-template-rows` defines the row tracks:

```css
.container {
    grid-template-rows: 100px 1fr 100px;
}
```

`grid-row` positions an individual grid item within those tracks:

```css
.item {
    grid-row: 1 / 3;
}
```

So:

```text
grid-template-rows
        ↓
Defines the grid rows

grid-row
        ↓
Positions an individual item
```

### `grid-row` With `grid-column`

Grid items can be positioned in both directions.

```css
.item {
    grid-column: 1 / 3;
    grid-row: 1 / 3;
}
```

This makes the item span:

```text
2 columns
+
2 rows
```

Conceptually:

```text
┌──────────────────────┬──────────┐
│                      │          │
│        Item          │  Item 2  │
│                      ├──────────┤
│                      │  Item 3  │
└──────────────────────┴──────────┘
```

### Important Points

```text
grid-row
│
├── Positions a grid item vertically
├── Uses row grid lines
├── Can define start and end lines
├── Can use span
├── Can use negative line numbers
├── grid-row-start → starting line
├── grid-row-end → ending line
└── Can be combined with grid-column
```

Common examples:

```css
grid-row: 1 / 3;
```

```css
grid-row: span 2;
```

```css
grid-row: 2 / span 2;
```

```css
grid-row: 1 / -1;
```

> 💡 **Remember:** `grid-row` controls an individual grid item's vertical placement by specifying the row grid lines where the item starts and ends.

---

## Grid Areas

A **grid area** is one or more grid cells that form a rectangular region of a CSS Grid.

Grid areas can be created and controlled using the `grid-area` property and, most commonly, the `grid-template-areas` property.

They are especially useful for creating readable page layouts.

### Basic Concept

Consider a grid:

```text
┌──────────┬──────────┐
│  Header  │  Header  │
├──────────┼──────────┤
│ Sidebar  │   Main   │
├──────────┼──────────┤
│  Footer  │  Footer  │
└──────────┴──────────┘
```

Here:

```text
Header → spans two cells
Sidebar → occupies one cell
Main → occupies one cell
Footer → spans two cells
```

Each named region is a **grid area**.

### `grid-template-areas`

The `grid-template-areas` property allows you to name areas of a grid.

Example:

```css
.layout {
    display: grid;

    grid-template-columns: 200px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

This defines three rows and two columns:

```text
┌──────────┬──────────┐
│  header  │  header  │
├──────────┼──────────┤
│ sidebar  │   main   │
├──────────┼──────────┤
│  footer  │  footer  │
└──────────┴──────────┘
```

The repeated names indicate that an area spans multiple cells.

### Assigning Elements to Areas

After defining the areas, individual grid items can be assigned using `grid-area`.

```css
header {
    grid-area: header;
}

aside {
    grid-area: sidebar;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

HTML:

```html
<div class="layout">
    <header>Header</header>

    <aside>Sidebar</aside>

    <main>Main Content</main>

    <footer>Footer</footer>
</div>
```

The complete layout becomes:

```text
┌───────────────────────────────┐
│            Header             │
├──────────────┬────────────────┤
│   Sidebar    │  Main Content  │
├──────────────┴────────────────┤
│            Footer             │
└───────────────────────────────┘
```

### Complete Example

HTML:

```html
<div class="layout">
    <header>Header</header>
    <aside>Sidebar</aside>
    <main>Main Content</main>
    <footer>Footer</footer>
</div>
```

CSS:

```css
.layout {
    display: grid;

    grid-template-columns: 200px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";

    gap: 20px;
}

header {
    grid-area: header;
}

aside {
    grid-area: sidebar;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

### Understanding the Area Definition

This:

```css
grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
```

can be read visually as:

```text
header  header
sidebar main
footer  footer
```

Each quoted string represents one **row**.

Each name inside the string represents a **column**.

Therefore:

```text
"header header"
```

means:

```text
Header occupies two columns
```

while:

```text
"sidebar main"
```

means:

```text
Sidebar → Column 1
Main    → Column 2
```

### Area Names Must Form Rectangles

A named grid area must form a rectangular region.

Valid:

```css
grid-template-areas:
    "header header"
    "main main";
```

Visual representation:

```text
┌──────────┬──────────┐
│  header  │  header  │
├──────────┼──────────┤
│   main   │   main   │
└──────────┴──────────┘
```

Also valid:

```css
grid-template-areas:
    "header header"
    "sidebar main"
    "sidebar main";
```

Here `sidebar` forms a rectangle covering two rows.

### Invalid Non-Rectangular Areas

An area cannot form an irregular shape.

For example, this is not a valid shape for a single named area:

```text
┌──────────┬──────────┐
│   box    │   box    │
├──────────┼──────────┤
│   box    │          │
└──────────┴──────────┘
```

The `box` area would be L-shaped rather than rectangular.

Grid areas must form rectangular regions.

### Empty Grid Cells

A period (`.`) represents an empty grid cell.

Example:

```css
grid-template-areas:
    "header header"
    "sidebar main"
    ".      footer";
```

Visual representation:

```text
┌──────────┬──────────┐
│  header  │  header  │
├──────────┼──────────┤
│ sidebar  │   main   │
├──────────┼──────────┤
│          │  footer  │
└──────────┴──────────┘
```

The `.` means that the cell is intentionally left empty.

### `grid-area`

The `grid-area` property can assign an item to a named grid area:

```css
.header {
    grid-area: header;
}
```

This is different from using `grid-area` with line numbers, which can also act as a shorthand for grid positioning.

For named areas, the syntax is simply:

```css
grid-area: area-name;
```

### Grid Areas and `grid-column` / `grid-row`

You can create layouts using either:

```css
grid-column
grid-row
```

or:

```css
grid-template-areas
grid-area
```

For example, using lines:

```css
header {
    grid-column: 1 / -1;
}
```

Using named areas:

```css
header {
    grid-area: header;
}
```

Named areas can make larger layouts easier to read.

### Practical Website Layout

A common website structure is:

```css
.layout {
    display: grid;

    grid-template-columns: 220px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "sidebar footer";
}
```

The structure is:

```text
┌───────────────────────────────┐
│            Header             │
├──────────────┬────────────────┤
│              │                │
│   Sidebar    │      Main      │
│              │                │
│              ├────────────────┤
│              │     Footer     │
└──────────────┴────────────────┘
```

### Responsive Grid Areas

Grid areas can be changed inside media queries.

For example:

```css
.layout {
    display: grid;

    grid-template-columns: 200px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}

@media (max-width: 600px) {
    .layout {
        grid-template-columns: 1fr;

        grid-template-areas:
            "header"
            "main"
            "sidebar"
            "footer";
    }
}
```

Large screens:

```text
┌──────────────┬──────────────┐
│    Header    │    Header    │
├──────────────┼──────────────┤
│   Sidebar    │     Main     │
├──────────────┴──────────────┤
│           Footer             │
└──────────────────────────────┘
```

Small screens:

```text
┌──────────────────────────────┐
│           Header             │
├──────────────────────────────┤
│            Main              │
├──────────────────────────────┤
│           Sidebar            │
├──────────────────────────────┤
│           Footer             │
└──────────────────────────────┘
```

The same HTML can therefore use a different visual arrangement.

### Advantages of Grid Areas

Named grid areas can make layouts:

- Easier to read
- Easier to understand
- Easier to modify
- Easier to make responsive
- More descriptive than relying only on line numbers

Compare:

```css
header {
    grid-column: 1 / -1;
}
```

with:

```css
header {
    grid-area: header;
}
```

The second approach clearly communicates the semantic role of the element.

### Important Points

```text
grid-template-areas
│
├── Defines named grid regions
├── Each string represents a row
├── Each name represents a cell
├── Repeated names create larger areas
├── "." represents an empty cell
└── Areas must form rectangles
```

And:

```text
grid-area
│
└── Assigns a grid item to a named area
```

> 💡 **Remember:** `grid-template-areas` lets you describe a grid layout using readable names such as `header`, `sidebar`, `main`, and `footer`. The elements can then be assigned to those areas using `grid-area`.

---

## Grid Alignment

CSS Grid provides several properties for controlling the **alignment and positioning of grid items and the grid itself**.

Grid alignment can be understood in two levels:

```text
Grid Container
      ↓
Align the grid tracks
      ↓
Grid Items
      ↓
Align individual items
```

The main alignment properties are:

```css
justify-items
align-items
place-items

justify-self
align-self
place-self

justify-content
align-content
place-content
```

### Grid Alignment Directions

Grid alignment uses two main axes:

```text
Horizontal → Inline axis
Vertical   → Block axis
```

In a typical left-to-right layout:

```text
          Horizontal
       ←──────────────→
       Inline axis

       ┌──────────────┐
       │              │
       │              │
       │              │
       └──────────────┘
              ↑
              │
              ↓
          Vertical
          Block axis
```

The `justify-*` properties generally control the inline axis, while the `align-*` properties generally control the block axis.

---

### `justify-items`

The `justify-items` property controls the horizontal alignment of **grid items inside their grid areas**.

Example:

```css
.container {
    display: grid;
    justify-items: center;
}
```

This centers the grid items within their cells.

```text
┌────────────────────┬────────────────────┐
│                    │                    │
│       Item         │        Item        │
│        ↕           │         ↕          │
│      center        │       center       │
│                    │                    │
└────────────────────┴────────────────────┘
```

Common values include:

```css
justify-items: start;
justify-items: end;
justify-items: center;
justify-items: stretch;
```

### `justify-items: start`

```css
.container {
    justify-items: start;
}
```

Items are aligned toward the start of their grid areas.

### `justify-items: end`

```css
.container {
    justify-items: end;
}
```

Items are aligned toward the end of their grid areas.

### `justify-items: center`

```css
.container {
    justify-items: center;
}
```

Items are centered horizontally within their grid areas.

### `justify-items: stretch`

```css
.container {
    justify-items: stretch;
}
```

Items stretch to fill the available inline space when their size allows it.

---

### `align-items`

The `align-items` property controls the vertical alignment of **grid items inside their grid areas**.

Example:

```css
.container {
    display: grid;
    align-items: center;
}
```

This centers the items along the block axis.

```text
┌────────────────────┐
│                    │
│      Item          │
│                    │
└────────────────────┘
          ↕
        center
```

Common values include:

```css
align-items: start;
align-items: end;
align-items: center;
align-items: stretch;
```

### `align-items: start`

```css
.container {
    align-items: start;
}
```

Items are aligned toward the start of their grid areas.

### `align-items: end`

```css
.container {
    align-items: end;
}
```

Items are aligned toward the end of their grid areas.

### `align-items: center`

```css
.container {
    align-items: center;
}
```

Items are centered vertically within their grid areas.

### `align-items: stretch`

```css
.container {
    align-items: stretch;
}
```

Items stretch along the block axis when their size allows it.

---

### `place-items`

`place-items` is a shorthand for:

```css
align-items
justify-items
```

For example:

```css
.container {
    place-items: center;
}
```

This is equivalent to:

```css
.container {
    align-items: center;
    justify-items: center;
}
```

You can also specify two values:

```css
.container {
    place-items: center start;
}
```

The first value applies to:

```text
align-items
```

The second value applies to:

```text
justify-items
```

---

### `justify-self`

The `justify-self` property controls the alignment of **one individual grid item** along the inline axis.

Example:

```css
.item {
    justify-self: center;
}
```

Only that item is centered.

```text
┌──────────────┬──────────────┐
│              │              │
│              │    Item      │
│              │    center    │
│              │              │
└──────────────┴──────────────┘
```

This overrides the container's `justify-items` behavior for that specific item.

### `align-self`

The `align-self` property controls the alignment of **one individual grid item** along the block axis.

```css
.item {
    align-self: center;
}
```

Only that item is vertically centered within its grid area.

### `place-self`

`place-self` is a shorthand for:

```css
align-self
justify-self
```

For example:

```css
.item {
    place-self: center;
}
```

This is equivalent to:

```css
.item {
    align-self: center;
    justify-self: center;
}
```

---

### `justify-content`

`justify-content` controls the alignment of the **grid tracks inside the grid container** along the inline axis.

This is different from `justify-items`.

```text
justify-content
      ↓
Moves the grid tracks

justify-items
      ↓
Moves items inside their grid areas
```

Example:

```css
.container {
    display: grid;
    grid-template-columns: 100px 100px;
    justify-content: center;
}
```

If there is extra horizontal space, the grid tracks are centered inside the container.

```text
┌──────────────────────────────────────┐
│       ┌───────┬───────┐              │
│       │ 100px │ 100px │              │
│       └───────┴───────┘              │
└──────────────────────────────────────┘
```

Common values include:

```css
justify-content: start;
justify-content: end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
justify-content: stretch;
```

---

### `align-content`

The `align-content` property controls the alignment of the **grid tracks inside the grid container** along the block axis.

Example:

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px;
    align-content: center;
}
```

If the container has extra vertical space, the grid tracks are centered.

```text
┌────────────────────────────┐
│                            │
│    ┌──────────────────┐    │
│    │      100px       │    │
│    ├──────────────────┤    │
│    │      100px       │    │
│    └──────────────────┘    │
│                            │
└────────────────────────────┘
```

---

### `place-content`

`place-content` is a shorthand for:

```css
align-content
justify-content
```

For example:

```css
.container {
    place-content: center;
}
```

This centers the grid tracks along both axes when there is extra space.

---

### `justify-items` vs `justify-content`

These properties are easy to confuse.

#### `justify-items`

Controls:

```text
Items inside their grid areas
```

Example:

```css
.container {
    justify-items: center;
}
```

#### `justify-content`

Controls:

```text
The grid tracks inside the container
```

Example:

```css
.container {
    justify-content: center;
}
```

Think of it as:

```text
Container
│
├── Grid Tracks
│      ↑
│   justify-content
│
└── Grid Items
       ↑
    justify-items
```

---

### `align-items` vs `align-content`

Similarly:

```text
align-items
    ↓
Aligns items inside grid areas

align-content
    ↓
Aligns the grid tracks inside the container
```

---

### `justify-self` vs `justify-items`

```text
justify-items
      ↓
Affects all grid items

justify-self
      ↓
Affects one grid item
```

For example:

```css
.container {
    justify-items: center;
}

.special {
    justify-self: end;
}
```

Most items are centered, while `.special` is aligned to the end.

---

### `align-self` vs `align-items`

```text
align-items
    ↓
Affects all grid items

align-self
    ↓
Affects one grid item
```

Example:

```css
.container {
    align-items: center;
}

.special {
    align-self: end;
}
```

---

### Practical Example

HTML:

```html
<div class="grid">
    <div class="item">Item 1</div>
    <div class="item special">Item 2</div>
    <div class="item">Item 3</div>
</div>
```

CSS:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 150px;
    gap: 20px;

    justify-items: center;
    align-items: center;
}

.special {
    justify-self: end;
    align-self: start;
}
```

The general grid items are centered within their cells, while the special item has its own alignment.

---

### Centering Grid Items

A common pattern for centering items is:

```css
.container {
    display: grid;
    place-items: center;
}
```

This is equivalent to:

```css
.container {
    align-items: center;
    justify-items: center;
}
```

This is useful for simple cards, icons, buttons, and other centered content.

### Important Points

```text
Grid Alignment
│
├── justify-items
│     └── Aligns all items horizontally
│
├── align-items
│     └── Aligns all items vertically
│
├── place-items
│     └── Shorthand for both
│
├── justify-self
│     └── Aligns one item horizontally
│
├── align-self
│     └── Aligns one item vertically
│
├── place-self
│     └── Shorthand for both
│
├── justify-content
│     └── Aligns grid tracks horizontally
│
├── align-content
│     └── Aligns grid tracks vertically
│
└── place-content
      └── Shorthand for both
```

> 💡 **Remember:** `*-items` controls items within their grid areas, `*-self` controls an individual item, and `*-content` controls the grid tracks within the grid container.

---

## Grid Auto Placement

CSS Grid can automatically place grid items into available grid cells.

This behavior is called **auto-placement**.

When you create a grid but do not explicitly position every item using properties such as `grid-column` or `grid-row`, the browser automatically determines where the items should go.

### Basic Example

HTML:

```html
<div class="grid">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
    <div>Item 4</div>
</div>
```

CSS:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
}
```

The browser automatically places the items:

```text
┌──────────┬──────────┐
│  Item 1  │  Item 2  │
├──────────┼──────────┤
│  Item 3  │  Item 4  │
└──────────┴──────────┘
```

### Default Placement

By default, Grid places items in **row order**.

For example:

```css
grid-template-columns: repeat(3, 1fr);
```

with six items produces:

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │ Item 5 │ Item 6 │
└────────┴────────┴────────┘
```

The browser fills available cells from one row to the next.

### `grid-auto-flow`

The `grid-auto-flow` property controls how automatically placed items are inserted into the grid.

Basic syntax:

```css
grid-auto-flow: value;
```

The main values are:

```css
row
column
dense
row dense
column dense
```

### `grid-auto-flow: row`

This is the default behavior.

```css
.grid {
    display: grid;
    grid-auto-flow: row;
}
```

Items are placed across rows.

Example:

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │ Item 5 │ Item 6 │
└────────┴────────┴────────┘
```

### `grid-auto-flow: column`

With:

```css
.grid {
    display: grid;
    grid-auto-flow: column;
}
```

the auto-placement direction changes to columns.

For example, with an explicitly defined number of rows:

```css
.grid {
    display: grid;
    grid-template-rows: repeat(2, 100px);
    grid-auto-flow: column;
}
```

the items are placed down the first column before moving to the next:

```text
┌──────────┬──────────┬──────────┐
│  Item 1  │  Item 3  │  Item 5  │
├──────────┼──────────┼──────────┤
│  Item 2  │  Item 4  │  Item 6  │
└──────────┴──────────┴──────────┘
```

### `grid-auto-flow: dense`

The `dense` keyword tells the auto-placement algorithm to try to fill earlier available spaces when possible.

Example:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-flow: dense;
}
```

This can allow later items to fill gaps that would otherwise remain empty.

### Why Gaps Can Appear

Consider a grid with three columns:

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │        │ Item 5 │
└────────┴────────┴────────┘
```

Suppose an item has been explicitly positioned or spans multiple tracks, leaving an earlier cell unavailable.

The normal auto-placement algorithm generally preserves the order of items rather than moving later items backward to fill every possible gap.

Using:

```css
grid-auto-flow: dense;
```

allows the browser to attempt to fill suitable earlier gaps.

### `row dense`

You can combine `row` with `dense`:

```css
grid-auto-flow: row dense;
```

This keeps row-based placement while enabling dense packing.

### `column dense`

Similarly:

```css
grid-auto-flow: column dense;
```

uses column-based placement with dense packing.

### Auto Placement With Spanning Items

Auto-placement becomes especially useful when some items span multiple tracks.

Example:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.featured {
    grid-column: span 2;
}
```

The browser can automatically place the remaining items around the spanning item.

Conceptually:

```text
┌──────────────────────┬──────────┐
│      Featured        │  Item 2  │
│       span 2         │          │
├──────────┬───────────┼──────────┤
│  Item 3  │  Item 4   │  Item 5  │
└──────────┴───────────┴──────────┘
```

### Explicit Placement and Auto Placement Together

You can explicitly position some items while allowing the browser to automatically place others.

Example:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.header {
    grid-column: 1 / -1;
}
```

The header is explicitly positioned:

```text
┌──────────────────────────────┐
│            Header            │
└──────────────────────────────┘
```

The remaining items can still be automatically placed into available cells.

### Auto Placement and Implicit Rows

If there are more items than the explicitly defined rows can accommodate, Grid can create additional rows automatically.

Example:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
}
```

With five items:

```text
┌──────────┬──────────┐
│  Item 1  │  Item 2  │
├──────────┼──────────┤
│  Item 3  │  Item 4  │
├──────────┼──────────┤
│  Item 5  │          │
└──────────┴──────────┘
```

The additional row is an **implicit row**.

The topic of explicit and implicit grids will be covered separately.

### Auto Placement With Responsive Grids

Auto-placement is commonly used with responsive card layouts.

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

The browser determines the number of columns that can fit and automatically places the cards.

Example:

```text
Wide screen:

┌────────┬────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │ Card 4 │
└────────┴────────┴────────┴────────┘
```

Narrower screen:

```text
┌────────┬────────┐
│ Card 1 │ Card 2 │
├────────┼────────┤
│ Card 3 │ Card 4 │
└────────┴────────┘
```

The HTML does not need to change.

### Auto Placement vs Explicit Placement

**Auto placement:**

```css
.grid {
    display: grid;
}
```

The browser determines item positions.

**Explicit placement:**

```css
.item {
    grid-column: 2 / 4;
    grid-row: 1 / 3;
}
```

You specify where the item goes.

Both approaches can be used in the same grid.

### Important Points

```text
Auto Placement
│
├── Automatically places grid items
├── Default flow is row
├── grid-auto-flow controls the direction
├── row → place across rows
├── column → place down columns
├── dense → tries to fill earlier gaps
├── row dense → row flow + dense packing
└── column dense → column flow + dense packing
```

> 💡 **Remember:** CSS Grid automatically places items into available cells when their positions are not explicitly specified. `grid-auto-flow` controls the direction and packing behavior of this automatic placement.

---

## Explicit vs Implicit Grid

CSS Grid can contain two types of grid tracks:

- **Explicit grid tracks**
- **Implicit grid tracks**

The difference is whether the tracks were directly defined by the author or created automatically by the browser.

### Explicit Grid

An **explicit grid** is the part of the grid that you define directly using:

```css
grid-template-columns
grid-template-rows
```

For example:

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

Conceptually:

```text
┌──────────┬──────────┐
│          │          │
│ Column 1 │ Column 2 │
│          │          │
├──────────┼──────────┤
│          │          │
│ Row 2    │          │
│          │          │
└──────────┴──────────┘
```

The tracks created by `grid-template-columns` and `grid-template-rows` are explicit tracks.

### Explicit Columns

For example:

```css
.container {
    grid-template-columns: 200px 1fr 1fr;
}
```

This explicitly defines three column tracks:

```text
200px | 1fr | 1fr
```

Therefore:

```text
Explicit columns → 3
```

### Explicit Rows

Similarly:

```css
.container {
    grid-template-rows: 100px 200px;
}
```

creates:

```text
Explicit rows → 2
```

### Implicit Grid

An **implicit grid** is created when the browser needs additional grid tracks that were not explicitly defined.

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
}
```

This explicitly defines two columns:

```text
┌──────────┬──────────┐
│          │          │
└──────────┴──────────┘
```

Now suppose there are five items:

```text
Item 1
Item 2
Item 3
Item 4
Item 5
```

The browser can automatically create additional rows:

```text
┌──────────┬──────────┐
│  Item 1  │  Item 2  │
├──────────┼──────────┤
│  Item 3  │  Item 4  │
├──────────┼──────────┤
│  Item 5  │          │
└──────────┴──────────┘
```

The additional row is an **implicit row**.

### Why Implicit Tracks Are Created

Implicit tracks can be created when:

- There are more items than explicitly defined tracks can accommodate.
- An item is positioned outside the explicitly defined grid.
- Grid auto-placement requires additional tracks.

The browser creates the required tracks automatically.

### `grid-auto-rows`

The size of automatically created rows can be controlled with:

```css
grid-auto-rows
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: 100px;
}
```

The explicitly defined columns remain:

```text
1fr | 1fr
```

and automatically created rows have a size of:

```text
100px
```

### `grid-auto-columns`

Similarly, automatically created columns can be controlled with:

```css
grid-auto-columns
```

For example:

```css
.container {
    display: grid;
    grid-template-rows: repeat(2, 100px);
    grid-auto-columns: 200px;
    grid-auto-flow: column;
}
```

Automatically generated columns use:

```text
200px
```

### Explicit vs Implicit Example

Consider:

```css
.container {
    display: grid;

    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 100px;
}
```

The explicitly defined grid is:

```text
┌──────────┬──────────┐
│          │          │
│          │          │ 100px
└──────────┴──────────┘
```

If more items require additional rows:

```text
┌──────────┬──────────┐
│  Item 1  │  Item 2  │  Explicit row
├──────────┼──────────┤
│  Item 3  │  Item 4  │  Implicit row
├──────────┼──────────┤
│  Item 5  │  Item 6  │  Implicit row
└──────────┴──────────┘
```

The first row was explicitly defined.

The additional rows were automatically generated.

### Explicit Grid With `grid-template-columns`

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

This creates three explicit columns:

```text
1fr | 1fr | 1fr
```

If the layout needs more rows, the browser can create implicit rows.

### Implicit Rows

A very common situation is:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

With six items:

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │ Item 5 │ Item 6 │
└────────┴────────┴────────┘
```

The columns are explicitly defined.

The rows are generated by auto-placement when they are not explicitly defined.

### Controlling Implicit Rows

You can define the size of those automatically created rows:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 120px;
}
```

Now automatically created rows use:

```text
120px
```

### Explicit and Implicit Tracks Can Coexist

A grid can contain both:

```text
Explicit tracks
      +
Implicit tracks
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr;
    grid-template-rows: 100px;
    grid-auto-rows: 150px;
}
```

The grid contains:

```text
Explicit row → 100px
Implicit rows → 150px
```

### Explicit Grid Lines

Explicit tracks also create explicit grid lines.

For example:

```css
grid-template-columns: 1fr 1fr;
```

creates:

```text
Line 1     Line 2     Line 3
   │          │          │
   │   1fr    │   1fr    │
```

If additional implicit tracks are created, additional grid lines are also generated.

### Explicit Placement Can Create Implicit Tracks

Consider:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}

.item {
    grid-column: 3;
}
```

Only two columns were explicitly defined.

However, the item is positioned in column line/track space beyond the explicit columns, so Grid can create an implicit track to accommodate it.

Conceptually:

```text
Explicit:
┌──────────┬──────────┐
│ Column 1 │ Column 2 │
└──────────┴──────────┘

After required implicit space:
┌──────────┬──────────┬──────────┐
│ Column 1 │ Column 2 │ Column 3 │
└──────────┴──────────┴──────────┘
```

### Explicit vs Implicit

The core difference is:

```text
Explicit
   ↓
Defined by the author

Implicit
   ↓
Created automatically by Grid
```

### Main Properties

Explicit tracks:

```css
grid-template-columns
grid-template-rows
```

Implicit track sizing:

```css
grid-auto-columns
grid-auto-rows
```

Automatic placement direction:

```css
grid-auto-flow
```

### Practical Example

```css
.gallery {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 200px;
    gap: 20px;
}
```

Here:

```text
grid-template-columns
        ↓
3 explicit columns

grid-auto-rows
        ↓
200px size for automatically created rows
```

With many gallery items, Grid can automatically create the required rows.

### Important Points

```text
Explicit Grid
│
├── Directly defined
├── grid-template-columns
└── grid-template-rows

Implicit Grid
│
├── Created automatically
├── grid-auto-columns
├── grid-auto-rows
└── Often used with auto-placement
```

> 💡 **Remember:** The explicit grid is the grid structure you define with `grid-template-columns` and `grid-template-rows`. The implicit grid consists of additional tracks that Grid creates automatically when they are needed.

---

## Responsive Grid

A **responsive grid** is a CSS Grid layout that adapts its columns, rows, and spacing to different screen sizes.

CSS Grid provides several features that make responsive layouts easier to create, including:

```text
fr
repeat()
minmax()
auto-fit
auto-fill
media queries
```

### Basic Responsive Grid

A simple responsive grid can use a media query:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

On larger screens:

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │ Item 5 │ Item 6 │
└────────┴────────┴────────┘
```

On smaller screens:

```text
┌──────────────────────────┐
│          Item 1          │
├──────────────────────────┤
│          Item 2          │
├──────────────────────────┤
│          Item 3          │
└──────────────────────────┘
```

### Using `fr`

The `fr` unit allows grid tracks to share available space.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The two columns automatically divide the available flexible space.

```text
Wide screen:

┌────────────────────┬────────────────────┐
│       Item 1       │       Item 2       │
└────────────────────┴────────────────────┘
```

The columns remain proportional as the container changes size.

### Using `repeat()`

`repeat()` makes repeated responsive track definitions easier to write.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

This creates:

```text
1fr | 1fr | 1fr
```

The same pattern can later be changed with a media query.

### Using `minmax()`

`minmax()` can prevent columns from becoming too narrow.

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(3, minmax(200px, 1fr));
}
```

Each column has:

```text
Minimum → 200px
Maximum → 1fr
```

This is useful when grid items need a minimum amount of horizontal space.

### `auto-fit`

`auto-fit` allows the browser to determine how many columns can fit.

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

The number of columns can change according to the available container width.

For example, a wider layout might display:

```text
┌────────┬────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │ Item 4 │
└────────┴────────┴────────┴────────┘
```

A narrower layout might display:

```text
┌────────┬────────┐
│ Item 1 │ Item 2 │
├────────┼────────┤
│ Item 3 │ Item 4 │
└────────┴────────┘
```

### `auto-fill`

`auto-fill` can also determine how many tracks can fit.

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(auto-fill, minmax(200px, 1fr));
}
```

It can create as many tracks as can fit according to the minimum track size.

### `auto-fit` vs `auto-fill`

Both are commonly used in responsive grids:

```css
repeat(auto-fit, minmax(200px, 1fr))
```

and:

```css
repeat(auto-fill, minmax(200px, 1fr))
```

A simplified way to think about them is:

```text
auto-fill
    ↓
Fits as many tracks as possible

auto-fit
    ↓
Fits tracks and collapses empty tracks,
allowing existing tracks to expand
```

Their differences become more noticeable when there are fewer items than the number of tracks that could fit.

### Responsive Card Grid

A common responsive card layout is:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(250px, 1fr));
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
</div>
```

The browser can automatically adjust the number of columns according to the available width.

### Responsive Sidebar Layout

A common desktop layout is:

```css
.layout {
    display: grid;
    grid-template-columns: 250px 1fr;
    gap: 20px;
}
```

Conceptually:

```text
┌──────────────┬────────────────────────┐
│   Sidebar    │       Main Content     │
│    250px     │          1fr           │
└──────────────┴────────────────────────┘
```

For smaller screens:

```css
@media (max-width: 700px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

The layout becomes:

```text
┌──────────────────────────────┐
│           Sidebar            │
├──────────────────────────────┤
│         Main Content         │
└──────────────────────────────┘
```

### Responsive Grid Areas

Grid areas can also be changed at different screen sizes.

```css
.layout {
    display: grid;

    grid-template-columns: 200px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}

header {
    grid-area: header;
}

aside {
    grid-area: sidebar;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

For smaller screens:

```css
@media (max-width: 600px) {
    .layout {
        grid-template-columns: 1fr;

        grid-template-areas:
            "header"
            "main"
            "sidebar"
            "footer";
    }
}
```

This changes the layout without changing the HTML structure.

### Responsive Gaps

The gap can also be adjusted:

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(3, 1fr);
    gap: 24px;
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
        gap: 12px;
    }
}
```

Large screens:

```text
Gap → 24px
```

Small screens:

```text
Gap → 12px
```

### Responsive Grid Without Media Queries

Some layouts can adapt without explicitly writing media queries.

For example:

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

The grid can automatically change the number of columns as the available width changes.

This is especially useful for:

- Cards
- Product grids
- Image galleries
- Article lists
- Dashboard components

### Choosing a Responsive Technique

Use a media query when you need specific layout changes.

```css
@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

Use `auto-fit` and `minmax()` when you want the grid to adapt automatically:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
```

A layout can also combine both approaches.

### Practical Responsive Card Example

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

CSS:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}

.cards article {
    padding: 20px;
}
```

The grid automatically adapts to the available width:

```text
Large:

┌────────┬────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │ Card 4 │
├────────┼────────┼────────┼────────┤
│ Card 5 │ Card 6 │        │        │
└────────┴────────┴────────┴────────┘
```

Smaller:

```text
┌────────────┬────────────┐
│   Card 1   │   Card 2   │
├────────────┼────────────┤
│   Card 3   │   Card 4   │
├────────────┼────────────┤
│   Card 5   │   Card 6   │
└────────────┴────────────┘
```

Very small:

```text
┌──────────────────────────┐
│          Card 1          │
├──────────────────────────┤
│          Card 2          │
├──────────────────────────┤
│          Card 3          │
├──────────────────────────┤
│          Card 4          │
└──────────────────────────┘
```

### Important Points

```text
Responsive Grid
│
├── fr → flexible track sizing
├── repeat() → repeated tracks
├── minmax() → minimum and maximum track size
├── auto-fit → adapts track count and collapses empty tracks
├── auto-fill → fits as many tracks as possible
├── gap → consistent spacing
├── media queries → explicit breakpoint-based changes
└── grid-template-areas → responsive page structures
```

> 💡 **Remember:** Responsive CSS Grid layouts can be created with media queries or with flexible Grid features such as `fr`, `minmax()`, `repeat()`, `auto-fit`, and `auto-fill`. Combining these features makes it possible to build layouts that adapt to different screen sizes.

---

## Practical Examples

The following examples combine the CSS Grid concepts covered so far into common real-world layouts.

### Example 1: Basic Two-Column Layout

HTML:

```html
<div class="layout">
    <aside>Sidebar</aside>
    <main>Main Content</main>
</div>
```

CSS:

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
    gap: 20px;
}
```

Result:

```text
┌──────────────┬────────────────────────┐
│   Sidebar    │      Main Content      │
│    200px     │          1fr           │
└──────────────┴────────────────────────┘
```

The sidebar has a fixed width while the main content uses the remaining space.

---

### Example 2: Three-Column Card Grid

HTML:

```html
<div class="cards">
    <div>Card 1</div>
    <div>Card 2</div>
    <div>Card 3</div>
    <div>Card 4</div>
    <div>Card 5</div>
    <div>Card 6</div>
</div>
```

CSS:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Result:

```text
┌────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │
├────────┼────────┼────────┤
│ Card 4 │ Card 5 │ Card 6 │
└────────┴────────┴────────┘
```

This example uses:

```text
display: grid
repeat()
fr
gap
```

---

### Example 3: Responsive Card Grid

A responsive card grid can use `auto-fit` and `minmax()`.

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

The number of columns adapts to the available width.

Wide screen:

```text
┌────────┬────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │ Card 4 │
└────────┴────────┴────────┴────────┘
```

Medium screen:

```text
┌────────────┬────────────┐
│   Card 1   │   Card 2   │
├────────────┼────────────┤
│   Card 3   │   Card 4   │
└────────────┴────────────┘
```

Small screen:

```text
┌──────────────────────────┐
│          Card 1          │
├──────────────────────────┤
│          Card 2          │
├──────────────────────────┤
│          Card 3          │
└──────────────────────────┘
```

---

### Example 4: Header, Sidebar, Main, Footer

HTML:

```html
<div class="page">
    <header>Header</header>
    <aside>Sidebar</aside>
    <main>Main Content</main>
    <footer>Footer</footer>
</div>
```

CSS:

```css
.page {
    display: grid;

    grid-template-columns: 220px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";

    gap: 20px;
}

header {
    grid-area: header;
}

aside {
    grid-area: sidebar;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

Result:

```text
┌───────────────────────────────┐
│            Header             │
├──────────────┬────────────────┤
│   Sidebar    │  Main Content  │
├──────────────┴────────────────┤
│            Footer             │
└───────────────────────────────┘
```

This example uses named grid areas to describe the page structure.

---

### Example 5: Full-Width Header

A header can span all columns using `grid-column`.

```css
.page {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

header {
    grid-column: 1 / -1;
}
```

Result:

```text
┌──────────────────────────────────┐
│              Header              │
├────────────┬────────────┬────────┤
│   Item 1   │   Item 2   │ Item 3 │
└────────────┴────────────┴────────┘
```

The value:

```css
grid-column: 1 / -1;
```

makes the header span from the first column line to the last column line.

---

### Example 6: Full-Height Sidebar

A sidebar can span multiple rows using `grid-row`.

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
    grid-template-rows: 80px 1fr 60px;
}

.sidebar {
    grid-row: 1 / -1;
}
```

Conceptually:

```text
┌──────────────┬───────────────────┐
│              │      Header       │
│              ├───────────────────┤
│   Sidebar    │                   │
│              │   Main Content    │
│              ├───────────────────┤
│              │      Footer       │
└──────────────┴───────────────────┘
```

The sidebar spans from the first row line to the last row line.

---

### Example 7: Featured Card

One card can occupy more than one column.

HTML:

```html
<div class="cards">
    <article class="featured">Featured</article>
    <article>Card 2</article>
    <article>Card 3</article>
    <article>Card 4</article>
</div>
```

CSS:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

.featured {
    grid-column: span 2;
}
```

Result:

```text
┌──────────────────────┬──────────┐
│      Featured        │  Card 2  │
│       span 2         │          │
├──────────┬───────────┼──────────┤
│  Card 3  │  Card 4   │          │
└──────────┴───────────┴──────────┘
```

The featured card occupies two column tracks.

---

### Example 8: Featured Card Spanning Rows

An item can span both columns and rows.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 150px);
    gap: 20px;
}

.featured {
    grid-column: span 2;
    grid-row: span 2;
}
```

Conceptually:

```text
┌──────────────────────┬──────────┐
│                      │  Card 2  │
│      Featured        ├──────────┤
│                      │  Card 3  │
├──────────────────────┴──────────┤
│          Other content          │
└─────────────────────────────────┘
```

The exact automatic placement of remaining items depends on the available grid cells and auto-placement rules.

---

### Example 9: Dashboard Layout

A dashboard can use multiple grid areas.

```css
.dashboard {
    display: grid;

    grid-template-columns: 220px 1fr 1fr;

    grid-template-areas:
        "sidebar header header"
        "sidebar card1 card2"
        "sidebar chart chart";

    gap: 20px;
}

.sidebar {
    grid-area: sidebar;
}

.header {
    grid-area: header;
}

.card1 {
    grid-area: card1;
}

.card2 {
    grid-area: card2;
}

.chart {
    grid-area: chart;
}
```

Conceptually:

```text
┌──────────┬──────────────┬──────────────┐
│          │    Header    │    Header    │
│          ├──────────────┼──────────────┤
│ Sidebar  │    Card 1    │    Card 2    │
│          ├──────────────┴──────────────┤
│          │            Chart            │
└──────────┴─────────────────────────────┘
```

This demonstrates how named areas can describe a more complex layout.

---

### Example 10: Responsive Dashboard

The dashboard can be changed for smaller screens.

```css
.dashboard {
    display: grid;

    grid-template-columns: 220px 1fr 1fr;

    grid-template-areas:
        "sidebar header header"
        "sidebar card1 card2"
        "sidebar chart chart";

    gap: 20px;
}

@media (max-width: 700px) {
    .dashboard {
        grid-template-columns: 1fr;

        grid-template-areas:
            "header"
            "card1"
            "card2"
            "chart"
            "sidebar";
    }
}
```

Desktop:

```text
┌──────────┬────────────┬────────────┐
│ Sidebar  │   Header   │   Header   │
│          ├────────────┼────────────┤
│          │   Card 1   │   Card 2   │
│          ├────────────┴────────────┤
│          │          Chart          │
└──────────┴─────────────────────────┘
```

Mobile:

```text
┌──────────────────────────┐
│          Header          │
├──────────────────────────┤
│          Card 1          │
├──────────────────────────┤
│          Card 2          │
├──────────────────────────┤
│           Chart          │
├──────────────────────────┤
│          Sidebar         │
└──────────────────────────┘
```

---

### Example 11: Centering Content

Grid can be used to center an element in both directions.

```css
.container {
    display: grid;
    place-items: center;
}
```

HTML:

```html
<div class="container">
    <div>Centered Content</div>
</div>
```

The item is centered inside its grid area.

```text
┌──────────────────────────────┐
│                              │
│                              │
│       Centered Content       │
│                              │
│                              │
└──────────────────────────────┘
```

---

### Example 12: Fixed Sidebar With Flexible Content

A practical page layout:

```css
.layout {
    display: grid;
    grid-template-columns: 240px minmax(0, 1fr);
    gap: 24px;
}
```

Conceptually:

```text
┌────────────────┬────────────────────────┐
│                │                        │
│    Sidebar     │      Main Content      │
│     240px      │        flexible        │
│                │                        │
└────────────────┴────────────────────────┘
```

Using `minmax(0, 1fr)` can be useful when you need the flexible track to be able to shrink to zero rather than being forced by the minimum content contribution of a grid item.

---

### Example 13: Image Gallery

HTML:

```html
<div class="gallery">
    <img src="image1.jpg" alt="Image 1">
    <img src="image2.jpg" alt="Image 2">
    <img src="image3.jpg" alt="Image 3">
    <img src="image4.jpg" alt="Image 4">
</div>
```

CSS:

```css
.gallery {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px;
}
```

This creates a responsive image gallery:

```text
┌────────┬────────┬────────┐
│ Image  │ Image  │ Image  │
├────────┼────────┼────────┤
│ Image  │ Image  │ Image  │
└────────┴────────┴────────┘
```

The number of columns changes according to the available width.

---

### Example 14: Explicit Grid With Automatic Rows

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 120px;
    gap: 20px;
}
```

The three columns are explicitly defined.

Additional rows are automatically created as needed, with each implicit row set to `120px`.

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │ Item 5 │ Item 6 │
├────────┼────────┼────────┤
│ Item 7 │ Item 8 │ Item 9 │
└────────┴────────┴────────┘
```

---

### Example 15: Combining Major Grid Features

A practical responsive card layout can combine several Grid features:

```css
.cards {
    display: grid;

    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));

    gap: 20px;

    align-items: stretch;
}

.featured {
    grid-column: span 2;
}
```

This example combines:

```text
display: grid
repeat()
auto-fit
minmax()
1fr
gap
align-items
grid-column
```

The browser handles the placement of most items automatically while the featured item can occupy more than one column.

### Choosing the Right Technique

Use:

```css
grid-template-columns
```

when you need to define column tracks.

Use:

```css
grid-template-rows
```

when you need to define row tracks.

Use:

```css
grid-column
```

when you need to position or span an item horizontally.

Use:

```css
grid-row
```

when you need to position or span an item vertically.

Use:

```css
grid-template-areas
```

when you want a named page structure.

Use:

```css
repeat()
```

when a track pattern repeats.

Use:

```css
minmax()
```

when a track needs a minimum and maximum size.

Use:

```css
auto-fit
auto-fill
```

when the number of responsive tracks should adapt automatically.

Use:

```css
gap
```

for consistent spacing between tracks.

### Practical Combination

A reusable responsive card grid often looks like:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

A typical page layout can look like:

```css
.page {
    display: grid;
    grid-template-columns: 220px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";

    gap: 20px;
}
```

These two patterns cover many common CSS Grid use cases.

> 💡 **Remember:** CSS Grid becomes especially powerful when its features are combined. Use tracks to define structure, `grid-column` and `grid-row` to position items, named areas for page layouts, and `repeat()`, `minmax()`, `auto-fit`, and `fr` for responsive designs.

---

## Key Takeaways

CSS Grid is a two-dimensional layout system that allows you to control both **rows and columns**.

### Core Concepts

```text
Grid Container
      ↓
Grid Tracks
      ↓
Grid Lines
      ↓
Grid Cells
      ↓
Grid Items
```

- `display: grid` turns an element into a grid container.
- Grid items are the direct children of a grid container.
- Rows and columns create the grid structure.
- Grid lines define the boundaries of tracks.
- Grid cells are the individual spaces created by rows and columns.
- Grid items can occupy one or multiple cells.

### Defining the Grid

Use:

```css
grid-template-columns
grid-template-rows
```

to create explicit column and row tracks.

Example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: 100px 1fr;
}
```

### Flexible Sizing

The `fr` unit represents a fraction of the available flexible space.

```css
grid-template-columns: 1fr 2fr;
```

creates a proportional relationship:

```text
1 : 2
```

### Repeating Tracks

Use `repeat()` when a pattern needs to be repeated.

```css
grid-template-columns: repeat(3, 1fr);
```

creates:

```text
1fr | 1fr | 1fr
```

### Minimum and Maximum Track Sizes

Use `minmax()` when a track needs a minimum and maximum size.

```css
grid-template-columns:
    minmax(200px, 1fr);
```

This is particularly useful for responsive layouts.

### Spacing

Use `gap` to create space between grid tracks.

```css
gap: 20px;
```

You can also control rows and columns independently:

```css
row-gap: 20px;
column-gap: 30px;
```

### Positioning Items

Use:

```css
grid-column
grid-row
```

to position or span individual grid items.

For example:

```css
.item {
    grid-column: 1 / 3;
    grid-row: 1 / 3;
}
```

This makes the item span multiple columns and rows.

### Named Grid Areas

Use:

```css
grid-template-areas
```

to create named regions.

Example:

```css
.layout {
    display: grid;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

Then assign items:

```css
header {
    grid-area: header;
}

aside {
    grid-area: sidebar;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

### Alignment

Grid provides alignment properties for both the grid items and the grid itself.

For items:

```css
justify-items
align-items
place-items
```

For individual items:

```css
justify-self
align-self
place-self
```

For grid tracks:

```css
justify-content
align-content
place-content
```

### Auto Placement

Grid automatically places items when their positions are not explicitly specified.

The direction can be controlled using:

```css
grid-auto-flow
```

Common values include:

```css
grid-auto-flow: row;
grid-auto-flow: column;
grid-auto-flow: dense;
```

### Explicit and Implicit Grids

Explicit tracks are defined directly:

```css
grid-template-columns
grid-template-rows
```

Implicit tracks are created automatically when additional space is required.

Their sizes can be controlled using:

```css
grid-auto-columns
grid-auto-rows
```

### Responsive Grid

CSS Grid provides several tools for responsive layouts:

```css
fr
repeat()
minmax()
auto-fit
auto-fill
```

A common responsive pattern is:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

### Most Important Grid Properties

```text
display
grid-template-columns
grid-template-rows
grid-template-areas
grid-column
grid-row
grid-area
grid-auto-flow
grid-auto-columns
grid-auto-rows
gap
row-gap
column-gap
justify-items
align-items
justify-self
align-self
justify-content
align-content
```

### CSS Grid Mental Model

```text
                    CSS GRID
                       │
          ┌────────────┴────────────┐
          ↓                         ↓
     Grid Container            Grid Items
          │
          ↓
   ┌───────────────┐
   │ Rows + Columns│
   └───────┬───────┘
           ↓
      Grid Tracks
           ↓
       Grid Lines
           ↓
       Grid Cells
           ↓
    Item Placement
```

### Quick Rules

```text
Need columns?
→ grid-template-columns

Need rows?
→ grid-template-rows

Need flexible space?
→ fr

Need repeated tracks?
→ repeat()

Need min/max sizing?
→ minmax()

Need spacing?
→ gap

Need horizontal item placement?
→ grid-column

Need vertical item placement?
→ grid-row

Need named regions?
→ grid-template-areas

Need automatic placement?
→ grid-auto-flow

Need responsive tracks?
→ repeat() + minmax() + auto-fit/auto-fill

Need item alignment?
→ justify-items / align-items

Need individual item alignment?
→ justify-self / align-self

Need track alignment?
→ justify-content / align-content
```

> 💡 **Remember:** CSS Grid provides a complete two-dimensional layout system. Learn the relationship between **tracks, lines, cells, and items** first, then use `fr`, `repeat()`, `minmax()`, placement, alignment, and responsive techniques to build more advanced layouts.

---

## References

The following resources can be used to learn more about CSS Grid and verify the concepts covered in this chapter.

### MDN Web Docs

- [CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout)
- [Basic concepts of Grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)
- [grid-template-columns](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
- [grid-template-rows](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)
- [grid-column](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column)
- [grid-row](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row)
- [grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas)
- [grid-auto-flow](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow)
- [gap](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
- [CSS `fr` unit](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout#the_fr_unit)

### W3C / CSS Specification

- [CSS Grid Layout Module](https://www.w3.org/TR/css-grid-1/)
- [CSS Grid Layout Module Level 2](https://www.w3.org/TR/css-grid-2/)

### CSS-Tricks

- [A Complete Guide to CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

### Reference Usage

These references are useful for:

- Understanding CSS Grid terminology
- Checking property syntax
- Learning advanced Grid behavior
- Understanding track sizing
- Learning responsive Grid techniques
- Verifying browser-supported features

> 💡 **Remember:** Use the official MDN and W3C documentation as the primary references when checking CSS Grid behavior and syntax.

---

## Quick Revision

### 1. What is CSS Grid?

CSS Grid is a **two-dimensional layout system** used to arrange elements into rows and columns.

```css
.container {
    display: grid;
}
```

---

### 2. Grid Container

An element becomes a grid container when:

```css
display: grid;
```

Its direct children become grid items.

---

### 3. Grid Columns

Use:

```css
grid-template-columns
```

Example:

```css
grid-template-columns: 1fr 1fr 1fr;
```

Creates three columns.

---

### 4. Grid Rows

Use:

```css
grid-template-rows
```

Example:

```css
grid-template-rows: 100px 1fr;
```

Creates two row tracks.

---

### 5. Grid Tracks

A grid track is a row or column of the grid.

```text
Column Track
     ↓
┌──────────┬──────────┐
│          │          │
│          │          │
└──────────┴──────────┘
```

---

### 6. Grid Lines

Grid lines define the boundaries of grid tracks.

For two columns:

```text
Line 1       Line 2       Line 3
   │            │            │
   │   Column   │   Column   │
```

Two columns require three vertical grid lines.

---

### 7. Grid Cells

A grid cell is the individual space created by the intersection of a row track and a column track.

```text
┌──────────┬──────────┐
│ Cell 1   │ Cell 2   │
├──────────┼──────────┤
│ Cell 3   │ Cell 4   │
└──────────┴──────────┘
```

---

### 8. The `fr` Unit

`fr` means **fraction**.

```css
grid-template-columns: 1fr 2fr;
```

creates a flexible ratio of:

```text
1 : 2
```

---

### 9. `repeat()`

`repeat()` creates repeated grid tracks.

```css
grid-template-columns: repeat(3, 1fr);
```

is equivalent to:

```css
grid-template-columns: 1fr 1fr 1fr;
```

---

### 10. `minmax()`

`minmax()` defines a minimum and maximum track size.

```css
grid-template-columns: minmax(200px, 1fr);
```

The track has:

```text
Minimum → 200px
Maximum → 1fr
```

---

### 11. `gap`

`gap` creates space between grid tracks.

```css
gap: 20px;
```

Different values can be used for rows and columns:

```css
gap: 10px 20px;
```

Meaning:

```text
Row gap    → 10px
Column gap → 20px
```

---

### 12. `grid-column`

Controls an item's horizontal placement.

```css
.item {
    grid-column: 1 / 3;
}
```

The item spans from column line 1 to column line 3.

A common full-width pattern:

```css
.item {
    grid-column: 1 / -1;
}
```

---

### 13. `grid-row`

Controls an item's vertical placement.

```css
.item {
    grid-row: 1 / 3;
}
```

The item spans from row line 1 to row line 3.

Full-height pattern:

```css
.item {
    grid-row: 1 / -1;
}
```

---

### 14. `grid-area`

`grid-area` can assign an item to a named grid area.

```css
header {
    grid-area: header;
}
```

Named areas are created with:

```css
grid-template-areas
```

---

### 15. `grid-template-areas`

Example:

```css
.layout {
    display: grid;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

Visual structure:

```text
┌──────────┬──────────┐
│  header  │  header  │
├──────────┼──────────┤
│ sidebar  │   main   │
├──────────┼──────────┤
│  footer  │  footer  │
└──────────┴──────────┘
```

A repeated area name creates an area spanning multiple cells.

---

### 16. Grid Alignment

For all grid items:

```css
justify-items
align-items
place-items
```

For one grid item:

```css
justify-self
align-self
place-self
```

For grid tracks:

```css
justify-content
align-content
place-content
```

A common centering technique is:

```css
.container {
    display: grid;
    place-items: center;
}
```

---

### 17. Auto Placement

Grid automatically places items when their positions are not explicitly defined.

```css
grid-auto-flow: row;
```

is the default flow.

Other options include:

```css
grid-auto-flow: column;
grid-auto-flow: dense;
grid-auto-flow: row dense;
grid-auto-flow: column dense;
```

---

### 18. Explicit Grid

Explicit tracks are directly defined with:

```css
grid-template-columns
grid-template-rows
```

Example:

```css
grid-template-columns: 1fr 1fr;
```

---

### 19. Implicit Grid

Implicit tracks are created automatically when Grid needs additional tracks.

Their sizes can be controlled using:

```css
grid-auto-columns
grid-auto-rows
```

---

### 20. Responsive Grid

Responsive Grid commonly uses:

```css
fr
repeat()
minmax()
auto-fit
auto-fill
```

A common pattern is:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

---

### 21. `auto-fit` vs `auto-fill`

A simplified distinction:

```text
auto-fill
    ↓
Fits as many tracks as possible

auto-fit
    ↓
Fits tracks and can collapse empty tracks
```

Both are commonly used with:

```css
minmax()
```

---

### 22. Most Important Properties

```text
display: grid

grid-template-columns
grid-template-rows

grid-template-areas
grid-area

grid-column
grid-row

grid-auto-flow
grid-auto-columns
grid-auto-rows

gap
row-gap
column-gap

justify-items
align-items
place-items

justify-self
align-self
place-self

justify-content
align-content
place-content
```

---

### 23. Common Responsive Pattern

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

This combines:

```text
Grid
+
repeat()
+
auto-fit
+
minmax()
+
1fr
+
gap
```

---

### 24. Grid Mental Model

```text
CSS Grid
   │
   ├── Container
   │
   ├── Tracks
   │     ├── Rows
   │     └── Columns
   │
   ├── Lines
   │
   ├── Cells
   │
   └── Items
         │
         ├── Placement
         ├── Spanning
         └── Alignment
```

---

### Quick Syntax Reference

```css
/* Create a grid */
display: grid;

/* Columns */
grid-template-columns: repeat(3, 1fr);

/* Rows */
grid-template-rows: 100px 1fr;

/* Flexible sizing */
grid-template-columns: 1fr 2fr;

/* Minimum / maximum */
grid-template-columns: minmax(200px, 1fr);

/* Spacing */
gap: 20px;

/* Column placement */
grid-column: 1 / 3;

/* Row placement */
grid-row: 1 / 3;

/* Named areas */
grid-template-areas:
    "header header"
    "main main";

/* Assign area */
grid-area: header;

/* Automatic placement */
grid-auto-flow: row;

/* Alignment */
place-items: center;
```

> 💡 **Remember:** The most important CSS Grid concepts are **tracks, lines, cells, placement, sizing, alignment, and responsive behavior**. Once these concepts are clear, the individual Grid properties become much easier to understand.

---

## Best Practices

Following consistent practices makes CSS Grid layouts easier to read, maintain, debug, and adapt to different screen sizes.

### 1. Use `display: grid` on the Correct Container

Grid should be applied to the element whose direct children need to participate in the grid layout.

```css
.container {
    display: grid;
}
```

Remember:

```text
Grid container
      ↓
Direct children
      ↓
Grid items
```

### 2. Prefer `gap` for Grid Spacing

Use:

```css
gap: 20px;
```

instead of adding margins to every grid item just to create spacing between tracks.

Example:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

This keeps spacing controlled by the grid container.

### 3. Use `fr` for Flexible Space

When columns should share available space, `fr` is often more suitable than manually calculating percentages.

```css
.container {
    grid-template-columns: 1fr 2fr;
}
```

This creates a flexible `1 : 2` relationship.

### 4. Use `repeat()` for Repeated Tracks

Instead of:

```css
grid-template-columns: 1fr 1fr 1fr 1fr;
```

prefer:

```css
grid-template-columns: repeat(4, 1fr);
```

This makes repeated patterns easier to read and maintain.

### 5. Use `minmax()` for Flexible Minimum Sizes

When a track should not become too narrow, use `minmax()`.

```css
.container {
    grid-template-columns:
        repeat(3, minmax(200px, 1fr));
}
```

This is particularly useful for cards and responsive components.

### 6. Use `auto-fit` for Responsive Card Layouts

A common responsive pattern is:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

This allows the number of columns to adapt to the available width.

### 7. Use Named Areas for Complex Page Layouts

For layouts such as:

```text
Header
Sidebar
Main
Footer
```

named areas can make the CSS easier to understand.

```css
.layout {
    display: grid;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

Then:

```css
header {
    grid-area: header;
}
```

The names communicate the purpose of each region.

### 8. Keep Grid Definitions Readable

For larger layouts, format complex declarations clearly.

Instead of putting everything on one line:

```css
grid-template-areas: "header header" "sidebar main" "footer footer";
```

use:

```css
grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
```

This makes the visual structure easier to understand.

### 9. Use `grid-column` and `grid-row` for Specific Placement

When an individual item needs a specific position or span, use:

```css
grid-column
grid-row
```

For example:

```css
.featured {
    grid-column: span 2;
}
```

Avoid unnecessarily complicated placement rules when normal auto-placement already produces the desired layout.

### 10. Let Auto-Placement Handle Simple Layouts

You do not need to explicitly position every grid item.

For a simple card grid:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

The browser can automatically place the cards.

This is usually simpler than writing separate `grid-column` and `grid-row` rules for every item.

### 11. Use Explicit Placement Only When Necessary

If an item has a special role, explicit placement can be useful:

```css
.featured {
    grid-column: span 2;
}
```

But avoid manually positioning every item unless the design actually requires it.

### 12. Be Careful With `grid-auto-flow: dense`

`dense` can fill available gaps:

```css
grid-auto-flow: dense;
```

However, dense packing can cause later items to appear visually before earlier items.

If the visual order matters, use dense placement carefully.

### 13. Use `minmax(0, 1fr)` When Appropriate

For flexible content columns, this pattern can be useful:

```css
grid-template-columns: 240px minmax(0, 1fr);
```

It allows the flexible track to shrink appropriately instead of being forced wider by the minimum content contribution of its contents.

This can help prevent unexpected overflow in layouts containing long or otherwise difficult-to-shrink content.

### 14. Avoid Unnecessary Fixed Widths

Instead of creating layouts that depend heavily on fixed widths:

```css
grid-template-columns: 300px 500px 400px;
```

consider flexible sizing where appropriate:

```css
grid-template-columns: 1fr 2fr 1fr;
```

or:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
```

The correct approach depends on the design requirements.

### 15. Use Media Queries When the Layout Actually Needs a Breakpoint

Automatic responsive Grid features are useful, but media queries are still appropriate when the layout structure needs to change.

Example:

```css
.layout {
    display: grid;
    grid-template-columns: 220px 1fr;
}

@media (max-width: 700px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

Use a breakpoint when the design calls for a specific structural change.

### 16. Keep Responsive Layouts Content-Friendly

Do not choose breakpoints only because a particular device has a certain screen size.

Consider when the content actually needs more or less space.

For example:

```css
repeat(auto-fit, minmax(220px, 1fr))
```

can often adapt naturally without requiring many breakpoint rules.

### 17. Use Semantic HTML With Grid

CSS Grid controls layout; it does not replace meaningful HTML structure.

Prefer semantic elements where appropriate:

```html
<header>
</header>

<nav>
</nav>

<main>
</main>

<aside>
</aside>

<footer>
</footer>
```

Then use Grid to arrange them.

### 18. Do Not Use Grid for Every Layout

CSS Grid is excellent for two-dimensional layouts, but it is not automatically the best tool for every situation.

Use Grid when you need to control:

```text
Rows + Columns
```

For simple one-dimensional layouts, Flexbox may be more appropriate.

### 19. Use Clear Class Names

For named grid areas, descriptive names improve readability.

Prefer:

```css
grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
```

over unclear names such as:

```css
grid-template-areas:
    "a a"
    "b c"
    "d d";
```

### 20. Keep Layout Responsibility in the Container

Whenever possible, let the grid container define:

```css
grid-template-columns
grid-template-rows
gap
grid-template-areas
```

and use item-specific rules only where necessary.

This creates a clearer separation:

```text
Container
   ↓
Defines layout

Item
   ↓
Defines special placement or alignment
```

### 21. Test Different Content Sizes

A Grid layout should not only work with ideal sample content.

Test with:

- Long text
- Short text
- Different image sizes
- More items
- Fewer items
- Narrow screens
- Wide screens

This helps identify overflow and sizing problems.

### 22. Test Responsive Behavior

Check the layout at different widths.

For example:

```text
Large
  ↓
Medium
  ↓
Small
```

Look for:

```text
Overflow
Unexpected wrapping
Too-small columns
Large empty spaces
Overlapping content
```

### 23. Avoid Overusing Magic Numbers

Avoid layouts that depend on many unrelated hard-coded values:

```css
grid-column: 7 / 13;
grid-row: 4 / 9;
margin-left: 137px;
```

When possible, create a clear grid structure and let Grid handle the positioning.

### 24. Keep Grid CSS Maintainable

A maintainable Grid layout should make it easy to answer:

```text
How many columns are there?
Where does this item go?
How much space is between items?
What happens on smaller screens?
Which areas belong to which elements?
```

If these answers are difficult to find in the CSS, simplify the layout where possible.

### Best-Practice Pattern

A clean responsive card grid might look like:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

A named page layout might look like:

```css
.page {
    display: grid;

    grid-template-columns: 220px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";

    gap: 20px;
}
```

### Quick Checklist

Before considering a Grid layout complete, check:

```text
☐ Is display: grid applied to the correct container?
☐ Are the column and row definitions clear?
☐ Is gap used for track spacing where appropriate?
☐ Are repeated tracks using repeat() where useful?
☐ Are flexible tracks using fr appropriately?
☐ Are minimum sizes handled with minmax() where needed?
☐ Is auto-placement sufficient for normal items?
☐ Are explicit placements limited to items that need them?
☐ Is the layout responsive?
☐ Have different content sizes been tested?
☐ Have small and large screen sizes been tested?
☐ Are class and area names descriptive?
```

> 💡 **Remember:** Good CSS Grid code is not about using the most Grid properties. It is about creating a layout that is **clear, flexible, responsive, maintainable, and appropriate for the design**.

---

## Common Mistakes

Avoiding common CSS Grid mistakes helps prevent unexpected spacing, sizing, positioning, and responsive-layout problems.

### 1. Forgetting `display: grid`

Grid properties do not work as expected if the parent is not a grid container.

Incorrect:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

Correct:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

### 2. Confusing `grid-column` With `grid-template-columns`

These properties have different purposes.

```css
grid-template-columns
```

defines the grid columns:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

While:

```css
grid-column
```

positions an individual item:

```css
.item {
    grid-column: 1 / 3;
}
```

Think:

```text
grid-template-columns
        ↓
Defines the grid

grid-column
        ↓
Positions an item
```

### 3. Confusing `grid-row` With `grid-template-rows`

Similarly:

```css
grid-template-rows
```

defines row tracks:

```css
.container {
    grid-template-rows: 100px 1fr;
}
```

while:

```css
grid-row
```

positions an individual item:

```css
.item {
    grid-row: 1 / 3;
}
```

### 4. Forgetting That Grid Lines Are Not Grid Tracks

For two columns, there are three vertical grid lines:

```text
Line 1       Line 2       Line 3
   │            │            │
   │  Column 1  │  Column 2  │
```

Therefore:

```css
grid-column: 1 / 3;
```

spans two columns, not three.

The values refer to **grid lines**, not column numbers.

### 5. Using the Wrong `gap` Order

With two values:

```css
gap: 10px 20px;
```

the order is:

```text
row-gap    → 10px
column-gap → 20px
```

Do not reverse the values accidentally.

### 6. Expecting `gap` to Add Space Around the Container

`gap` controls the space **between grid tracks**.

```css
.container {
    gap: 20px;
}
```

It does not create `20px` of outer padding around the grid container.

If outer spacing is needed, use:

```css
padding: 20px;
```

### 7. Making Every Item Explicitly Positioned

It is usually unnecessary to position every grid item manually.

Instead of:

```css
.item1 {
    grid-column: 1;
    grid-row: 1;
}

.item2 {
    grid-column: 2;
    grid-row: 1;
}

.item3 {
    grid-column: 3;
    grid-row: 1;
}
```

a simple grid can often use:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Grid's auto-placement can handle the normal items.

### 8. Overusing `grid-auto-flow: dense`

`dense` can fill available gaps:

```css
grid-auto-flow: dense;
```

However, it can cause later items to appear visually before earlier items.

This can be undesirable when visual order is important.

Use it only when dense packing is actually needed.

### 9. Confusing `1fr` With `1px`

These are completely different:

```css
1fr
```

means one fraction of available flexible space.

```css
1px
```

means one CSS pixel.

For example:

```css
grid-template-columns: 1fr 1fr;
```

creates two flexible columns.

### 10. Assuming `1fr` Always Prevents Overflow

Consider:

```css
grid-template-columns: 1fr 1fr;
```

A grid item containing long or otherwise difficult-to-shrink content can still cause sizing or overflow issues.

When appropriate, use:

```css
grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
```

This allows the flexible tracks to shrink to zero rather than being forced by their minimum content contribution.

### 11. Using `minmax()` Incorrectly

The first value should represent the minimum and the second the maximum.

Correct:

```css
minmax(200px, 1fr)
```

This means:

```text
Minimum → 200px
Maximum → 1fr
```

The order matters.

### 12. Forgetting the Minimum Size in Responsive Grids

This:

```css
repeat(auto-fit, 1fr)
```

does not provide a useful minimum card size.

A common responsive pattern is:

```css
repeat(auto-fit, minmax(200px, 1fr))
```

This gives each track a minimum size while allowing it to grow.

### 13. Confusing `auto-fit` and `auto-fill`

They are related but not identical.

```css
repeat(auto-fit, minmax(200px, 1fr))
```

and:

```css
repeat(auto-fill, minmax(200px, 1fr))
```

can behave differently when there are fewer items than the number of tracks that can fit.

Do not assume they are always interchangeable.

### 14. Creating Invalid `grid-template-areas`

Named areas must form rectangular regions.

Valid:

```css
grid-template-areas:
    "header header"
    "main main";
```

Invalid shapes should not be used for a single named area.

For example, an L-shaped area is not valid:

```text
┌──────────┬──────────┐
│   box    │   box    │
├──────────┼──────────┤
│   box    │          │
└──────────┴──────────┘
```

A named area must form a rectangle.

### 15. Forgetting `.` for Empty Grid-Area Cells

A period represents an empty cell.

```css
grid-template-areas:
    "header header"
    "sidebar main"
    ".      footer";
```

The `.` is important because it explicitly represents an empty grid cell.

### 16. Using Different Area Names Accidentally

Each element's `grid-area` value must match a name defined in `grid-template-areas`.

For example:

```css
grid-template-areas:
    "header header"
    "main main";
```

Then:

```css
header {
    grid-area: header;
}

main {
    grid-area: main;
}
```

If the names do not match, the intended named-area placement will not work.

### 17. Confusing `justify-items` With `justify-content`

These properties operate at different levels.

```text
justify-items
      ↓
Aligns items inside their grid areas

justify-content
      ↓
Aligns the grid tracks inside the container
```

For example:

```css
.container {
    justify-items: center;
}
```

is not equivalent to:

```css
.container {
    justify-content: center;
}
```

### 18. Confusing `align-items` With `align-content`

Similarly:

```text
align-items
      ↓
Aligns items inside their grid areas

align-content
      ↓
Aligns grid tracks inside the container
```

Understanding this distinction prevents many alignment problems.

### 19. Using `justify-self` When You Need `justify-items`

`justify-self` affects one item:

```css
.item {
    justify-self: center;
}
```

`justify-items` affects all grid items:

```css
.container {
    justify-items: center;
}
```

Choose the property according to the required scope.

### 20. Using Fixed Sizes Everywhere

A layout such as:

```css
grid-template-columns:
    200px 300px 400px;
```

may work at one width but become difficult to adapt to smaller screens.

Where appropriate, consider:

```css
grid-template-columns:
    1fr 2fr 1fr;
```

or:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
```

The correct choice depends on the design.

### 21. Ignoring Implicit Grid Tracks

If you define:

```css
grid-template-columns: repeat(3, 1fr);
```

but do not define rows, additional rows can be created automatically as items are added.

If their size needs to be controlled, use:

```css
grid-auto-rows: 150px;
```

### 22. Forgetting About Implicit Track Sizing

Explicitly defined tracks and automatically created tracks can have different sizing rules.

For example:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 150px;
}
```

Here:

```text
Columns → explicitly defined
Rows    → automatically created and sized at 150px
```

### 23. Using Too Many Media Queries

A Grid layout can sometimes be made responsive without multiple breakpoints.

For example:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

Before adding many media queries, consider whether Grid's intrinsic responsive features can solve the problem.

### 24. Not Testing Long Content

A layout that works with:

```text
Short title
```

may fail with:

```text
A very long title that takes much more space than expected
```

Test Grid layouts with realistic content.

Also test:

```text
Long text
Large images
Small images
Many items
Few items
```

### 25. Ignoring Overflow

If content is larger than the available grid area, it can cause unexpected overflow.

Check:

```css
overflow
```

and consider track sizing such as:

```css
minmax(0, 1fr)
```

when appropriate.

### 26. Using Grid When Flexbox Is Simpler

Grid is designed for two-dimensional layouts.

If the layout only needs a single direction, Flexbox may be simpler.

Think:

```text
One dimension
    ↓
Flexbox may be suitable

Two dimensions
    ↓
Grid may be suitable
```

This is a guideline, not a strict rule.

### 27. Relying on Visual Order Without Considering Source Order

CSS Grid can visually reposition items.

However, the HTML source order still matters for accessibility and logical navigation.

Prefer an HTML order that makes sense before using CSS to rearrange the visual presentation.

### 28. Making Layouts Dependent on Arbitrary Line Numbers

Complex rules such as:

```css
.item {
    grid-column: 7 / 13;
    grid-row: 5 / 10;
}
```

can become difficult to maintain.

For larger semantic layouts, named areas may be clearer:

```css
grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
```

### 29. Forgetting to Test at Different Widths

Always test:

```text
Large screen
     ↓
Medium screen
     ↓
Small screen
```

Check for:

```text
Overflow
Tiny columns
Unexpected gaps
Broken areas
Overlapping content
```

### 30. Overcomplicating the Grid

CSS Grid has many features, but a simple layout does not need all of them.

For example, this may be enough:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Do not add:

```text
grid-auto-flow
grid-template-areas
multiple line placements
many breakpoints
```

unless the design actually requires them.

### Common Mistake Checklist

```text
☐ Forgot display: grid
☐ Confused grid-template-columns with grid-column
☐ Confused grid-template-rows with grid-row
☐ Misunderstood grid lines
☐ Used gap incorrectly
☐ Added unnecessary item positioning
☐ Overused dense placement
☐ Confused fr with px
☐ Used minmax() incorrectly
☐ Forgot minimum sizes in responsive layouts
☐ Confused auto-fit and auto-fill
☐ Created invalid grid areas
☐ Forgot "." for empty areas
☐ Used incorrect area names
☐ Confused items and content alignment
☐ Ignored implicit tracks
☐ Used too many fixed sizes
☐ Added unnecessary media queries
☐ Ignored overflow
☐ Used Grid when a simpler layout method was appropriate
☐ Failed to test different screen sizes
```

> 💡 **Remember:** Most CSS Grid problems come from confusing **grid definition, item placement, alignment, and automatic track creation**. Understand which level a property controls before changing the CSS.

---

## Interview Questions

### Basic Questions

#### 1. What is CSS Grid?

CSS Grid is a two-dimensional CSS layout system used to create layouts with rows and columns.

```css
.container {
    display: grid;
}
```

---

#### 2. What is the difference between CSS Grid and Flexbox?

The main distinction is:

```text
CSS Grid
→ Two-dimensional layout
→ Rows + Columns

Flexbox
→ One-dimensional layout
→ Row OR Column
```

Grid is particularly useful when both dimensions need to be controlled.

---

#### 3. How do you create a Grid container?

Use:

```css
display: grid;
```

Example:

```css
.container {
    display: grid;
}
```

The direct children become grid items.

---

#### 4. What is a grid track?

A grid track is a **row or column** in a Grid layout.

```text
Column track
     ↓
┌──────────┬──────────┐
│          │          │
│          │          │
└──────────┴──────────┘
```

---

#### 5. What is a grid line?

A grid line is a boundary between grid tracks.

For two columns:

```text
Line 1       Line 2       Line 3
   │            │            │
   │  Column 1  │  Column 2  │
```

Grid lines are used by properties such as:

```css
grid-column
grid-row
```

---

#### 6. What is a grid cell?

A grid cell is the individual space formed by the intersection of a row and a column.

```text
┌──────────┬──────────┐
│ Cell 1   │ Cell 2   │
├──────────┼──────────┤
│ Cell 3   │ Cell 4   │
└──────────┴──────────┘
```

---

### Grid Sizing Questions

#### 7. What does `grid-template-columns` do?

It defines the columns of the explicit grid.

```css
.container {
    grid-template-columns: 1fr 2fr;
}
```

This creates two columns with a flexible `1 : 2` ratio.

---

#### 8. What does `grid-template-rows` do?

It defines the rows of the explicit grid.

```css
.container {
    grid-template-rows: 100px 1fr;
}
```

---

#### 9. What is the `fr` unit?

`fr` represents a fraction of the available flexible space.

```css
grid-template-columns: 1fr 2fr;
```

The available flexible space is divided in a:

```text
1 : 2
```

ratio.

---

#### 10. What does `repeat()` do?

`repeat()` allows a track pattern to be repeated.

```css
grid-template-columns: repeat(3, 1fr);
```

is equivalent to:

```css
grid-template-columns: 1fr 1fr 1fr;
```

---

#### 11. What does `minmax()` do?

`minmax()` defines a minimum and maximum size for a grid track.

```css
grid-template-columns:
    minmax(200px, 1fr);
```

The track can have a minimum of `200px` and a flexible maximum of `1fr`.

---

#### 12. What is the `gap` property used for in Grid?

`gap` creates spacing between grid tracks.

```css
.container {
    gap: 20px;
}
```

It can also be separated into:

```css
row-gap: 20px;
column-gap: 30px;
```

---

### Placement Questions

#### 13. What does `grid-column` do?

It controls the horizontal placement of a grid item using column grid lines.

```css
.item {
    grid-column: 1 / 3;
}
```

The item spans from line 1 to line 3.

---

#### 14. What does `grid-row` do?

It controls the vertical placement of a grid item using row grid lines.

```css
.item {
    grid-row: 1 / 3;
}
```

---

#### 15. How do you make an item span multiple columns?

Use `span`.

```css
.item {
    grid-column: span 2;
}
```

The item occupies two column tracks.

---

#### 16. How do you make an item span the entire grid width?

A common pattern is:

```css
.item {
    grid-column: 1 / -1;
}
```

`-1` refers to the last grid line.

---

#### 17. How do you make an item span the entire grid height?

Use:

```css
.item {
    grid-row: 1 / -1;
}
```

---

### Grid Area Questions

#### 18. What is `grid-template-areas`?

It allows you to define named regions of a grid.

Example:

```css
.layout {
    display: grid;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

---

#### 19. How do you assign an item to a named grid area?

Use:

```css
.item {
    grid-area: header;
}
```

The name must match the name defined in:

```css
grid-template-areas
```

---

#### 20. What does `.` mean in `grid-template-areas`?

A period represents an empty grid cell.

Example:

```css
grid-template-areas:
    "header header"
    "sidebar main"
    ".      footer";
```

The `.` leaves that cell empty.

---

#### 21. What is a restriction on named grid areas?

A named grid area must form a **rectangle**.

Irregular shapes such as L-shaped areas cannot be represented as one named grid area.

---

### Auto Placement Questions

#### 22. What is Grid auto-placement?

When grid items are not explicitly positioned, CSS Grid automatically places them into available cells.

Example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

The browser automatically places the items into the available cells.

---

#### 23. What is `grid-auto-flow`?

`grid-auto-flow` controls the direction and packing behavior of automatically placed grid items.

Common values:

```css
grid-auto-flow: row;
grid-auto-flow: column;
grid-auto-flow: dense;
```

---

#### 24. What is the default value of `grid-auto-flow`?

The default is:

```css
grid-auto-flow: row;
```

Items are automatically placed in row order.

---

#### 25. What does `grid-auto-flow: column` do?

It changes automatic placement to proceed by columns.

```css
.container {
    grid-auto-flow: column;
}
```

---

#### 26. What does `dense` do?

The `dense` keyword tells the auto-placement algorithm to try to fill earlier available gaps.

```css
grid-auto-flow: dense;
```

It can change the visual placement order, so it should be used carefully when order matters.

---

### Explicit and Implicit Grid Questions

#### 27. What is an explicit grid?

The explicit grid consists of tracks directly defined using:

```css
grid-template-columns
grid-template-rows
```

---

#### 28. What is an implicit grid?

The implicit grid consists of tracks that Grid creates automatically when additional tracks are needed.

---

#### 29. How do you control automatically created rows?

Use:

```css
grid-auto-rows
```

Example:

```css
.container {
    grid-auto-rows: 150px;
}
```

---

#### 30. How do you control automatically created columns?

Use:

```css
grid-auto-columns
```

Example:

```css
.container {
    grid-auto-columns: 200px;
}
```

---

### Alignment Questions

#### 31. What does `justify-items` do?

It controls the alignment of grid items along the inline axis within their grid areas.

Example:

```css
.container {
    justify-items: center;
}
```

---

#### 32. What does `align-items` do?

It controls the alignment of grid items along the block axis within their grid areas.

```css
.container {
    align-items: center;
}
```

---

#### 33. What does `justify-self` do?

It controls the inline-axis alignment of one individual grid item.

```css
.item {
    justify-self: center;
}
```

---

#### 34. What does `align-self` do?

It controls the block-axis alignment of one individual grid item.

```css
.item {
    align-self: center;
}
```

---

#### 35. What does `place-items` do?

`place-items` is a shorthand for:

```css
align-items
justify-items
```

For example:

```css
.container {
    place-items: center;
}
```

---

#### 36. What does `place-self` do?

`place-self` is a shorthand for:

```css
align-self
justify-self
```

Example:

```css
.item {
    place-self: center;
}
```

---

#### 37. What does `justify-content` do?

It controls the alignment of the grid tracks inside the grid container along the inline axis.

This is different from `justify-items`, which controls items inside their grid areas.

---

#### 38. What does `align-content` do?

It controls the alignment of the grid tracks inside the grid container along the block axis.

---

#### 39. How do you center Grid items in both directions?

A common approach is:

```css
.container {
    display: grid;
    place-items: center;
}
```

---

### Responsive Grid Questions

#### 40. How can CSS Grid be made responsive?

Common techniques include:

```css
fr
repeat()
minmax()
auto-fit
auto-fill
media queries
```

For example:

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
}
```

---

#### 41. What is `auto-fit`?

`auto-fit` allows the browser to determine how many tracks can fit and can collapse empty tracks, allowing existing tracks to expand.

Example:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
```

---

#### 42. What is `auto-fill`?

`auto-fill` allows Grid to create as many tracks as can fit according to the available space and track sizing.

Example:

```css
grid-template-columns:
    repeat(auto-fill, minmax(200px, 1fr));
```

---

#### 43. What is the difference between `auto-fit` and `auto-fill`?

A simplified distinction is:

```text
auto-fill
→ Fits as many tracks as possible

auto-fit
→ Fits tracks and can collapse empty tracks
```

The difference is most noticeable when there are fewer items than the number of tracks that could fit.

---

### Scenario-Based Questions

#### 44. How would you create a responsive card grid?

A common solution is:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}
```

---

#### 45. How would you create a layout with a sidebar and main content?

For example:

```css
.layout {
    display: grid;
    grid-template-columns: 220px 1fr;
    gap: 20px;
}
```

---

#### 46. How would you make a header span the complete grid?

Use:

```css
header {
    grid-column: 1 / -1;
}
```

---

#### 47. How would you create a header, sidebar, main content, and footer using named areas?

```css
.layout {
    display: grid;

    grid-template-columns: 220px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

Then:

```css
header {
    grid-area: header;
}

aside {
    grid-area: sidebar;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

---

#### 48. When would you use `minmax(0, 1fr)`?

It can be useful for flexible content columns when you need the track to be able to shrink below its minimum content contribution.

Example:

```css
.layout {
    grid-template-columns:
        240px minmax(0, 1fr);
}
```

---

#### 49. When should you consider using Grid instead of Flexbox?

A useful guideline is:

```text
Need one-dimensional layout?
→ Flexbox may be suitable

Need two-dimensional layout?
→ Grid may be suitable
```

The choice ultimately depends on the layout requirements.

---

#### 50. What are the most important CSS Grid properties to know?

A strong foundation includes:

```css
display: grid;

grid-template-columns;
grid-template-rows;

grid-template-areas;
grid-area;

grid-column;
grid-row;

grid-auto-flow;
grid-auto-columns;
grid-auto-rows;

gap;
row-gap;
column-gap;

justify-items;
align-items;
justify-self;
align-self;

justify-content;
align-content;
```

For responsive layouts, also know:

```css
repeat()
minmax()
auto-fit
auto-fill
fr
```

### Quick Interview Summary

```text
CSS Grid
→ Two-dimensional layout system

fr
→ Fraction of flexible space

repeat()
→ Repeats track patterns

minmax()
→ Defines minimum and maximum track sizes

gap
→ Space between tracks

grid-column
→ Horizontal item placement

grid-row
→ Vertical item placement

grid-template-areas
→ Defines named layout regions

grid-area
→ Assigns an item to a named region

grid-auto-flow
→ Controls automatic placement

grid-auto-rows / columns
→ Controls implicit track sizes

justify-items / align-items
→ Align all items

justify-self / align-self
→ Align one item

justify-content / align-content
→ Align grid tracks

auto-fit / auto-fill
→ Responsive track generation
```

> 💡 **Interview Tip:** Do not only memorize property definitions. Be able to explain the difference between **tracks and lines**, **items and content alignment**, **explicit and implicit grids**, and **`auto-fit` vs `auto-fill`**. These distinctions commonly reveal whether you understand how CSS Grid actually works.

---

## Practice Exercises

Use the following exercises to practice the CSS Grid concepts covered in this chapter.

### Exercise 1: Basic Grid

Create a grid with **three equal columns**.

Requirements:

```text
3 columns
Equal width
20px gap
```

Expected CSS:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

---

### Exercise 2: Two-Column Layout

Create a layout with:

```text
Sidebar → 250px
Main    → Remaining space
```

Requirements:

```text
Use CSS Grid
Use 250px for the sidebar
Use 1fr for the main content
```

Expected pattern:

```css
grid-template-columns: 250px 1fr;
```

---

### Exercise 3: Grid With Rows

Create a grid with:

```text
3 columns
2 rows
```

Make each row `100px` high.

Use:

```css
grid-template-columns
grid-template-rows
```

---

### Exercise 4: `repeat()`

Rewrite:

```css
grid-template-columns:
    1fr 1fr 1fr 1fr;
```

using `repeat()`.

Expected pattern:

```css
grid-template-columns: repeat(4, 1fr);
```

---

### Exercise 5: `minmax()`

Create three columns where each column:

```text
Minimum → 200px
Maximum → 1fr
```

Use:

```css
repeat()
minmax()
```

Expected pattern:

```css
grid-template-columns:
    repeat(3, minmax(200px, 1fr));
```

---

### Exercise 6: Grid Gap

Create a grid with:

```text
Row gap    → 10px
Column gap → 30px
```

Use the `gap` shorthand.

Expected pattern:

```css
gap: 10px 30px;
```

---

### Exercise 7: Column Spanning

Create a three-column grid.

Make the first item span **two columns**.

Expected pattern:

```css
.item:first-child {
    grid-column: span 2;
}
```

---

### Exercise 8: Full-Width Item

Create a four-column grid.

Make the header span the entire grid width.

Expected pattern:

```css
header {
    grid-column: 1 / -1;
}
```

---

### Exercise 9: Row Spanning

Create a grid with three rows.

Make one item span two rows.

Expected pattern:

```css
.item {
    grid-row: span 2;
}
```

---

### Exercise 10: Full-Height Sidebar

Create a layout with:

```text
2 columns
3 rows
```

Make the sidebar span all rows.

Expected pattern:

```css
.sidebar {
    grid-row: 1 / -1;
}
```

---

### Exercise 11: Named Grid Areas

Create the following layout:

```text
┌──────────────────────────────┐
│            Header            │
├──────────────┬───────────────┤
│   Sidebar    │     Main      │
├──────────────┴───────────────┤
│            Footer            │
└──────────────────────────────┘
```

Use:

```css
grid-template-areas
grid-area
```

Do not use `grid-column` or `grid-row` for the main placement.

---

### Exercise 12: Empty Grid Area

Create a two-column layout where the bottom-left cell remains empty:

```text
┌──────────────┬──────────────┐
│    Header    │    Header    │
├──────────────┼──────────────┤
│   Sidebar    │     Main     │
├──────────────┼──────────────┤
│              │    Footer    │
└──────────────┴──────────────┘
```

Use `.` inside `grid-template-areas`.

---

### Exercise 13: Center an Item

Create a grid container and center an item both horizontally and vertically.

Use:

```css
place-items
```

Expected pattern:

```css
.container {
    display: grid;
    place-items: center;
}
```

---

### Exercise 14: Individual Item Alignment

Create a grid where all items are centered.

Then make one specific item:

```text
Horizontal → end
Vertical   → start
```

Use:

```css
justify-self
align-self
```

---

### Exercise 15: Responsive Card Grid

Create a responsive card layout where each card has:

```text
Minimum width → 220px
Maximum       → 1fr
```

The number of columns should automatically adapt to the available width.

Use:

```css
auto-fit
minmax()
repeat()
```

Expected pattern:

```css
grid-template-columns:
    repeat(auto-fit, minmax(220px, 1fr));
```

---

### Exercise 16: `auto-fill`

Create the same responsive card layout using:

```css
auto-fill
```

instead of:

```css
auto-fit
```

Then compare the behavior when there are fewer items than the number of tracks that can fit.

---

### Exercise 17: Implicit Rows

Create:

```text
3 explicit columns
```

but do not explicitly define rows.

Add enough items to require multiple rows.

Then use:

```css
grid-auto-rows
```

to give automatically created rows a fixed height.

---

### Exercise 18: Auto Placement

Create a grid with three columns and six items.

Do not assign `grid-column` or `grid-row` to the items.

Observe how Grid automatically places them.

Then experiment with:

```css
grid-auto-flow: column;
```

---

### Exercise 19: Dense Placement

Create a grid containing items with different column spans.

Use:

```css
grid-auto-flow: dense;
```

Observe how the browser attempts to fill available gaps.

Then remove `dense` and compare the result.

---

### Exercise 20: Responsive Dashboard

Create a dashboard containing:

```text
Header
Sidebar
Card 1
Card 2
Chart
Footer
```

Desktop layout:

```text
┌──────────┬────────────┬────────────┐
│ Sidebar  │   Header   │   Header   │
├──────────┼────────────┼────────────┤
│ Sidebar  │   Card 1   │   Card 2   │
├──────────┼────────────┴────────────┤
│ Sidebar  │          Chart          │
├──────────┴─────────────────────────┤
│              Footer                │
└────────────────────────────────────┘
```

Use:

```css
grid-template-areas
```

Then create a mobile layout where the sections are stacked vertically.

---

### Exercise 21: Image Gallery

Create a responsive image gallery using:

```css
repeat()
auto-fit
minmax()
gap
```

Each image should have a minimum track width of `180px`.

Expected pattern:

```css
.gallery {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px;
}
```

---

### Exercise 22: Featured Card

Create a four-column card grid.

Make one featured card span:

```text
2 columns
2 rows
```

Use:

```css
grid-column
grid-row
```

Expected pattern:

```css
.featured {
    grid-column: span 2;
    grid-row: span 2;
}
```

---

### Exercise 23: Fixed Sidebar With Flexible Content

Create:

```text
Sidebar → 240px
Main    → Flexible
```

Use:

```css
minmax(0, 1fr)
```

for the main content.

Expected pattern:

```css
grid-template-columns:
    240px minmax(0, 1fr);
```

Add long content to the main area and observe the behavior.

---

### Exercise 24: Build a Complete Page

Create a complete responsive page containing:

```text
Header
Navigation
Sidebar
Main Content
Cards
Footer
```

Requirements:

```text
Use CSS Grid
Use named grid areas
Use gap
Use responsive behavior
Use repeat()
Use minmax()
```

The page should work on both large and small screens.

---

### Exercise 25: Grid Challenge

Build a responsive dashboard without copying the previous examples.

Requirements:

```text
✓ CSS Grid
✓ At least 3 columns on wide screens
✓ Responsive layout
✓ Named grid areas
✓ At least one spanning item
✓ gap
✓ repeat()
✓ minmax()
✓ auto-fit or auto-fill
✓ Grid alignment
✓ Implicit or automatically placed content
```

Try to create the layout from scratch before checking previous examples.

### Self-Check

After completing the exercises, make sure you can explain:

```text
☐ What is a grid container?
☐ What is a grid item?
☐ What is a grid track?
☐ What is a grid line?
☐ What is a grid cell?
☐ What does 1fr mean?
☐ What does repeat() do?
☐ What does minmax() do?
☐ What does gap do?
☐ How does grid-column work?
☐ How does grid-row work?
☐ What is grid-template-areas?
☐ What is grid-area?
☐ What is auto-placement?
☐ What is grid-auto-flow?
☐ What is an explicit grid?
☐ What is an implicit grid?
☐ What does auto-fit do?
☐ What does auto-fill do?
☐ How do you create a responsive Grid?
☐ When might Grid be preferable to Flexbox?
```

> 💡 **Remember:** Practice by first building simple grids, then combine features such as `repeat()`, `minmax()`, spanning, named areas, alignment, and responsive auto-placement. The goal is to understand why each property is used, not just memorize its syntax.