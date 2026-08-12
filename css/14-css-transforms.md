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

---

## Skew

The `skew()` function distorts an element by tilting it along the **X-axis, Y-axis, or both axes**.

Unlike `rotate()`, which turns an element, `skew()` changes the angles of the element's sides while keeping its general position.

### Basic Syntax

```css
selector {
    transform: skew(x-angle, y-angle);
}
```

For example:

```css
.box {
    transform: skew(20deg, 10deg);
}
```

Here:

```text
20deg → X-axis skew
10deg → Y-axis skew
```

### Skewing on Both Axes

You can provide two angle values:

```css
.box {
    transform: skew(20deg, 10deg);
}
```

The first value controls the X-axis and the second value controls the Y-axis.

### Skewing on the X-Axis

You can provide only one value:

```css
.box {
    transform: skew(20deg);
}
```

When only one value is provided, the element is skewed along the X-axis.

### Positive Values

Positive values tilt the element in one direction:

```css
.box {
    transform: skew(20deg);
}
```

The element is visually tilted along the X-axis.

### Negative Values

Negative values tilt the element in the opposite direction:

```css
.box {
    transform: skew(-20deg);
}
```

### Practical Example

```html
<div class="box">Skew Me</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform: skew(15deg);
}
```

The element is visually tilted along the X-axis.

### Skewing on the Y-Axis

You can explicitly control the Y-axis:

```css
.box {
    transform: skew(0, 20deg);
}
```

The element is skewed vertically along the Y-axis.

### Hover Effect

`skew()` can be combined with a transition:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: skew(10deg);
}
```

When the user hovers over the element, it smoothly tilts.

### `skew()` vs `rotate()`

`rotate()` turns the entire element:

```css
.box {
    transform: rotate(20deg);
}
```

`skew()` distorts the element:

```css
.box {
    transform: skew(20deg);
}
```

The two transformations produce different visual effects.

> 💡 **Tip:** Use `skew()` when you want to create a slanted or distorted appearance rather than simply rotating an element.

> 💡 **Remember:** `skew()` accepts angle values and can control both the X-axis and Y-axis.

---

## Skew X

The `skewX()` function distorts an element by tilting it along the **X-axis**.

It changes the horizontal angles of the element while keeping its general position in the document flow.

### Basic Syntax

```css
selector {
    transform: skewX(angle);
}
```

For example:

```css
.box {
    transform: skewX(20deg);
}
```

This skews the element by `20deg` along the X-axis.

### Positive Values

Positive values skew the element in one direction:

```css
.box {
    transform: skewX(20deg);
}
```

The element is visually tilted along the X-axis.

### Negative Values

Negative values skew the element in the opposite direction:

```css
.box {
    transform: skewX(-20deg);
}
```

This creates a tilt in the opposite direction.

### Practical Example

```html
<div class="box">Skew X</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform: skewX(15deg);
}
```

The element is visually distorted along the X-axis.

### Hover Effect

`skewX()` can be combined with a transition:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: skewX(10deg);
}
```

When the user hovers over the element, it smoothly tilts along the X-axis.

### Comparing `skew()` and `skewX()`

`skew()` can control both the X-axis and Y-axis:

```css
.box {
    transform: skew(20deg, 10deg);
}
```

`skewX()` specifically controls the X-axis:

```css
.box {
    transform: skewX(20deg);
}
```

Therefore, `skewX()` is useful when you only want to distort the element horizontally.

> 💡 **Tip:** Use `skewX()` when you need a horizontal slant without changing the Y-axis skew.

> 💡 **Remember:** Positive and negative angle values control the direction of the X-axis skew.

---

## Skew Y

The `skewY()` function distorts an element by tilting it along the **Y-axis**.

It changes the vertical angles of the element while keeping its general position in the document flow.

### Basic Syntax

```css
selector {
    transform: skewY(angle);
}
```

For example:

```css
.box {
    transform: skewY(20deg);
}
```

This skews the element by `20deg` along the Y-axis.

### Positive Values

Positive values skew the element in one direction:

```css
.box {
    transform: skewY(20deg);
}
```

The element is visually tilted along the Y-axis.

### Negative Values

Negative values skew the element in the opposite direction:

```css
.box {
    transform: skewY(-20deg);
}
```

This creates a tilt in the opposite direction.

### Practical Example

```html
<div class="box">Skew Y</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform: skewY(15deg);
}
```

The element is visually distorted along the Y-axis.

### Hover Effect

