## Table of Contents

1. [Introduction](#introduction)
2. [What Are Media Queries?](#what-are-media-queries)
3. [Why Are Media Queries Important?](#why-are-media-queries-important)
4. [Media Query Syntax](#media-query-syntax)
5. [Media Types](#media-types)
6. [Media Features](#media-features)
7. [Width and Height](#width-and-height)
8. [min-width](#min-width)
9. [max-width](#max-width)
10. [Combining Conditions](#combining-conditions)
11. [Logical Operators](#logical-operators)
12. [Orientation](#orientation)
13. [Responsive Breakpoints](#responsive-breakpoints)
14. [Mobile-First Approach](#mobile-first-approach)
15. [Desktop-First Approach](#desktop-first-approach)
16. [Common Responsive Patterns](#common-responsive-patterns)
17. [Practical Examples](#practical-examples)
18. [Key Takeaways](#key-takeaways)
19. [References](#references)
20. [Quick Revision](#quick-revision)
21. [Best Practices](#best-practices)
22. [Common Mistakes](#common-mistakes)
23. [Interview Questions](#interview-questions)
24. [Practice Exercises](#practice-exercises)
25. [Related Topics](#related-topics)

---

# Introduction

CSS Media Queries are an important part of responsive web design.

They allow CSS styles to be applied conditionally based on characteristics of the device, viewport, or browsing environment.

For example, a webpage can use one layout on a large screen and a different layout on a smaller screen.

```css
@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

In this example, the style inside the media query is applied when the viewport width is `600px` or less.

Media queries are commonly used to adapt:

- Layouts
- Navigation
- Typography
- Spacing
- Images
- Components
- Columns
- Flexbox layouts
- Grid layouts

They are especially useful when building websites that need to work across different screen sizes.

Responsive design allows a webpage to provide a better user experience on:

- Mobile phones
- Tablets
- Laptops
- Desktop computers
- Large displays

Media queries work together with other CSS features such as Flexbox and Grid to create layouts that can adapt to different viewport sizes.

---

## Why Responsive Design Is Important

Users access websites from devices with different screen sizes and display characteristics.

A layout that works well on a large desktop screen may not provide the same experience on a smaller mobile screen.

For example, a desktop layout may display multiple elements in a row:

```text
┌────────────┬────────────┬────────────┐
│   Item 1   │   Item 2   │   Item 3   │
└────────────┴────────────┴────────────┘
```

On a smaller screen, the same elements may need to be arranged vertically:

```text
┌────────────┐
│   Item 1   │
├────────────┤
│   Item 2   │
├────────────┤
│   Item 3   │
└────────────┘
```

Media queries allow CSS to change the presentation of these elements according to the available viewport space.

---

## Responsive Design and Media Queries

Responsive design is an approach where a webpage adapts to different screen sizes and devices.

Media queries help implement responsive designs by allowing different CSS rules to be applied under different conditions.

For example:

```css
.container {
    display: flex;
}

@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
}
```

In this example:

- Larger screens use a horizontal Flexbox layout.
- Smaller screens use a vertical Flexbox layout.
- The HTML structure remains the same.
- Only the CSS presentation changes.

---

> 💡 **Pro Tip:** Think of a media query as a condition that tells CSS when a particular set of styles should be used.

---

> 💡 **Remember:** Media queries allow CSS to respond to different conditions and are one of the fundamental tools used to create responsive websites.

---

# What Are Media Queries?

**Media Queries** are a CSS feature that allows styles to be applied conditionally based on the characteristics of the device, viewport, or browsing environment.

They are mainly used to create **responsive layouts** that can adapt to different screen sizes and device conditions.

A basic media query looks like this:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
    }
}
```

In this example, the CSS rule inside the media query is applied when the viewport width is `600px` or less.

---

## Basic Concept

A media query allows CSS to check whether a particular condition is true.

The basic structure is:

```css
@media (condition) {
    /* CSS rules */
}
```

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

Here, the browser checks the following condition:

```text
Is the viewport width 768px or less?
```

If the condition is true, the CSS rules inside the media query are applied.

If the condition is false, those rules are not applied.

---

## Media Queries Are Conditional CSS

A normal CSS rule is applied whenever its selector matches an element.

For example:

```css
.container {
    width: 80%;
}
```

A media query adds an additional condition:

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

The `.container` will have a width of `100%` only when the viewport width is `768px` or less.

This can be visualized as:

```text
CSS Rule
   │
   ▼
Condition Checked
   │
   ├── True  → Apply CSS
   │
   └── False → Do Not Apply CSS
```

---

## Media Queries and Responsive Design

Media queries are one of the fundamental tools used to create responsive websites.

A responsive website can change its layout depending on the available screen space.

For example, a desktop layout may display items horizontally:

```text
┌──────────┐  ┌──────────┐  ┌──────────┐
│  Item 1  │  │  Item 2  │  │  Item 3  │
└──────────┘  └──────────┘  └──────────┘
```

On a smaller screen, the same items can be arranged vertically:

```text
┌──────────┐
│  Item 1  │
└──────────┘
      ↓
┌──────────┐
│  Item 2  │
└──────────┘
      ↓
┌──────────┐
│  Item 3  │
└──────────┘
```

This can be achieved using a media query:

```css
.container {
    display: flex;
}

@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
}
```

The HTML structure can remain unchanged while the CSS layout adapts to the viewport.

---

## Common Characteristics Checked by Media Queries

Media queries can be used to check different characteristics of the browsing environment.

Common examples include:

- Viewport width
- Viewport height
- Device orientation
- Display characteristics
- User preferences

For example:

```css
@media (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

This rule is applied when the viewport is in landscape orientation.

---

## Media Queries Do Not Require Separate HTML Pages

A media query allows the same webpage to adapt to different conditions.

For example, the same HTML can be used for both desktop and mobile layouts:

```html
<div class="container">
    <div class="box">One</div>
    <div class="box">Two</div>
    <div class="box">Three</div>
</div>
```

The layout can then be changed with CSS:

```css
.container {
    display: flex;
}

@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

The HTML remains the same.

Only the CSS presentation changes according to the viewport condition.

---

## Media Query Example

Consider a navigation menu:

```css
.nav {
    display: flex;
    gap: 20px;
}
```

On a smaller screen, the navigation can be changed to a vertical layout:

```css
@media (max-width: 600px) {
    .nav {
        flex-direction: column;
    }
}
```

The result can be visualized as:

```text
Large Screen:

Home    About    Services    Contact


Small Screen:

Home
About
Services
Contact
```

This is one of the common ways media queries are used in responsive web development.

---

> 💡 **Pro Tip:** Think of a media query as a condition that tells CSS when a particular set of styles should be used.

---

> 💡 **Remember:** A media query is a conditional CSS feature that allows different styles to be applied when specific conditions of the viewing environment are satisfied.

---

## Why Are Media Queries Important?

Media queries are important because they allow CSS to adapt a webpage's layout and appearance to different screen sizes and viewing conditions.

Modern websites are accessed from many different devices, including:

- Mobile phones
- Tablets
- Laptops
- Desktop computers
- Large displays

Each device can have a different viewport size. A layout that works well on a large desktop screen may not work well on a smaller mobile screen.

Media queries allow CSS to respond to these differences and create responsive layouts.

---

## Responsive Design

One of the main reasons media queries are important is that they help create responsive websites.

A responsive website can change its layout according to the available screen space.

For example, a desktop layout may display three columns:

```text
┌────────────┬────────────┬────────────┐
│   Column 1 │   Column 2 │   Column 3 │
└────────────┴────────────┴────────────┘
```

On a smaller screen, the same columns can be arranged vertically:

```text
┌────────────┐
│   Column 1 │
├────────────┤
│   Column 2 │
├────────────┤
│   Column 3 │
└────────────┘
```

This can be achieved using a media query:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

The HTML structure can remain the same while the CSS layout changes according to the viewport size.

---

## Better User Experience

Media queries help improve the user experience by making websites easier to use on different devices.

For example, a navigation menu that fits comfortably on a desktop screen may not fit properly on a mobile screen.

```css
.navigation {
    display: flex;
    gap: 20px;
}

@media (max-width: 600px) {
    .navigation {
        flex-direction: column;
        gap: 10px;
    }
}
```

The navigation can therefore change its layout when the available screen width becomes smaller.

---

## Better Readability

Media queries can be used to adjust typography for different screen sizes.

For example:

```css
h1 {
    font-size: 40px;
}

@media (max-width: 600px) {
    h1 {
        font-size: 28px;
    }
}
```

On larger screens, the heading can use a larger font size.

On smaller screens, the font size can be reduced to make better use of the available space.

---

## Better Use of Available Space

Different devices provide different amounts of available screen space.

Media queries allow elements to use that space more effectively.

For example:

```css
.container {
    width: 80%;
}

@media (max-width: 600px) {
    .container {
        width: 95%;
    }
}
```

The container can use a larger portion of the available viewport width on smaller screens.

---

## Adapting Components

Media queries can also be used to change individual components.

For example, cards may appear in a row on a larger screen:

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│  Card 1 │  │  Card 2 │  │  Card 3 │
└─────────┘  └─────────┘  └─────────┘
```

On a smaller screen, the cards can be displayed vertically:

```text
┌─────────┐
│  Card 1 │
└─────────┘

┌─────────┐
│  Card 2 │
└─────────┘

┌─────────┐
│  Card 3 │
└─────────┘
```

This allows components to remain usable across different screen sizes.

---

## Working With Flexbox and Grid

Media queries are commonly used together with CSS layout systems such as Flexbox and Grid.

For example, Flexbox can change from a horizontal layout to a vertical layout:

```css
.container {
    display: flex;
    gap: 20px;
}

@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
}
```

Grid can also change the number of columns:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

This makes it easier to create layouts that work across different screen sizes.

---

## Supporting Different Orientations

Media queries can also respond to the orientation of the viewport.

For example:

```css
@media (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

This allows the design to respond differently when the viewport is in landscape orientation.

---

## One Website for Different Devices

Media queries make it possible to maintain one website while adapting its presentation for different devices.

```text
                 Same HTML
                     ↓
                    CSS
                     ↓
              Media Queries
                     ↓
          ┌──────────┼──────────┐
          ↓          ↓          ↓
       Mobile      Tablet     Desktop
```

The same HTML structure can therefore be styled differently depending on the conditions of the viewing environment.

This makes responsive development easier to maintain than creating completely separate layouts for every device.

---

## Common Areas Where Media Queries Are Useful

Media queries can be used to adapt many parts of a webpage, including:

- Layouts
- Navigation
- Typography
- Spacing
- Images
- Components
- Columns
- Flexbox layouts
- Grid layouts

For example, a webpage may use:

```text
Large screens
     ↓
Multiple columns

Medium screens
     ↓
Fewer columns

Small screens
     ↓
Single column
```

This allows the layout to respond naturally to the available space.

---

## Media Queries and Maintainability

Media queries can make responsive CSS easier to organize because different responsive changes can be grouped together.

For example:

```css
.card {
    width: 300px;
    padding: 20px;
}

@media (max-width: 768px) {
    .card {
        width: 100%;
        padding: 15px;
    }
}
```

The base styles define the normal appearance, while the media query contains the changes required for smaller screens.

This approach helps keep responsive behavior close to the CSS that controls the design.

---

> 💡 **Pro Tip:** Use media queries when the layout or presentation needs to change because of the available space or viewing conditions, rather than targeting specific device names.

---

> 💡 **Remember:** Media queries are important because they allow websites to adapt their layouts, typography, navigation, components, spacing, and other styles to different screen sizes and viewing conditions.

---

## Media Query Syntax

A media query uses the `@media` rule to apply CSS styles only when a specified condition is satisfied.

The basic syntax is:

```css
@media (condition) {
    /* CSS rules */
}
```

The browser evaluates the condition.

If the condition is true, the CSS rules inside the media query are applied.

If the condition is false, those rules are not applied.

Conceptually:

```text
@media
   ↓
Condition
   ↓
Is the condition true?
   ├── Yes → Apply the CSS rules
   │
   └── No  → Do not apply the CSS rules
```

---

## Basic Media Query

A simple media query can check the width of the viewport.

```css
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

In this example, the style inside the media query is applied when the viewport width is `600px` or less.

The media query can be understood as:

```text
Viewport width
      ↓
Is it 600px or less?
      ↓
     Yes
      ↓
Apply the CSS rules
```

If the viewport is wider than `600px`, the condition is not satisfied and the styles inside the media query are not applied.

---

## Understanding the `@media` Rule

The `@media` rule starts a media query.

It tells the browser that the following CSS rules should be applied only when a specified condition is satisfied.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

The structure can be understood as:

```text
@media
   ↓
Start media query

(max-width: 600px)
   ↓
Condition

{
    CSS rules
}
   ↓
Rules applied when the condition is true
```

---

## Understanding the Condition

The condition determines when the CSS rules inside the media query should be applied.

For example:

```css
(max-width: 600px)
```

checks the viewport width.

It can be understood as:

```text
Viewport width
      ↓
600px or less?
      ├── Yes → Apply styles
      │
      └── No  → Do not apply styles
```

The condition can use different media features such as:

- `max-width`
- `min-width`
- `orientation`
- `height`

These media features will be covered in more detail later in the chapter.

---

## Understanding the CSS Block

The curly braces contain the CSS rules that should be applied when the condition is satisfied.

For example:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
    }

    h1 {
        font-size: 28px;
    }
}
```

When the condition is true, both CSS rules are applied.

Conceptually:

```text
max-width: 600px
       ↓
Condition is true
       ↓
┌──────────────────────┐
│ body → 14px          │
│ h1   → 28px          │
└──────────────────────┘
```

A single media query can therefore contain multiple CSS rules.

---

## Media Queries With Normal CSS

Media queries are normally written together with regular CSS rules.

For example:

```css
.container {
    width: 80%;
    margin: auto;
}

@media (max-width: 600px) {
    .container {
        width: 95%;
    }
}
```

The normal CSS rule provides the default styling.

When the viewport becomes `600px` or smaller, the media query changes the width.

The process can be represented as:

```text
Default CSS
    ↓
width: 80%

Smaller viewport
    ↓
Media Query
    ↓
width: 95%
```

This pattern is commonly used when creating responsive layouts.

---

## Using `min-width`

The `min-width` media feature checks whether the viewport width is at least the specified value.

For example:

```css
@media (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition means:

```text
Viewport width >= 768px
        ↓
       True
        ↓
Apply the styles
```

Therefore, the styles are applied when the viewport is `768px` or wider.

---

## Using `max-width`

The `max-width` media feature checks whether the viewport width is at most the specified value.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

The condition means:

```text
Viewport width <= 768px
        ↓
       True
        ↓
Apply the styles
```

Therefore, the styles are applied when the viewport is `768px` or narrower.

---

## `min-width` vs `max-width`

These two media features work in opposite directions.

```text
min-width
    ↓
At or above the specified width
```

```text
max-width
    ↓
At or below the specified width
```

For example:

```css
@media (min-width: 768px) {
    /* 768px and wider */
}
```

```css
@media (max-width: 768px) {
    /* 768px and narrower */
}
```

A simple mental model is:

```text
min-width
    ↓
Minimum viewport width

max-width
    ↓
Maximum viewport width
```

---

## Media Queries With Multiple CSS Rules

A media query can contain multiple CSS declarations and multiple selectors.

For example:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
        margin: 10px;
    }

    h1 {
        font-size: 28px;
    }

    .container {
        width: 95%;
    }
}
```

When the condition is satisfied, all of these rules can be applied.

Conceptually:

```text
Media Query
     ↓
┌─────────────────────────┐
│ Typography              │
│ Spacing                 │
│ Container width         │
└─────────────────────────┘
```

This makes media queries useful when several parts of a layout need to change together.

---

## Media Query With a Media Type

A media query can also include a media type.

For example:

```css
@media screen and (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

Here:

```text
screen
   ↓
Media Type

and
   ↓
Logical Operator

(max-width: 600px)
   ↓
Condition
```

The media type and logical operator will be covered in more detail in later sections.

---

## Media Query Without a Media Type

The media type can be omitted.

For example:

```css
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

This is a common form of media query syntax.

The browser evaluates the condition and applies the styles when the condition matches.

---

## Multiple Media Queries

A stylesheet can contain multiple media queries.

For example:

```css
.container {
    width: 95%;
}

@media (min-width: 600px) {
    .container {
        width: 85%;
    }
}

@media (min-width: 1000px) {
    .container {
        width: 75%;
    }
}
```

The layout can therefore change as the viewport becomes wider.

```text
Small viewport
     ↓
width: 95%

Medium viewport
     ↓
width: 85%

Large viewport
     ↓
width: 75%
```

This allows different responsive styles to be applied at different viewport sizes.

---

## Media Queries and Responsive Layouts

Media queries are especially useful when a layout needs to change its structure.

For example, a navigation layout may use a horizontal arrangement on larger screens:

```text
┌────────┬────────┬────────┬────────┐
│  Home  │ About  │Contact │ Login  │
└────────┴────────┴────────┴────────┘
```

On a smaller screen, the same navigation can become vertical:

```text
┌──────────┐
│   Home   │
├──────────┤
│  About   │
├──────────┤
│ Contact  │
├──────────┤
│  Login   │
└──────────┘
```

The HTML structure can remain the same while the CSS changes through a media query.

---

## Media Queries With Flexbox

Media queries are commonly used together with Flexbox.

For example:

```css
.container {
    display: flex;
    gap: 20px;
}

@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

On a larger screen:

```text
┌──────────┐  ┌──────────┐
│  Item 1  │  │  Item 2  │
└──────────┘  └──────────┘
```

On a smaller screen:

```text
┌──────────┐
│  Item 1  │
└──────────┘
      ↓
┌──────────┐
│  Item 2  │
└──────────┘
```

The media query changes the Flexbox direction when the viewport becomes smaller.

---

## Media Queries With Grid

Media queries can also change the number of Grid columns.

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

On a larger screen:

```text
┌───────┬───────┬───────┐
│   1   │   2   │   3   │
└───────┴───────┴───────┘
```

On a smaller screen:

```text
┌───────┐
│   1   │
├───────┤
│   2   │
├───────┤
│   3   │
└───────┘
```

The media query allows the Grid layout to adapt to the available space.

---

## Media Query Syntax and the CSS Cascade

Media queries are part of CSS, so normal CSS cascade rules still apply.

For example:

```css
.box {
    width: 300px;
}

@media (max-width: 600px) {
    .box {
        width: 100%;
    }
}
```

When the viewport is `600px` or smaller, the media query matches and its declaration can change the width.

The basic flow is:

```text
Normal CSS
    ↓
width: 300px
    ↓
Viewport becomes 600px or smaller
    ↓
Media query matches
    ↓
width: 100%
```

Specificity and source order still matter when multiple CSS declarations apply to the same element.

---

## Common Mistake: Confusing `min-width` and `max-width`

A common mistake is confusing the direction of `min-width` and `max-width`.

For example:

```css
@media (max-width: 600px) {
    /* Smaller viewport */
}
```

means:

```text
600px or smaller
```

Whereas:

```css
@media (min-width: 600px) {
    /* Larger viewport */
}
```

means:

```text
600px or larger
```

Remember:

```text
max-width
    ↓
At or below

min-width
    ↓
At or above
```

---

## Practical Mental Model

A useful way to understand media query syntax is to think of it as a decision.

```text
                Media Query
                     ↓
              Check condition
                     ↓
             Is it satisfied?
               ↙          ↘
             Yes           No
              ↓             ↓
        Apply CSS       Ignore CSS
```

For example:

```css
@media (max-width: 600px) {
    .card {
        width: 100%;
    }
}
```

The browser effectively checks:

```text
Is viewport width <= 600px?
          ↓
      ┌───┴───┐
     Yes      No
      ↓        ↓
Apply CSS   Ignore CSS
```

This mental model becomes especially useful when working with multiple conditions and logical operators.

---

> 💡 **Pro Tip:** Read a media query as a condition. Instead of memorizing the syntax, ask yourself: **"Under what condition should these CSS rules be applied?"**

---

> 💡 **Remember:** A media query starts with `@media`, contains a condition, and includes CSS rules that are applied when that condition is satisfied.

---

## Media Types

Media types describe the general category of media for which a CSS style is intended.

A media query can use a media type together with media features to determine when CSS rules should be applied.

The basic structure is:

```css
@media media-type {
    /* CSS rules */
}
```

For example:

```css
@media screen {
    body {
        font-size: 16px;
    }
}
```

Here, `screen` is the media type.

---

## Common Media Types

CSS media queries provide several media types, including:

- `all`
- `screen`
- `print`

These media types can be used to target different output environments.

Conceptually:

```text
Media Types
     ↓
┌─────────┬──────────┬─────────┐
│   all   │  screen  │  print  │
└─────────┴──────────┴─────────┘
```

---

## `all`

The `all` media type matches all devices.

For example:

```css
@media all {
    body {
        font-family: Arial, sans-serif;
    }
}
```

This media type is useful when the styles are intended to apply across all media types.

In many situations, the media type can simply be omitted because `all` is the default media type.

For example:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
    }
}
```

This is effectively targeting the default `all` media type together with the specified condition.

---

## `screen`

The `screen` media type is used for devices with screens.

For example:

```css
@media screen {
    body {
        background-color: white;
    }
}
```

A screen can include devices such as:

- Mobile phones
- Tablets
- Laptops
- Desktop computers

The `screen` media type is commonly seen when a stylesheet also contains styles specifically intended for printed documents.

---

## `print`

The `print` media type is used when a document is printed or prepared for print output.

For example:

```css
@media print {
    body {
        color: black;
        background: white;
    }
}
```

Print styles can be used to create a more suitable version of a webpage for printing.

For example, a navigation menu may not be useful on a printed page.

```css
@media print {
    .navigation {
        display: none;
    }
}
```

This hides the navigation when the document is printed.

---

## Screen vs Print

A webpage may need different styles for screen viewing and printing.

For example:

```text
                 Webpage
                    ↓
          ┌─────────┴─────────┐
          ↓                   ↓
       Screen                Print
          ↓                   ↓
   Interactive layout     Printable layout
```

The CSS can therefore provide different presentations for the same document.

For example:

```css
body {
    font-family: Arial, sans-serif;
}

@media print {
    body {
        font-family: serif;
    }
}
```

The normal style is used for the webpage, while the print media query provides a different style for printed output.

---

## Combining Media Types With Media Features

A media type can be combined with a media feature.

For example:

```css
@media screen and (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

This contains two parts:

```text
screen
   ↓
Media Type

and
   ↓
Logical Operator

(max-width: 600px)
   ↓
Media Feature
```

The CSS is applied when the query matches the screen media type and the viewport width is `600px` or less.

---

## `screen` With `min-width`

Media types can also be combined with `min-width`.

For example:

```css
@media screen and (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition can be understood as:

```text
Is the output a screen?
        ↓
      Yes
        ↓
Is the viewport at least 768px?
        ↓
      Yes
        ↓
Apply the styles
```

---

## `print` With Media Features

Print styles can also use media features.

For example:

```css
@media print and (orientation: landscape) {
    .report {
        width: 100%;
    }
}
```

This allows print styles to be adjusted according to additional conditions.

Media features such as orientation will be discussed in more detail later.

---

## Using Separate Screen and Print Styles

A stylesheet can contain separate rules for screens and printing.

For example:

```css
.navigation {
    display: flex;
}

@media print {
    .navigation {
        display: none;
    }
}
```

On a screen:

```text
Navigation
    ↓
Visible
```

When printing:

```text
Navigation
    ↓
Hidden
```

This allows the same webpage to provide an appropriate presentation for different output environments.

---

## Practical Example: Printable Article

Consider an article page with navigation, content, and a footer.

```text
Screen
┌──────────────────────────────┐
│          Navigation          │
├──────────────────────────────┤
│                              │
│          Article             │
│                              │
├──────────────────────────────┤
│           Footer             │
└──────────────────────────────┘
```

For printing, some elements may not be necessary.

```css
@media print {
    .navigation,
    .footer {
        display: none;
    }
}
```

The printed version can therefore focus on the article content.

```text
Print
┌──────────────────────────────┐
│                              │
│          Article             │
│                              │
└──────────────────────────────┘
```

This is a practical use of the `print` media type.

---

## Why Media Types Matter

Media types allow CSS to distinguish between different output environments.

For example:

```text
Same HTML
    ↓
Different Media Types
    ↓
┌──────────────┬──────────────┐
│    Screen    │    Print     │
└──────────────┴──────────────┘
       ↓               ↓
Interactive        Printable
  design             design
```

This allows a single document to have different presentations without requiring separate HTML pages.

---

## Media Type vs Media Feature

A media type describes the general type of output.

A media feature describes a characteristic or condition of that output.

For example:

```css
@media screen and (max-width: 600px) {
    /* CSS rules */
}
```

Here:

```text
screen
   ↓
Media Type

max-width
   ↓
Media Feature
```

A useful mental model is:

```text
Media Type
    ↓
"What kind of output?"

Media Feature
    ↓
"What condition does it have?"
```

This distinction becomes important when writing more advanced media queries.

---

## Omitting the Media Type

The media type is optional in many common media queries.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

This is often preferred when the styles are intended for the normal screen-based presentation and no explicit media type is required.

Compared with:

```css
@media screen and (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

both forms can be useful, but the shorter form is common in responsive CSS.

---

## Quick Comparison

| Media Type | Purpose |
|------------|---------|
| `all` | Matches all media types |
| `screen` | Targets screen-based output |
| `print` | Targets printed output |

Example:

```css
@media screen {
    /* Screen styles */
}
```

```css
@media print {
    /* Print styles */
}
```

```css
@media all {
    /* Styles for all media types */
}
```

---

## Common Mistake

Do not confuse a media type with a media feature.

For example:

```css
@media screen and (max-width: 600px) {
    /* CSS rules */
}
```

Here:

```text
screen
    ↓
Media Type

max-width: 600px
    ↓
Media Feature
```

`screen` does not describe the viewport width.

`max-width` describes the viewport width condition.

---

> 💡 **Pro Tip:** Use a media type when you actually need to distinguish the output environment, such as screen and print. For many responsive layouts, a media feature such as `max-width` or `min-width` is enough.

---

> 💡 **Remember:** Media types describe the general output environment, such as `screen`, `print`, or `all`. Media features describe characteristics or conditions such as width, height, or orientation.

---

## Media Features

Media features describe specific characteristics of the device, browser, or viewing environment.

While a media type describes the general type of output, such as `screen` or `print`, a media feature describes a particular characteristic or condition.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

Here, `max-width` is a media feature.

It checks the available viewport width and determines whether the condition is satisfied.

Conceptually:

```text
Media Query
     ↓
Media Feature
     ↓
Check a characteristic
     ↓
Condition satisfied?
     ├── Yes → Apply CSS
     │
     └── No  → Do not apply CSS
```

---

## Media Type vs Media Feature

A media type describes the general type of output.

A media feature describes a specific characteristic of that output.

For example:

```css
@media screen and (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

The query can be divided into:

```text
screen
   ↓
Media Type

max-width: 600px
   ↓
Media Feature
```

A simple way to remember the difference is:

```text
Media Type
    ↓
"What kind of output is this?"

Media Feature
    ↓
"What characteristics or conditions does it have?"
```

---

## Common Media Features

CSS provides many media features that can be used to describe characteristics of the viewing environment.

Common examples include:

- `width`
- `min-width`
- `max-width`
- `height`
- `min-height`
- `max-height`
- `orientation`
- `aspect-ratio`
- `resolution`

Some media features describe viewport dimensions, while others describe characteristics such as orientation or display resolution.

---

## Width

The `width` media feature checks the width of the viewport.

For example:

```css
@media (width: 600px) {
    .container {
        width: 100%;
    }
}
```

The condition checks whether the viewport width is exactly `600px`.

Conceptually:

```text
Viewport width
      ↓
Exactly 600px?
      ↓
   ┌───┴───┐
  Yes      No
   ↓        ↓
Apply    Ignore
 CSS       CSS
```

Exact-value queries are less common in responsive design than range-based queries such as `min-width` and `max-width`.

---

## `min-width`

The `min-width` media feature checks whether the viewport width is at least a specified value.

For example:

```css
@media (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition means:

```text
Viewport width >= 768px
```

Therefore, the styles apply at `768px` and wider.

---

## `max-width`

The `max-width` media feature checks whether the viewport width is at most a specified value.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

The condition means:

```text
Viewport width <= 768px
```

Therefore, the styles apply at `768px` and narrower.

---

## Width Range

Media features can be combined to target a range of viewport widths.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

The condition can be understood as:

```text
Viewport width
      ↓
At least 600px?
      ↓
     Yes
      ↓
At most 1000px?
      ↓
     Yes
      ↓
Apply the styles
```

This allows a design to target a specific range rather than only a single minimum or maximum size.

---

## Height

The `height` media feature checks the height of the viewport.

For example:

```css
@media (height: 800px) {
    .container {
        min-height: 400px;
    }
}
```

This checks whether the viewport height is exactly `800px`.

As with exact width queries, exact height queries are less common than range-based conditions.

---

## `min-height`

The `min-height` media feature checks whether the viewport height is at least a specified value.

For example:

```css
@media (min-height: 700px) {
    .hero {
        min-height: 500px;
    }
}
```

The condition means:

```text
Viewport height >= 700px
        ↓
Apply the styles
```

This can be useful when a design needs to respond to available vertical space.

---

## `max-height`

The `max-height` media feature checks whether the viewport height is at most a specified value.

For example:

```css
@media (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The condition means:

```text
Viewport height <= 600px
        ↓
Apply the styles
```

This can be useful when the available vertical space becomes limited.

---

## Width and Height Together

Width and height conditions can be combined.

For example:

```css
@media (max-width: 768px) and (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The styles are applied when both conditions are satisfied.

Conceptually:

```text
Viewport
   ↓
Width <= 768px?
   ↓
 Yes
   ↓
Height <= 600px?
   ↓
 Yes
   ↓
Apply CSS
```

This allows responsive styles to consider both horizontal and vertical space.

---

## Orientation

The `orientation` media feature checks whether the viewport is in portrait or landscape orientation.

There are two commonly used values:

```text
portrait
landscape
```

For example:

```css
@media (orientation: portrait) {
    .container {
        width: 95%;
    }
}
```

This applies when the viewport is in portrait orientation.

For landscape:

```css
@media (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

The basic relationship is:

```text
Orientation
     ↓
┌─────────────┬─────────────┐
│  portrait   │  landscape  │
└─────────────┴─────────────┘
```

---

## Portrait Orientation

Portrait orientation means the viewport is taller than it is wide.

Conceptually:

```text
┌──────────┐
│          │
│          │
│          │
│          │
│          │
└──────────┘
```

A media query can target portrait orientation:

```css
@media (orientation: portrait) {
    .navigation {
        flex-direction: column;
    }
}
```

This can be useful when the available horizontal space is limited.

---

## Landscape Orientation

Landscape orientation means the viewport is wider than it is tall.

Conceptually:

```text
┌────────────────────┐
│                    │
│                    │
└────────────────────┘
```

A media query can target landscape orientation:

```css
@media (orientation: landscape) {
    .navigation {
        flex-direction: row;
    }
}
```

This can be useful when more horizontal space is available.

---

## Aspect Ratio

The `aspect-ratio` media feature describes the ratio between the viewport's width and height.

For example:

```css
@media (aspect-ratio: 16 / 9) {
    .video {
        width: 100%;
    }
}
```

An aspect ratio can be represented as:

```text
Width : Height
   ↓
16 : 9
```

The `aspect-ratio` feature can be useful when a design needs to respond to the shape of the viewport rather than only its width or height.

---

## Minimum and Maximum Aspect Ratio

Aspect ratio can also be used with range conditions.

For example:

```css
@media (min-aspect-ratio: 16 / 9) {
    .container {
        width: 90%;
    }
}
```

And:

```css
@media (max-aspect-ratio: 4 / 3) {
    .container {
        width: 95%;
    }
}
```

These conditions allow CSS to respond to different viewport proportions.

---

## Resolution

The `resolution` media feature describes the resolution of the output device.

For example:

```css
@media (min-resolution: 2dppx) {
    .logo {
        background-image: url("logo-high-resolution.png");
    }
}
```

This can be useful when different assets or styles are needed for displays with different pixel densities.

The `resolution` feature is more specialized than common responsive features such as `min-width` and `max-width`.

---

## Combining Different Media Features

Multiple media features can be combined using logical operators.

For example:

```css
@media screen and (min-width: 768px) and (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

The query contains:

```text
screen
   ↓
Media Type

min-width: 768px
   ↓
Width Condition

orientation: landscape
   ↓
Orientation Condition
```

All conditions must match for the styles to apply.

---

## Media Features and Responsive Design

Media features are one of the main tools used to make responsive layouts.

A responsive layout can respond to:

```text
Viewport Width
      ↓
Viewport Height
      ↓
Orientation
      ↓
Aspect Ratio
      ↓
Resolution
      ↓
Responsive CSS
```

For example:

```css
.container {
    width: 80%;
}

@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}

@media (orientation: landscape) {
    .container {
        max-width: 1000px;
    }
}
```

Different media features can therefore control different aspects of the design.

---

## Practical Example

Consider a card layout that needs to adapt to different viewport conditions.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

@media (max-width: 900px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout changes as the available width decreases.

```text
Large viewport

┌───────┬───────┬───────┐
│ Card  │ Card  │ Card  │
└───────┴───────┴───────┘


Medium viewport

┌───────┬───────┐
│ Card  │ Card  │
├───────┼───────┤
│ Card  │ Card  │
└───────┴───────┘


Small viewport

┌───────┐
│ Card  │
├───────┤
│ Card  │
├───────┤
│ Card  │
└───────┘
```

This demonstrates how media features can be used to create layouts that adapt to available space.

---

## Choosing the Right Media Feature

Different design problems require different media features.

```text
Need to respond to width?
        ↓
Use width / min-width / max-width

Need to respond to height?
        ↓
Use height / min-height / max-height

Need to respond to orientation?
        ↓
Use orientation

Need to respond to viewport proportions?
        ↓
Use aspect-ratio

Need to respond to display resolution?
        ↓
Use resolution
```

This makes it easier to choose an appropriate condition instead of using the same media feature for every situation.

---

## Common Mistake

Do not assume that `min-width` and `max-width` are the only media features available.

Responsive design can also respond to:

- Height
- Orientation
- Aspect ratio
- Resolution
- Other media characteristics

However, width-based conditions are commonly used because many layout changes are primarily caused by limited horizontal space.

---

> 💡 **Pro Tip:** Choose a media feature based on the actual design problem. If the layout breaks because there is not enough horizontal space, use a width-based condition. If the problem is vertical space or orientation, use the corresponding media feature.

---

> 💡 **Remember:** Media features describe characteristics of the viewing environment. Common examples include `width`, `height`, `min-width`, `max-width`, `orientation`, `aspect-ratio`, and `resolution`.

---

## Width and Height

The `width` and `height` media features allow CSS to respond to the dimensions of the viewport.

Viewport dimensions are important in responsive design because the available horizontal and vertical space can change significantly between devices and window sizes.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

Here, `max-width` checks the available viewport width.

The basic relationship is:

```text
Viewport
    ↓
┌──────────────────────────────┐
│                              │
│          Content             │
│                              │
└──────────────────────────────┘
      ←──── Width ────→

             ↑
             │
           Height
             │
             ↓
```

---

## Viewport Width

The viewport width represents the horizontal space available to the webpage.

For example:

```text
←────────────── Viewport Width ──────────────→

┌─────────────────────────────────────────────┐
│                                             │
│                 Webpage                     │
│                                             │
└─────────────────────────────────────────────┘
```

A media query can use the viewport width to change the layout.

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

When the viewport becomes `768px` or smaller, the styles inside the media query are applied.

---

## Exact `width`

The `width` media feature can check for an exact viewport width.

For example:

```css
@media (width: 600px) {
    .container {
        width: 100%;
    }
}
```

This condition checks whether the viewport width is exactly `600px`.

Conceptually:

```text
Viewport width
      ↓
Exactly 600px?
   ┌──┴──┐
  Yes    No
   ↓      ↓
Apply   Ignore
 CSS      CSS
```

Exact width conditions are less common in responsive layouts because viewport sizes can vary continuously.

Range-based features such as `min-width` and `max-width` are generally more useful.

---

## `min-width`

The `min-width` media feature checks whether the viewport width is at least a specified value.

For example:

```css
@media (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition means:

```text
Viewport width >= 768px
```

Therefore:

```text
600px
   ↓
Condition false

768px
   ↓
Condition true

900px
   ↓
Condition true
```

The styles apply when the viewport is `768px` or wider.

---

## `max-width`

The `max-width` media feature checks whether the viewport width is at most a specified value.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

The condition means:

```text
Viewport width <= 768px
```

Therefore:

```text
500px
   ↓
Condition true

768px
   ↓
Condition true

900px
   ↓
Condition false
```

The styles apply when the viewport is `768px` or narrower.

---

## Comparing `min-width` and `max-width`

The difference can be visualized as:

```text
min-width: 768px

0px ─────────── 767px │ 768px ───────────────→
                       ↑
                    Apply CSS
```

```text
max-width: 768px

0px ───────────────── 768px │ 769px ─────────→
                       ↑
                    Apply CSS
```

A simple rule to remember is:

```text
min-width
    ↓
768px and above

max-width
    ↓
768px and below
```

---

## Using Width Ranges

A design may need to respond only within a specific width range.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

The condition requires both rules to be satisfied.

```text
Viewport width
      ↓
At least 600px?
      ↓
     Yes
      ↓
At most 1000px?
      ↓
     Yes
      ↓
Apply CSS
```

The range can be visualized as:

```text
0px        600px                  1000px       →
│────────────│──────────────────────│────────────│
             ↑                      ↑
          Start                    End
```

Only the viewport widths inside the specified range match the condition.

---

## Width and Responsive Layouts

Width-based media queries are commonly used to change the structure of a layout.

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 900px) {
    .container {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

The layout changes as the viewport becomes narrower.

Large viewport:

```text
┌────────┬────────┬────────┐
│   1    │   2    │   3    │
└────────┴────────┴────────┘
```

Medium viewport:

```text
┌────────┬────────┐
│   1    │   2    │
├────────┼────────┤
│   3    │   4    │
└────────┴────────┘
```

Small viewport:

```text
┌────────┐
│   1    │
├────────┤
│   2    │
├────────┤
│   3    │
└────────┘
```

This is one of the most common uses of width-based media queries.

---

## Viewport Height

The viewport height represents the vertical space available to the webpage.

For example:

```text
        ↑
        │
      Height
        │
        ↓

┌──────────────────┐
│                  │
│                  │
│     Webpage      │
│                  │
│                  │
└──────────────────┘
   ←──── Width ───→
```

Height-based media queries can be useful when the amount of vertical space affects the layout.

---

## Exact `height`

The `height` media feature can check for an exact viewport height.

For example:

```css
@media (height: 800px) {
    .hero {
        min-height: 400px;
    }
}
```

This condition matches when the viewport height is exactly `800px`.

Conceptually:

```text
Viewport height
      ↓
Exactly 800px?
   ┌──┴──┐
  Yes    No
   ↓      ↓
Apply   Ignore
 CSS      CSS
```

As with exact width conditions, exact height queries are less common than minimum and maximum height conditions.

---

## `min-height`

The `min-height` media feature checks whether the viewport height is at least a specified value.

For example:

```css
@media (min-height: 700px) {
    .hero {
        min-height: 500px;
    }
}
```

The condition means:

```text
Viewport height >= 700px
```

Therefore, the styles apply when there is at least `700px` of vertical viewport space.

---

## `max-height`

The `max-height` media feature checks whether the viewport height is at most a specified value.

For example:

```css
@media (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The condition means:

```text
Viewport height <= 600px
```

The styles apply when the available vertical space is limited.

---

## Comparing `min-height` and `max-height`

The difference is similar to `min-width` and `max-width`.

```text
min-height
    ↓
At or above the specified height
```

```text
max-height
    ↓
At or below the specified height
```

For example:

```css
@media (min-height: 700px) {
    /* 700px and taller */
}
```

```css
@media (max-height: 600px) {
    /* 600px and shorter */
}
```

---

## Width and Height Together

Width and height can be used together in the same media query.

For example:

```css
@media (max-width: 768px) and (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The CSS is applied only when both conditions are satisfied.

Conceptually:

```text
Viewport
    ↓
Width <= 768px?
    ↓
   Yes
    ↓
Height <= 600px?
    ↓
   Yes
    ↓
Apply CSS
```

If either condition is false, the complete media query does not match.

---

## Practical Example: Limited Vertical Space

Consider a hero section with a large amount of padding.

```css
.hero {
    padding: 100px 20px;
}
```

On a viewport with limited height, this may consume too much vertical space.

A media query can reduce the padding:

```css
@media (max-height: 600px) {
    .hero {
        padding: 40px 20px;
    }
}
```

The result can be represented as:

```text
Normal height

┌──────────────────────────┐
│                          │
│       Large padding      │
│                          │
│        HERO CONTENT      │
│                          │
│       Large padding      │
│                          │
└──────────────────────────┘
```

With limited height:

```text
┌──────────────────────────┐
│      Smaller padding     │
│      HERO CONTENT        │
│      Smaller padding     │
└──────────────────────────┘
```

This prevents the hero section from consuming too much vertical space.

---

## Practical Example: Full-Screen Layout

A page may use a minimum height based on the viewport.

```css
.hero {
    min-height: 100vh;
}
```

A height-based media query can further adjust the design when the viewport becomes very short.

```css
@media (max-height: 600px) {
    .hero {
        min-height: auto;
        padding: 40px 20px;
    }
}
```

This gives the layout more flexibility when vertical space is limited.

---

## Width and Height With Flexbox

Width and height conditions can also work together with Flexbox.

For example:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-height: 100vh;
}

@media (max-height: 600px) {
    .container {
        justify-content: flex-start;
        padding-top: 30px;
    }
}
```

The normal layout centers the content vertically.

When the viewport becomes short, the layout moves the content toward the top.

Conceptually:

```text
Normal viewport
       ↓
┌───────────────┐
│               │
│               │
│    CONTENT    │
│               │
│               │
└───────────────┘
       ↓
    Centered


Short viewport
       ↓
┌───────────────┐
│    CONTENT    │
│               │
│               │
└───────────────┘
       ↓
    Top aligned
```

---

## Width and Height With Navigation

A navigation layout may also need to respond to both width and height.

For example:

```css
.navigation {
    padding: 20px;
}

@media (max-width: 600px) {
    .navigation {
        padding: 10px;
    }
}

@media (max-height: 500px) {
    .navigation {
        padding: 5px;
    }
}
```

Different conditions can therefore adjust the same component according to different constraints.

---

## Width vs Height

Width and height solve different responsive problems.

| Media Feature | Checks |
|---|---|
| `width` | Exact viewport width |
| `min-width` | Minimum viewport width |
| `max-width` | Maximum viewport width |
| `height` | Exact viewport height |
| `min-height` | Minimum viewport height |
| `max-height` | Maximum viewport height |

A useful mental model is:

```text
Horizontal space
       ↓
width
min-width
max-width

Vertical space
       ↓
height
min-height
max-height
```

---

## Choosing Width or Height

When deciding which feature to use, first identify what is causing the layout problem.

```text
Layout problem
      ↓
Is horizontal space the issue?
      ↓
     Yes
      ↓
Use width-based media features
```

Or:

```text
Layout problem
      ↓
Is vertical space the issue?
      ↓
     Yes
      ↓
Use height-based media features
```

This helps avoid adding unnecessary media queries.

---

## Common Mistake

Do not assume that every responsive change should be based on width.

Width is often the most important factor because layouts frequently become constrained horizontally, but some interfaces also depend heavily on vertical space.

For example:

```css
@media (max-height: 500px) {
    .hero {
        padding: 20px;
    }
}
```

This is useful when the problem is limited height rather than limited width.

---

## Another Common Mistake

Do not confuse CSS element dimensions with viewport media features.

For example:

```css
.container {
    width: 600px;
}
```

This changes the width of an element.

Whereas:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

checks the viewport width before applying the CSS rule.

Conceptually:

```text
Element property
    ↓
Changes an element

Media feature
    ↓
Checks the viewing environment
```

---

> 💡 **Pro Tip:** Start by identifying whether your responsive problem comes from limited horizontal space or limited vertical space. Then choose a width-based or height-based media feature accordingly.

---

> 💡 **Remember:** `width`, `min-width`, and `max-width` respond to viewport width, while `height`, `min-height`, and `max-height` respond to viewport height. Use the feature that matches the actual responsive problem.

---

## Combining Conditions

Media queries can combine multiple conditions to create more specific responsive rules.

Instead of checking only one condition, a media query can check several conditions at the same time.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 80%;
    }
}
```

This query checks two conditions:

```text
Viewport width
      ↓
At least 600px?
      ↓
     Yes
      ↓
At most 1000px?
      ↓
     Yes
      ↓
Apply the CSS
```

The styles are applied only when both conditions are satisfied.

---

## Why Combine Conditions?

A single media feature may not always be enough to describe the situation a layout needs to respond to.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

This checks only the viewport width.

Sometimes a design needs to consider additional conditions such as:

- Minimum width
- Maximum width
- Height
- Orientation
- Media type
- Aspect ratio

Combining conditions allows CSS to target a more specific situation.

---

## Using `and`

The `and` operator is used to combine media conditions.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

The two conditions are:

```text
(min-width: 600px)
        AND
(max-width: 1000px)
```

Both must be true.

Conceptually:

```text
Condition 1
    ↓
   TRUE
    ↓
Condition 2
    ↓
   TRUE
    ↓
Apply CSS
```

If either condition is false, the complete media query does not match.

---

## Combining `min-width` and `max-width`

One of the most common combinations is:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 80%;
    }
}
```

This creates a width range.

```text
0px          600px                 1000px          →
│──────────────│──────────────────────│──────────────│
               ↑                      ↑
            Minimum                Maximum
```

The styles apply between the specified limits.

Conceptually:

```text
600px ≤ viewport width ≤ 1000px
```

This is useful when a layout needs a specific design for medium-sized viewports.

---

## Combining Width and Height

Width and height conditions can also be combined.

For example:

```css
@media (max-width: 768px) and (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The browser checks:

```text
Width <= 768px?
       ↓
      Yes
       ↓
Height <= 600px?
       ↓
      Yes
       ↓
Apply CSS
```

The CSS is therefore applied only when both the width and height conditions match.

---

## Combining a Media Type and a Feature

A media type can also be combined with a media feature.

For example:

```css
@media screen and (max-width: 600px) {
    .navigation {
        flex-direction: column;
    }
}
```

The query contains:

```text
screen
   ↓
Media Type

and
   ↓
Combines Conditions

(max-width: 600px)
   ↓
Media Feature
```

The CSS is applied when the query matches the screen media type and the viewport width is `600px` or less.

---

## Combining Multiple Features

More than two conditions can be combined.

For example:

```css
@media screen and (min-width: 768px) and (max-width: 1200px) and (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

This query contains three conditions:

```text
screen
   ↓
Media Type

min-width: 768px
   ↓
Minimum Width

max-width: 1200px
   ↓
Maximum Width

orientation: landscape
   ↓
Orientation
```

All conditions must match.

The logical flow is:

```text
screen?
   ↓
 Yes
   ↓
Width >= 768px?
   ↓
 Yes
   ↓
Width <= 1200px?
   ↓
 Yes
   ↓
Landscape?
   ↓
 Yes
   ↓
Apply CSS
```

If any condition fails, the complete query does not match.

---

## Combining Conditions as a Range

Combining `min-width` and `max-width` is especially useful for creating responsive ranges.

For example:

```css
@media (min-width: 768px) and (max-width: 1199px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

The layout can be represented as:

```text
Small
0px ──────────────── 767px
                         ↓
                      Other CSS


Medium
768px ─────────────── 1199px
   ↓                       ↓
   └────── Apply CSS ──────┘


Large
1200px ─────────────────────→
             ↓
          Other CSS
```

This allows a specific layout to be used for a specific viewport range.

---

## Combining Conditions With Flexbox

Media query conditions can be used to control Flexbox layouts.

For example:

```css
.navigation {
    display: flex;
}

@media (max-width: 600px) and (orientation: portrait) {
    .navigation {
        flex-direction: column;
    }
}
```

The navigation changes to a column only when:

```text
Viewport <= 600px
        AND
Orientation = portrait
```

This allows the responsive behavior to be more specific than using width alone.

---

## Combining Conditions With Grid

Multiple conditions can also control CSS Grid layouts.

For example:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (min-width: 600px) and (max-width: 900px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 599px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout can therefore respond to different viewport ranges.

```text
Large
┌──────┬──────┬──────┐
│ Card │ Card │ Card │
└──────┴──────┴──────┘

Medium
┌──────┬──────┐
│ Card │ Card │
├──────┼──────┤
│ Card │ Card │
└──────┴──────┘

Small
┌──────┐
│ Card │
├──────┤
│ Card │
├──────┤
│ Card │
└──────┘
```

---

## Multiple Conditions Must Match

When conditions are combined with `and`, every condition must match.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 80%;
    }
}
```

Consider different viewport widths:

```text
500px
  ↓
min-width: 600px → FALSE
  ↓
Do not apply


800px
  ↓
min-width: 600px → TRUE
  ↓
max-width: 1000px → TRUE
  ↓
Apply CSS


1200px
  ↓
min-width: 600px → TRUE
  ↓
max-width: 1000px → FALSE
  ↓
Do not apply
```

This is the key behavior of combined `and` conditions.

---

## Combining Width, Height, and Orientation

A more specific query can combine width, height, and orientation.

For example:

```css
@media (max-width: 800px) and (max-height: 600px) and (orientation: landscape) {
    .hero {
        padding: 20px;
    }
}
```

The CSS applies only when all three conditions match:

```text
Width <= 800px
       ↓
Height <= 600px
       ↓
Landscape orientation
       ↓
Apply CSS
```

This can be useful for layouts that have very limited space in both dimensions.

---

## Combining Conditions With `print`

Conditions can also be combined with the `print` media type.

For example:

```css
@media print and (orientation: landscape) {
    .report {
        width: 100%;
    }
}
```

This targets printed output in landscape orientation.

The query can be understood as:

```text
Print?
   ↓
 Yes
   ↓
Landscape?
   ↓
 Yes
   ↓
Apply CSS
```

This can be useful for reports, tables, charts, and other content that may need a different print layout.

---

## Conditions and Specific Responsive Behavior

Combining conditions allows different parts of a design to respond to different situations.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 95%;
    }
}

@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}

@media (min-width: 1001px) {
    .container {
        width: 75%;
    }
}
```

The design can be divided into different ranges:

```text
Small
     ↓
0px ───────────── 599px

Medium
     ↓
600px ─────────── 1000px

Large
     ↓
1001px ─────────────────→
```

Each range can have its own responsive rules.

---

## Practical Example: Responsive Dashboard

Consider a dashboard with several cards.

```css
.dashboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

@media (min-width: 768px) and (max-width: 1200px) {
    .dashboard {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 767px) {
    .dashboard {
        grid-template-columns: 1fr;
    }
}
```

The dashboard changes according to viewport width.

```text
Large

┌────┬────┬────┬────┐
│  1 │  2 │  3 │  4 │
└────┴────┴────┴────┘


Medium

┌────┬────┐
│  1 │  2 │
├────┼────┤
│  3 │  4 │
└────┴────┘


Small

┌────┐
│  1 │
├────┤
│  2 │
├────┤
│  3 │
├────┤
│  4 │
└────┘
```

The media queries allow the same dashboard to adapt without changing the HTML structure.

---

## Practical Example: Short Mobile Landscape View

A mobile device can have a small width and limited height when rotated into landscape mode.

A media query can target that situation:

```css
@media (max-width: 800px) and (max-height: 500px) and (orientation: landscape) {
    .header {
        padding: 10px;
    }

    .hero {
        min-height: auto;
    }
}
```

The layout can therefore respond to the combination of:

```text
Small width
    +
Short height
    +
Landscape orientation
```

This is more precise than using only one condition.

---

## Combining Conditions vs Separate Media Queries

Sometimes several conditions can be combined into one query.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

Instead of writing separate rules for each condition:

```css
@media (min-width: 600px) {
    /* ... */
}

@media (max-width: 1000px) {
    /* ... */
}
```

The combined version is more precise when the CSS should apply only to the overlapping range.

Conceptually:

```text
min-width: 600px
       ↓
     Range
       ↓
max-width: 1000px
       ↓
Specific target area
```

---

## Common Mistake

A common mistake is assuming that:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    /* CSS */
}
```

means either condition can be true.

It does not.

With `and`, both conditions must be satisfied.

```text
Condition A = TRUE
Condition B = TRUE
        ↓
   Apply CSS
```

But:

```text
Condition A = TRUE
Condition B = FALSE
        ↓
 Do not apply CSS
```

---

## Another Common Mistake

Avoid combining conditions unnecessarily.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        color: red;
    }
}
```

If the color does not actually need to change based on this range, the condition may add unnecessary complexity.

Media queries should represent a real responsive requirement.

---

## Practical Decision Guide

When deciding whether to combine conditions, ask:

```text
Does one condition describe the situation?
        ↓
       Yes
        ↓
Use one media feature


Do multiple conditions need to be true?
        ↓
       Yes
        ↓
Combine them with "and"
```

For example:

```text
Need a style below 600px?
        ↓
max-width


Need a style between 600px and 1000px?
        ↓
min-width + max-width


Need a style only in portrait?
        ↓
orientation


Need a style for a small portrait screen?
        ↓
max-width + orientation
```

---

> 💡 **Pro Tip:** Combine conditions only when the design actually depends on multiple characteristics. This keeps your media queries easier to read, debug, and maintain.

---

> 💡 **Remember:** When media query conditions are combined with `and`, all conditions must match before the CSS rules are applied. Combining `min-width` and `max-width` is a common way to target a specific viewport range.

---

## Logical Operators

Logical operators allow multiple conditions to be combined in CSS media queries.

They make it possible to create more specific rules based on different characteristics of the viewing environment.

Common ways to combine media query conditions include:

- `and`
- comma-separated conditions, which act like `or`
- `not`

For example:

```css
@media screen and (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

Here, `and` connects the media type with the media feature.

---

## `and` Operator

The `and` operator requires all conditions in the media query to match.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 80%;
    }
}
```

Both conditions must be true:

```text
min-width: 600px
       AND
max-width: 1000px
       ↓
Apply CSS
```

If either condition is false, the CSS is not applied.

---

## Understanding `and`

Consider this query:

```css
@media (min-width: 600px) and (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

The browser checks:

```text
Width >= 600px?
      ↓
     Yes
      ↓
Landscape?
      ↓
     Yes
      ↓
Apply CSS
```

If the viewport is `700px` wide but in portrait orientation:

```text
Width >= 600px → TRUE
Orientation landscape → FALSE
                     ↓
              Do not apply CSS
```

Both conditions are required.

---

## Multiple `and` Conditions

More than two conditions can be connected with `and`.

For example:

```css
@media screen and (min-width: 768px) and (max-width: 1200px) and (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

This requires all conditions to match:

```text
screen
   AND
width >= 768px
   AND
width <= 1200px
   AND
landscape
   ↓
Apply CSS
```

This allows a very specific responsive situation to be targeted.

---

## Comma-Separated Conditions

A comma can be used to create alternatives in a media query.

For example:

```css
@media (max-width: 600px), (orientation: portrait) {
    .container {
        width: 100%;
    }
}
```

This means the CSS applies when **at least one** of the conditions matches.

Conceptually:

```text
Condition A
     OR
Condition B
     ↓
Apply CSS
```

So:

```text
(max-width: 600px), (orientation: portrait)
```

means:

```text
Viewport <= 600px
OR
Orientation = portrait
```

---

## `and` vs Comma

The difference between `and` and a comma is important.

Using `and`:

```css
@media (max-width: 600px) and (orientation: portrait) {
    /* CSS */
}
```

Means:

```text
Small width
    AND
Portrait
```

Both must match.

Using a comma:

```css
@media (max-width: 600px), (orientation: portrait) {
    /* CSS */
}
```

Means:

```text
Small width
    OR
Portrait
```

Either condition can match.

---

## Visual Comparison

### Using `and`

```text
Condition A ─────── TRUE
                     +
Condition B ─────── TRUE
                     ↓
                Apply CSS
```

If either condition is false:

```text
TRUE + FALSE
     ↓
Do not apply CSS
```

### Using a comma

```text
Condition A ─────── TRUE
                     OR
Condition B ─────── FALSE
                     ↓
                Apply CSS
```

Only one matching condition is enough.

---

## Multiple Comma-Separated Conditions

Several alternatives can be included.

For example:

```css
@media (max-width: 600px), (orientation: portrait), (max-height: 500px) {
    .container {
        padding: 10px;
    }
}
```

The CSS can apply when any of these conditions matches:

```text
Viewport <= 600px
       OR
Portrait orientation
       OR
Viewport height <= 500px
```

This provides multiple ways for the media query to match.

---

## `not` Operator

The `not` operator is used to negate a media query condition.

For example:

```css
@media not print {
    body {
        font-family: Arial, sans-serif;
    }
}
```

This targets media environments that do not match the `print` media type.

Conceptually:

```text
Print?
  ↓
Yes → Condition does not match
No  → Condition matches
```

---

## Using `not` With a Media Type

A simple example is:

```css
@media not print {
    .navigation {
        display: flex;
    }
}
```

The rule is intended for media that is not `print`.

This can be useful when styles should apply to other media types but not printed output.

---

## `not` and Media Features

The `not` operator can also be used to negate a media condition.

For example:

```css
@media not (orientation: portrait) {
    .container {
        width: 80%;
    }
}
```

The idea is to target environments that do not match the specified condition.

Conceptually:

```text
orientation = portrait?
        ↓
       NOT
        ↓
Apply when condition is not matched
```

---

## Important `not` Syntax

When using `not`, the placement of the operator matters.

For example:

```css
@media not print {
    /* CSS */
}
```

The `not` applies to the media query.

It should not be treated as a replacement for `and`.

Compare:

```css
@media not print {
    /* CSS */
}
```

with:

```css
@media screen and (max-width: 600px) {
    /* CSS */
}
```

These perform different logical operations.

---

## Combining `not` With Other Conditions

Media queries can also contain more complex combinations.

For example:

```css
@media not screen and (max-width: 600px) {
    .container {
        padding: 20px;
    }
}
```

When writing complex media queries, it is important to understand which part of the query is being negated.

For maintainability, prefer clear and simple conditions whenever possible.

---

## Logical Thinking

Media queries become easier to understand when they are viewed as logical expressions.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    /* CSS */
}
```

Can be represented as:

```text
A AND B
```

Where:

```text
A = width >= 600px
B = width <= 1000px
```

The result is:

```text
A = TRUE
B = TRUE
     ↓
  TRUE
```

---

## OR Logic

A comma-separated query can be represented as `OR`.

For example:

```css
@media (max-width: 600px), (orientation: portrait) {
    /* CSS */
}
```

Can be represented as:

```text
A OR B
```

Where:

```text
A = width <= 600px
B = orientation = portrait
```

The result is true when either condition matches.

---

## NOT Logic

The `not` operator can be represented as negation.

For example:

```css
@media not print {
    /* CSS */
}
```

Can be thought of as:

```text
NOT print
```

The query matches when the specified condition is not matched.

---

## Combining Logical Operators

Media queries can use different logical concepts together.

For example:

```css
@media screen and (min-width: 768px), print {
    .container {
        width: 80%;
    }
}
```

This creates two alternatives:

```text
Option 1:
screen
AND
width >= 768px

OR

Option 2:
print
```

This can be useful when the same style should apply under different circumstances.

---

## Practical Example

Consider a navigation menu that should be displayed as a column on small screens or portrait-oriented layouts.

```css
@media (max-width: 600px), (orientation: portrait) {
    .navigation {
        flex-direction: column;
    }
}
```

The layout changes when either condition matches.

```text
Small viewport?
      OR
Portrait?
      ↓
Yes
      ↓
Column navigation
```

---

## Practical Example With `and`

Suppose a layout should use a compact design only when the viewport is both narrow and short.

```css
@media (max-width: 800px) and (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

This requires:

```text
Width <= 800px
       AND
Height <= 600px
```

Both conditions must match.

---

## Practical Example With Multiple Alternatives

A design may need compact spacing in several situations.

```css
@media (max-width: 600px),
       (max-height: 500px),
       (orientation: portrait) {
    .container {
        padding: 10px;
    }
}
```

The CSS applies when at least one of the listed conditions matches.

This can be useful when different device characteristics can independently create a need for compact spacing.

---

## Practical Example With `not`

Suppose a navigation element should be displayed except when the document is being printed.

```css
@media not print {
    .navigation {
        display: flex;
    }
}
```

When viewing the page normally:

```text
Not print
   ↓
Navigation visible
```

When printing:

```text
Print
   ↓
Condition does not match
   ↓
Navigation rule is not applied
```

---

## Logical Operators Summary

| Operator | Meaning | Example |
|---|---|---|
| `and` | All conditions must match | `(min-width: 600px) and (max-width: 1000px)` |
| `,` | At least one condition can match | `(max-width: 600px), (orientation: portrait)` |
| `not` | Negates a media query | `not print` |

A simple way to remember them is:

```text
and
 ↓
ALL

comma
 ↓
ANY

not
 ↓
NEGATE
```

---

## Common Mistake

Do not confuse `and` with a comma.

This:

```css
@media (max-width: 600px) and (orientation: portrait) {
    /* CSS */
}
```

requires both conditions.

While this:

```css
@media (max-width: 600px), (orientation: portrait) {
    /* CSS */
}
```

allows either condition to match.

The difference can completely change when the CSS is applied.

---

## Another Common Mistake

Avoid making media queries unnecessarily complicated.

For example:

```css
@media screen and (min-width: 500px) and (max-width: 1000px) and (orientation: landscape) and (min-height: 500px) {
    /* CSS */
}
```

This may be valid, but if the design does not actually require all these conditions, it becomes harder to understand and maintain.

Prefer the simplest condition that correctly describes the responsive requirement.

---

## Choosing the Right Operator

Use this simple decision guide:

```text
Do ALL conditions need to match?
        ↓
       Yes
        ↓
      and


Can ANY condition match?
        ↓
       Yes
        ↓
Comma-separated conditions


Do you need to exclude a condition?
        ↓
       Yes
        ↓
       not
```

This makes logical media queries easier to construct.

---

> 💡 **Pro Tip:** Keep complex media queries readable. If a query contains many conditions, format it across multiple lines and make sure every condition represents a real responsive requirement.

---

> 💡 **Remember:** `and` requires all conditions to match, comma-separated media queries provide alternatives where any matching query can apply, and `not` negates a media query condition.

---

## Orientation

The `orientation` media feature allows CSS to respond to the orientation of the viewport.

It is useful when a layout needs to change depending on whether the available space is arranged vertically or horizontally.

CSS provides two orientation values:

- `portrait`
- `landscape`

For example:

```css
@media (orientation: portrait) {
    .container {
        width: 95%;
    }
}
```

The CSS is applied when the viewport is in portrait orientation.

---

## What Is Portrait Orientation?

A viewport is considered to be in `portrait` orientation when its height is greater than its width.

Conceptually:

```text
Height > Width

┌──────────┐
│          │
│          │
│          │
│          │
│          │
└──────────┘
```

A typical portrait layout has more vertical space than horizontal space.

For example:

```css
@media (orientation: portrait) {
    .navigation {
        flex-direction: column;
    }
}
```

This can make a navigation layout better suited to a vertically oriented viewport.

---

## What Is Landscape Orientation?

A viewport is considered to be in `landscape` orientation when its width is greater than its height.

Conceptually:

```text
Width > Height

┌────────────────────┐
│                    │
│                    │
└────────────────────┘
```

For example:

```css
@media (orientation: landscape) {
    .navigation {
        flex-direction: row;
    }
}
```

This can take advantage of the additional horizontal space available in landscape orientation.

---

## Portrait vs Landscape

The two orientation values can be visualized as:

```text
              Orientation
                   ↓
        ┌──────────┴──────────┐
        ↓                     ↓
    Portrait              Landscape
        ↓                     ↓
 Height > Width          Width > Height
        ↓                     ↓
 Vertical layout        Horizontal layout
```

A simple rule to remember is:

```text
portrait
    ↓
Taller than wide

landscape
    ↓
Wider than tall
```

---

## Basic Orientation Syntax

The basic syntax is:

```css
@media (orientation: portrait) {
    /* CSS rules */
}
```

Or:

```css
@media (orientation: landscape) {
    /* CSS rules */
}
```

The value determines which viewport orientation the styles target.

---

## Portrait Example

Consider a card layout.

```css
.cards {
    display: flex;
    gap: 20px;
}

@media (orientation: portrait) {
    .cards {
        flex-direction: column;
    }
}
```

In portrait orientation, the cards are arranged vertically.

```text
Portrait

┌─────────────┐
│    Card 1   │
├─────────────┤
│    Card 2   │
├─────────────┤
│    Card 3   │
└─────────────┘
```

This can make better use of limited horizontal space.

---

## Landscape Example

The same layout can use a horizontal arrangement in landscape orientation.

```css
.cards {
    display: flex;
    gap: 20px;
}

@media (orientation: landscape) {
    .cards {
        flex-direction: row;
    }
}
```

The cards can appear horizontally:

```text
Landscape

┌────────┐  ┌────────┐  ┌────────┐
│ Card 1 │  │ Card 2 │  │ Card 3 │
└────────┘  └────────┘  └────────┘
```

This takes advantage of the additional horizontal space.

---

## Using Orientation With Width

Orientation can be combined with width conditions.

For example:

```css
@media (max-width: 800px) and (orientation: portrait) {
    .container {
        width: 95%;
    }
}
```

Both conditions must match:

```text
Width <= 800px
       AND
Portrait orientation
       ↓
Apply CSS
```

This is more specific than checking orientation alone.

---

## Using Orientation With Height

Orientation can also be combined with height.

For example:

```css
@media (max-height: 500px) and (orientation: landscape) {
    .hero {
        padding: 20px;
    }
}
```

The CSS applies when:

```text
Height <= 500px
       AND
Landscape orientation
       ↓
Apply CSS
```

This can be useful for short landscape viewports where vertical space is limited.

---

## Orientation With Width and Height

Multiple conditions can be combined.

For example:

```css
@media (max-width: 800px) and (max-height: 500px) and (orientation: landscape) {
    .hero {
        min-height: auto;
        padding: 20px;
    }
}
```

The browser checks:

```text
Width <= 800px?
      ↓
     Yes
      ↓
Height <= 500px?
      ↓
     Yes
      ↓
Landscape?
      ↓
     Yes
      ↓
Apply CSS
```

This targets a very specific viewing situation.

---

## Orientation With Flexbox

Orientation media queries work especially well with Flexbox.

For example:

```css
.navigation {
    display: flex;
    flex-direction: row;
}

@media (orientation: portrait) {
    .navigation {
        flex-direction: column;
    }
}
```

The layout changes according to the viewport orientation.

```text
Landscape

┌──────┬──────┬──────┐
│ Home │ Blog │ About│
└──────┴──────┴──────┘
```

Portrait:

```text
┌──────────────┐
│     Home     │
├──────────────┤
│     Blog     │
├──────────────┤
│     About    │
└──────────────┘
```

---

## Orientation With CSS Grid

CSS Grid can also respond to orientation.

For example:

```css
.gallery {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

@media (orientation: portrait) {
    .gallery {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

The grid uses fewer columns in portrait orientation.

This can help prevent individual grid items from becoming too narrow.

---

## Practical Example: Image Gallery

Consider an image gallery.

```css
.gallery {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 15px;
}

@media (orientation: portrait) {
    .gallery {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (orientation: landscape) {
    .gallery {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

The gallery can adapt to the available space.

Portrait:

```text
┌───────┬───────┐
│ Image │ Image │
├───────┼───────┤
│ Image │ Image │
├───────┼───────┤
│ Image │ Image │
└───────┴───────┘
```

Landscape:

```text
┌──────┬──────┬──────┬──────┐
│ Img  │ Img  │ Img  │ Img  │
└──────┴──────┴──────┴──────┘
```

---

## Orientation and Mobile Devices

Orientation is particularly useful on mobile devices because users can change the orientation of the device.

For example:

```text
Phone held vertically

┌─────────┐
│         │
│         │
│         │
│         │
└─────────┘

    ↓ Rotate

Phone held horizontally

┌─────────────────┐
│                 │
│                 │
└─────────────────┘
```

The webpage can respond to the change without requiring a page reload.

For example:

```css
@media (orientation: portrait) {
    .sidebar {
        display: none;
    }
}

@media (orientation: landscape) {
    .sidebar {
        display: block;
    }
}
```

The available space can therefore determine which layout is more appropriate.

---

## Orientation Is Not the Same as Device Type

Do not assume that `portrait` always means mobile and `landscape` always means desktop.

Orientation describes the relationship between viewport width and height.

A desktop browser window can be narrow and tall.

A tablet can be in either orientation.

A phone can also be in either orientation.

Therefore:

```text
Orientation
    ↓
Describes viewport shape

Not:

Orientation
    ↓
Identifies a specific device
```

This distinction is important when writing responsive CSS.

---

## Orientation and Viewport Dimensions

Orientation can be understood using viewport dimensions.

```text
Portrait:

Height > Width
```

```text
Landscape:

Width > Height
```

For example:

```text
800 × 1200

Width  = 800px
Height = 1200px

1200 > 800
    ↓
Portrait
```

And:

```text
1200 × 800

Width  = 1200px
Height = 800px

1200 > 800
    ↓
Landscape
```

The orientation is therefore determined by the relationship between the viewport dimensions.

---

## Orientation With Responsive Breakpoints

Orientation can be combined with responsive breakpoints.

For example:

```css
@media (max-width: 768px) and (orientation: portrait) {
    .container {
        padding: 15px;
    }
}

@media (max-width: 768px) and (orientation: landscape) {
    .container {
        padding: 10px;
    }
}
```

The same viewport width can therefore have different styles depending on its orientation.

---

## Same Width, Different Orientation

Suppose a device has a viewport width that matches a responsive condition.

The layout may still behave differently depending on orientation.

For example:

```text
Portrait
┌──────────┐
│          │
│          │
│          │
│          │
└──────────┘
```

Versus:

```text
Landscape
┌────────────────────┐
│                    │
│                    │
└────────────────────┘
```

The available horizontal and vertical space changes, so the layout may need to change as well.

---

## Practical Example: Hero Section

A hero section may be tall in portrait mode:

```css
.hero {
    min-height: 80vh;
}

@media (orientation: landscape) {
    .hero {
        min-height: 60vh;
    }
}
```

The landscape version uses a smaller minimum height because the viewport may have limited vertical space.

Conceptually:

```text
Portrait
    ↓
More vertical space available
    ↓
Larger hero height


Landscape
    ↓
Less vertical space available
    ↓
Smaller hero height
```

---

## Practical Example: Navigation

A navigation menu can change based on orientation.

```css
.navigation {
    display: flex;
    gap: 20px;
}

@media (orientation: portrait) {
    .navigation {
        flex-direction: column;
        gap: 10px;
    }
}
```

In portrait orientation:

```text
Home
Blog
Projects
Contact
```

In landscape orientation:

```text
Home   Blog   Projects   Contact
```

The layout adapts to the available space.

---

## Practical Example: Dashboard

A dashboard can use different numbers of columns depending on orientation.

```css
.dashboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

@media (orientation: portrait) {
    .dashboard {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

Landscape:

```text
┌────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │
└────┴────┴────┴────┘
```

Portrait:

```text
┌────┬────┐
│ 1  │ 2  │
├────┼────┤
│ 3  │ 4  │
└────┴────┘
```

This can improve readability when horizontal space is reduced.

---

## Orientation and Content Priority

Orientation can also be used to prioritize content.

For example:

```css
@media (orientation: portrait) {
    .secondary-content {
        display: none;
    }
}
```

This can keep the primary content visible when horizontal space is limited.

However, hiding important content should be done carefully. Responsive design should preserve usability and access to important information.

---

## Common Mistake

Do not use orientation as a replacement for width-based responsive design in every situation.

For example:

```css
@media (orientation: portrait) {
    .container {
        width: 100%;
    }
}
```

This may work for a particular design, but orientation alone does not tell you how much actual space is available.

A better approach may sometimes be:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

Or a combination:

```css
@media (max-width: 600px) and (orientation: portrait) {
    .container {
        width: 100%;
    }
}
```

Choose the condition that matches the actual design requirement.

---

## Another Common Mistake

Do not assume that rotating a device always changes the physical device type or the HTML structure.

The document remains the same.

Only the available viewing conditions change.

```text
Same HTML
    ↓
Viewport changes
    ↓
Media query evaluated
    ↓
Different CSS can apply
```

This is one of the fundamental ideas behind responsive design.

---

## Orientation vs Width

Width and orientation provide different information.

```text
Width
    ↓
How much horizontal space is available?

Orientation
    ↓
Is the viewport taller or wider?
```

For example, two viewports can have different widths but the same orientation.

Therefore, orientation should be used when the shape of the viewport matters to the design.

---

## Quick Comparison

| Orientation | Relationship | Typical Layout |
|---|---|---|
| `portrait` | Height > Width | More vertical arrangement |
| `landscape` | Width > Height | More horizontal arrangement |

Example:

```css
@media (orientation: portrait) {
    /* Portrait styles */
}
```

```css
@media (orientation: landscape) {
    /* Landscape styles */
}
```

---

## Orientation With Multiple Conditions

Orientation can be combined with other media features.

For example:

```css
@media screen and (max-width: 800px) and (orientation: portrait) {
    .container {
        padding: 15px;
    }
}
```

This means:

```text
Screen
  AND
Width <= 800px
  AND
Portrait
  ↓
Apply CSS
```

This provides more control over the responsive behavior.

---

> 💡 **Pro Tip:** Use `orientation` when the difference between a tall viewport and a wide viewport actually affects your layout. Combine it with width or height conditions when you need more precise control.

---

> 💡 **Remember:** `orientation: portrait` targets viewports where the height is greater than the width, while `orientation: landscape` targets viewports where the width is greater than the height. Orientation describes the viewport shape, not a specific device type.

---

## Responsive Breakpoints

Responsive breakpoints are viewport sizes where the CSS layout changes to provide a better experience for the available space.

A breakpoint is usually defined with a media query.

For example:

```css
@media (max-width: 768px) {
    .container {
        padding: 15px;
    }
}
```

Here, `768px` acts as a breakpoint.

When the viewport becomes `768px` or smaller, the styles inside the media query can be applied.

---

## Why Are Breakpoints Used?

A responsive layout may work well at one viewport size but become difficult to use at another size.

For example:

```text
Large viewport

┌────────┬────────┬────────┐
│  Card  │  Card  │  Card  │
└────────┴────────┴────────┘
```

As the viewport becomes narrower, the cards may become too small:

```text
┌────┬────┬────┐
│ C1 │ C2 │ C3 │
└────┴────┴────┘
```

A breakpoint can change the layout:

```text
┌────────┐
│ Card 1 │
├────────┤
│ Card 2 │
├────────┤
│ Card 3 │
└────────┘
```

The breakpoint therefore allows the layout to adapt when the current design no longer provides enough space.

---

## What Is a Breakpoint?

A breakpoint is a condition at which responsive CSS changes the layout or presentation.

For example:

```css
@media (max-width: 600px) {
    .navigation {
        flex-direction: column;
    }
}
```

The breakpoint is:

```text
600px
```

The responsive behavior can be represented as:

```text
Viewport width
       ↓
Is width <= 600px?
       ↓
      Yes
       ↓
Apply mobile layout
```

---

## Breakpoints Are Not Device Names

A common misunderstanding is to think of breakpoints as fixed device categories.

For example:

```text
Mobile = 600px
Tablet = 768px
Desktop = 1024px
```

These values can be useful as rough references, but CSS should not assume that every device fits perfectly into these categories.

Devices have many different viewport sizes.

Browser windows can also be resized.

Therefore, responsive design should focus on the available space rather than specific device names.

```text
❌ Device-first thinking

Phone
Tablet
Laptop
Desktop


✅ Responsive thinking

Available viewport space
        ↓
Does the current layout still work?
        ↓
If not, change the layout
```

---

## Common Breakpoint Values

Some commonly used breakpoint values are:

```text
480px
576px
600px
768px
900px
992px
1024px
1200px
1400px
```

These values are not mandatory.

They are simply commonly encountered viewport widths.

The correct breakpoint depends on the design.

---

## Choosing a Breakpoint

A breakpoint should be introduced when the layout needs to change.

For example, imagine a navigation bar:

```text
Home | About | Services | Projects | Contact
```

At a sufficiently wide viewport, everything may fit comfortably.

As the viewport becomes narrower:

```text
Home | About | Services | Projects | Contact
```

the items may become crowded.

Instead of choosing a breakpoint simply because a device is called a tablet, choose a breakpoint where the navigation actually becomes difficult to use.

For example:

```css
@media (max-width: 850px) {
    .navigation {
        flex-direction: column;
    }
}
```

The `850px` value is based on the layout requirement.

---

## Content-Based Breakpoints

A content-based breakpoint is selected according to how the actual content behaves.

For example:

```text
Wide enough
    ↓
Navigation fits
    ↓
Keep horizontal layout


Too narrow
    ↓
Navigation becomes crowded
    ↓
Change layout
```

This is often better than blindly using a predefined device breakpoint.

---

## Example: Navigation Breakpoint

Start with a horizontal navigation:

```css
.navigation {
    display: flex;
    gap: 30px;
}
```

If the navigation becomes crowded at smaller widths:

```css
@media (max-width: 700px) {
    .navigation {
        flex-direction: column;
        gap: 10px;
    }
}
```

The breakpoint creates two layout ranges:

```text
700px and below
       ↓
Column navigation


Above 700px
       ↓
Row navigation
```

---

## Example: Card Layout

A card layout can use different numbers of columns at different widths.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

@media (max-width: 1000px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout changes progressively:

```text
Large

┌────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │
└────┴────┴────┴────┘


Medium

┌────┬────┐
│ 1  │ 2  │
├────┼────┤
│ 3  │ 4  │
└────┴────┘


Small

┌────┐
│ 1  │
├────┤
│ 2  │
├────┤
│ 3  │
├────┤
│ 4  │
└────┘
```

This is an example of using multiple responsive breakpoints.

---

## Breakpoints With `max-width`

A breakpoint can be used with `max-width`.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

The styles apply at or below the specified width.

```text
0px ─────────────────── 768px │ 769px ─────────→
                              ↑
                         Breakpoint
```

This approach is commonly used when progressively changing a desktop-oriented layout as the viewport becomes narrower.

---

## Breakpoints With `min-width`

Breakpoints can also be used with `min-width`.

For example:

```css
@media (min-width: 768px) {
    .container {
        max-width: 1100px;
        margin: auto;
    }
}
```

The styles apply at or above the specified width.

```text
0px ─────────── 767px │ 768px ─────────────────→
                       ↑
                  Breakpoint
```

This approach is commonly used in mobile-first responsive design.

---

## Multiple Breakpoints

A responsive layout can contain several breakpoints.

For example:

```css
.container {
    width: 100%;
}

@media (min-width: 600px) {
    .container {
        width: 90%;
    }
}

@media (min-width: 900px) {
    .container {
        width: 80%;
    }
}

@media (min-width: 1200px) {
    .container {
        width: 70%;
    }
}
```

The layout becomes progressively wider as more horizontal space becomes available.

Conceptually:

```text
0px ─────── 599px
   ↓
100% width


600px ───── 899px
   ↓
90% width


900px ───── 1199px
   ↓
80% width


1200px ───────────→
   ↓
70% width
```

---

## Breakpoints and Layout Changes

A breakpoint does not have to change only width.

It can change many properties.

For example:

```css
@media (max-width: 768px) {
    .navigation {
        flex-direction: column;
    }

    .cards {
        grid-template-columns: 1fr;
    }

    .hero {
        padding: 40px 20px;
    }

    .title {
        font-size: 2rem;
    }
}
```

A single breakpoint can therefore coordinate several responsive changes.

```text
Breakpoint
    ↓
┌─────────────────────────┐
│ Navigation changes      │
│ Grid changes             │
│ Hero spacing changes     │
│ Typography changes       │
└─────────────────────────┘
```

---

## Breakpoints Should Represent Layout Changes

A breakpoint should have a reason.

For example:

```text
Problem:
Cards become too narrow.

Solution:
Reduce the number of columns.

Breakpoint:
Choose the width where the cards stop being comfortable.
```

Another example:

```text
Problem:
Navigation items no longer fit.

Solution:
Change navigation layout.

Breakpoint:
Choose the width where the navigation becomes crowded.
```

The breakpoint should therefore be connected to an actual layout requirement.

---

## Too Many Breakpoints

Using too many breakpoints can make CSS difficult to maintain.

For example:

```css
@media (max-width: 1400px) { ... }
@media (max-width: 1300px) { ... }
@media (max-width: 1200px) { ... }
@media (max-width: 1100px) { ... }
@media (max-width: 1000px) { ... }
@media (max-width: 900px) { ... }
@media (max-width: 800px) { ... }
@media (max-width: 700px) { ... }
@media (max-width: 600px) { ... }
```

This may create unnecessary complexity if the design does not actually require so many layout changes.

Prefer a smaller number of meaningful breakpoints.

---

## Too Few Breakpoints

The opposite problem is using too few breakpoints.

For example:

```css
@media (max-width: 600px) {
    /* Mobile */
}
```

A layout may work at `1200px` and `600px` but become awkward at `900px`.

If the design needs a change around `900px`, an additional breakpoint may be appropriate.

The goal is not:

```text
Fewest possible breakpoints
```

The goal is:

```text
Fewest necessary breakpoints
```

---

## Breakpoints and Fluid Design

Not every responsive change requires a breakpoint.

Modern CSS can often create flexible layouts without many media queries.

For example:

```css
.container {
    width: min(90%, 1200px);
    margin-inline: auto;
}
```

The container can adapt continuously as the viewport changes.

Similarly, Grid can use:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}
```

This allows the grid to adapt based on available space.

Therefore:

```text
Flexible CSS
    +
Necessary breakpoints
    ↓
More adaptable responsive layout
```

---

## Breakpoints and Flexbox

Flexbox can often reduce the number of breakpoints required.

For example:

```css
.navigation {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

Instead of manually creating many breakpoints, Flexbox can allow items to wrap when there is not enough space.

However, a breakpoint may still be useful when the design needs a completely different arrangement.

For example:

```css
@media (max-width: 700px) {
    .navigation {
        flex-direction: column;
    }
}
```

---

## Breakpoints and Grid

CSS Grid also provides flexible layout tools.

For example:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}
```

The grid can automatically adjust the number of columns according to the available space.

This may eliminate the need for several explicit breakpoints.

However, if the design requires a specific layout at a certain range, a breakpoint can still be used.

---

## Breakpoints and Typography

Breakpoints can also change typography.

For example:

```css
.title {
    font-size: 3rem;
}

@media (max-width: 768px) {
    .title {
        font-size: 2rem;
    }
}

@media (max-width: 480px) {
    .title {
        font-size: 1.5rem;
    }
}
```

The typography becomes smaller as the available width decreases.

However, responsive typography can also be handled with fluid CSS functions such as `clamp()`.

For example:

```css
.title {
    font-size: clamp(1.5rem, 5vw, 3rem);
}
```

This allows the font size to scale continuously within a defined range.

---

## Breakpoints and Spacing

Spacing can also change at breakpoints.

For example:

```css
.section {
    padding: 80px 40px;
}

@media (max-width: 768px) {
    .section {
        padding: 50px 20px;
    }
}
```

Large screens can use more spacing while smaller screens use more compact spacing.

---

## Breakpoints and Images

Images may also need responsive adjustments.

For example:

```css
.image {
    width: 500px;
}

@media (max-width: 600px) {
    .image {
        width: 100%;
    }
}
```

The image becomes flexible on smaller viewports.

A better general approach is often:

```css
.image {
    max-width: 100%;
    height: auto;
}
```

This allows the image to scale within its container without necessarily requiring a breakpoint.

---

## Breakpoint Strategy

A simple breakpoint strategy can look like:

```text
Start with flexible layout
        ↓
Test at different viewport widths
        ↓
Find where the layout becomes difficult to use
        ↓
Add a breakpoint
        ↓
Change the layout
        ↓
Test again
```

This is better than choosing breakpoints without looking at the actual design.

---

## Testing Breakpoints

Breakpoints should be tested at several viewport sizes.

For example:

```text
320px
375px
480px
600px
768px
900px
1024px
1200px
1440px
```

The exact test sizes depend on the project.

The important thing is to check whether the layout remains usable between breakpoints as well as at the breakpoint itself.

---

## Breakpoint Boundaries

Suppose you have:

```css
@media (max-width: 768px) {
    /* Small layout */
}

@media (min-width: 769px) {
    /* Large layout */
}
```

The ranges are:

```text
0px ───────────── 768px
       Small


769px ─────────────────→
       Large
```

In many designs, a mobile-first approach can make breakpoint relationships easier to manage:

```css
/* Base styles */

@media (min-width: 768px) {
    /* Larger layout */
}
```

The exact strategy depends on how the CSS is structured.

---

## Breakpoints Are About Content

The most important principle is:

```text
Do not ask:

"What breakpoint should I use for this device?"

Ask:

"At what width does my layout need to change?"
```

For example:

```text
Navigation fits
       ↓
Keep current layout

Navigation becomes crowded
       ↓
Add breakpoint

Cards become too narrow
       ↓
Reduce columns

Text becomes difficult to read
       ↓
Adjust typography or layout
```

This creates breakpoints based on the actual design.

---

## Practical Example: Complete Responsive Layout

```css
.container {
    width: 100%;
    margin-inline: auto;
    padding: 20px;
}

.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

@media (max-width: 1000px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .container {
        padding: 15px;
    }

    .cards {
        grid-template-columns: 1fr;
    }
}
```

The responsive behavior is:

```text
Large viewport
       ↓
4 columns


Medium viewport
       ↓
2 columns


Small viewport
       ↓
1 column
```

This is a simple and practical breakpoint strategy.

---

## Common Mistake

Do not create breakpoints only because a device specification says a certain width is common.

For example:

```css
@media (max-width: 768px) {
    /* Everything mobile */
}
```

This does not automatically guarantee a good mobile layout.

A better approach is to test the actual content and determine where the layout needs to change.

---

## Another Common Mistake

Do not assume that a breakpoint fixes every responsive problem.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

If the problem is caused by a fixed-width child element, changing the container width may not solve it.

Responsive design often requires a combination of:

- Flexible widths
- Flexbox
- Grid
- Responsive images
- Flexible typography
- Appropriate spacing
- Media queries

Breakpoints are only one part of responsive design.

---

## Best Practice

A good breakpoint strategy usually follows these principles:

```text
1. Start with a flexible layout.
2. Test the actual content.
3. Find where the layout starts to break.
4. Add a meaningful breakpoint.
5. Change only what needs to change.
6. Test again.
7. Avoid unnecessary breakpoints.
```

This keeps responsive CSS easier to maintain.

---

> 💡 **Pro Tip:** Choose breakpoints based on where your layout needs to change, not simply because a particular device has a certain screen size.

---

> 💡 **Remember:** A responsive breakpoint is a point where your CSS changes to accommodate the available viewport space. There is no single set of breakpoints that is correct for every website. Use flexible CSS where possible and add breakpoints when the design actually needs them.

---

## Mobile-First Approach

The mobile-first approach is a responsive design strategy where the base CSS is written for smaller screens first.

Larger-screen layouts are then added using media queries with `min-width`.

The basic idea is:

```text
Small screen
    ↓
Base CSS
    ↓
Larger screen
    ↓
Add styles with media queries
```

For example:

```css
.container {
    width: 100%;
    padding: 15px;
}

@media (min-width: 768px) {
    .container {
        width: 90%;
        padding: 30px;
    }
}
```

The base styles work on smaller screens, while the media query adds or changes styles when the viewport becomes wider.

---

## Why Is It Called Mobile-First?

It is called mobile-first because the development process starts with the smaller-screen experience.

Instead of creating a large desktop layout first and then trying to reduce it, the layout begins with the constraints of smaller screens.

```text
Mobile
   ↓
Base design
   ↓
Tablet
   ↓
Add enhancements
   ↓
Desktop
   ↓
Add more enhancements
```

This creates a progressive approach to responsive design.

---

## Basic Mobile-First Structure

A typical mobile-first stylesheet looks like this:

```css
/* Base styles - smaller screens */

.container {
    width: 100%;
}

.cards {
    display: grid;
    grid-template-columns: 1fr;
}

/* Larger screens */

@media (min-width: 768px) {
    .container {
        width: 90%;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Even larger screens */

@media (min-width: 1200px) {
    .container {
        width: 80%;
    }

    .cards {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

The base CSS establishes the smallest layout.

The media queries progressively enhance it.

---

## Mobile-First Uses `min-width`

Mobile-first designs commonly use `min-width`.

For example:

```css
.card {
    width: 100%;
}

@media (min-width: 768px) {
    .card {
        width: 50%;
    }
}

@media (min-width: 1200px) {
    .card {
        width: 25%;
    }
}
```

The logic is:

```text
Base
 ↓
All viewport sizes

min-width: 768px
 ↓
768px and wider

min-width: 1200px
 ↓
1200px and wider
```

As the viewport gets wider, additional styles become active.

---

## Mobile-First vs Desktop-First

The two approaches work in opposite directions.

### Mobile-First

```text
Small
  ↓
Base styles
  ↓
Larger
  ↓
Add enhancements
```

Usually:

```css
/* Base */
```

followed by:

```css
@media (min-width: 768px) {
    /* Larger layout */
}
```

### Desktop-First

```text
Large
  ↓
Base styles
  ↓
Smaller
  ↓
Override styles
```

Usually:

```css
/* Base */
```

followed by:

```css
@media (max-width: 768px) {
    /* Smaller layout */
}
```

The important difference is the direction in which the layout is developed.

---

## Example Comparison

### Mobile-First

```css
.navigation {
    display: flex;
    flex-direction: column;
}

@media (min-width: 768px) {
    .navigation {
        flex-direction: row;
    }
}
```

The default layout is vertical.

On larger screens, it becomes horizontal.

```text
Small
┌──────────────┐
│ Home         │
├──────────────┤
│ About        │
├──────────────┤
│ Projects     │
└──────────────┘

        ↓

Large
┌──────┬───────┬──────────┐
│ Home │ About │ Projects │
└──────┴───────┴──────────┘
```

---

### Desktop-First

The same layout can be written in the opposite direction:

```css
.navigation {
    display: flex;
    flex-direction: row;
}

@media (max-width: 767px) {
    .navigation {
        flex-direction: column;
    }
}
```

The default layout is horizontal.

The smaller-screen media query changes it to vertical.

---

## Why Use Mobile-First?

Mobile-first design can make responsive CSS easier to structure.

The smaller layout is often simpler.

For example:

```css
.cards {
    display: grid;
    grid-template-columns: 1fr;
}
```

Then larger screens can progressively add columns:

```css
@media (min-width: 768px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 1200px) {
    .cards {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

The layout grows as more space becomes available.

```text
Small
   ↓
1 column

Medium
   ↓
2 columns

Large
   ↓
4 columns
```

---

## Mobile-First and Progressive Enhancement

Mobile-first development follows a progressive enhancement idea.

Start with a simple layout:

```text
Small viewport
     ↓
Basic usable experience
```

Then add capabilities as more space becomes available:

```text
Small
 ↓
Basic layout

Medium
 ↓
Additional columns
Additional spacing

Large
 ↓
More columns
Larger spacing
Additional layout features
```

The design therefore grows with the available space.

---

## Mobile-First and Content

A mobile-first approach encourages developers to prioritize important content.

On a small screen, there is limited space.

Therefore, the design should first ensure that the essential information is accessible.

For example:

```text
Small screen

┌──────────────┐
│ Logo         │
│ Navigation   │
│ Main Content │
│ Main Action  │
└──────────────┘
```

Larger screens can then provide additional space for secondary content:

```text
Large screen

┌────────┬──────────────────────┐
│ Side   │ Main Content         │
│ bar    │                      │
│        │ Additional Content   │
└────────┴──────────────────────┘
```

---

## Mobile-First Navigation

A navigation menu can start as a compact vertical layout.

```css
.navigation {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
```

On larger screens:

```css
@media (min-width: 768px) {
    .navigation {
        flex-direction: row;
        gap: 20px;
    }
}
```

The navigation progressively uses the additional horizontal space.

---

## Mobile-First Cards

Cards are another common example.

Start with one column:

```css
.cards {
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
}
```

Add columns for larger viewports:

```css
@media (min-width: 600px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 1000px) {
    .cards {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

The result is:

```text
Small

┌───────────┐
│   Card    │
├───────────┤
│   Card    │
├───────────┤
│   Card    │
└───────────┘
```

```text
Medium

┌───────────┬───────────┐
│   Card    │   Card    │
├───────────┼───────────┤
│   Card    │   Card    │
└───────────┴───────────┘
```

```text
Large

┌──────┬──────┬──────┬──────┐
│ Card │ Card │ Card │ Card │
└──────┴──────┴──────┴──────┘
```

---

## Mobile-First Typography

Typography can also start with smaller values.

For example:

```css
h1 {
    font-size: 2rem;
}

@media (min-width: 768px) {
    h1 {
        font-size: 2.5rem;
    }
}

@media (min-width: 1200px) {
    h1 {
        font-size: 3rem;
    }
}
```

The heading becomes larger as more space becomes available.

```text
Small
 ↓
2rem

Medium
 ↓
2.5rem

Large
 ↓
3rem
```

For many situations, fluid sizing with `clamp()` can also reduce the need for multiple typography breakpoints.

---

## Mobile-First Spacing

Spacing can follow the same pattern.

```css
.section {
    padding: 40px 15px;
}

@media (min-width: 768px) {
    .section {
        padding: 60px 30px;
    }
}

@media (min-width: 1200px) {
    .section {
        padding: 80px 40px;
    }
}
```

The layout starts compact and progressively gains space.

---

## Mobile-First Images

Images should generally be flexible by default.

For example:

```css
.image {
    max-width: 100%;
    height: auto;
}
```

Additional styles can be introduced at larger widths when necessary:

```css
@media (min-width: 768px) {
    .image {
        max-width: 600px;
    }
}
```

The image remains responsive while larger screens can use a larger maximum size.

---

## Mobile-First With Flexbox

Flexbox works naturally with mobile-first design.

For example:

```css
.container {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

@media (min-width: 768px) {
    .container {
        flex-direction: row;
    }
}
```

The layout starts vertically:

```text
Small

┌───────────┐
│ Content 1 │
├───────────┤
│ Content 2 │
└───────────┘
```

Then becomes horizontal:

```text
Large

┌───────────┬───────────┐
│ Content 1 │ Content 2 │
└───────────┴───────────┘
```

---

## Mobile-First With Grid

Grid also works well with the mobile-first approach.

```css
.layout {
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
}

@media (min-width: 768px) {
    .layout {
        grid-template-columns: 2fr 1fr;
    }
}
```

The mobile layout uses one column.

The larger layout uses two columns.

```text
Small

┌───────────────┐
│ Main Content  │
├───────────────┤
│ Sidebar       │
└───────────────┘
```

```text
Large

┌────────────────────┬──────────┐
│ Main Content       │ Sidebar  │
└────────────────────┴──────────┘
```

---

## Mobile-First CSS Order

A mobile-first stylesheet can be organized like this:

```css
/* Base styles */

body {
    margin: 0;
}

.container {
    width: 100%;
    padding: 15px;
}

.cards {
    display: grid;
    grid-template-columns: 1fr;
}

/* Medium screens */

@media (min-width: 768px) {
    .container {
        width: 90%;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Large screens */

@media (min-width: 1200px) {
    .container {
        width: 80%;
    }

    .cards {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

The structure is easy to follow:

```text
Base
 ↓
768px+
 ↓
1200px+
```

---

## Mobile-First and CSS Cascade

Mobile-first CSS works with the normal CSS cascade.

The base rules are written first:

```css
.cards {
    grid-template-columns: 1fr;
}
```

A later media query can override the property:

```css
@media (min-width: 768px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

At larger widths, the media query's declaration applies because the media condition matches and the rule appears later.

---

## Mobile-First Does Not Mean Mobile-Only

The mobile-first approach does not mean the website should be designed only for mobile devices.

It means the smallest practical layout is established first.

Then larger layouts are added.

```text
Mobile
   ↓
Tablet
   ↓
Laptop
   ↓
Desktop
   ↓
Large displays
```

The same HTML and CSS can support all of these viewport sizes.

---

## Mobile-First and Accessibility

A mobile-first approach can also encourage developers to prioritize essential content.

Important content and actions should remain usable at smaller sizes.

For example:

```text
Primary action
     ↓
Always accessible

Secondary information
     ↓
Can use additional space when available
```

However, responsive design alone does not guarantee accessibility.

Accessibility also requires appropriate:

- Contrast
- Font sizes
- Keyboard navigation
- Focus styles
- Semantic HTML
- Alternative text
- Touch target sizes

Responsive design is one part of creating an accessible interface.

---

## Mobile-First and Performance

Mobile-first development can encourage attention to the constraints of smaller devices and networks.

For example, the base design should avoid unnecessary visual complexity.

However, CSS media queries alone do not automatically make a website faster.

Performance also depends on:

- Image sizes
- JavaScript
- Fonts
- Network requests
- CSS size
- Caching
- Rendering complexity

Therefore:

```text
Mobile-first
    ≠
Automatically fast
```

It is a design strategy, not a complete performance strategy.

---

## When Mobile-First Works Well

Mobile-first is particularly useful when:

- The majority of users are on smaller screens.
- The layout needs to progressively expand.
- The mobile layout is simpler than the desktop layout.
- The project is being designed responsively from the beginning.
- The CSS can naturally use `min-width` enhancements.

For example:

```text
Small
 ↓
Simple layout

Medium
 ↓
More columns

Large
 ↓
More space and additional layout features
```

---

## When the Approach May Need More Planning

Some applications are primarily designed around large-screen interfaces.

For example, a complex desktop dashboard may contain many controls and data tables.

In such cases, the mobile experience may require significant redesign rather than simply shrinking the desktop layout.

The important principle is:

```text
Do not simply shrink the desktop layout.

Design an appropriate experience for each available space.
```

---

## Mobile-First vs Shrinking Desktop

A common mistake is to create a desktop layout first and then simply reduce everything.

For example:

```text
Desktop layout
      ↓
Make everything smaller
      ↓
Mobile
```

This can produce:

```text
Tiny text
Crowded controls
Horizontal scrolling
Difficult navigation
```

Mobile-first encourages a different process:

```text
Small layout
      ↓
Prioritize content
      ↓
Create usable structure
      ↓
Expand for larger screens
```

---

## Practical Complete Example

```css
/* Base: small screens */

.container {
    width: 100%;
    padding: 15px;
}

.navigation {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.cards {
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
}

.title {
    font-size: 2rem;
}

/* Medium screens */

@media (min-width: 768px) {
    .container {
        width: 90%;
        padding: 30px;
    }

    .navigation {
        flex-direction: row;
        gap: 20px;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }

    .title {
        font-size: 2.5rem;
    }
}

/* Large screens */

@media (min-width: 1200px) {
    .container {
        width: 80%;
        padding: 40px;
    }

    .cards {
        grid-template-columns: repeat(4, 1fr);
    }

    .title {
        font-size: 3rem;
    }
}
```

The complete progression is:

```text
SMALL
 ↓
1 column
Vertical navigation
Compact spacing
Smaller heading
 ↓
MEDIUM
 ↓
2 columns
Horizontal navigation
More spacing
Larger heading
 ↓
LARGE
 ↓
4 columns
More available space
Larger heading
```

---

## Mobile-First Development Workflow

A practical workflow is:

```text
1. Start with the smallest layout.
        ↓
2. Make the essential content usable.
        ↓
3. Use flexible widths and layouts.
        ↓
4. Test the layout at larger widths.
        ↓
5. Find where the layout can improve.
        ↓
6. Add a min-width media query.
        ↓
7. Test again.
        ↓
8. Repeat only when necessary.
```

This produces a progressive responsive layout.

---

## Common Mistake

Do not automatically add a media query for every device size.

For example:

```css
@media (min-width: 375px) { ... }
@media (min-width: 480px) { ... }
@media (min-width: 576px) { ... }
@media (min-width: 768px) { ... }
@media (min-width: 820px) { ... }
@media (min-width: 900px) { ... }
@media (min-width: 1024px) { ... }
@media (min-width: 1200px) { ... }
```

This may be unnecessary.

Instead:

```text
Flexible base CSS
        +
Meaningful breakpoints
        ↓
Simpler responsive design
```

---

## Another Common Mistake

Do not write the mobile-first base styles and then unnecessarily override every property at larger sizes.

For example:

```css
.container {
    width: 100%;
    padding: 15px;
    margin: 0;
}

@media (min-width: 768px) {
    .container {
        width: 90%;
        padding: 15px;
        margin: 0;
    }
}
```

If `padding` and `margin` do not need to change, they do not need to be repeated.

A cleaner version is:

```css
.container {
    width: 100%;
    padding: 15px;
    margin: 0;
}

@media (min-width: 768px) {
    .container {
        width: 90%;
    }
}
```

Only change what actually needs to change.

---

## Best Practices

A good mobile-first approach generally follows these principles:

```text
1. Write base styles for smaller screens.
2. Use flexible layouts.
3. Use min-width for larger-screen enhancements.
4. Add breakpoints based on layout needs.
5. Avoid unnecessary overrides.
6. Keep important content accessible.
7. Test between breakpoints.
8. Use Flexbox and Grid where appropriate.
9. Use fluid CSS where possible.
10. Keep the responsive CSS maintainable.
```

---

> 💡 **Pro Tip:** Think of mobile-first CSS as building upward. Start with the simplest usable layout, then use `min-width` media queries to progressively enhance the design as more viewport space becomes available.

---

> 💡 **Remember:** In a mobile-first approach, the base CSS targets the smaller layout and larger layouts are added progressively using `min-width` media queries. Mobile-first is not about targeting a specific device; it is about starting with limited space and enhancing the layout as more space becomes available.

---

## Desktop-First Approach

The desktop-first approach is a responsive design strategy where the base CSS is written for larger screens first.

Smaller-screen layouts are then created using media queries with `max-width`.

The basic idea is:

```text
Large screen
    ↓
Base CSS
    ↓
Smaller screen
    ↓
Adjust styles with media queries
```

For example:

```css
.container {
    width: 80%;
    padding: 40px;
}

@media (max-width: 768px) {
    .container {
        width: 100%;
        padding: 20px;
    }
}
```

The base styles create the larger-screen layout, while the media query changes the layout when the viewport becomes narrower.

---

## Why Is It Called Desktop-First?

It is called desktop-first because development begins with the larger-screen experience.

The desktop layout is established first, and then adjustments are made for smaller screens.

```text
Desktop
   ↓
Base design
   ↓
Tablet
   ↓
Adjust layout
   ↓
Mobile
   ↓
Adjust further
```

This is the opposite direction of the mobile-first approach.

---

## Basic Desktop-First Structure

A typical desktop-first stylesheet can look like this:

```css
/* Base styles - larger screens */

.container {
    width: 80%;
}

.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}

/* Smaller screens */

@media (max-width: 1000px) {
    .container {
        width: 90%;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Small screens */

@media (max-width: 600px) {
    .container {
        width: 100%;
    }

    .cards {
        grid-template-columns: 1fr;
    }
}
```

The base CSS establishes the large layout.

The media queries progressively simplify it as the viewport becomes narrower.

---

## Desktop-First Uses `max-width`

Desktop-first designs commonly use `max-width`.

For example:

```css
.card {
    width: 25%;
}

@media (max-width: 1000px) {
    .card {
        width: 50%;
    }
}

@media (max-width: 600px) {
    .card {
        width: 100%;
    }
}
```

The logic is:

```text
Base
 ↓
Large viewport

max-width: 1000px
 ↓
1000px and below

max-width: 600px
 ↓
600px and below
```

As the viewport becomes narrower, additional responsive styles are applied.

---

## Desktop-First vs Mobile-First

The two approaches work in opposite directions.

### Desktop-First

```text
Large
  ↓
Base styles
  ↓
Smaller
  ↓
Override styles
```

Usually:

```css
/* Base desktop styles */
```

followed by:

```css
@media (max-width: 768px) {
    /* Smaller layout */
}
```

### Mobile-First

```text
Small
  ↓
Base styles
  ↓
Larger
  ↓
Add enhancements
```

Usually:

```css
/* Base mobile styles */
```

followed by:

```css
@media (min-width: 768px) {
    /* Larger layout */
}
```

The main difference is the direction in which the responsive layout is developed.

---

## Example Comparison

### Desktop-First

```css
.navigation {
    display: flex;
    flex-direction: row;
    gap: 20px;
}

@media (max-width: 768px) {
    .navigation {
        flex-direction: column;
        gap: 10px;
    }
}
```

The default layout is horizontal.

On smaller screens, it becomes vertical.

```text
Large

┌──────┬───────┬──────────┐
│ Home │ About │ Projects │
└──────┴───────┴──────────┘
```

Smaller:

```text
┌──────────────┐
│ Home         │
├──────────────┤
│ About        │
├──────────────┤
│ Projects     │
└──────────────┘
```

---

## Desktop-First Cards

A desktop layout can begin with several columns.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}
```

Then reduce the number of columns as the viewport becomes narrower:

```css
@media (max-width: 1000px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout becomes:

```text
Large

┌────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │
└────┴────┴────┴────┘
```

Medium:

```text
┌────┬────┐
│ 1  │ 2  │
├────┼────┤
│ 3  │ 4  │
└────┴────┘
```

Small:

```text
┌────┐
│ 1  │
├────┤
│ 2  │
├────┤
│ 3  │
├────┤
│ 4  │
└────┘
```

---

## Desktop-First Navigation

Desktop navigation often starts horizontally:

```css
.navigation {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

A smaller-screen media query can change the layout:

```css
@media (max-width: 700px) {
    .navigation {
        flex-direction: column;
        align-items: flex-start;
    }
}
```

The navigation adapts as horizontal space decreases.

---

## Desktop-First Layout With Sidebar

A desktop layout may start with two columns:

```css
.layout {
    display: grid;
    grid-template-columns: 3fr 1fr;
    gap: 30px;
}
```

On smaller screens, the columns can be arranged vertically:

```css
@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

Desktop:

```text
┌──────────────────────┬──────────┐
│ Main Content         │ Sidebar  │
│                      │          │
└──────────────────────┴──────────┘
```

Smaller screen:

```text
┌──────────────────────┐
│ Main Content         │
├──────────────────────┤
│ Sidebar              │
└──────────────────────┘
```

---

## Desktop-First Typography

A desktop-first design may begin with larger typography:

```css
h1 {
    font-size: 3rem;
}

p {
    font-size: 1.1rem;
}
```

Smaller screens can reduce the sizes:

```css
@media (max-width: 768px) {
    h1 {
        font-size: 2rem;
    }

    p {
        font-size: 1rem;
    }
}
```

The typography is adjusted to better fit smaller viewports.

---

## Desktop-First Spacing

A large-screen layout may use generous spacing:

```css
.section {
    padding: 80px 40px;
}
```

Smaller screens can use more compact spacing:

```css
@media (max-width: 768px) {
    .section {
        padding: 50px 20px;
    }
}
```

This prevents excessive spacing from consuming too much of the limited viewport.

---

## Desktop-First Images

A desktop layout may display an image at a larger size:

```css
.image {
    width: 600px;
}
```

On smaller screens:

```css
@media (max-width: 600px) {
    .image {
        width: 100%;
    }
}
```

A more generally responsive approach is:

```css
.image {
    max-width: 100%;
    height: auto;
}
```

This can reduce the need for additional breakpoint-specific image rules.

---

## Desktop-First With Flexbox

Flexbox can make desktop-first layouts easier to adapt.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    gap: 30px;
}

@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
}
```

Large screen:

```text
┌───────────┬───────────┐
│ Content 1 │ Content 2 │
└───────────┴───────────┘
```

Small screen:

```text
┌───────────┐
│ Content 1 │
├───────────┤
│ Content 2 │
└───────────┘
```

---

## Desktop-First With Grid

CSS Grid can also be used with a desktop-first strategy.

```css
.dashboard {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    gap: 20px;
}

@media (max-width: 900px) {
    .dashboard {
        grid-template-columns: 1fr 1fr;
    }
}

@media (max-width: 600px) {
    .dashboard {
        grid-template-columns: 1fr;
    }
}
```

The grid progressively reduces its columns as space becomes limited.

---

## Desktop-First CSS Order

A desktop-first stylesheet can be organized like this:

```css
/* Base styles - large screens */

body {
    margin: 0;
}

.container {
    width: 80%;
    padding: 40px;
}

.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}

/* Medium screens */

@media (max-width: 1000px) {
    .container {
        width: 90%;
        padding: 30px;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Small screens */

@media (max-width: 600px) {
    .container {
        width: 100%;
        padding: 15px;
    }

    .cards {
        grid-template-columns: 1fr;
    }
}
```

The structure is:

```text
Large
 ↓
max-width: 1000px
 ↓
max-width: 600px
```

---

## Desktop-First and CSS Cascade

Desktop-first CSS also relies on the CSS cascade.

The base rule is defined first:

```css
.cards {
    grid-template-columns: repeat(4, 1fr);
}
```

A later media query overrides it:

```css
@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

When the media condition matches, the responsive declaration can override the base declaration.

---

## Desktop-First Does Not Mean Desktop-Only

Desktop-first does not mean the website is designed only for desktop users.

It means the larger-screen layout is established first.

Smaller layouts are then created through responsive rules.

```text
Desktop
   ↓
Tablet
   ↓
Mobile
```

The goal is still to provide a usable experience across different viewport sizes.

---

## When Desktop-First Works Well

Desktop-first can be useful when:

- The project is primarily designed around large-screen interfaces.
- The desktop layout is the main starting point for the design.
- The application contains complex desktop-oriented structures.
- The existing CSS is already desktop-oriented.
- The smaller layout can be created through clear responsive overrides.

For example:

```text
Large dashboard
       ↓
Establish desktop structure
       ↓
Reduce columns
       ↓
Stack sections
       ↓
Adapt controls
       ↓
Smaller layout
```

---

## Desktop-First and Existing Projects

Desktop-first can be practical when working with an existing project whose CSS was originally written for desktop.

For example:

```text
Existing desktop CSS
        ↓
Identify layouts that break
        ↓
Add max-width media queries
        ↓
Adjust smaller layouts
        ↓
Test across viewports
```

Rewriting an entire project into mobile-first CSS may not always be necessary.

The appropriate strategy depends on the project and its existing structure.

---

## Desktop-First and Content

The desktop-first approach should still prioritize important content on smaller screens.

A common mistake is to simply shrink everything.

Instead, smaller layouts may need structural changes.

For example:

```text
Desktop:

Main Content | Sidebar | Extra Panel
```

On a smaller screen:

```text
Main Content
     ↓
Sidebar
     ↓
Extra Panel
```

The content remains available while the layout changes to fit the smaller viewport.

---

## Desktop-First vs Shrinking Everything

A poor desktop-first implementation may do this:

```text
Desktop layout
      ↓
Make everything smaller
      ↓
Mobile
```

This can create:

- Tiny text
- Crowded controls
- Difficult navigation
- Horizontal scrolling
- Poor spacing

A better approach is:

```text
Desktop layout
      ↓
Identify what no longer fits
      ↓
Change structure
      ↓
Adjust spacing
      ↓
Adjust typography
      ↓
Create usable smaller layout
```

---

## Desktop-First and Breakpoints

Desktop-first commonly uses descending `max-width` breakpoints.

For example:

```css
@media (max-width: 1200px) {
    /* Smaller desktop / large tablet */
}

@media (max-width: 900px) {
    /* Tablet */
}

@media (max-width: 600px) {
    /* Small screens */
}
```

These breakpoints should still be based on layout requirements.

They are not required to match particular device categories.

---

## Desktop-First and Fluid CSS

Desktop-first does not mean every responsive change must use a media query.

Flexible CSS can reduce the number of breakpoints.

For example:

```css
.container {
    width: min(90%, 1200px);
    margin-inline: auto;
}
```

Grid can also adapt automatically:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}
```

This allows the layout to respond continuously to available space.

---

## Desktop-First and `clamp()`

Fluid typography can also reduce breakpoint usage.

For example:

```css
h1 {
    font-size: clamp(2rem, 5vw, 3.5rem);
}
```

Instead of manually changing the font size at several breakpoints, the value can scale within a defined range.

This works alongside desktop-first responsive design.

---

## Desktop-First and Flex-Wrapping

Flexbox can also handle some responsive behavior without explicit breakpoints.

For example:

```css
.navigation {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

Items can wrap when the available space becomes insufficient.

A breakpoint may still be needed if the design requires a completely different arrangement.

---

## Desktop-First and Accessibility

A desktop-first layout must still remain accessible on smaller screens.

Important considerations include:

- Readable text
- Adequate contrast
- Keyboard navigation
- Visible focus states
- Accessible controls
- Appropriate touch target sizes
- No unnecessary horizontal scrolling
- Logical content order

Responsive CSS should change presentation without making important content inaccessible.

---

## Testing a Desktop-First Layout

A desktop-first layout should be tested at multiple viewport sizes.

For example:

```text
1440px
1200px
1024px
900px
768px
600px
480px
375px
320px
```

The exact values are not mandatory.

The important point is to test the layout across a range of widths, including widths between breakpoints.

---

## Breakpoint Boundary Testing

Suppose the CSS contains:

```css
@media (max-width: 768px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

Test around the breakpoint:

```text
767px
768px
769px
```

This helps identify unexpected layout changes.

Also test widths between major breakpoints:

```text
650px
700px
750px
800px
850px
```

A responsive layout should not only work at the exact breakpoint values.

---

## Mobile-First vs Desktop-First

| Feature | Mobile-First | Desktop-First |
|---|---|---|
| Base layout | Smaller screens | Larger screens |
| Common media feature | `min-width` | `max-width` |
| Direction | Progressive enhancement | Progressive reduction |
| Starting point | Limited space | More available space |
| Common CSS flow | Small → Large | Large → Small |

Example mobile-first:

```css
/* Base */
.container {
    width: 100%;
}

@media (min-width: 768px) {
    .container {
        width: 90%;
    }
}
```

Example desktop-first:

```css
/* Base */
.container {
    width: 80%;
}

@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

Both approaches can produce responsive websites.

---

## Which Approach Should You Use?

There is no universal rule that every project must use one approach.

Choose based on the project.

```text
New responsive project
        ↓
Mobile-first is often a strong choice


Existing desktop-oriented project
        ↓
Desktop-first may be practical


Desktop-heavy application
        ↓
Desktop-first may fit the design process
```

The important goal is a responsive and usable interface.

---

## Practical Complete Example

```css
/* Base: large screens */

.container {
    width: 80%;
    margin-inline: auto;
    padding: 40px;
}

.navigation {
    display: flex;
    flex-direction: row;
    gap: 20px;
}

.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

.title {
    font-size: 3rem;
}

/* Medium screens */

@media (max-width: 1000px) {
    .container {
        width: 90%;
        padding: 30px;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }

    .title {
        font-size: 2.5rem;
    }
}

/* Small screens */

@media (max-width: 600px) {
    .container {
        width: 100%;
        padding: 15px;
    }

    .navigation {
        flex-direction: column;
        gap: 10px;
    }

    .cards {
        grid-template-columns: 1fr;
    }

    .title {
        font-size: 2rem;
    }
}
```

The progression is:

```text
LARGE
 ↓
4 columns
Horizontal navigation
Large spacing
Large heading
 ↓
MEDIUM
 ↓
2 columns
Reduced spacing
Smaller heading
 ↓
SMALL
 ↓
1 column
Vertical navigation
Compact spacing
Smaller heading
```

---

## Desktop-First Development Workflow

A practical workflow is:

```text
1. Start with the large-screen layout.
        ↓
2. Make the desktop experience usable.
        ↓
3. Test the layout at narrower widths.
        ↓
4. Find where the layout starts to break.
        ↓
5. Add a max-width media query.
        ↓
6. Change the layout where necessary.
        ↓
7. Test again.
        ↓
8. Repeat only when necessary.
```

This creates a progressive responsive layout from large to small.

---

## Common Mistake

Do not create a separate media query for every device.

For example:

```css
@media (max-width: 1400px) { ... }
@media (max-width: 1200px) { ... }
@media (max-width: 1024px) { ... }
@media (max-width: 900px) { ... }
@media (max-width: 768px) { ... }
@media (max-width: 600px) { ... }
@media (max-width: 480px) { ... }
```

This may create unnecessary CSS complexity.

Instead:

```text
Flexible CSS
      +
Meaningful breakpoints
      ↓
Maintainable responsive layout
```

---

## Another Common Mistake

Do not override properties unnecessarily.

For example:

```css
.container {
    width: 80%;
    padding: 40px;
}

@media (max-width: 768px) {
    .container {
        width: 100%;
        padding: 40px;
    }
}
```

If the padding does not need to change, there is no reason to repeat it.

A cleaner version is:

```css
.container {
    width: 80%;
    padding: 40px;
}

@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

Only change what actually needs to change.

---

## Best Practices

A good desktop-first approach generally follows these principles:

```text
1. Establish a usable large-screen layout.
2. Use flexible widths and layouts.
3. Use max-width for smaller-screen adjustments.
4. Add breakpoints based on layout requirements.
5. Avoid unnecessary overrides.
6. Change structure when shrinking is not enough.
7. Test between breakpoints.
8. Use Flexbox and Grid where appropriate.
9. Use fluid CSS where possible.
10. Keep responsive CSS maintainable.
```

---

> 💡 **Pro Tip:** Think of desktop-first CSS as building downward. Start with the larger layout, then use `max-width` media queries to progressively adapt the design as the available viewport space decreases.

---

> 💡 **Remember:** In a desktop-first approach, the base CSS targets the larger layout and smaller layouts are created using `max-width` media queries. Desktop-first and mobile-first are both valid responsive strategies; choose the approach that fits the project's design and development requirements.

---

## Common Responsive Patterns

Responsive design often uses a set of common layout patterns to adapt a webpage to different viewport sizes.

These patterns are built using CSS features such as:

- Media queries
- Flexbox
- CSS Grid
- Flexible widths
- Relative units
- Responsive images
- `clamp()`
- `min()`
- `max()`

The goal is to make the layout remain usable as the available space changes.

---

## Stacking Columns

One of the most common responsive patterns is changing multiple columns into a single vertical layout.

For example:

```css
.layout {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 30px;
}

@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

Large screens:

```text
┌──────────────────────┬──────────┐
│ Main Content         │ Sidebar  │
└──────────────────────┴──────────┘
```

Smaller screens:

```text
┌──────────────────────┐
│ Main Content         │
├──────────────────────┤
│ Sidebar              │
└──────────────────────┘
```

This pattern is useful when side-by-side content becomes too narrow on smaller screens.

---

## Changing Grid Columns

Another common pattern is reducing the number of grid columns as the viewport becomes narrower.

For example:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

@media (max-width: 1000px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout progressively changes:

```text
Large
4 columns

┌────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │
└────┴────┴────┴────┘
```

```text
Medium
2 columns

┌────┬────┐
│ 1  │ 2  │
├────┼────┤
│ 3  │ 4  │
└────┴────┘
```

```text
Small
1 column

┌────┐
│ 1  │
├────┤
│ 2  │
├────┤
│ 3  │
├────┤
│ 4  │
└────┘
```

---

## Horizontal to Vertical Navigation

Navigation is commonly horizontal on larger screens and vertical on smaller screens.

For example:

```css
.navigation {
    display: flex;
    flex-direction: row;
    gap: 20px;
}

@media (max-width: 700px) {
    .navigation {
        flex-direction: column;
        gap: 10px;
    }
}
```

Large screen:

```text
Home   About   Projects   Contact
```

Small screen:

```text
Home
About
Projects
Contact
```

This allows navigation items to use the available space more effectively.

---

## Wrapping Navigation Items

Sometimes navigation does not need to become completely vertical.

Flexbox can allow items to wrap:

```css
.navigation {
    display: flex;
    flex-wrap: wrap;
    gap: 15px;
}
```

When there is not enough horizontal space, items can move to another line.

```text
Wide:

Home   About   Projects   Contact


Narrow:

Home   About
Projects   Contact
```

This can be useful when a full vertical navigation is unnecessary.

---

## Hiding Secondary Content

Some content may be less important on smaller screens.

A responsive design may hide secondary content:

```css
.sidebar {
    display: block;
}

@media (max-width: 600px) {
    .sidebar {
        display: none;
    }
}
```

Large screen:

```text
┌──────────────────────┬──────────┐
│ Main Content         │ Sidebar  │
└──────────────────────┴──────────┘
```

Small screen:

```text
┌──────────────────────┐
│ Main Content         │
└──────────────────────┘
```

This should be used carefully.

Important information should not simply disappear because the screen is smaller.

---

## Moving Secondary Content Below Main Content

Instead of hiding secondary content, it can be moved below the main content.

For example:

```css
.layout {
    display: grid;
    grid-template-columns: 2fr 1fr;
}

@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

Desktop:

```text
Main Content | Sidebar
```

Mobile:

```text
Main Content
     ↓
Sidebar
```

This preserves the content while adapting its position.

---

## Responsive Container Width

A container often needs to become flexible.

For example:

```css
.container {
    width: 80%;
    max-width: 1200px;
    margin-inline: auto;
}
```

The container can also use a media query:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
        padding: 15px;
    }
}
```

This prevents the content from becoming too wide on large screens while allowing it to use available space on smaller screens.

---

## Full-Width Mobile Layout

A common pattern is allowing content to use almost the full viewport width on smaller screens.

For example:

```css
.container {
    width: 80%;
    margin-inline: auto;
}

@media (max-width: 600px) {
    .container {
        width: 100%;
        padding-inline: 15px;
    }
}
```

Large screens:

```text
┌────────────────────────────────────┐
│       ┌──────────────────┐         │
│       │     Content      │         │
│       └──────────────────┘         │
└────────────────────────────────────┘
```

Small screens:

```text
┌──────────────────────┐
│    Content           │
│                      │
└──────────────────────┘
```

---

## Responsive Padding

Large screens can use more spacing while smaller screens use less.

```css
.section {
    padding: 80px 40px;
}

@media (max-width: 768px) {
    .section {
        padding: 50px 20px;
    }
}
```

This prevents excessive whitespace on smaller screens.

---

## Responsive Typography

Typography can also change at different viewport sizes.

For example:

```css
h1 {
    font-size: 3rem;
}

@media (max-width: 768px) {
    h1 {
        font-size: 2rem;
    }
}
```

The heading becomes smaller when less horizontal space is available.

Fluid typography can also be used:

```css
h1 {
    font-size: clamp(2rem, 5vw, 3.5rem);
}
```

Here, the browser can calculate a flexible size within the specified minimum and maximum values.

---

## Responsive Images

Images should generally be able to shrink within their containers.

A common pattern is:

```css
img {
    max-width: 100%;
    height: auto;
}
```

This prevents an image from overflowing its container.

For example:

```text
Large:

┌─────────────────────────┐
│                         │
│        IMAGE            │
│                         │
└─────────────────────────┘
```

Smaller:

```text
┌──────────────────┐
│                  │
│      IMAGE       │
│                  │
└──────────────────┘
```

The image scales with the available width.

---

## Responsive Hero Sections

Hero sections often need different spacing or layout arrangements on smaller screens.

For example:

```css
.hero {
    display: flex;
    align-items: center;
    gap: 40px;
    padding: 100px 40px;
}

@media (max-width: 768px) {
    .hero {
        flex-direction: column;
        padding: 60px 20px;
        text-align: center;
    }
}
```

Large screens:

```text
┌───────────────────────────────────┐
│ Text              Image           │
└───────────────────────────────────┘
```

Small screens:

```text
┌──────────────────┐
│      Text        │
│                  │
│      Image       │
└──────────────────┘
```

---

## Responsive Buttons

Buttons can also adapt to smaller screens.

For example:

```css
.button-group {
    display: flex;
    gap: 15px;
}

@media (max-width: 600px) {
    .button-group {
        flex-direction: column;
    }
}
```

Large:

```text
[ Learn More ] [ Contact ]
```

Small:

```text
[ Learn More ]
[ Contact   ]
```

This can make buttons easier to tap and prevent them from becoming crowded.

---

## Responsive Forms

Forms often need to change from multiple columns to a single column.

For example:

```css
.form {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}

@media (max-width: 700px) {
    .form {
        grid-template-columns: 1fr;
    }
}
```

Large:

```text
First Name     Last Name
Email          Phone
```

Small:

```text
First Name
Last Name
Email
Phone
```

This improves readability and reduces horizontal crowding.

---

## Responsive Tables

Tables can become difficult to display on small screens because they contain many columns.

One solution is allowing horizontal scrolling:

```css
.table-container {
    overflow-x: auto;
}
```

HTML:

```html
<div class="table-container">
    <table>
        ...
    </table>
</div>
```

On a smaller viewport:

```text
┌──────────────────────┐
│ Table → → → → →     │
└──────────────────────┘
```

The user can scroll horizontally to access the remaining columns.

This can be preferable to forcing a complex table into a narrow width.

---

## Responsive Cards

Cards can change from horizontal layouts to vertical layouts.

For example:

```css
.card {
    display: flex;
    align-items: center;
    gap: 20px;
}

@media (max-width: 600px) {
    .card {
        flex-direction: column;
        text-align: center;
    }
}
```

Large:

```text
┌────────┬──────────────────┐
│ Image  │ Card Content     │
└────────┴──────────────────┘
```

Small:

```text
┌──────────────────┐
│      Image       │
├──────────────────┤
│   Card Content   │
└──────────────────┘
```

---

## Responsive Sidebars

Sidebars are commonly displayed beside content on large screens.

```css
.layout {
    display: grid;
    grid-template-columns: 3fr 1fr;
    gap: 30px;
}
```

On smaller screens:

```css
@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

This converts the sidebar into content below the main section.

---

## Responsive Header

A header can change structure on smaller screens.

For example:

```css
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

@media (max-width: 700px) {
    .header {
        flex-direction: column;
        gap: 15px;
    }
}
```

Large:

```text
Logo                     Navigation
```

Small:

```text
Logo
Navigation
```

More advanced navigation may use a menu button to reveal navigation links.

---

## Responsive Footer

Footers often contain several columns.

For example:

```css
.footer {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 30px;
}

@media (max-width: 768px) {
    .footer {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 500px) {
    .footer {
        grid-template-columns: 1fr;
    }
}
```

The footer progressively reduces its columns.

---

## Responsive Spacing Between Components

Spacing can also be adjusted at breakpoints.

```css
.section {
    margin-bottom: 80px;
}

@media (max-width: 768px) {
    .section {
        margin-bottom: 50px;
    }
}
```

Smaller screens often benefit from more compact spacing because vertical space becomes more important.

---

## Responsive Alignment

A layout may change its alignment depending on the viewport.

For example:

```css
.hero {
    text-align: left;
}

@media (max-width: 600px) {
    .hero {
        text-align: center;
    }
}
```

Large:

```text
Heading
Description
Button
```

with left alignment.

Small:

```text
       Heading
      Description
        Button
```

with centered alignment.

---

## Responsive Flex Direction

Changing `flex-direction` is one of the most common responsive patterns.

```css
.container {
    display: flex;
    flex-direction: row;
}

@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
}
```

The layout changes from horizontal to vertical.

This pattern is useful for:

- Cards
- Navigation
- Hero sections
- Forms
- Content sections
- Button groups

---

## Responsive Grid Columns

Changing `grid-template-columns` is another common pattern.

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .grid {
        grid-template-columns: 1fr;
    }
}
```

The number of columns is reduced when the viewport becomes narrower.

---

## Responsive Order

Flexbox can change the visual order of elements.

For example:

```css
.content {
    display: flex;
}

.image {
    order: 1;
}

.text {
    order: 2;
}

@media (max-width: 768px) {
    .image {
        order: 2;
    }

    .text {
        order: 1;
    }
}
```

This can change which content appears first visually.

However, visual order should be used carefully so that the visual presentation does not create confusion compared with the document and reading order.

---

## Responsive Visibility

CSS can change whether an element is displayed.

For example:

```css
.desktop-only {
    display: block;
}

@media (max-width: 600px) {
    .desktop-only {
        display: none;
    }
}
```

This can be useful for decorative or secondary elements.

Important content should not be hidden merely because the viewport is smaller.

---

## Responsive Utility Classes

A project may also define utility classes for responsive behavior.

For example:

```css
.hide-mobile {
    display: block;
}

@media (max-width: 600px) {
    .hide-mobile {
        display: none;
    }
}
```

HTML:

```html
<div class="hide-mobile">
    Secondary content
</div>
```

This allows responsive behavior to be reused across multiple components.

---

## Responsive Navigation Pattern

A common navigation pattern is:

```text
Large screen:

Logo     Home   About   Projects   Contact


Small screen:

Logo                         ☰
```

The navigation links can be hidden or collapsed behind a menu control.

The CSS may look like:

```css
.menu {
    display: flex;
}

.menu-button {
    display: none;
}

@media (max-width: 700px) {
    .menu {
        display: none;
    }

    .menu-button {
        display: block;
    }
}
```

The actual menu interaction usually requires JavaScript or another appropriate mechanism to open and close the navigation.

---

## Responsive Dashboard Pattern

A dashboard may use several columns on large screens:

```css
.dashboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}
```

Then reduce columns:

```css
@media (max-width: 1000px) {
    .dashboard {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .dashboard {
        grid-template-columns: 1fr;
    }
}
```

This is useful for cards, statistics, widgets, and other dashboard components.

---

## Responsive Content Priority

Responsive design is not only about changing dimensions.

It can also change the priority of content.

For example:

```text
Large screen:

Main Content
Sidebar
Related Content
Extra Information
```

Smaller screen:

```text
Main Content
Sidebar
```

Very small screen:

```text
Main Content
```

The goal is to keep the most important information accessible when space becomes limited.

---

## Responsive Pattern: Expand and Collapse

Some components can expand on larger screens and collapse on smaller screens.

For example:

```text
Large:

┌──────────────────────────┐
│ Filters                  │
│ Category                 │
│ Price                    │
│ Rating                   │
└──────────────────────────┘


Small:

┌──────────────────────────┐
│ Filters ▼               │
└──────────────────────────┘
```

The visual design can change significantly on smaller screens.

The interaction for expanding and collapsing the content may require HTML and JavaScript in addition to CSS.

---

## Responsive Pattern: Horizontal to Vertical

This is one of the most common responsive transformations.

```text
Large:

A | B | C


Small:

A
B
C
```

CSS:

```css
.items {
    display: flex;
    flex-direction: row;
}

@media (max-width: 700px) {
    .items {
        flex-direction: column;
    }
}
```

This simple pattern can be applied to many components.

---

## Responsive Pattern: Multi-Column to Single Column

Another common transformation is:

```text
Large:

┌──────┬──────┬──────┐
│  A   │  B   │  C   │
└──────┴──────┴──────┘
```

to:

```text
Small:

┌──────────────┐
│      A       │
├──────────────┤
│      B       │
├──────────────┤
│      C       │
└──────────────┘
```

CSS:

```css
.items {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 700px) {
    .items {
        grid-template-columns: 1fr;
    }
}
```

---

## Responsive Pattern: Multi-Column to Fewer Columns

Instead of immediately switching to one column, a layout can progressively reduce columns.

```css
.items {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}

@media (max-width: 1000px) {
    .items {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .items {
        grid-template-columns: 1fr;
    }
}
```

This provides a smoother transition between large, medium, and small layouts.

---

## Responsive Pattern: Fixed to Fluid

A fixed-width element may need to become flexible.

For example:

```css
.image {
    width: 600px;
}
```

A better responsive approach can be:

```css
.image {
    width: 100%;
    max-width: 600px;
}
```

Now the image can shrink when the available space becomes smaller while still being limited to `600px` on larger screens.

---

## Responsive Pattern: Fixed Sidebar to Stacked Content

A desktop layout may use a fixed-width sidebar:

```css
.layout {
    display: grid;
    grid-template-columns: 250px 1fr;
}
```

On smaller screens:

```css
@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

The sidebar becomes part of the normal vertical flow.

---

## Responsive Pattern: Large Spacing to Compact Spacing

```css
.section {
    padding: 100px 50px;
}

@media (max-width: 768px) {
    .section {
        padding: 50px 20px;
    }
}
```

This prevents large spacing values from consuming too much space on small screens.

---

## Responsive Pattern: Large Typography to Smaller Typography

```css
.title {
    font-size: 4rem;
}

@media (max-width: 768px) {
    .title {
        font-size: 2.5rem;
    }
}

@media (max-width: 480px) {
    .title {
        font-size: 2rem;
    }
}
```

However, fluid sizing can sometimes provide a smoother solution:

```css
.title {
    font-size: clamp(2rem, 6vw, 4rem);
}
```

---

## Combining Responsive Patterns

Real websites usually combine several patterns.

For example:

```css
.layout {
    display: grid;
    grid-template-columns: 3fr 1fr;
    gap: 40px;
}

.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

.navigation {
    display: flex;
    gap: 20px;
}

@media (max-width: 900px) {
    .layout {
        grid-template-columns: 1fr;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }

    .navigation {
        flex-direction: column;
    }
}
```

Several responsive patterns work together:

```text
Large
 ↓
Sidebar + Content
3 Card Columns
Horizontal Navigation

Medium
 ↓
Stacked Layout
2 Card Columns
Horizontal Navigation

Small
 ↓
Stacked Layout
1 Card Column
Vertical Navigation
```

---

## Common Mistake

Do not treat responsive design as simply making everything smaller.

For example:

```text
Desktop
   ↓
Scale everything down
   ↓
Mobile
```

This can create poor usability.

Instead:

```text
Desktop
   ↓
Identify layout changes
   ↓
Rearrange content
   ↓
Adjust spacing
   ↓
Adjust typography
   ↓
Adapt controls
   ↓
Mobile
```

Responsive design often requires structural changes, not just smaller dimensions.

---

## Another Common Mistake

Do not hide important content without providing an alternative.

For example:

```css
@media (max-width: 600px) {
    .important-information {
        display: none;
    }
}
```

This can make the information inaccessible.

Instead, consider:

```text
Move it
  ↓
Stack it
  ↓
Collapse it appropriately
  ↓
Make it scrollable
  ↓
Keep it accessible
```

The correct solution depends on the content.

---

## Best Practices

Common responsive patterns should generally follow these principles:

```text
1. Let content determine the layout.
2. Use Flexbox for one-dimensional layouts.
3. Use Grid for two-dimensional layouts.
4. Stack columns when horizontal space becomes limited.
5. Reduce grid columns progressively when appropriate.
6. Keep important content accessible.
7. Use flexible images.
8. Adjust spacing when necessary.
9. Use fluid typography where appropriate.
10. Avoid unnecessary media queries.
11. Test layouts between breakpoints.
12. Combine patterns when the design requires it.
```

---

> 💡 **Pro Tip:** Most responsive layouts are combinations of a few simple patterns: stack columns, reduce grid columns, wrap or rearrange navigation, adjust spacing, and make content flexible. Learn these patterns well and you can solve many responsive layout problems without creating complicated CSS.

---

> 💡 **Remember:** Responsive design is about adapting the structure and presentation of content to available space. Media queries provide the conditions, while Flexbox, Grid, flexible sizing, and other CSS features provide the actual layout changes.

---

## Practical Examples

The concepts of CSS media queries become easier to understand when they are applied to real layouts.

The following examples demonstrate how media queries can be combined with Flexbox, Grid, spacing, typography, and responsive sizing.

---

## Example 1: Responsive Navigation

A navigation bar can be horizontal on larger screens and vertical on smaller screens.

```html
<nav class="navigation">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Projects</a>
    <a href="#">Contact</a>
</nav>
```

```css
.navigation {
    display: flex;
    justify-content: center;
    gap: 30px;
}

.navigation a {
    text-decoration: none;
    padding: 10px;
}

@media (max-width: 600px) {
    .navigation {
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }
}
```

Large screen:

```text
Home    About    Projects    Contact
```

Small screen:

```text
Home
About
Projects
Contact
```

The media query changes the direction of the navigation when the viewport becomes narrower.

---

## Example 2: Responsive Card Grid

A card layout can use multiple columns on large screens and fewer columns on smaller screens.

```html
<div class="cards">
    <article class="card">Card 1</article>
    <article class="card">Card 2</article>
    <article class="card">Card 3</article>
    <article class="card">Card 4</article>
</div>
```

```css
.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

.card {
    padding: 30px;
    border: 1px solid #ccc;
}

@media (max-width: 1000px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout changes from:

```text
4 columns
    ↓
2 columns
    ↓
1 column
```

This is one of the most common responsive patterns.

---

## Example 3: Responsive Two-Column Layout

A common page structure contains main content and a sidebar.

```html
<div class="layout">
    <main class="content">
        <h1>Main Content</h1>
        <p>
            This is the main content area.
        </p>
    </main>

    <aside class="sidebar">
        <h2>Sidebar</h2>
        <p>
            Additional information.
        </p>
    </aside>
</div>
```

```css
.layout {
    display: grid;
    grid-template-columns: 3fr 1fr;
    gap: 30px;
}

.content,
.sidebar {
    padding: 20px;
}

@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

Large screen:

```text
┌────────────────────────┬──────────┐
│ Main Content            │ Sidebar  │
└────────────────────────┴──────────┘
```

Small screen:

```text
┌────────────────────────────┐
│ Main Content               │
├────────────────────────────┤
│ Sidebar                    │
└────────────────────────────┘
```

---

## Example 4: Responsive Hero Section

A hero section can place text and an image beside each other on larger screens.

```html
<section class="hero">
    <div class="hero-content">
        <h1>Build Responsive Websites</h1>
        <p>
            Create layouts that adapt to different screen sizes.
        </p>
        <button>Learn More</button>
    </div>

    <img src="hero.jpg" alt="Responsive design example">
</section>
```

```css
.hero {
    display: flex;
    align-items: center;
    gap: 50px;
    padding: 80px 40px;
}

.hero-content {
    flex: 1;
}

.hero img {
    width: 50%;
    max-width: 500px;
    height: auto;
}

@media (max-width: 768px) {
    .hero {
        flex-direction: column;
        text-align: center;
        padding: 50px 20px;
    }

    .hero img {
        width: 100%;
    }
}
```

Large:

```text
┌──────────────────────────────────┐
│ Text              Image          │
│                                  │
└──────────────────────────────────┘
```

Small:

```text
┌──────────────────────┐
│        Text          │
│                      │
│        Image         │
└──────────────────────┘
```

---

## Example 5: Responsive Form

A form can use two columns on larger screens and one column on smaller screens.

```html
<form class="form">
    <div>
        <label for="first-name">First Name</label>
        <input id="first-name" type="text">
    </div>

    <div>
        <label for="last-name">Last Name</label>
        <input id="last-name" type="text">
    </div>

    <div>
        <label for="email">Email</label>
        <input id="email" type="email">
    </div>

    <div>
        <label for="phone">Phone</label>
        <input id="phone" type="tel">
    </div>
</form>
```

```css
.form {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}

.form div {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.form input {
    padding: 10px;
}

@media (max-width: 700px) {
    .form {
        grid-template-columns: 1fr;
    }
}
```

Large:

```text
First Name       Last Name
Email            Phone
```

Small:

```text
First Name
Last Name
Email
Phone
```

This prevents form controls from becoming too narrow.

---

## Example 6: Responsive Button Group

Buttons can be arranged horizontally on large screens and vertically on smaller screens.

```html
<div class="buttons">
    <button>Learn More</button>
    <button>Contact Us</button>
</div>
```

```css
.buttons {
    display: flex;
    gap: 15px;
}

@media (max-width: 500px) {
    .buttons {
        flex-direction: column;
    }

    .buttons button {
        width: 100%;
    }
}
```

Large:

```text
[ Learn More ] [ Contact Us ]
```

Small:

```text
[ Learn More ]
[ Contact Us ]
```

---

## Example 7: Responsive Typography

Media queries can adjust typography for smaller screens.

```html
<h1 class="title">
    Responsive Web Design
</h1>
```

```css
.title {
    font-size: 4rem;
}

@media (max-width: 900px) {
    .title {
        font-size: 3rem;
    }
}

@media (max-width: 600px) {
    .title {
        font-size: 2rem;
    }
}
```

The heading becomes smaller as the viewport becomes narrower.

A fluid alternative is:

```css
.title {
    font-size: clamp(2rem, 6vw, 4rem);
}
```

This allows the browser to calculate a size within the specified range.

---

## Example 8: Responsive Spacing

Large screens may have more generous spacing.

```css
.section {
    padding: 100px 60px;
}

@media (max-width: 768px) {
    .section {
        padding: 60px 20px;
    }
}

@media (max-width: 480px) {
    .section {
        padding: 40px 15px;
    }
}
```

The spacing progressively becomes smaller.

```text
Large
100px / 60px
     ↓
Medium
60px / 20px
     ↓
Small
40px / 15px
```

---

## Example 9: Responsive Image

Images should generally be able to shrink with their container.

```html
<img
    class="responsive-image"
    src="image.jpg"
    alt="Example image"
>
```

```css
.responsive-image {
    max-width: 100%;
    height: auto;
}
```

The image will not normally become wider than its containing element.

A maximum size can also be added:

```css
.responsive-image {
    width: 100%;
    max-width: 600px;
    height: auto;
}
```

This allows the image to remain flexible while preventing it from becoming excessively large.

---

## Example 10: Responsive Footer

A footer with multiple columns can progressively reduce its columns.

```html
<footer class="footer">
    <section>
        <h2>Company</h2>
        <p>About us</p>
        <p>Careers</p>
    </section>

    <section>
        <h2>Services</h2>
        <p>Design</p>
        <p>Development</p>
    </section>

    <section>
        <h2>Support</h2>
        <p>Help</p>
        <p>Contact</p>
    </section>

    <section>
        <h2>Social</h2>
        <p>GitHub</p>
        <p>LinkedIn</p>
    </section>
</footer>
```

```css
.footer {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 30px;
    padding: 50px;
}

@media (max-width: 900px) {
    .footer {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 500px) {
    .footer {
        grid-template-columns: 1fr;
        padding: 30px 20px;
    }
}
```

The footer changes from:

```text
4 columns
    ↓
2 columns
    ↓
1 column
```

---

## Example 11: Responsive Dashboard

A dashboard can use a grid that adapts to different viewport sizes.

```html
<div class="dashboard">
    <div class="widget">Users</div>
    <div class="widget">Revenue</div>
    <div class="widget">Orders</div>
    <div class="widget">Messages</div>
    <div class="widget">Reports</div>
    <div class="widget">Settings</div>
</div>
```

```css
.dashboard {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

.widget {
    padding: 30px;
    border: 1px solid #ccc;
}

@media (max-width: 900px) {
    .dashboard {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .dashboard {
        grid-template-columns: 1fr;
    }
}
```

Large:

```text
┌──────┬──────┬──────┐
│  1   │  2   │  3   │
├──────┼──────┼──────┤
│  4   │  5   │  6   │
└──────┴──────┴──────┘
```

Medium:

```text
┌──────┬──────┐
│  1   │  2   │
├──────┼──────┤
│  3   │  4   │
├──────┼──────┤
│  5   │  6   │
└──────┴──────┘
```

Small:

```text
┌──────┐
│  1   │
├──────┤
│  2   │
├──────┤
│  3   │
├──────┤
│  4   │
├──────┤
│  5   │
├──────┤
│  6   │
└──────┘
```

---

## Example 12: Responsive Table

Tables can become difficult to fit on smaller screens.

A wrapper can provide horizontal scrolling.

```html
<div class="table-container">
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Email</th>
                <th>Role</th>
                <th>Status</th>
            </tr>
        </thead>

        <tbody>
            <tr>
                <td>Alex</td>
                <td>alex@example.com</td>
                <td>Developer</td>
                <td>Active</td>
            </tr>
        </tbody>
    </table>
</div>
```

```css
.table-container {
    overflow-x: auto;
}

table {
    width: 100%;
    min-width: 600px;
    border-collapse: collapse;
}

th,
td {
    padding: 12px;
    border: 1px solid #ccc;
}
```

The table remains readable while the wrapper allows horizontal scrolling when necessary.

---

## Example 13: Responsive Card With Image

A card can use a horizontal layout on large screens.

```html
<article class="profile-card">
    <img src="profile.jpg" alt="Profile">

    <div>
        <h2>Developer Profile</h2>
        <p>
            Front-end development and responsive design.
        </p>
    </div>
</article>
```

```css
.profile-card {
    display: flex;
    align-items: center;
    gap: 20px;
    padding: 20px;
}

.profile-card img {
    width: 180px;
    height: 180px;
    object-fit: cover;
}

@media (max-width: 600px) {
    .profile-card {
        flex-direction: column;
        text-align: center;
    }

    .profile-card img {
        width: 120px;
        height: 120px;
    }
}
```

Large:

```text
┌──────────┬─────────────────────┐
│  Image   │ Profile Information │
└──────────┴─────────────────────┘
```

Small:

```text
┌─────────────────────┐
│        Image        │
│                     │
│ Profile Information │
└─────────────────────┘
```

---

## Example 14: Responsive Header

A header can change from a horizontal arrangement to a vertical arrangement.

```html
<header class="header">
    <div class="logo">
        My Website
    </div>

    <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </nav>
</header>
```

```css
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 40px;
}

.header nav {
    display: flex;
    gap: 20px;
}

@media (max-width: 700px) {
    .header {
        flex-direction: column;
        gap: 15px;
        padding: 20px;
    }

    .header nav {
        flex-direction: column;
        align-items: center;
    }
}
```

---

## Example 15: Desktop Navigation to Mobile Menu

A common responsive pattern is showing full navigation on larger screens and a menu button on smaller screens.

```html
<header class="header">
    <div class="logo">
        My Website
    </div>

    <button class="menu-button">
        ☰
    </button>

    <nav class="menu">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Projects</a>
        <a href="#">Contact</a>
    </nav>
</header>
```

```css
.menu {
    display: flex;
    gap: 20px;
}

.menu-button {
    display: none;
}

@media (max-width: 700px) {
    .menu {
        display: none;
    }

    .menu-button {
        display: block;
    }
}
```

The layout becomes:

```text
Large:

Logo       Home About Projects Contact
```

Small:

```text
Logo                         ☰
```

This example only changes visibility.

Opening and closing the menu requires an appropriate interaction mechanism, such as JavaScript.

---

## Example 16: Responsive Two-Column Article

A long article may have a main reading area and related information.

```html
<div class="article-layout">
    <article class="article">
        <h1>Responsive CSS</h1>
        <p>
            Responsive design allows a layout to adapt
            to different viewport sizes.
        </p>
    </article>

    <aside class="related">
        <h2>Related Topics</h2>
        <ul>
            <li>Flexbox</li>
            <li>Grid</li>
            <li>Media Queries</li>
        </ul>
    </aside>
</div>
```

```css
.article-layout {
    display: grid;
    grid-template-columns: 3fr 1fr;
    gap: 40px;
}

@media (max-width: 800px) {
    .article-layout {
        grid-template-columns: 1fr;
    }
}
```

The related content moves below the article on smaller screens.

---

## Example 17: Responsive Pricing Cards

Pricing cards can use multiple columns on large screens.

```html
<section class="pricing">
    <article class="plan">
        <h2>Basic</h2>
        <p>$10</p>
    </article>

    <article class="plan">
        <h2>Pro</h2>
        <p>$25</p>
    </article>

    <article class="plan">
        <h2>Business</h2>
        <p>$50</p>
    </article>
</section>
```

```css
.pricing {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

.plan {
    padding: 30px;
    border: 1px solid #ccc;
    text-align: center;
}

@media (max-width: 768px) {
    .pricing {
        grid-template-columns: 1fr;
    }
}
```

Large:

```text
┌────────┬────────┬────────┐
│ Basic  │  Pro   │Business│
└────────┴────────┴────────┘
```

Small:

```text
┌────────────┐
│   Basic    │
├────────────┤
│    Pro     │
├────────────┤
│  Business  │
└────────────┘
```

---

## Example 18: Responsive Gallery

A gallery can automatically change the number of columns.

```html
<div class="gallery">
    <img src="1.jpg" alt="Gallery image 1">
    <img src="2.jpg" alt="Gallery image 2">
    <img src="3.jpg" alt="Gallery image 3">
    <img src="4.jpg" alt="Gallery image 4">
</div>
```

```css
.gallery {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

.gallery img {
    width: 100%;
    height: auto;
    display: block;
}

@media (max-width: 900px) {
    .gallery {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 500px) {
    .gallery {
        grid-template-columns: 1fr;
    }
}
```

The gallery changes from:

```text
4 → 2 → 1 columns
```

as the viewport becomes smaller.

---

## Example 19: Responsive Sidebar With Navigation

A dashboard sidebar can be displayed beside the main content on large screens.

```html
<div class="dashboard-layout">
    <aside class="dashboard-sidebar">
        <a href="#">Dashboard</a>
        <a href="#">Users</a>
        <a href="#">Reports</a>
        <a href="#">Settings</a>
    </aside>

    <main class="dashboard-content">
        <h1>Dashboard</h1>
        <p>
            Dashboard content goes here.
        </p>
    </main>
</div>
```

```css
.dashboard-layout {
    display: grid;
    grid-template-columns: 240px 1fr;
    min-height: 100vh;
}

.dashboard-sidebar {
    display: flex;
    flex-direction: column;
    gap: 15px;
    padding: 20px;
}

.dashboard-content {
    padding: 40px;
}

@media (max-width: 768px) {
    .dashboard-layout {
        grid-template-columns: 1fr;
    }

    .dashboard-sidebar {
        flex-direction: row;
        overflow-x: auto;
    }

    .dashboard-content {
        padding: 20px;
    }
}
```

On large screens:

```text
┌───────────┬────────────────────┐
│ Sidebar   │ Main Content       │
│           │                    │
│ Dashboard │                    │
│ Users     │                    │
│ Reports   │                    │
│ Settings  │                    │
└───────────┴────────────────────┘
```

On smaller screens:

```text
┌───────────────────────────────┐
│ Dashboard Users Reports ... → │
├───────────────────────────────┤
│ Main Content                  │
└───────────────────────────────┘
```

---

## Example 20: Complete Responsive Page

A complete page can combine several responsive patterns.

```html
<header class="site-header">
    <h1>My Website</h1>

    <nav class="site-nav">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Projects</a>
        <a href="#">Contact</a>
    </nav>
</header>

<main>
    <section class="hero">
        <div>
            <h2>Build Responsive Websites</h2>
            <p>
                Create interfaces that adapt to different
                viewport sizes.
            </p>
            <button>Get Started</button>
        </div>

        <img src="hero.jpg" alt="Responsive design">
    </section>

    <section class="cards">
        <article class="card">
            <h3>HTML</h3>
            <p>Structure your content.</p>
        </article>

        <article class="card">
            <h3>CSS</h3>
            <p>Style your interface.</p>
        </article>

        <article class="card">
            <h3>Responsive Design</h3>
            <p>Adapt your layout.</p>
        </article>
    </section>
</main>
```

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: sans-serif;
}

.site-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 25px 50px;
}

.site-nav {
    display: flex;
    gap: 20px;
}

.hero {
    display: flex;
    align-items: center;
    gap: 50px;
    padding: 100px 50px;
}

.hero > div {
    flex: 1;
}

.hero img {
    width: 50%;
    max-width: 500px;
    height: auto;
}

.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    padding: 50px;
}

.card {
    padding: 30px;
    border: 1px solid #ccc;
}

@media (max-width: 900px) {
    .site-header {
        padding: 20px 30px;
    }

    .hero {
        padding: 70px 30px;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
        padding: 30px;
    }
}

@media (max-width: 600px) {
    .site-header {
        flex-direction: column;
        gap: 15px;
        padding: 20px;
    }

    .site-nav {
        flex-direction: column;
        align-items: center;
    }

    .hero {
        flex-direction: column;
        text-align: center;
        padding: 50px 20px;
    }

    .hero img {
        width: 100%;
    }

    .cards {
        grid-template-columns: 1fr;
        padding: 20px;
    }
}
```

This example combines:

```text
Header
  ↓
Responsive navigation
  ↓
Hero section
  ↓
Responsive image
  ↓
Responsive cards
  ↓
Multiple breakpoints
```

The page progressively adapts:

```text
Large
│
├── Horizontal header
├── Horizontal hero
└── 3-column cards
        ↓
Medium
│
├── Horizontal header
├── Horizontal hero
└── 2-column cards
        ↓
Small
│
├── Vertical header
├── Vertical hero
└── 1-column cards
```

---

## Example 21: Responsive Layout Without Many Media Queries

Not every responsive layout needs many breakpoints.

CSS Grid can automatically adapt using `auto-fit` and `minmax()`.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(250px, 1fr)
    );
    gap: 20px;
}
```

The browser automatically determines how many columns can fit.

Conceptually:

```text
Wide
┌────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │
└────┴────┴────┴────┘

Narrower
┌────┬────┬────┐
│ 1  │ 2  │ 3  │
└────┴────┴────┘

Smaller
┌────┬────┐
│ 1  │ 2  │
└────┴────┘
```

The exact number of columns depends on the available width and the minimum column size.

---

## Example 22: Responsive Container With `min()`

A container can also use `min()` to limit its width.

```css
.container {
    width: min(90%, 1200px);
    margin-inline: auto;
}
```

This means the container uses the smaller of:

```text
90% of available width
        OR
1200px
```

This can reduce the need for breakpoint-specific container widths.

---

## Example 23: Responsive Width With `clamp()`

`clamp()` can provide a flexible value between a minimum and maximum.

```css
.container {
    width: clamp(300px, 80%, 1200px);
}
```

The value is constrained between:

```text
Minimum: 300px
Preferred: 80%
Maximum: 1200px
```

This can help create fluid layouts without adding many media queries.

---

## Example 24: Responsive Gap

Spacing between grid or flex items can also be fluid.

```css
.cards {
    display: grid;
    gap: clamp(10px, 3vw, 30px);
}
```

The gap can change according to viewport width while remaining within the specified range.

---

## Example 25: Responsive Layout Using Container Queries

Media queries respond to the viewport.

Container queries can respond to the size of a component's container.

For example:

```css
.card-container {
    container-type: inline-size;
}

.card {
    display: block;
}

@container (min-width: 500px) {
    .card {
        display: flex;
        gap: 20px;
    }
}
```

This allows the card to adapt based on the available width of its container rather than the entire viewport.

Container queries are useful for reusable components that may appear in different parts of a page.

---

## Practical Responsive Design Process

When creating a responsive component, follow a simple process:

```text
1. Create the normal layout.
        ↓
2. Identify where the content becomes crowded.
        ↓
3. Decide what needs to change.
        ↓
4. Choose Flexbox, Grid, or another CSS feature.
        ↓
5. Add a media query if necessary.
        ↓
6. Test at several widths.
        ↓
7. Test between breakpoints.
        ↓
8. Remove unnecessary CSS.
```

---

## Testing Practical Examples

After creating a responsive layout, test it at different viewport sizes.

For example:

```text
320px
375px
480px
600px
768px
900px
1024px
1200px
1440px
```

Also test widths between breakpoints.

For example, if a media query uses:

```css
@media (max-width: 768px)
```

test:

```text
767px
768px
769px
```

This helps identify unexpected layout transitions.

---

## What These Examples Demonstrate

The examples in this section demonstrate several important responsive techniques:

```text
Media Queries
      +
Flexbox
      +
CSS Grid
      +
Flexible Widths
      +
Responsive Images
      +
Responsive Typography
      +
Responsive Spacing
      +
Content Reordering
      +
Progressive Column Reduction
      ↓
Responsive Layout
```

The key idea is that media queries do not create responsiveness by themselves.

They provide conditions under which CSS rules can change.

The actual responsive behavior comes from changing properties such as:

```css
display
flex-direction
grid-template-columns
width
padding
margin
font-size
gap
order
```

and many others.

---

> 💡 **Pro Tip:** Before adding a media query, first ask whether Flexbox, Grid, `min()`, `max()`, `clamp()`, `auto-fit`, or flexible sizing can solve the problem automatically. Good responsive CSS often uses fewer media queries than expected.

---

> 💡 **Remember:** A practical responsive layout usually changes structure rather than simply shrinking everything. Columns can stack, grids can reduce columns, navigation can wrap, images can become fluid, and spacing and typography can adapt to the available space.

---

## Key Takeaways

CSS media queries allow CSS rules to respond to different conditions, especially viewport size.

They are one of the core tools used to build responsive websites.

---

## 1. Media Queries Apply Conditional CSS

A media query allows CSS to be applied only when a condition is true.

```css
@media (max-width: 768px) {
    body {
        font-size: 14px;
    }
}
```

The rule inside the media query applies when the viewport width is `768px` or less.

---

## 2. Basic Syntax

The general structure is:

```css
@media (condition) {
    selector {
        property: value;
    }
}
```

For example:

```css
@media (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

---

## 3. `min-width` and `max-width`

These are commonly used for responsive layouts.

### `min-width`

Applies styles when the viewport is at least the specified width.

```css
@media (min-width: 768px) {
    .container {
        max-width: 1200px;
    }
}
```

### `max-width`

Applies styles when the viewport is at most the specified width.

```css
@media (max-width: 768px) {
    .container {
        padding: 20px;
    }
}
```

---

## 4. Media Queries Can Use Multiple Conditions

Conditions can be combined.

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        padding: 30px;
    }
}
```

The styles apply only when both conditions are satisfied.

---

## 5. Media Queries Are Not Limited to Width

Media queries can check different features.

Common examples include:

```css
@media (orientation: portrait) {
    /* styles */
}
```

```css
@media (orientation: landscape) {
    /* styles */
}
```

Other media features can also be used depending on the requirement.

---

## 6. Breakpoints Should Be Based on Content

A breakpoint is a point where the layout changes.

For example:

```css
@media (max-width: 768px) {
    .navigation {
        flex-direction: column;
    }
}
```

The exact value should not be chosen only because it represents a particular device.

Instead, choose a breakpoint where the content or layout actually starts to become difficult to use.

---

## 7. Mobile-First Design

A mobile-first approach starts with the smaller layout and progressively enhances it.

```css
.cards {
    display: grid;
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 1024px) {
    .cards {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

The layout progresses from:

```text
Mobile
1 column
   ↓
Tablet
2 columns
   ↓
Desktop
3 columns
```

---

## 8. Desktop-First Design

A desktop-first approach starts with the larger layout and modifies it for smaller screens.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

Both approaches can work.

The important thing is to use a consistent strategy within a project.

---

## 9. Media Queries Work With Flexbox

Media queries can change Flexbox behavior.

```css
.container {
    display: flex;
    flex-direction: row;
}

@media (max-width: 700px) {
    .container {
        flex-direction: column;
    }
}
```

This is useful for:

- Navigation
- Cards
- Hero sections
- Forms
- Button groups
- Content layouts

---

## 10. Media Queries Work With CSS Grid

Grid layouts can change the number of columns.

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .grid {
        grid-template-columns: 1fr;
    }
}
```

A layout can therefore change from:

```text
3 columns
    ↓
2 columns
    ↓
1 column
```

as the viewport becomes smaller.

---

## 11. Responsive Design Is More Than Changing Width

A responsive design may change:

```text
Layout
Spacing
Typography
Navigation
Alignment
Image size
Column count
Content order
Visibility
```

For example:

```css
.hero {
    display: flex;
    flex-direction: row;
}

@media (max-width: 768px) {
    .hero {
        flex-direction: column;
        text-align: center;
    }
}
```

The structure changes instead of simply becoming smaller.

---

## 12. Responsive Images Are Important

Images should generally be flexible.

```css
img {
    max-width: 100%;
    height: auto;
}
```

This helps prevent images from overflowing their containers.

A maximum width can also be used:

```css
img {
    width: 100%;
    max-width: 600px;
    height: auto;
}
```

---

## 13. Responsive Typography

Typography can change at different viewport sizes.

```css
h1 {
    font-size: 4rem;
}

@media (max-width: 768px) {
    h1 {
        font-size: 2.5rem;
    }
}
```

Fluid typography can also be used:

```css
h1 {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

This can reduce the need for multiple typography breakpoints.

---

## 14. Responsive Spacing

Spacing can also adapt.

```css
.section {
    padding: 100px 50px;
}

@media (max-width: 768px) {
    .section {
        padding: 50px 20px;
    }
}
```

Large layouts can use more spacing while smaller layouts can use more compact spacing.

---

## 15. Common Responsive Patterns

Some patterns appear repeatedly in responsive websites.

### Horizontal to Vertical

```text
Desktop:

A | B | C


Mobile:

A
B
C
```

### Multiple Columns to Fewer Columns

```text
Desktop:

A | B | C | D


Tablet:

A | B
C | D


Mobile:

A
B
C
D
```

### Sidebar to Stacked Content

```text
Desktop:

Main Content | Sidebar


Mobile:

Main Content
Sidebar
```

### Large Navigation to Compact Navigation

```text
Desktop:

Home | About | Projects | Contact


Mobile:

Home
About
Projects
Contact
```

---

## 16. Not Everything Requires a Media Query

Modern CSS provides features that can create responsive behavior automatically.

For example:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(250px, 1fr)
    );
}
```

Other useful functions include:

```css
min()
max()
clamp()
```

These can reduce the number of media queries required.

---

## 17. Container Queries Are Different

Media queries generally respond to the viewport.

Container queries can respond to the size of a component's container.

```css
.card-container {
    container-type: inline-size;
}

@container (min-width: 500px) {
    .card {
        display: flex;
    }
}
```

This is particularly useful for reusable components.

---

## 18. Test Between Breakpoints

Do not test only the exact breakpoint values.

If the CSS contains:

```css
@media (max-width: 768px) {
    /* styles */
}
```

test around the breakpoint:

```text
767px
768px
769px
```

Also test common viewport sizes and intermediate widths.

A layout can work at `768px` and still break at `820px`.

---

## 19. Avoid Too Many Breakpoints

A stylesheet does not need a media query for every device size.

Instead of:

```text
320px
375px
390px
414px
480px
600px
768px
820px
900px
1024px
1200px
1440px
```

prefer a small number of meaningful breakpoints when possible.

The breakpoints should represent actual layout changes.

---

## 20. Keep Important Content Accessible

Responsive design should not unnecessarily remove important information.

Avoid doing this:

```css
@media (max-width: 600px) {
    .important-content {
        display: none;
    }
}
```

unless there is a valid reason and an appropriate alternative exists.

Instead consider:

```text
Move it
   ↓
Stack it
   ↓
Collapse it appropriately
   ↓
Make it scrollable
   ↓
Keep it accessible
```

---

## 21. Media Queries Should Support Usability

The goal of responsive CSS is not simply to make a page fit.

The layout should remain:

```text
Readable
Usable
Accessible
Navigable
Visually clear
```

A technically fitting layout can still provide a poor user experience.

---

## 22. Combine CSS Features

Responsive layouts usually combine multiple CSS features.

For example:

```css
.layout {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 30px;
}

@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

Here:

```text
Grid
 +
Media Query
 +
Flexible Columns
 +
Gap
 =
Responsive Layout
```

Media queries are therefore one part of a larger responsive CSS strategy.

---

## 23. Use Flexible Units

Responsive designs commonly use flexible units such as:

```text
%
rem
em
vw
vh
fr
```

For example:

```css
.container {
    width: 90%;
}

.title {
    font-size: 5vw;
}
```

Flexible units can allow layouts to adapt naturally.

---

## 24. Use Relative Constraints

Functions such as `min()`, `max()`, and `clamp()` can create useful responsive constraints.

Example:

```css
.container {
    width: min(90%, 1200px);
}
```

Example:

```css
.title {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

These techniques can complement media queries.

---

## 25. Main Idea to Remember

The most important concept is:

```text
Media Query
     ↓
Detect a condition
     ↓
Apply different CSS
     ↓
Adapt the layout
     ↓
Improve usability
```

A media query does not automatically make a website responsive.

It provides the condition that allows the stylesheet to adapt.

---

## Quick Summary

```text
CSS Media Queries
│
├── Conditional CSS
│
├── min-width
├── max-width
├── orientation
├── Multiple conditions
│
├── Breakpoints
│
├── Mobile-first
├── Desktop-first
│
├── Flexbox
├── Grid
│
├── Responsive navigation
├── Responsive cards
├── Responsive forms
├── Responsive images
├── Responsive typography
├── Responsive spacing
│
├── min()
├── max()
├── clamp()
├── auto-fit
├── minmax()
│
├── Container queries
│
└── Testing and usability
```

---

> 💡 **Pro Tip:** Do not memorize a fixed list of device breakpoints. Understand how to recognize when content needs to change and then choose the simplest CSS technique that solves the problem.

---

> 💡 **Remember:** The purpose of responsive CSS is not to create a different website for every device. It is to create one flexible design that adapts gracefully to different available spaces.

---

## References

The following resources can be used to study CSS media queries and related responsive CSS concepts in more detail.

### MDN Web Docs

**CSS Media Queries**

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries

This is the primary reference for understanding CSS media queries, media features, conditions, and responsive styling.

---

**`@media` CSS at-rule**

https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media

This reference explains the syntax and behavior of the `@media` rule.

---

**Using media queries**

https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Media_queries/Using

This guide provides practical information about creating and using media queries.

---

### W3C

**CSS Conditional Rules Module**

https://www.w3.org/TR/css-conditional-3/

This specification describes conditional CSS rules, including the foundations behind media queries.

---

### Related CSS References

**CSS Flexible Box Layout**

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout

Useful for understanding how Flexbox can be combined with media queries to create responsive layouts.

---

**CSS Grid Layout**

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout

Useful for understanding responsive grid layouts and changing grid columns at different viewport sizes.

---

**CSS `clamp()`**

https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Values/clamp

Useful for creating fluid responsive values for properties such as typography and spacing.

---

**CSS Container Queries**

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_queries

Useful for understanding component-level responsive behavior based on container size rather than viewport size.

---

> 💡 **Note:** MDN should be the primary learning reference for this chapter, while the W3C specification can be used when you need the formal definition and technical details of CSS conditional rules.

---

## Quick Revision

Use this section to quickly revise the complete CSS Media Queries chapter.

---

### What Are Media Queries?

Media queries are CSS conditions that allow different styles to be applied depending on characteristics of the device or viewport.

```css
@media (max-width: 768px) {
    .container {
        padding: 20px;
    }
}
```

---

### Basic Syntax

```css
@media (condition) {
    selector {
        property: value;
    }
}
```

---

### Common Conditions

```css
@media (min-width: 768px) {
    /* At least 768px */
}
```

```css
@media (max-width: 768px) {
    /* At most 768px */
}
```

```css
@media (orientation: portrait) {
    /* Portrait */
}
```

```css
@media (orientation: landscape) {
    /* Landscape */
}
```

---

### Combining Conditions

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        padding: 30px;
    }
}
```

Multiple conditions can be combined using logical operators such as:

```text
and
not
or
```

---

### Common Responsive Breakpoints

There is no universal list of breakpoints.

Breakpoints should generally be chosen according to when the content or layout needs to change.

Example:

```css
@media (max-width: 768px) {
    /* Smaller layout */
}
```

---

### Mobile-First Approach

Start with the smaller layout and progressively add styles for larger screens.

```css
.cards {
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 1024px) {
    .cards {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

Pattern:

```text
Mobile
  ↓
Tablet
  ↓
Desktop
```

---

### Desktop-First Approach

Start with the larger layout and modify it for smaller screens.

```css
.cards {
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

Pattern:

```text
Desktop
  ↓
Tablet
  ↓
Mobile
```

---

### Media Queries With Flexbox

```css
.container {
    display: flex;
    flex-direction: row;
}

@media (max-width: 700px) {
    .container {
        flex-direction: column;
    }
}
```

Common transformation:

```text
Horizontal
     ↓
Vertical
```

---

### Media Queries With Grid

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .grid {
        grid-template-columns: 1fr;
    }
}
```

Common transformation:

```text
3 columns
    ↓
2 columns
    ↓
1 column
```

---

### Responsive Navigation

Desktop:

```text
Home | About | Projects | Contact
```

Mobile:

```text
Home
About
Projects
Contact
```

Example:

```css
.navigation {
    display: flex;
    gap: 20px;
}

@media (max-width: 600px) {
    .navigation {
        flex-direction: column;
    }
}
```

---

### Responsive Sidebar

Desktop:

```text
Main Content | Sidebar
```

Mobile:

```text
Main Content
Sidebar
```

Example:

```css
.layout {
    display: grid;
    grid-template-columns: 3fr 1fr;
}

@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

---

### Responsive Cards

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

Cards can progressively change:

```text
3 → 2 → 1
```

---

### Responsive Images

Use flexible image sizing:

```css
img {
    max-width: 100%;
    height: auto;
}
```

This helps prevent images from overflowing their containers.

---

### Responsive Typography

Using media queries:

```css
h1 {
    font-size: 4rem;
}

@media (max-width: 768px) {
    h1 {
        font-size: 2.5rem;
    }
}
```

Using fluid typography:

```css
h1 {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

---

### Responsive Spacing

```css
.section {
    padding: 100px 50px;
}

@media (max-width: 768px) {
    .section {
        padding: 50px 20px;
    }
}
```

Large screens can use more spacing while smaller screens can use more compact spacing.

---

### Common Responsive Patterns

Remember these common transformations:

```text
Horizontal
    ↓
Vertical
```

```text
Multiple Columns
    ↓
Fewer Columns
```

```text
Sidebar
    ↓
Stacked Content
```

```text
Large Navigation
    ↓
Compact Navigation
```

```text
Large Spacing
    ↓
Compact Spacing
```

```text
Large Typography
    ↓
Smaller Typography
```

---

### Flexible CSS Without Media Queries

Modern CSS can sometimes create responsive behavior automatically.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(250px, 1fr)
    );
}
```

Useful functions include:

```css
min()
max()
clamp()
```

---

### `clamp()`

```css
.title {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

Structure:

```text
clamp(minimum, preferred, maximum)
```

---

### `min()`

```css
.container {
    width: min(90%, 1200px);
}
```

The smaller value is used.

---

### Container Queries

Media queries generally respond to the viewport.

Container queries respond to the size of a component's container.

```css
.card-container {
    container-type: inline-size;
}

@container (min-width: 500px) {
    .card {
        display: flex;
    }
}
```

---

### Important Responsive Properties

Media queries commonly modify:

```text
display
flex-direction
grid-template-columns
width
max-width
padding
margin
gap
font-size
text-align
order
visibility
```

---

### Testing Responsive Layouts

Do not test only one device size.

Test:

```text
320px
375px
480px
600px
768px
900px
1024px
1200px
1440px
```

Also test around breakpoints.

For:

```css
@media (max-width: 768px)
```

test:

```text
767px
768px
769px
```

---

### Important Best Practices

```text
1. Choose breakpoints based on content.
2. Do not memorize device-specific breakpoints.
3. Use Flexbox for one-dimensional layouts.
4. Use Grid for two-dimensional layouts.
5. Keep images flexible.
6. Use relative and flexible units.
7. Consider clamp(), min(), max(), and minmax().
8. Avoid unnecessary media queries.
9. Test between breakpoints.
10. Keep important content accessible.
11. Focus on usability, not just fitting the screen.
12. Combine media queries with other CSS features.
```

---

### Main Concept

The complete idea can be remembered as:

```text
Media Query
     ↓
Detect Condition
     ↓
Apply CSS Rules
     ↓
Change Layout
     ↓
Adapt to Available Space
     ↓
Improve Usability
```

---

### One-Line Revision

> **CSS media queries allow CSS to conditionally adapt the presentation and layout of a webpage according to viewport or other media characteristics.**

---

> 💡 **Quick Memory Tip:** Think of responsive CSS as **condition → change → adapt**. The media query provides the condition, CSS properties provide the change, and the resulting layout adapts to the available space.