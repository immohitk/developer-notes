## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Transforms?](#what-are-css-transforms)
- [Why Are CSS Transforms Important?](#why-are-css-transforms-important)
- [Transform Syntax](#transform-syntax)
- [Translate](#translate)
- [Translate X](#translate-x)
- [Translate Y](#translate-y)
- [Translate 3D](#translate-3d)
- [Scale](#scale)
- [Scale X](#scale-x)
- [Scale Y](#scale-y)
- [Rotate](#rotate)
- [Rotate X](#rotate-x)
- [Rotate Y](#rotate-y)
- [Rotate Z](#rotate-z)
- [Skew](#skew)
- [Skew X](#skew-x)
- [Skew Y](#skew-y)
- [Transform Origin](#transform-origin)
- [Multiple Transforms](#multiple-transforms)
- [2D Transforms](#2d-transforms)
- [3D Transforms](#3d-transforms)
- [Perspective](#perspective)
- [Transform Style](#transform-style)
- [Backface Visibility](#backface-visibility)
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

CSS Transforms are used to visually modify an element without changing its normal position in the document flow.

They allow you to **move, resize, rotate, and distort elements** using the CSS `transform` property.

For example:

```css
.box {
    transform: rotate(45deg);
}
```

This rotates the element by `45deg`.

Another example:

```css
.box {
    transform: scale(1.2);
}
```

This makes the element visually larger.

CSS Transforms are commonly used to create:

- Hover effects
- Interactive UI elements
- Smooth visual effects
- Card effects
- Image effects
- 2D transformations
- 3D transformations
- Animation effects

> 💡 **Tip:** CSS Transforms are especially useful when you want to visually change an element while keeping its original place in the document layout.

In this chapter, you will learn how to use different CSS transform functions, control the transformation point, combine multiple transformations, and create both 2D and 3D effects.

---

### Example

```html
<div class="box">Transform Me</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: rotate(10deg);
}
```

The element is visually rotated without changing the normal document flow around it.

---

### Basic Syntax

The basic syntax for CSS transforms is:

```css
selector {
    transform: function(value);
}
```

For example:

```css
.box {
    transform: translateX(50px);
}
```

Here:

- `transform` is the CSS property.
- `translateX()` is the transform function.
- `50px` is the value applied to the transformation.

> 💡 **Remember:** The `transform` property can contain one or multiple transform functions.

---

## What Are CSS Transforms?

CSS Transforms allow you to visually modify an element in two-dimensional or three-dimensional space.

Using the `transform` property, you can:

- Move an element
- Resize an element
- Rotate an element
- Skew an element
- Create 2D effects
- Create 3D effects

### Basic Example

```css
.box {
    transform: translateX(50px);
}
```

This moves the element `50px` horizontally.

You can also rotate an element:

```css
.box {
    transform: rotate(45deg);
}
```

This rotates the element by `45deg`.

### Transform Functions

CSS provides different transform functions for different purposes:

| Function | Purpose |
|----------|---------|
| `translate()` | Moves an element |
| `scale()` | Changes the size of an element |
| `rotate()` | Rotates an element |
| `skew()` | Distorts an element |
| `matrix()` | Applies a combined transformation |
| `translate3d()` | Moves an element in 3D space |
| `rotateX()` | Rotates around the X-axis |
| `rotateY()` | Rotates around the Y-axis |
| `rotateZ()` | Rotates around the Z-axis |

### Combining Transforms

Multiple transform functions can be used together:

```css
.box {
    transform: translateX(50px) rotate(20deg) scale(1.1);
}
```

This applies multiple transformations to the same element.

> 💡 **Tip:** Transform functions can be combined to create more advanced visual effects.

> 💡 **Remember:** The order of transform functions matters because each transformation is applied as part of the transformation sequence.

---

## Why Are CSS Transforms Important?

CSS Transforms are important because they make it possible to create visual changes and interactive effects without requiring complicated layout techniques.

They are commonly used for:

- Creating hover effects
- Moving elements visually
- Scaling buttons and cards
- Rotating icons and images
- Creating interactive components
- Building 2D effects
- Building 3D effects
- Supporting animations and transitions

### Example

```css
.card {
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-10px);
}
```

When the user hovers over the card, it smoothly moves upward.

### Transforms and Layout

Transforms are different from traditional layout properties.

For example:

```css
.box {
    transform: translateX(50px);
}
```

The element is visually moved, but its original position in the document flow is preserved.

This makes transforms particularly useful for visual effects and animations.

### Transforms and Animations

Transforms work well with CSS transitions and animations.

For example:

```css
.button {
    transition: transform 0.2s ease;
}

.button:hover {
    transform: scale(1.05);
}
```

This creates a smooth scaling effect when the user moves the pointer over the button.

> 💡 **Tip:** Use transforms for visual movement and effects instead of using positioning properties when you do not actually need to change the layout.

> 💡 **Remember:** CSS Transforms are especially useful for interactive interfaces because they can be combined with transitions and animations to create smooth visual feedback.

---

## Transform Syntax

The `transform` property is used to apply transformations to an element.

### Basic Syntax

```css
selector {
    transform: function(value);
}
```

For example:

```css
.box {
    transform: rotate(45deg);
}
```

Here:

- `transform` is the CSS property.
- `rotate()` is the transform function.
- `45deg` is the value passed to the function.

### Using Translate

```css
.box {
    transform: translateX(50px);
}
```

This moves the element `50px` along the X-axis.

### Using Scale

```css
.box {
    transform: scale(1.2);
}
```

This increases the visual size of the element.

### Using Rotate

```css
.box {
    transform: rotate(45deg);
}
```

This rotates the element by `45deg`.

### Using Skew

```css
.box {
    transform: skewX(20deg);
}
```

This skews the element along the X-axis.

### Multiple Transform Functions

Multiple transform functions can be combined in a single declaration:

```css
.box {
    transform: translateX(50px) rotate(20deg) scale(1.1);
}
```

The order of the functions matters because the transformations are applied as a sequence.

> 💡 **Tip:** The `transform` property accepts one or more transform functions.

> 💡 **Remember:** Transform functions such as `translate()`, `scale()`, `rotate()`, and `skew()` provide different ways to visually modify an element.

---

## Translate

The `translate()` function moves an element from its current position along the X-axis, Y-axis, or both axes.

It is commonly used to create movement effects without changing the element's normal position in the document flow.

### Basic Syntax

```css
selector {
    transform: translate(x, y);
}
```

For example:

```css
.box {
    transform: translate(50px, 20px);
}
```

This moves the element:

- `50px` to the right along the X-axis.
- `20px` downward along the Y-axis.

### Translate on the X-Axis

You can move an element horizontally by providing only the first value:

```css
.box {
    transform: translate(50px);
}
```

This moves the element `50px` to the right.

A negative value moves it to the left:

```css
.box {
    transform: translate(-50px);
}
```

### Translate on Both Axes

You can specify separate X and Y values:

```css
.box {
    transform: translate(100px, 50px);
}
```

Here:

```text
100px → X-axis
50px  → Y-axis
```

### Using Percentage Values

`translate()` can also use percentage values:

```css
.box {
    transform: translate(50%, 20%);
}
```

Percentage values are calculated relative to the element's own dimensions.

### Negative Values

Negative values can be used to move an element in the opposite direction:

```css
.box {
    transform: translate(-30px, -20px);
}
```

This moves the element:

```text
30px ← left
20px ↑ up
```

### Practical Example

```html
<div class="box">Move Me</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: translate(50px, 30px);
}
```

The box is visually moved `50px` to the right and `30px` downward.

> 💡 **Tip:** Use `translate()` when you need to move an element along the X and Y axes together.

> 💡 **Remember:** `translate()` visually moves an element without changing its original position in the normal document flow.

---

## Translate X

The `translateX()` function moves an element horizontally along the X-axis.

It is useful when you want to move an element to the left or right without changing its normal position in the document flow.

### Basic Syntax

```css
selector {
    transform: translateX(value);
}
```

For example:

```css
.box {
    transform: translateX(50px);
}
```

This moves the element `50px` to the right.

### Moving to the Right

Positive values move the element to the right:

```css
.box {
    transform: translateX(100px);
}
```

The element is visually moved `100px` toward the right.

### Moving to the Left

Negative values move the element to the left:

```css
.box {
    transform: translateX(-100px);
}
```

The element is visually moved `100px` toward the left.

### Using Percentage Values

You can also use percentage values:

```css
.box {
    transform: translateX(50%);
}
```

The percentage is calculated relative to the element's own width.

### Practical Example

```html
<div class="box">Move Me</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: translateX(80px);
}
```

The box is visually moved `80px` to the right.

### Hover Effect

`translateX()` is commonly used with transitions to create interactive effects:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateX(20px);
}
```

When the user hovers over the element, it smoothly moves `20px` to the right.

### Negative Hover Movement

You can also move an element toward the left:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateX(-20px);
}
```

> 💡 **Tip:** Use `translateX()` when you only need horizontal movement. It is simpler and clearer than using `translate()` when the Y-axis does not need to change.

> 💡 **Remember:** Positive values move the element to the right, while negative values move it to the left.

---

## Translate Y

The `translateY()` function moves an element vertically along the Y-axis.

It is useful when you want to move an element upward or downward without changing its normal position in the document flow.

### Basic Syntax

```css
selector {
    transform: translateY(value);
}
```

For example:

```css
.box {
    transform: translateY(50px);
}
```

This moves the element `50px` downward.

### Moving Down

Positive values move the element downward:

```css
.box {
    transform: translateY(100px);
}
```

The element is visually moved `100px` toward the bottom.

### Moving Up

Negative values move the element upward:

```css
.box {
    transform: translateY(-100px);
}
```

The element is visually moved `100px` toward the top.

### Using Percentage Values

You can also use percentage values:

```css
.box {
    transform: translateY(50%);
}
```

The percentage is calculated relative to the element's own height.

### Practical Example

```html
<div class="box">Move Me</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: translateY(50px);
}
```

The box is visually moved `50px` downward.

### Hover Effect

`translateY()` is commonly used with transitions to create smooth vertical movement:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateY(-10px);
}
```

When the user hovers over the element, it smoothly moves `10px` upward.

### Moving Down on Hover

You can also move an element downward:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: translateY(10px);
}
```

> 💡 **Tip:** Use `translateY()` when you only need vertical movement. It is clearer than using `translate()` when the X-axis does not need to change.

> 💡 **Remember:** Positive values move the element downward, while negative values move it upward.

---

## Translate 3D

The `translate3d()` function moves an element along the **X-axis, Y-axis, and Z-axis**.

It is used for three-dimensional transformations when you need to control horizontal movement, vertical movement, and depth.

### Basic Syntax

```css
selector {
    transform: translate3d(x, y, z);
}
```

For example:

```css
.box {
    transform: translate3d(50px, 30px, 20px);
}
```

Here:

```text
50px → X-axis
30px → Y-axis
20px → Z-axis
```

### X-Axis

The first value controls horizontal movement:

```css
.box {
    transform: translate3d(50px, 0, 0);
}
```

This moves the element `50px` to the right.

A negative value moves it to the left:

```css
.box {
    transform: translate3d(-50px, 0, 0);
}
```

### Y-Axis

The second value controls vertical movement:

```css
.box {
    transform: translate3d(0, 50px, 0);
}
```

This moves the element `50px` downward.

A negative value moves it upward:

```css
.box {
    transform: translate3d(0, -50px, 0);
}
```

### Z-Axis

The third value controls movement along the Z-axis:

```css
.box {
    transform: translate3d(0, 0, 50px);
}
```

The Z-axis represents movement in depth.

To see the depth effect clearly, 3D perspective is commonly used:

```css
.container {
    perspective: 800px;
}

.box {
    transform: translate3d(0, 0, 50px);
}
```

### Using All Three Axes

You can move an element along all three axes:

```css
.box {
    transform: translate3d(50px, 30px, 40px);
}
```

This applies:

```text
50px → Horizontal movement
30px → Vertical movement
40px → Depth movement
```

### Practical Example

```html
<div class="container">
    <div class="box">Move Me</div>
</div>
```

```css
.container {
    perspective: 800px;
}

.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: translate3d(50px, 20px, 40px);
}
```

The element is transformed along all three axes.

### Combining with Other Transforms

`translate3d()` can be combined with other transform functions:

```css
.box {
    transform: translate3d(50px, 20px, 30px)
               rotateY(20deg)
               scale(1.1);
}
```

This moves, rotates, and scales the element.

> 💡 **Tip:** Use `translate3d()` when you need to control movement along all three axes. For simple horizontal or vertical movement, `translateX()` or `translateY()` is usually clearer.

> 💡 **Remember:** The three values represent **X, Y, and Z** movement respectively.

---

## Scale

The `scale()` function changes the visual size of an element.

It can make an element **larger or smaller** while keeping its original position in the document flow.

### Basic Syntax

```css
selector {
    transform: scale(value);
}
```

For example:

```css
.box {
    transform: scale(1.5);
}
```

This makes the element visually **1.5 times larger** than its original size.

### Scaling Up

Values greater than `1` increase the size of the element:

```css
.box {
    transform: scale(1.5);
}
```

The element becomes `1.5` times its original size.

Another example:

```css
.box {
    transform: scale(2);
}
```

This makes the element twice its original visual size.

### Scaling Down

Values between `0` and `1` make the element smaller:

```css
.box {
    transform: scale(0.8);
}
```

The element becomes `80%` of its original visual size.

For example:

```css
.box {
    transform: scale(0.5);
}
```

This makes the element half its original visual size.

### Scaling on Both Axes

The `scale()` function can accept two values:

```css
.box {
    transform: scale(1.5, 0.8);
}
```

Here:

```text
1.5 → X-axis scaling
0.8 → Y-axis scaling
```

The element becomes wider while becoming shorter.

### Practical Example

```html
<div class="box">Scale Me</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: scale(1.2);
}
```

The element is visually increased to `1.2` times its original size.

### Hover Effect

`scale()` is commonly used to create hover effects:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(1.1);
}
```

When the user hovers over the element, it smoothly becomes slightly larger.

### Scaling Down on Hover

You can also create a shrinking effect:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(0.9);
}
```

The element becomes slightly smaller when hovered.

### Scale and Transform Origin

Scaling occurs around the element's transform origin.

By default, the transform origin is generally the center:

```css
.box {
    transform: scale(1.5);
}
```

You can change the origin:

```css
.box {
    transform-origin: top left;
    transform: scale(1.5);
}
```

Now the element scales outward from its top-left corner.

> 💡 **Tip:** Small scale changes such as `1.05` or `1.1` are commonly used for buttons, cards, and images because they provide subtle visual feedback.

> 💡 **Remember:** Values greater than `1` enlarge the element, values between `0` and `1` shrink it, and `1` keeps its original scale.

---

## Scale X

The `scaleX()` function changes the visual width of an element by scaling it along the **X-axis**.

It affects the element's horizontal size while keeping its vertical scale unchanged.

### Basic Syntax

```css
selector {
    transform: scaleX(value);
}
```

For example:

```css
.box {
    transform: scaleX(1.5);
}
```

This makes the element visually `1.5` times wider than its original width.

### Scaling Up Horizontally

Values greater than `1` increase the element's width:

```css
.box {
    transform: scaleX(2);
}
```

The element becomes twice as wide.

### Scaling Down Horizontally

Values between `0` and `1` reduce the element's width:

```css
.box {
    transform: scaleX(0.5);
}
```

The element becomes half as wide.

### Using `scaleX(1)`

A value of `1` keeps the original horizontal scale:

```css
.box {
    transform: scaleX(1);
}
```

The element keeps its original width.

### Negative Values

Negative values can flip the element horizontally:

```css
.box {
    transform: scaleX(-1);
}
```

This mirrors the element along the X-axis.

For example, an image can be flipped horizontally:

```css
.image {
    transform: scaleX(-1);
}
```

### Practical Example

```html
<div class="box">Scale X</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: scaleX(1.5);
}
```

The element becomes visually wider without changing its height.

### Hover Effect

`scaleX()` can be combined with a transition:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scaleX(1.1);
}
```

When the user hovers over the element, its width smoothly increases.

### Comparing `scale()` and `scaleX()`

`scale()` can control both the X and Y axes:

```css
.box {
    transform: scale(1.2);
}
```

`scaleX()` only affects the X-axis:

```css
.box {
    transform: scaleX(1.2);
}
```

Therefore, `scaleX()` is useful when you want to change the width without changing the height.

> 💡 **Tip:** Use `scaleX()` when you specifically need horizontal scaling and want to keep the vertical size unchanged.

> 💡 **Remember:** Values greater than `1` make the element wider, values between `0` and `1` make it narrower, and negative values can mirror the element horizontally.

---

## Scale Y

The `scaleY()` function changes the visual height of an element by scaling it along the **Y-axis**.

It affects the element's vertical size while keeping its horizontal scale unchanged.

### Basic Syntax

```css
selector {
    transform: scaleY(value);
}
```

For example:

```css
.box {
    transform: scaleY(1.5);
}
```

This makes the element visually `1.5` times taller than its original height.

### Scaling Up Vertically

Values greater than `1` increase the element's height:

```css
.box {
    transform: scaleY(2);
}
```

The element becomes twice as tall.

### Scaling Down Vertically

Values between `0` and `1` reduce the element's height:

```css
.box {
    transform: scaleY(0.5);
}
```

The element becomes half as tall.

### Using `scaleY(1)`

A value of `1` keeps the original vertical scale:

```css
.box {
    transform: scaleY(1);
}
```

The element keeps its original height.

### Negative Values

Negative values can flip the element vertically:

```css
.box {
    transform: scaleY(-1);
}
```

This mirrors the element along the Y-axis.

For example, an image can be flipped vertically:

```css
.image {
    transform: scaleY(-1);
}
```

### Practical Example

```html
<div class="box">Scale Y</div>
```

```css
.box {
    width: 150px;
    height: 100px;
    background: steelblue;
    transform: scaleY(1.5);
}
```

The element becomes visually taller without changing its horizontal size.

### Hover Effect

`scaleY()` can be combined with a transition:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scaleY(1.1);
}
```

When the user hovers over the element, its height smoothly increases.

### Comparing `scale()` and `scaleY()`

`scale()` can control both the X and Y axes:

```css
.box {
    transform: scale(1.2);
}
```

`scaleY()` only affects the Y-axis:

```css
.box {
    transform: scaleY(1.2);
}
```

Therefore, `scaleY()` is useful when you want to change the height without changing the width.

> 💡 **Tip:** Use `scaleY()` when you specifically need vertical scaling and want to keep the horizontal size unchanged.

> 💡 **Remember:** Values greater than `1` make the element taller, values between `0` and `1` make it shorter, and negative values can mirror the element vertically.

---

## Rotate

The `rotate()` function rotates an element around its **transform origin**.

It is commonly used to rotate elements clockwise or counterclockwise and is especially useful for icons, images, buttons, cards, and interactive effects.

### Basic Syntax

```css
selector {
    transform: rotate(angle);
}
```

For example:

```css
.box {
    transform: rotate(45deg);
}
```

This rotates the element by `45deg` clockwise.

### Positive Rotation

Positive angle values rotate the element clockwise:

```css
.box {
    transform: rotate(45deg);
}
```

Another example:

```css
.box {
    transform: rotate(90deg);
}
```

This rotates the element one-quarter of a full turn.

### Negative Rotation

Negative angle values rotate the element counterclockwise:

```css
.box {
    transform: rotate(-45deg);
}
```

This rotates the element `45deg` counterclockwise.

### Rotation Units

The `rotate()` function accepts angle units such as:

```text
deg
rad
grad
turn
```

For example:

```css
.box {
    transform: rotate(0.25turn);
}
```

A value of `0.25turn` represents one-quarter of a full rotation.

You can also use:

```css
.box {
    transform: rotate(1turn);
}
```

This represents a complete `360deg` rotation.

### Practical Example

```html
<div class="box">Rotate Me</div>
```

```css
.box {
    width: 150px;
    padding: 20px;
    background: steelblue;
    transform: rotate(15deg);
}
```

The element is visually rotated by `15deg`.

### Hover Effect

`rotate()` can be combined with a transition to create a smooth rotation:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: rotate(10deg);
}
```

When the user hovers over the element, it smoothly rotates `10deg`.

### Rotating an Icon

Rotation is commonly used for icons:

```css
.icon {
    transition: transform 0.3s ease;
}

.icon:hover {
    transform: rotate(180deg);
}
```

The icon smoothly rotates halfway around when hovered.

### Full Rotation

You can create a complete rotation:

```css
.icon:hover {
    transform: rotate(360deg);
}
```

For continuous rotation, CSS animations can be used:

```css
.icon {
    animation: spin 2s linear infinite;
}

@keyframes spin {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}
```

### Rotation and Transform Origin

The element rotates around its transform origin.

By default, the transform origin is generally the center of the element:

```css
.box {
    transform: rotate(45deg);
}
```

You can change the rotation point:

```css
.box {
    transform-origin: top left;
    transform: rotate(45deg);
}
```

Now the element rotates around its top-left corner.

> 💡 **Tip:** Use small rotation values for normal UI interactions. Values such as `5deg`, `10deg`, or `15deg` can provide subtle visual feedback without making the interface difficult to use.

> 💡 **Remember:** Positive angles rotate clockwise, while negative angles rotate counterclockwise.

---

## Rotate X

The `rotateX()` function rotates an element around the **X-axis**.

It is mainly used for **3D transformations** because the rotation creates a change in the element's depth and perspective.

### Basic Syntax

```css
selector {
    transform: rotateX(angle);
}
```

For example:

```css
.box {
    transform: rotateX(45deg);
}
```

This rotates the element `45deg` around the X-axis.

### Positive Rotation

A positive angle rotates the element around the X-axis in one direction:

```css
.box {
    transform: rotateX(45deg);
}
```

Increasing the angle produces a stronger 3D rotation effect.

For example:

```css
.box {
    transform: rotateX(90deg);
}
```

This rotates the element by `90deg` around the X-axis.

### Negative Rotation

Negative values rotate the element in the opposite direction:

```css
.box {
    transform: rotateX(-45deg);
}
```

This rotates the element `45deg` in the opposite direction around the X-axis.

### Understanding the X-Axis

The X-axis runs horizontally through the element:

```text
        X-axis
←──────────────────→
```

When an element is rotated around the X-axis, its top and bottom edges move toward or away from the viewer.

This creates a vertical 3D rotation effect.

### Perspective

To make the 3D effect easier to see, you can use `perspective`:

```css
.container {
    perspective: 800px;
}

.box {
    transform: rotateX(45deg);
}
```

The `perspective` property controls how the depth of the 3D transformation appears to the viewer.

### Practical Example

```html
<div class="container">
    <div class="box">Rotate X</div>
</div>
```

```css
.container {
    perspective: 800px;
}

.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform: rotateX(45deg);
}
```

The element rotates around its horizontal X-axis and produces a 3D effect.

### Hover Effect

`rotateX()` can be combined with a transition:

```css
.container {
    perspective: 800px;
}

.box {
    transition: transform 0.4s ease;
}

.box:hover {
    transform: rotateX(20deg);
}
```

When the user hovers over the element, it smoothly rotates around the X-axis.

### Combining with Other Transforms

`rotateX()` can be combined with other transform functions:

```css
.box {
    transform: translateY(-10px) rotateX(20deg) scale(1.05);
}
```

This moves, rotates, and scales the element.

> 💡 **Tip:** Use `rotateX()` when you want to create a 3D effect where the element appears to tilt forward or backward.

> 💡 **Remember:** `rotateX()` rotates an element around the horizontal X-axis and is commonly used together with `perspective` for realistic 3D effects.

---

## Rotate Y

The `rotateY()` function rotates an element around the **Y-axis**.

It is mainly used for **3D transformations** because the rotation creates a change in the element's depth and perspective.

### Basic Syntax

```css
selector {
    transform: rotateY(angle);
}
```

For example:

```css
.box {
    transform: rotateY(45deg);
}
```

This rotates the element `45deg` around the Y-axis.

### Positive Rotation

Positive angle values rotate the element around the Y-axis in one direction:

```css
.box {
    transform: rotateY(45deg);
}
```

A larger angle produces a stronger 3D rotation effect:

```css
.box {
    transform: rotateY(90deg);
}
```

This rotates the element by `90deg` around the Y-axis.

### Negative Rotation

Negative values rotate the element in the opposite direction:

```css
.box {
    transform: rotateY(-45deg);
}
```

This rotates the element `45deg` in the opposite direction around the Y-axis.

### Understanding the Y-Axis

The Y-axis runs vertically through the element:

```text
        Y-axis
          ↑
          │
          │
          │
          ↓
```

When an element is rotated around the Y-axis, its left and right sides move toward or away from the viewer.

This creates a horizontal 3D rotation effect.

### Perspective

To make the 3D effect easier to see, you can use `perspective`:

```css
.container {
    perspective: 800px;
}

.box {
    transform: rotateY(45deg);
}
```

The `perspective` property controls how the depth of the 3D transformation appears to the viewer.

### Practical Example

```html
<div class="container">
    <div class="box">Rotate Y</div>
</div>
```

```css
.container {
    perspective: 800px;
}

.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform: rotateY(45deg);
}
```

The element rotates around its vertical Y-axis and produces a 3D effect.

### Hover Effect

`rotateY()` can be combined with a transition:

```css
.container {
    perspective: 800px;
}

.box {
    transition: transform 0.4s ease;
}

.box:hover {
    transform: rotateY(20deg);
}
```

When the user hovers over the element, it smoothly rotates around the Y-axis.

### Combining with Other Transforms

`rotateY()` can be combined with other transform functions:

```css
.box {
    transform: translateY(-10px) rotateY(20deg) scale(1.05);
}
```

This moves, rotates, and scales the element.

> 💡 **Tip:** Use `rotateY()` when you want to create a 3D effect where an element appears to turn from side to side.

> 💡 **Remember:** `rotateY()` rotates an element around the vertical Y-axis and is commonly used together with `perspective` for 3D effects.

---

## Rotate Z

The `rotateZ()` function rotates an element around the **Z-axis**.

It is commonly used for **2D rotation** because the Z-axis points toward and away from the viewer.

### Basic Syntax

```css
selector {
    transform: rotateZ(angle);
}
```

For example:

```css
.box {
    transform: rotateZ(45deg);
}
```

This rotates the element by `45deg` around the Z-axis.

### Positive Rotation

Positive angle values rotate the element clockwise:

```css
.box {
    transform: rotateZ(45deg);
}
```

This rotates the element `45deg` clockwise.

Another example:

```css
.box {
    transform: rotateZ(90deg);
}
```

This rotates the element by `90deg`.

### Negative Rotation

Negative values rotate the element counterclockwise:

```css
.box {
    transform: rotateZ(-45deg);
}
```

This rotates the element `45deg` counterclockwise.

### Understanding the Z-Axis

The Z-axis represents depth and points toward or away from the viewer.

```text
             Z-axis
              ↕
              │
        ┌───────────┐
        │   Element │
        └───────────┘
```

When an element rotates around the Z-axis, it appears to rotate within the screen.

### Practical Example

```html
<div class="box">Rotate Z</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform: rotateZ(15deg);
}
```

The element is rotated by `15deg` around the Z-axis.

### Hover Effect

`rotateZ()` can be combined with a transition:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: rotateZ(10deg);
}
```

When the user hovers over the element, it smoothly rotates around the Z-axis.

### Full Rotation

You can rotate an element through a complete turn:

```css
.box:hover {
    transform: rotateZ(360deg);
}
```

This rotates the element by `360deg`.

### `rotate()` vs `rotateZ()`

The `rotate()` function is commonly used for simple 2D rotation:

```css
.box {
    transform: rotate(45deg);
}
```

`rotateZ()` explicitly specifies rotation around the Z-axis:

```css
.box {
    transform: rotateZ(45deg);
}
```

Both can produce the same visual result for a simple 2D rotation.

> 💡 **Tip:** Use `rotate()` for simple 2D rotation. Use `rotateZ()` when you want to explicitly describe the axis of rotation, especially when working with other 3D transform functions.

> 💡 **Remember:** `rotateZ()` rotates an element around the Z-axis, which produces the familiar clockwise or counterclockwise rotation seen on the screen.