`skewY()` can be combined with a transition:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: skewY(10deg);
}
```

When the user hovers over the element, it smoothly tilts along the Y-axis.

### Comparing `skew()` and `skewY()`

`skew()` can control both the X-axis and Y-axis:

```css
.box {
    transform: skew(20deg, 10deg);
}
```

`skewY()` specifically controls the Y-axis:

```css
.box {
    transform: skewY(20deg);
}
```

Therefore, `skewY()` is useful when you only want to distort the element vertically.

> 💡 **Tip:** Use `skewY()` when you need a vertical slant without changing the X-axis skew.

> 💡 **Remember:** Positive and negative angle values control the direction of the Y-axis skew.

---

## Transform Origin

The `transform-origin` property specifies the point around which a transformed element is rotated, scaled, or skewed.

By default, the transform origin is generally the **center of the element**.

### Basic Syntax

```css
selector {
    transform-origin: x-axis y-axis;
}
```

For example:

```css
.box {
    transform-origin: top left;
    transform: rotate(45deg);
}
```

Here, the element rotates around its **top-left corner** instead of its center.

### Default Transform Origin

If you do not specify `transform-origin`, the transformation generally occurs from the center:

```css
.box {
    transform: rotate(45deg);
}
```

This is equivalent to using:

```css
.box {
    transform-origin: center;
    transform: rotate(45deg);
}
```

### Using Keywords

Common keyword values include:

```text
left
center
right
top
bottom
```

You can combine horizontal and vertical values:

```css
.box {
    transform-origin: top left;
}
```

```css
.box {
    transform-origin: center center;
}
```

```css
.box {
    transform-origin: bottom right;
}
```

### Using Percentage Values

You can specify the transform origin using percentages:

```css
.box {
    transform-origin: 0% 0%;
}
```

This places the origin at the top-left corner.

Another example:

```css
.box {
    transform-origin: 50% 50%;
}
```

This places the origin at the center.

### Using Length Values

You can also use CSS length units:

```css
.box {
    transform-origin: 20px 30px;
}
```

The first value controls the horizontal position, while the second value controls the vertical position.

### Transform Origin with Rotation

The effect is easy to see when rotating an element.

Using the default center:

```css
.box {
    transform: rotate(45deg);
}
```

Using the top-left corner:

```css
.box {
    transform-origin: top left;
    transform: rotate(45deg);
}
```

The element rotates around a different point.

### Transform Origin with Scaling

`transform-origin` also affects scaling:

```css
.box {
    transform-origin: left center;
    transform: scale(1.5);
}
```

The element scales outward from its left-center point.

### Practical Example

```html
<div class="box">Transform Me</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform-origin: top left;
    transition: transform 0.3s ease;
}

.box:hover {
    transform: rotate(10deg);
}
```

When the user hovers over the element, it rotates around its top-left corner.

### Transform Origin and 3D Transforms

`transform-origin` can also be used with 3D transformations:

```css
.box {
    transform-origin: center;
    transform: rotateY(45deg);
}
```

You can also specify a third value for the Z-axis:

```css
.box {
    transform-origin: 50% 50% 20px;
}
```

This allows you to control the origin in three-dimensional space.

> 💡 **Tip:** Change `transform-origin` when you want an element to rotate or scale from a specific point instead of its center.

> 💡 **Remember:** `transform-origin` changes the point around which a transformation occurs; it does not itself transform the element.

---

## Multiple Transforms

CSS allows you to apply multiple transformations to the same element using a single `transform` property.

You can combine functions such as:

- `translate()`
- `scale()`
- `rotate()`
- `skew()`
- `translate3d()`
- `rotateX()`
- `rotateY()`
- `rotateZ()`

### Basic Syntax

```css
selector {
    transform: function1(value) function2(value) function3(value);
}
```

For example:

```css
.box {
    transform: translateX(50px) rotate(20deg) scale(1.2);
}
```

This applies three transformations:

```text
translateX() → Moves the element horizontally
rotate()     → Rotates the element
scale()      → Changes its size
```

### Combining Translate and Rotate

You can move and rotate an element together:

```css
.box {
    transform: translateX(50px) rotate(20deg);
}
```

The element is moved horizontally and rotated.

### Combining Scale and Rotate

You can also resize and rotate an element:

```css
.box {
    transform: scale(1.2) rotate(15deg);
}
```

The element becomes larger and rotates by `15deg`.

### Combining Translate, Rotate, and Scale

Multiple transformations can be combined:

```css
.box {
    transform: translate(50px, 20px) rotate(15deg) scale(1.1);
}
```

Here:

```text
translate() → Moves the element
rotate()    → Rotates the element
scale()     → Enlarges the element
```

### Combining 3D Transforms

3D transformations can also be combined:

```css
.box {
    transform: translate3d(50px, 20px, 30px)
               rotateX(20deg)
               rotateY(15deg);
}
```

This applies movement and rotation in three-dimensional space.

### Order of Transformations

The order of transform functions matters.

For example:

```css
.box {
    transform: translateX(50px) rotate(45deg);
}
```

is not necessarily equivalent to:

```css
.box {
    transform: rotate(45deg) translateX(50px);
}
```

The transformations are applied in the order in which they are written, so changing the order can produce a different final result.

### Practical Example

```html
<div class="box">Transform Me</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transition: transform 0.4s ease;
}

