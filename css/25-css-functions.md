## Table of Contents

1. [Introduction](#introduction)
2. [What Are CSS Functions?](#what-are-css-functions)
3. [CSS Function Syntax](#css-function-syntax)
4. [Common CSS Functions](#common-css-functions)
5. [The `calc()` Function](#the-calc-function)
6. [The `min()` Function](#the-min-function)
7. [The `max()` Function](#the-max-function)
8. [The `clamp()` Function](#the-clamp-function)
9. [The `var()` Function](#the-var-function)
10. [URL Functions](#url-functions)
11. [Color Functions](#color-functions)
12. [Transform Functions](#transform-functions)
13. [Gradient Functions](#gradient-functions)
14. [Mathematical Functions](#mathematical-functions)
15. [Practical Examples](#practical-examples)
16. [Key Takeaways](#key-takeaways)
17. [References](#references)
18. [Quick Revision](#quick-revision)
19. [Best Practices](#best-practices)
20. [Common Mistakes](#common-mistakes)
21. [Interview Questions](#interview-questions)
22. [Practice Exercises](#practice-exercises)
23. [Related Topics](#related-topics)

---

## Introduction

CSS functions are special functions that allow you to calculate values, reuse values, work with colors, create transformations, and perform other operations directly in CSS.

A CSS function is written using a function name followed by parentheses.

```css
function-name();
```

For example:

```css
width: calc(100% - 20px);
```

In this example:

```text
calc()
  ↓
Performs a calculation
  ↓
100% - 20px
  ↓
Produces the final value
```

CSS functions help make styles more flexible and dynamic.

For example:

```css
.container {
    width: calc(100% - 40px);
}
```

Instead of using a fixed width, CSS calculates the value based on the available space.

### Why CSS Functions Are Useful

CSS functions can help you:

- Perform calculations
- Create responsive layouts
- Define minimum and maximum values
- Limit values within a range
- Reuse CSS variable values
- Work with colors
- Apply transformations
- Create gradients
- Use external resources

### Example

```css
.box {
    width: min(500px, 100%);
}
```

The `min()` function selects the smaller value.

This helps create responsive elements without writing additional media queries.

### Common CSS Functions

Some commonly used CSS functions include:

```text
calc()
→ Performs calculations

min()
→ Selects the smallest value

max()
→ Selects the largest value

clamp()
→ Keeps a value within a range

var()
→ Uses a CSS custom property value

url()
→ References an external resource
```

### CSS Functions and Dynamic Values

CSS functions allow values to respond to different conditions.

For example:

```css
.heading {
    font-size: clamp(1.5rem, 4vw, 3rem);
}
```

The `clamp()` function allows the font size to change while staying within a minimum and maximum limit.

```text
Minimum value
      ↓
    clamp()
      ↓
Preferred value
      ↓
Maximum value
```

This is useful for responsive designs.

### CSS Functions Improve Flexibility

Without functions, you may need to use fixed values.

```css
.container {
    width: 500px;
}
```

With functions, values can adapt.

```css
.container {
    width: min(500px, 100%);
}
```

This allows the element to adjust to different screen sizes.

### Important Points

```text
CSS Functions
│
├── Use a function name
│
├── Use parentheses
│
├── Accept values as arguments
│
├── Can perform calculations
│
├── Can create dynamic values
│
├── Help create responsive designs
│
└── Make CSS more flexible
```

> 💡 **Remember:** CSS functions allow you to perform operations and generate values directly in CSS. They are useful for creating flexible, responsive, and reusable styles.

---

## What Are CSS Functions?

CSS functions are special value expressions that perform an operation or generate a value for a CSS property.

A CSS function is usually written with:

```text
function-name(arguments)
```

The function receives one or more values, processes them, and produces a result that CSS can use.

### Basic Example

```css
.box {
    width: calc(100% - 20px);
}
```

In this example:

```text
calc()
   ↓
Receives values
   ↓
Performs calculation
   ↓
Produces final value
```

The result is then used as the value of the `width` property.

### Functions Generate CSS Values

CSS functions can generate values for different properties.

For example:

```css
.box {
    width: min(500px, 100%);
}
```

The `min()` function compares the provided values and returns the smaller value.

Another example:

```css
.heading {
    font-size: clamp(1rem, 5vw, 3rem);
}
```

The `clamp()` function creates a value that stays between a minimum and maximum limit.

### Functions Can Accept Arguments

Values inside the parentheses are called arguments.

For example:

```css
width: calc(100% - 20px);
```

The values inside:

```text
100% - 20px
```

are used by the `calc()` function.

Another example:

```css
font-size: clamp(1rem, 5vw, 3rem);
```

The `clamp()` function receives three values:

```text
1rem
  ↓
Minimum value

5vw
  ↓
Preferred value

3rem
  ↓
Maximum value
```

### Functions Help Create Dynamic Values

CSS functions can make values more flexible.

For example:

```css
.container {
    width: 500px;
}
```

This uses a fixed width.

However:

```css
.container {
    width: min(500px, 100%);
}
```

allows the width to adapt based on the available space.

```text
Available space
       ↓
Compare with 500px
       ↓
Use smaller value
```

### Functions Can Be Used in Different Areas of CSS

CSS functions are used for many purposes.

```text
CSS Functions
│
├── Calculations
│   → calc()
│
├── Minimum values
│   → min()
│
├── Maximum values
│   → max()
│
├── Value ranges
│   → clamp()
│
├── Custom properties
│   → var()
│
├── External resources
│   → url()
│
├── Colors
│   → rgb(), hsl()
│
├── Transformations
│   → translate(), rotate(), scale()
│
└── Gradients
    → linear-gradient()
```

### CSS Functions Are Not JavaScript Functions

CSS functions perform operations within CSS.

For example:

```css
width: calc(100% - 20px);
```

This calculation is handled as part of CSS value processing.

CSS functions do not work in the same way as JavaScript functions.

```text
CSS Function
→ Produces a CSS value

JavaScript Function
→ Executes JavaScript instructions
```

Both use parentheses, but they serve different purposes.

### Simple Examples

#### Using `calc()`

```css
.container {
    width: calc(100% - 40px);
}
```

#### Using `min()`

```css
.box {
    width: min(600px, 100%);
}
```

#### Using `max()`

```css
.box {
    width: max(300px, 50%);
}
```

#### Using `clamp()`

```css
.heading {
    font-size: clamp(1.5rem, 5vw, 4rem);
}
```

#### Using `var()`

```css
:root {
    --primary-color: blue;
}

.button {
    background-color: var(--primary-color);
}
```

### Important Points

```text
CSS Functions
│
├── Use a function name
│
├── Use parentheses
│
├── Can accept arguments
│
├── Perform operations or generate values
│
├── Can make CSS more flexible
│
├── Help create responsive designs
│
└── Are different from JavaScript functions
```

> 💡 **Remember:** CSS functions are special expressions that generate or calculate CSS values. They help make styles more flexible, reusable, and responsive.

---

## CSS Function Syntax

A CSS function is written using a function name followed by parentheses.

The general syntax is:

```css
function-name(arguments)
```

The values inside the parentheses are called arguments.

### Basic Structure

```text
function-name
     ↓
   ( arguments )
```

For example:

```css
width: calc(100% - 20px);
```

In this example:

```text
calc
 ↓
Function name

(100% - 20px)
      ↓
Arguments
```

The function processes the values inside the parentheses and produces a CSS value.

### Functions Are Used as Property Values

CSS functions are commonly used as values for CSS properties.

```css
.element {
    property: function-name(arguments);
}
```

For example:

```css
.container {
    width: calc(100% - 40px);
}
```

The `calc()` function generates the final value for the `width` property.

```text
width
  ↓
calc(100% - 40px)
  ↓
Calculated value
```

### Functions With Multiple Arguments

Some CSS functions accept multiple arguments.

For example:

```css
font-size: clamp(1rem, 5vw, 3rem);
```

The `clamp()` function receives three values.

```text
clamp(
    minimum,
    preferred,
    maximum
)
```

In this example:

```text
1rem
→ Minimum value

5vw
→ Preferred value

3rem
→ Maximum value
```

### Arguments Are Often Separated by Commas

Many CSS functions use commas to separate arguments.

For example:

```css
color: rgb(255, 0, 0);
```

The function receives three values.

```text
rgb(
    255,
    0,
    0
)
```

However, CSS function syntax depends on the specific function.

Some functions use mathematical operators instead.

For example:

```css
width: calc(100% - 20px);
```

### Functions Can Be Nested

A CSS function can sometimes be used inside another function.

For example:

```css
width: min(500px, calc(100% - 40px));
```

The calculation is processed as part of the `min()` function.

```text
min()
 │
 ├── 500px
 │
 └── calc()
      │
      └── 100% - 40px
```

The nested function produces a value that can be used by the outer function.

### Functions Can Use Different Units

CSS functions can work with different types of values.

For example:

```css
width: calc(100% - 20px);
```

This uses:

```text
100%
→ Percentage value

20px
→ Pixel value
```

Another example:

```css
font-size: clamp(1rem, 5vw, 3rem);
```

This uses different units for flexible responsive behavior.

```text
1rem
→ Minimum

5vw
→ Responsive value

3rem
→ Maximum
```

### Function Syntax Must Be Valid

The function name, parentheses, and arguments must be written correctly.

Correct:

```css
width: calc(100% - 20px);
```

Incorrect:

```css
width: calc 100% - 20px;
```

The parentheses are required.

Another incorrect example:

```css
width: calc(100% - 20px;
```

The closing parenthesis is missing.

### Whitespace Can Matter

Some CSS functions require correct spacing.

For example:

```css
width: calc(100% - 20px);
```

The mathematical operator is separated by spaces.

Incorrect:

```css
width: calc(100%-20px);
```

Correct spacing makes the expression valid and easier to read.

### General Pattern

```text
CSS Property
     ↓
property: function-name(arguments);
```

Examples:

```css
width: calc(100% - 20px);

width: min(500px, 100%);

width: max(300px, 50%);

font-size: clamp(1rem, 5vw, 3rem);

color: var(--primary-color);
```

### Important Points

```text
CSS Function Syntax
│
├── Function name
│
├── Parentheses
│
├── Arguments
│
├── Can accept multiple values
│
├── Can use different units
│
├── Can sometimes be nested
│
└── Must follow valid syntax
```

> 💡 **Remember:** CSS functions are written using a function name followed by parentheses. The values inside the parentheses are arguments that the function uses to generate or calculate a CSS value.

---

## Common CSS Functions

CSS provides many built-in functions for calculating values, controlling sizes, working with colors, applying transformations, and creating visual effects.

Different functions are used for different purposes.

### Common Function Categories

```text
CSS Functions
│
├── Mathematical Functions
│   ├── calc()
│   ├── min()
│   ├── max()
│   └── clamp()
│
├── Variable Functions
│   └── var()
│
├── URL Functions
│   └── url()
│
├── Color Functions
│   ├── rgb()
│   ├── rgba()
│   ├── hsl()
│   └── hsla()
│
├── Transform Functions
│   ├── translate()
│   ├── rotate()
│   └── scale()
│
└── Gradient Functions
    ├── linear-gradient()
    └── radial-gradient()
```

### `calc()`

The `calc()` function performs mathematical calculations.

```css
.container {
    width: calc(100% - 40px);
}
```

This allows CSS to calculate a value using different units.

```text
100%
  -
40px
  ↓
Calculated result
```

### `min()`

The `min()` function selects the smallest value from the provided values.

```css
.box {
    width: min(500px, 100%);
}
```

```text
500px
   vs
100%
   ↓
Use smaller value
```

### `max()`

The `max()` function selects the largest value.

```css
.box {
    width: max(300px, 50%);
}
```

```text
300px
   vs
50%
   ↓
Use larger value
```

### `clamp()`

The `clamp()` function keeps a value between a minimum and maximum limit.

```css
.heading {
    font-size: clamp(1rem, 5vw, 3rem);
}
```

```text
Minimum
  ↓
1rem

Preferred
  ↓
5vw

Maximum
  ↓
3rem
```

This is commonly used for responsive typography.

### `var()`

The `var()` function uses the value of a CSS custom property.

```css
:root {
    --primary-color: blue;
}

.button {
    background-color: var(--primary-color);
}
```

```text
Custom property
      ↓
--primary-color
      ↓
var(--primary-color)
      ↓
Used value
```

### `url()`

The `url()` function references an external resource.

```css
.hero {
    background-image: url("image.jpg");
}
```

It is commonly used for:

- Background images
- Fonts
- Other external resources

### Color Functions

CSS functions can create and define colors.

For example:

```css
.box {
    background-color: rgb(255, 0, 0);
}
```

Other common color functions include:

```text
rgb()
rgba()
hsl()
hsla()
```

Example:

```css
.box {
    background-color: hsl(200, 80%, 50%);
}
```

### Transform Functions

Transform functions change the position, size, or rotation of an element.

Example:

```css
.box {
    transform: translateX(50px);
}
```

Other common transform functions include:

```text
translate()
rotate()
scale()
skew()
```

Example:

```css
.box {
    transform: rotate(45deg);
}
```

### Gradient Functions

Gradient functions create smooth transitions between colors.

Example:

```css
.box {
    background: linear-gradient(red, blue);
}
```

Another example:

```css
.box {
    background: radial-gradient(red, yellow, blue);
}
```

Common gradient functions include:

```text
linear-gradient()
radial-gradient()
conic-gradient()
```

### Function Summary

| Function | Purpose |
|---|---|
| `calc()` | Performs calculations |
| `min()` | Selects the smallest value |
| `max()` | Selects the largest value |
| `clamp()` | Keeps a value within a range |
| `var()` | Uses a custom property value |
| `url()` | References an external resource |
| `rgb()` | Creates colors using RGB values |
| `hsl()` | Creates colors using HSL values |
| `translate()` | Moves an element |
| `rotate()` | Rotates an element |
| `scale()` | Changes the size of an element |
| `linear-gradient()` | Creates a linear gradient |
| `radial-gradient()` | Creates a radial gradient |

### Important Points

```text
Common CSS Functions
│
├── Perform calculations
│
├── Control responsive values
│
├── Reuse custom properties
│
├── Work with external resources
│
├── Create colors
│
├── Transform elements
│
└── Create gradients
```

> 💡 **Remember:** CSS provides many built-in functions for different purposes. Learning the most common functions helps you create flexible, responsive, and dynamic styles.

---

## The `calc()` Function

The CSS `calc()` function allows you to perform mathematical calculations directly in CSS.

It is useful when a CSS value needs to be calculated from other values.

### Basic Syntax

```css
property: calc(expression);
```

For example:

```css
width: calc(100% - 20px);
```

The browser calculates the expression and uses the result as the property value.

```text
100%
  -
20px
  ↓
Calculated value
```

### Why Use `calc()`?

The `calc()` function is useful when combining different values and units.

For example:

```css
.container {
    width: calc(100% - 40px);
}
```

The element uses the full available width minus `40px`.

Without `calc()`, combining these values directly would not be possible in the same way.

### Addition

The `+` operator can be used to add values.

```css
.box {
    width: calc(50% + 20px);
}
```

The final width is calculated by adding `20px` to `50%` of the available space.

### Subtraction

The `-` operator can be used to subtract values.

```css
.container {
    width: calc(100% - 40px);
}
```

This is one of the most common uses of `calc()`.

### Multiplication

The `*` operator can be used in supported calculations.

For example:

```css
.element {
    width: calc(100px * 2);
}
```

The calculation produces:

```text
100px × 2
   ↓
200px
```

### Division

The `/` operator can be used to divide values.

For example:

```css
.element {
    width: calc(200px / 2);
}
```

The calculation produces:

```text
200px ÷ 2
   ↓
100px
```

### Combining Different Units

One major advantage of `calc()` is the ability to combine compatible CSS units.

For example:

```css
.container {
    width: calc(100% - 50px);
}
```

This combines:

```text
100%
  ↓
Relative to available space

50px
  ↓
Fixed size
```

The browser calculates the final result based on the available space.

### Example: Full Width With Spacing

```html
<div class="container">
    Content
</div>
```

```css
.container {
    width: calc(100% - 40px);
    margin: 20px;
}
```

The width accounts for the horizontal spacing.

### Example: Two Columns

```css
.column {
    width: calc(50% - 20px);
}
```

This can be useful when two columns need a gap between them.

```text
50% of available space
        -
      20px
        ↓
Final column width
```

### Example: Responsive Layout

```css
.container {
    width: calc(100vw - 40px);
}
```

The width is based on the viewport width minus `40px`.

This creates a responsive value.

### Using Parentheses

Complex calculations can use parentheses.

```css
.element {
    width: calc((100% - 40px) / 2);
}
```

The calculation follows the grouping defined by the parentheses.

```text
100% - 40px
     ↓
Calculate first
     ↓
Divide result by 2
```

### Using `calc()` With Other Functions

The `calc()` function can be used with other CSS functions.

For example:

```css
.element {
    width: min(600px, calc(100% - 40px));
}
```

The `calc()` function calculates the available width, and `min()` selects the smaller value.

```text
min()
 │
 ├── 600px
 │
 └── calc(100% - 40px)
```

### Common Uses

The `calc()` function is commonly used for:

- Responsive widths
- Responsive heights
- Layout spacing
- Column calculations
- Combining fixed and relative units
- Dynamic positioning
- Complex size calculations

### Important Syntax Rule

Spaces should be used around the `+` and `-` operators.

Correct:

```css
width: calc(100% - 20px);
```

Incorrect:

```css
width: calc(100%-20px);
```

Using proper spacing helps ensure that the expression is parsed correctly.

### Important Points

```text
calc()
│
├── Performs calculations
│
├── Uses mathematical operators
│
├── Can combine compatible units
│
├── Useful for responsive layouts
│
├── Can be nested with other functions
│
└── Produces a CSS value
```

> 💡 **Remember:** The `calc()` function allows CSS values to be calculated dynamically. It is especially useful when combining relative values such as percentages with fixed values such as pixels.

---

## The `min()` Function

The CSS `min()` function returns the smallest value from a list of values.

It is useful for creating flexible and responsive CSS values.

### Basic Syntax

```css
property: min(value1, value2);
```

The browser compares the provided values and uses the smallest valid value.

For example:

```css
width: min(500px, 100%);
```

```text
500px
   vs
100%
   ↓
Use the smaller value
```

### Why Use `min()`?

The `min()` function is useful when an element should have a maximum practical size while still adapting to smaller screens.

For example:

```css
.container {
    width: min(800px, 100%);
}
```

On a large screen, the element can use `800px`.

On a smaller screen, it can use `100%` of the available width.

### Responsive Example

```css
.box {
    width: min(500px, 90%);
}
```

The browser compares:

```text
500px
   vs
90% of available space
```

The smaller value is used.

```text
Large screen
→ 500px may be smaller

Small screen
→ 90% may be smaller
```

This can help create responsive layouts.

### Using More Than Two Values

The `min()` function can compare multiple values.

```css
.element {
    width: min(800px, 90%, 100%);
}
```

The browser selects the smallest valid calculated value.

```text
Value 1
   │
Value 2
   │
Value 3
   ↓
Compare values
   ↓
Use smallest value
```

### Example With Font Size

The `min()` function can also be used with other properties.

```css
.heading {
    font-size: min(5vw, 3rem);
}
```

The browser uses the smaller value.

This can help prevent a responsive font size from becoming too large.

### Example With Height

```css
.section {
    height: min(600px, 80vh);
}
```

The smaller value between `600px` and `80vh` is used.

### Using `min()` With `calc()`

The `min()` function can be combined with `calc()`.

```css
.container {
    width: min(800px, calc(100% - 40px));
}
```

The browser:

```text
1. Calculates:
   100% - 40px

        ↓

2. Compares the result
   with 800px

        ↓

3. Uses the smaller value
```

### Practical Example: Responsive Container

```html
<div class="container">
    Content
</div>
```

```css
.container {
    width: min(900px, calc(100% - 40px));
    margin: 0 auto;
}
```

This creates a responsive container.

```text
Large screen
      ↓
Maximum width is limited

Small screen
      ↓
Width adapts to available space
```

### `min()` and `max-width`

In some situations, `min()` can provide an alternative way to express responsive sizing.

For example:

```css
.box {
    width: min(500px, 100%);
}
```

This expresses that the width should not exceed the smaller of the two calculated values.

### Common Uses

The `min()` function is commonly used for:

- Responsive widths
- Responsive heights
- Limiting font sizes
- Preventing elements from becoming too large
- Flexible layouts
- Combining fixed and relative values

### Important Points

```text
min()
│
├── Compares multiple values
│
├── Returns the smallest value
│
├── Supports responsive values
│
├── Can work with different compatible units
│
├── Can be combined with calc()
│
└── Helps limit maximum sizes
```

> 💡 **Remember:** The `min()` function compares the provided values and uses the smallest result. It is especially useful for creating responsive elements that should not grow beyond a certain size.

---

## The `max()` Function

The CSS `max()` function returns the largest value from a list of values.

It is useful when an element should maintain a minimum practical size while still allowing the value to adapt.

### Basic Syntax

```css
property: max(value1, value2);
```

The browser compares the provided values and uses the largest valid value.

For example:

```css
width: max(300px, 50%);
```

```text
300px
   vs
50%
   ↓
Use the larger value
```

### Why Use `max()`?

The `max()` function is useful when a value should not become too small.

For example:

```css
.container {
    width: max(300px, 50%);
}
```

The browser calculates both values and uses the larger one.

```text
If 50% < 300px
→ Use 300px

If 50% > 300px
→ Use 50%
```

### Responsive Example

```css
.box {
    width: max(300px, 60%);
}
```

On a smaller available space:

```text
300px may be larger
```

On a larger available space:

```text
60% may be larger
```

The larger calculated value is used.

### Using More Than Two Values

The `max()` function can compare multiple values.

```css
.element {
    width: max(300px, 50%, 20rem);
}
```

The browser compares all the calculated values and selects the largest one.

```text
Value 1
   │
Value 2
   │
Value 3
   ↓
Compare values
   ↓
Use largest value
```

### Example With Font Size

The `max()` function can help prevent responsive text from becoming too small.

```css
.heading {
    font-size: max(1.5rem, 4vw);
}
```

The browser uses the larger value.

```text
1.5rem
   vs
4vw
   ↓
Use larger value
```

This allows the text to respond to the viewport while maintaining a minimum size.

### Example With Height

```css
.section {
    height: max(400px, 70vh);
}
```

The browser uses whichever calculated value is larger.

### Using `max()` With `calc()`

The `max()` function can be combined with `calc()`.

```css
.container {
    width: max(300px, calc(100% - 40px));
}
```

The browser:

```text
1. Calculates:
   100% - 40px

        ↓

2. Compares the result
   with 300px

        ↓

3. Uses the larger value
```

### Practical Example

```html
<div class="container">
    Content
</div>
```

```css
.container {
    width: max(300px, 80%);
}
```

This ensures that the container attempts to maintain at least the larger of the calculated values.

### `max()` and Minimum Values

The `max()` function is useful when creating responsive values with a minimum limit.

For example:

```css
font-size: max(1rem, 3vw);
```

```text
Responsive value
      ↓
3vw

Minimum practical value
      ↓
1rem

Browser
      ↓
Uses larger value
```

### Common Uses

The `max()` function is commonly used for:

- Preventing values from becoming too small
- Responsive font sizes
- Minimum dimensions
- Flexible layouts
- Responsive heights
- Combining fixed and relative values

### Important Points

```text
max()
│
├── Compares multiple values
│
├── Returns the largest value
│
├── Helps maintain minimum values
│
├── Supports responsive values
│
├── Can work with compatible units
│
├── Can be combined with calc()
│
└── Produces a CSS value
```

### `min()` vs `max()`

```text
min()
→ Returns the smallest value

max()
→ Returns the largest value
```

Example:

```css
width: min(500px, 100%);
```

```text
Use the smaller value
```

Example:

```css
width: max(300px, 50%);
```

```text
Use the larger value
```

> 💡 **Remember:** The `max()` function compares the provided values and uses the largest result. It is useful when creating responsive values that should not become smaller than a practical limit.

---

## The `clamp()` Function

The CSS `clamp()` function limits a value between a minimum value and a maximum value.

It is especially useful for creating responsive values that can grow or shrink within a controlled range.

### Basic Syntax

```css
property: clamp(minimum, preferred, maximum);
```

The `clamp()` function accepts three values:

```text
Minimum value
      ↓
Preferred value
      ↓
Maximum value
```

For example:

```css
font-size: clamp(1rem, 5vw, 3rem);
```

### How `clamp()` Works

The browser calculates the preferred value and keeps it within the minimum and maximum limits.

```text
Preferred value
      │
      ▼
Is it smaller than minimum?
      │
      ├── Yes → Use minimum
      │
      └── No
           │
           ▼
Is it larger than maximum?
      │
      ├── Yes → Use maximum
      │
      └── No → Use preferred value
```

### Minimum Value

The first value is the minimum allowed value.

```css
font-size: clamp(1rem, 5vw, 3rem);
```

```text
1rem
 ↓
Minimum value
```

The final value will not become smaller than `1rem`.

### Preferred Value

The second value is the preferred value.

```css
font-size: clamp(1rem, 5vw, 3rem);
```

```text
5vw
 ↓
Preferred value
```

This value can change based on conditions such as viewport size.

### Maximum Value

The third value is the maximum allowed value.

```css
font-size: clamp(1rem, 5vw, 3rem);
```

```text
3rem
 ↓
Maximum value
```

The final value will not become larger than `3rem`.

### Responsive Font Size Example

```css
.heading {
    font-size: clamp(1.5rem, 5vw, 4rem);
}
```

```text
Small screen
→ Use minimum value when needed

Medium screen
→ Preferred value can adjust

Large screen
→ Maximum value prevents excessive growth
```

This makes `clamp()` useful for responsive typography.

### Responsive Width Example

```css
.container {
    width: clamp(300px, 80%, 900px);
}
```

The width:

```text
Cannot be smaller than
→ 300px

Prefers
→ 80%

Cannot be larger than
→ 900px
```

### Using `clamp()` With Different Units

The values can use different compatible units.

For example:

```css
font-size: clamp(1rem, 4vw, 3rem);
```

This combines:

```text
1rem
→ Minimum size

4vw
→ Responsive size

3rem
→ Maximum size
```

### Using `clamp()` With `calc()`

The preferred value can include calculations.

```css
.heading {
    font-size: clamp(
        1rem,
        calc(1rem + 2vw),
        3rem
    );
}
```

The browser calculates the preferred value and then applies the minimum and maximum limits.

```text
Minimum
   ↓
1rem

Preferred
   ↓
calc(1rem + 2vw)

Maximum
   ↓
3rem
```

### `clamp()` Compared With `min()` and `max()`

```text
min()
→ Selects the smallest value

max()
→ Selects the largest value

clamp()
→ Keeps a value between minimum and maximum limits
```

Conceptually:

```text
max(minimum, min(preferred, maximum))
```

The preferred value cannot go below the minimum or above the maximum.

### Common Uses

The `clamp()` function is commonly used for:

- Responsive font sizes
- Responsive spacing
- Responsive widths
- Responsive heights
- Flexible layouts
- Limiting element sizes
- Creating fluid designs

### Example: Responsive Padding

```css
.section {
    padding: clamp(1rem, 5vw, 5rem);
}
```

The padding can grow based on the viewport while staying within the defined limits.

### Important Points

```text
clamp()
│
├── Accepts three values
│
├── Defines a minimum value
│
├── Defines a preferred value
│
├── Defines a maximum value
│
├── Helps create responsive values
│
├── Prevents values from becoming too small
│
├── Prevents values from becoming too large
│
└── Can be combined with calc()
```

> 💡 **Remember:** The `clamp()` function creates flexible values with clear limits. It is especially useful when you want a value to respond to screen size without becoming too small or too large.

---

## The `var()` Function

The CSS `var()` function is used to access the value of a CSS custom property.

CSS custom properties are reusable values that are defined using names starting with two hyphens.

### Basic Syntax

```css
var(--property-name)
```

A custom property can be defined like this:

```css
:root {
    --primary-color: blue;
}
```

The `var()` function can then use its value:

```css
.button {
    background-color: var(--primary-color);
}
```

```text
--primary-color
       ↓
    blue
       ↓
var(--primary-color)
       ↓
Used as CSS value
```

### Defining a Custom Property

Custom properties begin with:

```text
--
```

Example:

```css
:root {
    --primary-color: blue;
    --secondary-color: gray;
}
```

These values can then be reused using `var()`.

```css
.button {
    background-color: var(--primary-color);
}
```

### Why Use `var()`?

The `var()` function helps make CSS more reusable and easier to maintain.

Without custom properties:

```css
.button {
    background-color: blue;
}

.card {
    border-color: blue;
}

.heading {
    color: blue;
}
```

With a custom property:

```css
:root {
    --primary-color: blue;
}

.button {
    background-color: var(--primary-color);
}

.card {
    border-color: var(--primary-color);
}

.heading {
    color: var(--primary-color);
}
```

```text
One value
    ↓
Reusable in multiple places
```

### Changing a Reusable Value

Suppose the primary color needs to change.

```css
:root {
    --primary-color: green;
}
```

Every place using:

```css
var(--primary-color)
```

can automatically use the new value.

```text
Change custom property
        ↓
All var() references update
```

### Fallback Values

The `var()` function can include a fallback value.

Basic syntax:

```css
var(--property-name, fallback-value)
```

Example:

```css
.button {
    background-color: var(--primary-color, blue);
}
```

If `--primary-color` is not available, CSS uses:

```text
blue
```

as the fallback value.

### Example With a Missing Property

```css
.box {
    color: var(--text-color, black);
}
```

If:

```css
--text-color
```

is not defined, the browser uses:

```css
black
```

### Custom Properties Can Store Different Values

Custom properties are not limited to colors.

They can store values such as:

```text
Colors
Sizes
Spacing
Font families
Border values
Shadows
```

Example:

```css
:root {
    --primary-color: blue;
    --spacing: 20px;
    --border-radius: 8px;
}
```

Usage:

```css
.card {
    background-color: var(--primary-color);
    padding: var(--spacing);
    border-radius: var(--border-radius);
}
```

### Scope of Custom Properties

Custom properties follow the CSS cascade and can be defined in different scopes.

For global values:

```css
:root {
    --primary-color: blue;
}
```

For values limited to a specific element:

```css
.card {
    --card-color: white;
}
```

The custom property can be used within the appropriate scope.

### Overriding a Custom Property

A custom property can be overridden.

```css
:root {
    --primary-color: blue;
}

.dark-theme {
    --primary-color: white;
}
```

Elements inside `.dark-theme` can use the updated value.

```css
.button {
    background-color: var(--primary-color);
}
```

```text
Default value
→ blue

Inside .dark-theme
→ white
```

### Using `var()` With Other Functions

The `var()` function can be used inside other CSS functions.

Example:

```css
:root {
    --spacing: 20px;
}

.container {
    width: calc(100% - var(--spacing));
}
```

```text
calc()
  │
  ├── 100%
  │
  └── var(--spacing)
         ↓
       20px
```

The custom property value becomes part of the calculation.

### Practical Example

```css
:root {
    --primary-color: #2563eb;
    --spacing: 1rem;
    --radius: 8px;
}

.button {
    background-color: var(--primary-color);
    padding: var(--spacing);
    border-radius: var(--radius);
}
```

This makes common values easier to reuse and update.

### Important Points

```text
var()
│
├── Accesses CSS custom properties
│
├── Uses properties starting with --
│
├── Makes values reusable
│
├── Supports fallback values
│
├── Follows CSS scope and cascade
│
├── Allows values to be overridden
│
└── Can be used with other CSS functions
```

> 💡 **Remember:** The `var()` function allows you to reuse values stored in CSS custom properties. This makes styles easier to maintain, update, and organize.

---

## URL Functions

The CSS `url()` function is used to reference an external resource.

It provides the location of a resource that CSS needs to load and use.

### Basic Syntax

```css
url("path-to-resource")
```

For example:

```css
background-image: url("image.jpg");
```

```text
url()
  ↓
Resource location
  ↓
Browser loads resource
  ↓
Resource is used in CSS
```

### Using `url()` With Background Images

One of the most common uses of `url()` is loading background images.

```css
.hero {
    background-image: url("background.jpg");
}
```

The browser loads the image and uses it as the background.

### Relative URLs

A relative URL references a resource based on the location of the CSS file.

Example:

```css
background-image: url("images/photo.jpg");
```

The browser looks for the resource relative to the CSS file's location.

### Absolute URLs

An absolute URL provides the complete resource location.

Example:

```css
background-image: url("https://example.com/image.jpg");
```

This references a resource using its full address.

### Quoted and Unquoted URLs

URLs can be written with quotes.

```css
background-image: url("image.jpg");
```

They can also be written without quotes in many cases.

```css
background-image: url(image.jpg);
```

Using quotes is often clearer, especially when the path contains special characters.

### Using `url()` With Fonts

The `url()` function can also be used to load font files.

Example:

```css
@font-face {
    font-family: "CustomFont";
    src: url("fonts/custom-font.woff2");
}
```

The browser loads the font file from the specified location.

### Using `url()` With Other CSS Features

The `url()` function can be used with different CSS properties and rules.

Examples include:

- `background-image`
- `@font-face`
- `cursor`
- `list-style-image`

### Example: Custom Cursor

```css
.element {
    cursor: url("cursor.png"), pointer;
}
```

The browser attempts to use the custom cursor image.

If it cannot be used, the fallback cursor is:

```css
pointer
```

### Example: List Image

```css
ul {
    list-style-image: url("bullet.png");
}
```

The image can be used as the list marker.

### URL Paths

A URL can point to resources in different locations.

Example:

```text
image.jpg
```

Resource in the same directory.

```text
images/image.jpg
```

Resource inside an `images` directory.

```text
../image.jpg
```

Resource in the parent directory.

### Example Project Structure

```text
project/
│
├── index.html
│
├── css/
│   └── style.css
│
└── images/
    └── background.jpg
```

Inside `style.css`:

```css
.hero {
    background-image: url("../images/background.jpg");
}
```

The path moves:

```text
css/
 ↓
..
 ↓
project/
 ↓
images/
 ↓
background.jpg
```

### Common Uses

The `url()` function is commonly used for:

```text
External Resources
│
├── Background images
│
├── Font files
│
├── Custom cursor images
│
└── List marker images
```

### Important Points

```text
url()
│
├── References external resources
│
├── Can use relative paths
│
├── Can use absolute URLs
│
├── Commonly loads images
│
├── Can load font files
│
├── Can be used for custom cursors
│
└── Uses the resource location as its argument
```

> 💡 **Remember:** The `url()` function tells CSS where to find an external resource. It is commonly used for images, fonts, cursors, and other files used by CSS.