.box:hover {
    transform: translateY(-10px) rotate(5deg) scale(1.05);
}
```

When the user hovers over the element, it:

1. Moves upward.
2. Rotates slightly.
3. Becomes slightly larger.

### Using Multiple Transforms with `transform-origin`

The transform origin applies to transformations that use an origin point:

```css
.box {
    transform-origin: top left;
    transform: rotate(10deg) scale(1.2);
}
```

The element rotates and scales around its top-left origin.

> 💡 **Tip:** Keep transform combinations simple and use the order of functions intentionally because changing their order can change the final visual result.

> 💡 **Remember:** Multiple transform functions are written together inside the same `transform` declaration and are separated by spaces.

---

## 2D Transforms

CSS 2D transforms allow you to visually move, resize, rotate, and skew an element within a two-dimensional plane.

2D transformations work along the **X-axis and Y-axis**.

Common 2D transform functions include:

- `translate()`
- `translateX()`
- `translateY()`
- `scale()`
- `scaleX()`
- `scaleY()`
- `rotate()`
- `skew()`
- `skewX()`
- `skewY()`

### Basic Syntax

```css
selector {
    transform: function(value);
}
```

For example:

```css
.box {
    transform: translate(50px, 20px);
}
```

This moves the element horizontally and vertically.

### Moving an Element

You can use `translate()` to move an element:

```css
.box {
    transform: translate(50px, 30px);
}
```

The element moves:

```text
50px → X-axis
30px → Y-axis
```

### Scaling an Element

You can use `scale()` to change the visual size:

```css
.box {
    transform: scale(1.2);
}
```

The element becomes `1.2` times its original size.

### Rotating an Element

You can use `rotate()` to rotate an element:

```css
.box {
    transform: rotate(30deg);
}
```

The element rotates by `30deg`.

### Skewing an Element

You can use `skew()` to distort an element:

```css
.box {
    transform: skew(20deg, 10deg);
}
```

This skews the element along the X-axis and Y-axis.

### Combining 2D Transforms

Multiple 2D transformations can be combined:

```css
.box {
    transform: translate(50px, 20px)
               rotate(15deg)
               scale(1.1);
}
```

The element is moved, rotated, and scaled.

### Practical Example

```html
<div class="box">2D Transform</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transition: transform 0.4s ease;
}

.box:hover {
    transform: translateY(-10px) rotate(5deg) scale(1.05);
}
```

When the user hovers over the element, it moves upward, rotates slightly, and becomes slightly larger.

### 2D vs 3D Transforms

2D transforms work primarily with the **X-axis and Y-axis**:

```css
.box {
    transform: translate(50px, 20px);
}
```

3D transforms can additionally use the **Z-axis**:

```css
.box {
    transform: translate3d(50px, 20px, 30px);
}
```

The Z-axis introduces depth and is used for three-dimensional effects.

> 💡 **Tip:** Use 2D transforms for common interface effects such as moving, scaling, rotating, and skewing elements on the screen.

> 💡 **Remember:** 2D transforms operate within the X-Y plane, while 3D transforms can also manipulate depth using the Z-axis.

---

## 3D Transforms

CSS 3D transforms allow you to visually transform elements in **three-dimensional space**.

Unlike 2D transforms, which work mainly along the X-axis and Y-axis, 3D transforms also use the **Z-axis** to create depth.

### The Three Axes

3D transformations work with three axes:

```text
              Y-axis
                ↑
                │
                │
                │
                └────────────→ X-axis
               /
              /
             ↓
           Z-axis
```

They represent:

- **X-axis** → Horizontal direction
- **Y-axis** → Vertical direction
- **Z-axis** → Depth

### Common 3D Transform Functions

Some commonly used 3D transform functions include:

- `translate3d()`
- `translateZ()`
- `rotateX()`
- `rotateY()`
- `rotateZ()`

### Basic Syntax

```css
selector {
    transform: function(value);
}
```

For example:

```css
.box {
    transform: rotateY(45deg);
}
```

This rotates the element around the Y-axis.

### Moving in 3D Space

The `translate3d()` function can move an element along all three axes:

```css
.box {
    transform: translate3d(50px, 20px, 30px);
}
```

Here:

```text
50px → X-axis
20px → Y-axis
30px → Z-axis
```

### Rotating Around the X-Axis

```css
.box {
    transform: rotateX(45deg);
}
```

This rotates the element around the horizontal X-axis.

### Rotating Around the Y-Axis

```css
.box {
    transform: rotateY(45deg);
}
```

This rotates the element around the vertical Y-axis.

### Rotating Around the Z-Axis

```css
.box {
    transform: rotateZ(45deg);
}
```

This rotates the element around the Z-axis.

### Perspective

3D transformations are commonly combined with the `perspective` property:

```css
.container {
    perspective: 800px;
}

.box {
    transform: rotateY(45deg);
}
```

The `perspective` property gives the viewer a sense of depth.

### Practical Example

```html
<div class="container">
    <div class="box">3D Transform</div>
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
    transition: transform 0.4s ease;
}

.box:hover {
    transform: rotateY(35deg) translateZ(20px);
}
```

When the user hovers over the element, it rotates around the Y-axis and moves forward along the Z-axis.

### Combining Multiple 3D Transforms

You can combine several 3D transformations:

```css
.box {
    transform: translate3d(30px, 20px, 40px)
               rotateX(20deg)
               rotateY(25deg);
}
```

This applies movement and rotation in three-dimensional space.

> 💡 **Tip:** Use `perspective` with 3D transformations when you want the depth and rotation to appear more realistic.

> 💡 **Remember:** 3D transforms use the X, Y, and Z axes. The Z-axis represents depth, allowing elements to move toward or away from the viewer.

---

## Perspective

The `perspective` property defines the distance between the viewer and the **Z=0 plane** of a 3D transformed element.

It controls how strong the **3D depth effect** appears when using 3D transforms such as `rotateX()`, `rotateY()`, and `translateZ()`.

### Basic Syntax

```css
selector {
    perspective: value;
}
```

For example:

```css
.container {
    perspective: 800px;
}
```

A smaller perspective value generally creates a stronger depth effect, while a larger value creates a more subtle effect.

### Using Perspective with 3D Transforms

`perspective` is commonly used on a parent element:

```css
.container {
    perspective: 800px;
}

.box {
    transform: rotateY(45deg);
}
```

The parent establishes the perspective for its transformed child.

### Perspective Distance

Compare these examples:

```css
.container {
    perspective: 300px;
}
```

```css
.container {
    perspective: 1000px;
}
```

The `300px` perspective creates a stronger sense of depth, while `1000px` produces a more subtle 3D effect.

### Perspective with `rotateX()`

```css
.container {
    perspective: 800px;
}

.box {
    transform: rotateX(45deg);
}
```

The element appears to tilt forward or backward in 3D space.

### Perspective with `rotateY()`

```css
.container {
    perspective: 800px;
}

.box {
    transform: rotateY(45deg);
}
```

The element appears to turn from side to side.

### Perspective with `translateZ()`

```css
.container {
    perspective: 800px;
}

.box {
    transform: translateZ(100px);
}
```

The element moves along the Z-axis and appears closer to the viewer.

### Practical Example

```html
<div class="container">
    <div class="box">Perspective</div>
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
    transition: transform 0.4s ease;
}

.box:hover {
    transform: rotateY(35deg) translateZ(40px);
}
```

When the user hovers over the element, the perspective makes the rotation and depth movement appear three-dimensional.

### `perspective` Property vs `perspective()`

The `perspective` property is generally applied to a parent or containing element:

```css
.container {
    perspective: 800px;
}
```

The `perspective()` function is used directly inside the `transform` property:

```css
.box {
    transform: perspective(800px) rotateY(45deg);
}
```

They can produce similar visual effects, but they establish perspective differently.

### Perspective Origin

You can control the position from which the 3D scene is viewed using `perspective-origin`:

```css
.container {
    perspective: 800px;
    perspective-origin: center;
}
```

Other values can be used:

```css
.container {
    perspective-origin: top left;
}
```

This changes the viewer's perspective position.

> 💡 **Tip:** Use `perspective` when working with 3D transforms to make depth and rotation effects easier to see.

> 💡 **Remember:** Smaller perspective values create a stronger depth effect, while larger values create a more subtle 3D appearance.

---

## Transform Style

The `transform-style` property specifies how an element's child elements are positioned in **3D space**.

It is mainly used when creating 3D effects with nested elements.

### Basic Syntax

```css
selector {
    transform-style: value;
}
```

The property has two commonly used values:

```text
flat
preserve-3d
```

### `flat`

The default value is `flat`.

```css
.parent {
    transform-style: flat;
}
```

With `flat`, the child elements are rendered as if they are on the same plane as their parent.

Their 3D transformations are flattened into the parent's plane.

### `preserve-3d`

The `preserve-3d` value allows child elements to maintain their own 3D position:

```css
.parent {
    transform-style: preserve-3d;
}
```

This is useful when multiple nested elements need to participate in the same 3D scene.

### Practical Example

```html
<div class="container">
    <div class="box">
        <div class="face">3D</div>
    </div>
</div>
```

```css
.container {
    perspective: 800px;
}

.box {
    width: 200px;
    height: 200px;
    transform-style: preserve-3d;
    transition: transform 0.5s ease;
}

.box:hover {
    transform: rotateY(45deg);
}

.face {
    width: 100%;
    height: 100%;
    transform: translateZ(50px);
}
```

Here, `preserve-3d` allows the child `.face` to maintain its 3D position instead of being flattened into the parent's plane.

### `flat` vs `preserve-3d`

| Value | Description |
| --- | --- |
| `flat` | Child elements are flattened into the parent's plane |
| `preserve-3d` | Child elements maintain their 3D positioning |

### Using with `perspective`

`transform-style: preserve-3d` is commonly used together with `perspective`:

```css
.container {
    perspective: 800px;
}

.box {
    transform-style: preserve-3d;
}
```

The parent provides the perspective, while the transformed element allows its children to remain in 3D space.

> 💡 **Tip:** Use `preserve-3d` when building 3D cards, cubes, flip effects, or other interfaces containing nested 3D elements.

> 💡 **Remember:** `transform-style` controls whether an element's children remain in 3D space or are flattened into the element's plane.

---

## Backface Visibility

The `backface-visibility` property specifies whether the **back face of an element should be visible when it is rotated in 3D space**.

It is mainly useful when creating 3D effects such as flip cards, where an element can rotate far enough for its back side to face the viewer.

### Basic Syntax

```css
selector {
    backface-visibility: value;
}
```

The property has two commonly used values:

```text
visible
hidden
```

### `visible`

The default value is `visible`.

```css
.box {
    backface-visibility: visible;
}
```

The back face of the element remains visible when the element is rotated in 3D space.

### `hidden`

The `hidden` value hides the back face of the element:

```css
.box {
    backface-visibility: hidden;
}
```

When the back of the element faces the viewer, it is not displayed.

### Practical Example

```html
<div class="card">
    <div class="front">Front</div>
    <div class="back">Back</div>
</div>
```

```css
.card {
    width: 200px;
    height: 120px;
    position: relative;
    transform-style: preserve-3d;
}

.front,
.back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
}

.back {
    transform: rotateY(180deg);
}

.card:hover {
    transform: rotateY(180deg);
}
```

Here, `backface-visibility: hidden` prevents the back of each card face from being visible when it is facing away from the viewer.

### Combining with `transform-style`

`backface-visibility` is commonly used together with:

```css
transform-style: preserve-3d;
```

For example:

```css
.card {
    transform-style: preserve-3d;
}

.card-face {
    backface-visibility: hidden;
}
```

This combination is useful for creating 3D interfaces.

### Combining with `rotateY()`

A common pattern is:

```css
.card {
    transform-style: preserve-3d;
    transition: transform 0.6s ease;
}

.card:hover {
    transform: rotateY(180deg);
}

.card-face {
    backface-visibility: hidden;
}
```

As the card rotates, the hidden back faces are not shown when they face away from the viewer.

### `visible` vs `hidden`

| Value | Description |
| --- | --- |
| `visible` | The back face remains visible |
| `hidden` | The back face is hidden |

### When to Use It

`backface-visibility: hidden` is particularly useful for:

- 3D flip cards
- 3D navigation effects
- Rotating panels
- 3D UI components
- Interactive 3D animations

> 💡 **Tip:** Use `backface-visibility: hidden` when you do not want the reverse side of a 3D element to appear during rotation.

> 💡 **Remember:** `backface-visibility` controls whether the back face is visible; it does not create the 3D rotation itself.

---

## Practical Examples

CSS transforms are commonly used to create interactive and visually engaging effects without changing the normal layout flow of an element.

### Example 1: Moving a Card

```html
<div class="card">Move Me</div>
```

```css
.card {
    width: 200px;
    padding: 30px;
    background: steelblue;
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-10px);
}
```

When the user hovers over the card, it moves upward by `10px`.

### Example 2: Scaling a Button

```html
<button class="button">Hover Me</button>
```

```css
.button {
    padding: 12px 24px;
    transition: transform 0.2s ease;
}

.button:hover {
    transform: scale(1.05);
}
```

The button becomes slightly larger when hovered.

### Example 3: Rotating an Icon

```html
<div class="icon">↻</div>
```

```css
.icon {
    display: inline-block;
    transition: transform 0.4s ease;
}

.icon:hover {
    transform: rotate(180deg);
}
```

The icon smoothly rotates when the user hovers over it.

### Example 4: Skewed Element

```html
<div class="banner">Special Offer</div>
```

```css
.banner {
    padding: 20px;
    background: steelblue;
    transform: skewX(-10deg);
}
```

The element gets a slanted appearance using `skewX()`.

### Example 5: Combining Multiple Transforms

```html
<div class="card">Hover Me</div>
```

```css
.card {
    width: 200px;
    padding: 30px;
    background: steelblue;
    transition: transform 0.4s ease;
}

.card:hover {
    transform: translateY(-10px) rotate(3deg) scale(1.05);
}
```

Multiple transformations can be combined to create a single interaction:

```text
translateY() → Moves the card upward
rotate()     → Slightly rotates the card
scale()      → Makes the card slightly larger
```

### Example 6: 3D Card Effect

```html
<div class="container">
    <div class="card">3D Card</div>
</div>
```

```css
.container {
    perspective: 800px;
}

.card {
    width: 200px;
    padding: 40px;
    background: steelblue;
    transition: transform 0.5s ease;
}

.card:hover {
    transform: rotateY(20deg);
}
```

The `perspective` property provides a sense of depth while `rotateY()` creates the 3D rotation.

### Example 7: Flip Card

```html
<div class="card">
    <div class="card-front">Front</div>
    <div class="card-back">Back</div>
</div>
```

```css
.card {
    width: 200px;
    height: 120px;
    position: relative;
    perspective: 800px;
}

.card-front,
.card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    transition: transform 0.6s ease;
}

.card-back {
    transform: rotateY(180deg);
}

.card:hover .card-front {
    transform: rotateY(180deg);
}

.card:hover .card-back {
    transform: rotateY(0deg);
}
```

This creates a basic card-flipping effect using:

- `perspective`
- `rotateY()`
- `backface-visibility`
- `transition`

### Example 8: Transform Origin

```html
<div class="box">Rotate</div>
```

```css
.box {
    width: 150px;
    padding: 30px;
    background: steelblue;
    transform-origin: top left;
    transition: transform 0.4s ease;
}

.box:hover {
    transform: rotate(15deg);
}
```

The element rotates around its top-left corner instead of its center.

### Example 9: Image Zoom Effect

```html
<div class="image-container">
    <img src="image.jpg" alt="Example">
</div>
```

```css
.image-container {
    overflow: hidden;
}

.image-container img {
    transition: transform 0.4s ease;
}

.image-container img:hover {
    transform: scale(1.1);
}
```

The image smoothly zooms in when hovered.

### Example 10: Combining Transform with Transition

Transforms become especially useful when combined with `transition`:

```css
.card {
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-8px) scale(1.03);
}
```

The transition makes the transformation smooth instead of changing it instantly.

> 💡 **Tip:** CSS transforms are especially useful for hover effects, cards, buttons, images, icons, and 3D interfaces.

> 💡 **Remember:** Transforms can be combined with `transition` or `animation` to create smooth and interactive effects.

---

## Key Takeaways

CSS transforms allow you to visually modify elements without changing their normal position in the document layout.

The main transform categories covered in this chapter are:

### 1. Translate

Moves an element along the X, Y, or Z axis.

```css
.box {
    transform: translate(50px, 20px);
}
```

For 3D movement:

```css
.box {
    transform: translate3d(50px, 20px, 30px);
}
```

### 2. Scale

Changes the visual size of an element.

```css
.box {
    transform: scale(1.2);
}
```

You can also scale individual axes:

```css
.box {
    transform: scaleX(1.2);
}
```

```css
.box {
    transform: scaleY(1.2);
}
```

### 3. Rotate

Rotates an element around an axis.

```css
.box {
    transform: rotate(45deg);
}
```

For 3D rotations:

```css
.box {
    transform: rotateX(30deg);
}
```

```css
.box {
    transform: rotateY(30deg);
}
```

```css
.box {
    transform: rotateZ(30deg);
}
```

### 4. Skew

Tilts or distorts an element.

```css
.box {
    transform: skew(20deg, 10deg);
}
```

You can control individual axes:

```css
.box {
    transform: skewX(20deg);
}
```

```css
.box {
    transform: skewY(20deg);
}
```

### 5. Transform Origin

Controls the point around which a transformation occurs.

```css
.box {
    transform-origin: top left;
    transform: rotate(45deg);
}
```

### 6. Multiple Transforms

Multiple transform functions can be combined in one declaration:

```css
.box {
    transform: translateY(-10px) rotate(5deg) scale(1.05);
}
```

The order of the transformations matters.

### 7. 2D Transforms

2D transforms operate within the X-Y plane.

Common functions include:

```text
translate()
scale()
rotate()
skew()
```

### 8. 3D Transforms

3D transforms introduce the Z-axis and depth.

```css
.box {
    transform: translate3d(30px, 20px, 40px);
}
```

### 9. Perspective

The `perspective` property controls how 3D depth appears to the viewer.

```css
.container {
    perspective: 800px;
}
```

### 10. Transform Style

`transform-style` controls whether child elements remain in 3D space.

```css
.box {
    transform-style: preserve-3d;
}
```

### 11. Backface Visibility

Controls whether the back side of a 3D-transformed element is visible.

```css
.box {
    backface-visibility: hidden;
}
```

### Important Points

- `transform` changes the visual appearance of an element.
- Transform functions can be combined.
- The order of multiple transforms can affect the final result.
- `transform-origin` controls the transformation's reference point.
- 2D transforms use the X and Y axes.
- 3D transforms additionally use the Z-axis.
- `perspective` helps create a realistic 3D depth effect.
- `transform-style: preserve-3d` allows child elements to maintain 3D positioning.
- `backface-visibility: hidden` is useful for 3D flip effects.
- Transforms are commonly combined with `transition` and `animation` for smooth interactions.

> 💡 **Remember:** CSS transforms are primarily used to visually move, resize, rotate, skew, and create 3D effects on elements without changing the normal document layout.

---

## References

- [MDN Web Docs — CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
- [MDN Web Docs — CSS `translate()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate)
- [MDN Web Docs — CSS `scale()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale)
- [MDN Web Docs — CSS `rotate()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate)
- [MDN Web Docs — CSS `skew()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skew)
- [MDN Web Docs — CSS `transform-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)
- [MDN Web Docs — CSS `perspective`](https://developer.mozilla.org/en-US/docs/Web/CSS/perspective)
- [MDN Web Docs — CSS `transform-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style)
- [MDN Web Docs — CSS `backface-visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility)
- [MDN Web Docs — CSS `translate3d()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate3d)
- [MDN Web Docs — CSS `rotateX()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateX)
- [MDN Web Docs — CSS `rotateY()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateY)
- [MDN Web Docs — CSS `rotateZ()`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateZ)

---

## Quick Revision

### CSS Transform

The `transform` property is used to visually modify an element by moving, scaling, rotating, or skewing it.

```css
.box {
    transform: rotate(20deg);
}
```

### Translate

Moves an element along the X and Y axes.

```css
.box {
    transform: translate(50px, 20px);
}
```

### Translate X

Moves an element horizontally.

```css
.box {
    transform: translateX(50px);
}
```

### Translate Y

Moves an element vertically.

```css
.box {
    transform: translateY(20px);
}
```

### Translate 3D

Moves an element along the X, Y, and Z axes.

```css
.box {
    transform: translate3d(50px, 20px, 30px);
}
```

### Scale

Changes the visual size of an element.

```css
.box {
    transform: scale(1.2);
}
```

### Scale X

Changes the horizontal scale.

```css
.box {
    transform: scaleX(1.2);
}
```

### Scale Y

Changes the vertical scale.

```css
.box {
    transform: scaleY(1.2);
}
```

### Rotate

Rotates an element around the Z-axis.

```css
.box {
    transform: rotate(45deg);
}
```

### Rotate X

Rotates an element around the X-axis.

```css
.box {
    transform: rotateX(45deg);
}
```

### Rotate Y

Rotates an element around the Y-axis.

```css
.box {
    transform: rotateY(45deg);
}
```

### Rotate Z

Rotates an element around the Z-axis.

```css
.box {
    transform: rotateZ(45deg);
}
```

### Skew

Skews an element along the X and Y axes.

```css
.box {
    transform: skew(20deg, 10deg);
}
```

### Skew X

Skews an element along the X-axis.

```css
.box {
    transform: skewX(20deg);
}
```

### Skew Y

Skews an element along the Y-axis.

```css
.box {
    transform: skewY(20deg);
}
```

### Transform Origin

Controls the point around which a transformation occurs.

```css
.box {
    transform-origin: top left;
    transform: rotate(45deg);
}
```

### Multiple Transforms

Multiple transformations can be combined in one `transform` declaration.

```css
.box {
    transform: translateY(-10px) rotate(5deg) scale(1.05);
}
```

The order of the transformations matters.

### 2D Transforms

2D transforms work within the X-Y plane.

```css
.box {
    transform: translate(50px, 20px) rotate(15deg);
}
```

### 3D Transforms

3D transforms use the X, Y, and Z axes.

```css
.box {
    transform: translate3d(30px, 20px, 40px);
}
```

### Perspective

Creates a sense of depth for 3D transformations.

```css
.container {
    perspective: 800px;
}
```

### Transform Style

Controls whether child elements remain in 3D space.

```css
.box {
    transform-style: preserve-3d;
}
```

### Backface Visibility

Controls whether the back face of a 3D-transformed element is visible.

```css
.box {
    backface-visibility: hidden;
}
```

### Quick Reference Table

| Property / Function | Purpose |
| --- | --- |
| `transform` | Applies transformations |
| `translate()` | Moves an element |
| `translateX()` | Moves horizontally |
| `translateY()` | Moves vertically |
| `translate3d()` | Moves in 3D space |
| `scale()` | Changes size |
| `scaleX()` | Changes horizontal scale |
| `scaleY()` | Changes vertical scale |
| `rotate()` | Rotates an element |
| `rotateX()` | Rotates around X-axis |
| `rotateY()` | Rotates around Y-axis |
| `rotateZ()` | Rotates around Z-axis |
| `skew()` | Skews on X and Y axes |
| `skewX()` | Skews on X-axis |
| `skewY()` | Skews on Y-axis |
| `transform-origin` | Sets transformation origin |
| `perspective` | Controls 3D depth |
| `transform-style` | Controls child 3D rendering |
| `backface-visibility` | Controls visibility of the back face |

> 💡 **Remember:** `transform` is used for visual transformations, while properties such as `transform-origin`, `perspective`, `transform-style`, and `backface-visibility` control how those transformations behave.

---

## Best Practices

Following good practices when using CSS transforms makes styles easier to understand, maintain, and reuse.

### 1. Use Transforms for Visual Changes

Use `transform` when you need to visually move, rotate, scale, or skew an element.

```css
.card:hover {
    transform: translateY(-8px);
}
```

Avoid using transforms when the actual document layout needs to change.

### 2. Use `transition` for Smooth Effects

Combine transforms with `transition` when creating interactive effects:

```css
.card {
    transition: transform 0.3s ease;
}

.card:hover {
    transform: scale(1.05);
}
```

This creates a smoother visual effect.

### 3. Keep Transform Values Reasonable

Avoid unnecessarily large transformations:

```css
/* Better */
.box {
    transform: scale(1.05);
}
```

Instead of:

```css
.box {
    transform: scale(3);
}
```

Small transformations are often more suitable for interface interactions.

### 4. Use the Appropriate Transform Function

Choose the transform function that matches the required effect:

```css
transform: translateX(20px);
```

for horizontal movement,

```css
transform: rotate(10deg);
```

for rotation, and

```css
transform: scale(1.1);
```

for scaling.

Using the appropriate function makes the CSS easier to understand.

### 5. Be Careful with Multiple Transforms

When combining transforms, remember that their order matters:

```css
.box {
    transform: translateX(50px) rotate(20deg);
}
```

Keep the transformation order intentional and easy to understand.

### 6. Use `transform-origin` When Necessary

If an element needs to rotate or scale from a specific point, explicitly define the origin:

```css
.box {
    transform-origin: top left;
    transform: rotate(10deg);
}
```

This makes the intended transformation behavior clearer.

### 7. Use Perspective for 3D Effects

When creating 3D effects, use `perspective` to establish depth:

```css
.container {
    perspective: 800px;
}
```

Then apply a 3D transformation to the child:

```css
.box {
    transform: rotateY(30deg);
}
```

### 8. Use `preserve-3d` for Nested 3D Elements

When child elements need to remain in 3D space:

```css
.card {
    transform-style: preserve-3d;
}
```

This is especially useful for 3D card and flip effects.

### 9. Use `backface-visibility` for Flip Effects

For elements that rotate to reveal another side:

```css
.card-face {
    backface-visibility: hidden;
}
```

This prevents the reverse side from being displayed when it faces away from the viewer.

### 10. Avoid Unnecessary Transformations

Do not add transforms simply because they are available.

Use them when they provide a meaningful visual or interactive effect.

### 11. Keep Transform Code Readable

For simple transformations, keep the declaration concise:

```css
.card:hover {
    transform: translateY(-8px) scale(1.02);
}
```

For more complex effects, use clear formatting:

```css
.card:hover {
    transform:
        translateY(-10px)
        rotate(3deg)
        scale(1.05);
}
```

### 12. Consider Accessibility

Avoid creating excessive motion that can make interfaces uncomfortable for some users.

For animations and transitions involving transforms, consider the user's reduced-motion preference:

```css
@media (prefers-reduced-motion: reduce) {
    * {
        transition: none;
        animation: none;
    }
}
```

> 💡 **Tip:** Use transforms to enhance an interface rather than making the interface dependent on complex visual effects.

> 💡 **Remember:** Good transform code should be purposeful, readable, smooth, and appropriate for the interaction being created.

---

## Common Mistakes

Avoiding common mistakes when using CSS transforms helps keep your styles predictable, maintainable, and easier to debug.

### 1. Forgetting the `transform` Property

Transform functions must be used through the `transform` property:

```css
/* Correct */
.box {
    transform: rotate(20deg);
}
```

Writing the function without `transform` is invalid:

```css
/* Incorrect */
.box {
    rotate(20deg);
}
```

### 2. Overwriting the `transform` Property

If you declare `transform` more than once, the later declaration replaces the earlier one:

```css
/* Incorrect */
.box {
    transform: translateX(50px);
    transform: rotate(20deg);
}
```

Only the rotation is applied.

Combine the transformations instead:

```css
/* Correct */
.box {
    transform: translateX(50px) rotate(20deg);
}
```

### 3. Ignoring Transform Order

The order of multiple transformations can affect the final result:

```css
.box {
    transform: translateX(50px) rotate(20deg);
}
```

is not necessarily visually equivalent to:

```css
.box {
    transform: rotate(20deg) translateX(50px);
}
```

Always consider the order in which transformations are written.

### 4. Using the Wrong Axis

Using the wrong transform function can produce an unexpected result.

For horizontal movement:

```css
.box {
    transform: translateX(50px);
}
```

For vertical movement:

```css
.box {
    transform: translateY(50px);
}
```

For depth:

```css
.box {
    transform: translateZ(50px);
}
```

Choose the axis according to the desired effect.

### 5. Forgetting the Unit for Angles

Rotation and skew functions normally require an angle unit:

```css
/* Correct */
.box {
    transform: rotate(45deg);
}
```

Avoid leaving out the unit:

```css
/* Incorrect */
.box {
    transform: rotate(45);
}
```

### 6. Using Excessive Scaling

Very large scale values can make an interface look unnatural:

```css
/* Avoid excessive scaling */
.box:hover {
    transform: scale(3);
}
```

A smaller value is usually more appropriate for interface interactions:

```css
.box:hover {
    transform: scale(1.05);
}
```

### 7. Forgetting `transform-origin`

If an element needs to rotate or scale from a specific point, relying on the default origin may produce an unexpected result.

```css
.box {
    transform-origin: top left;
    transform: rotate(15deg);
}
```

### 8. Expecting Transforms to Change Layout

Transforms visually modify an element but do not generally cause surrounding elements to reposition as they would with normal layout properties.

For example:

```css
.box {
    transform: translateX(100px);
}
```

The element moves visually, but its original layout space remains in the document.

### 9. Using 3D Transforms Without Perspective

A 3D transform may not produce the expected depth effect without an appropriate perspective setup:

```css
.container {
    perspective: 800px;
}

.box {
    transform: rotateY(30deg);
}
```

Use perspective when a realistic 3D depth effect is needed.

### 10. Forgetting `transform-style`

When working with nested 3D elements, forgetting `preserve-3d` can cause child elements to be flattened:

```css
.parent {
    transform-style: preserve-3d;
}
```

Use it when child elements need to maintain their 3D positioning.

### 11. Forgetting `backface-visibility`

In 3D flip effects, the back side of an element may become visible when it should not be.

```css
.card-face {
    backface-visibility: hidden;
}
```

This is commonly used for card-flipping interfaces.

### 12. Adding Too Many Transformations

Complex transform combinations can make CSS difficult to understand:

```css
.box {
    transform:
        translateX(50px)
        translateY(20px)
        rotate(15deg)
        skewX(10deg)
        scale(1.2);
}
```

Use only the transformations that are necessary for the desired effect.

### 13. Forgetting Transitions for Interactive Effects

A transform applied on hover changes immediately if no transition is defined:

```css
.box:hover {
    transform: scale(1.05);
}
```

For a smoother effect:

```css
.box {
    transition: transform 0.3s ease;
}

.box:hover {
    transform: scale(1.05);
}
```

### 14. Creating Excessive Motion

Too much movement, rotation, or scaling can make an interface distracting or uncomfortable.

Keep interactive transformations subtle and consider reduced-motion preferences:

```css
@media (prefers-reduced-motion: reduce) {
    * {
        transition: none;
        animation: none;
    }
}
```

> 💡 **Tip:** When a transform does not behave as expected, first check the transform function, axis, order, origin, and whether the effect requires 3D perspective.

> 💡 **Remember:** Most transform problems come from incorrect syntax, transform order, unexpected origins, excessive values, or missing 3D-related properties.